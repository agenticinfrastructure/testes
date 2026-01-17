# Guia de Testes - Webhooks do Stripe

**Data**: 12 de Janeiro de 2026  
**Versão**: 1.0  
**Status**: Pronto para Testes

---

## 📋 Visão Geral

Este guia descreve como testar o processamento de webhooks do Stripe para validar:
1. Criação de assinatura com Payment Intent
2. Processamento de pagamentos bem-sucedidos
3. Atribuição de créditos aos usuários
4. Registro de transações no banco de dados

---

## 🔧 Pré-requisitos

### Ferramentas Necessárias
- Stripe CLI (v1.14+)
- cURL ou Postman
- Acesso ao banco de dados PostgreSQL
- Acesso ao cluster Kubernetes

### Configurações
```bash
# 1. Instalar Stripe CLI
brew install stripe/stripe-cli/stripe  # macOS
# ou
choco install stripe  # Windows
# ou
curl https://files.stripe.com/stripe-cli/install.sh -o install.sh && sh install.sh  # Linux

# 2. Autenticar com Stripe
stripe login
# Será aberto um navegador para autenticar

# 3. Verificar conexão
stripe status
```

---

## 🧪 Teste 1: Criar Assinatura com Payment Intent

### Objetivo
Validar que a rota `/billing/create-subscription` cria uma assinatura e retorna um `clientSecret`.

### Pré-requisitos
- Usuário criado no banco de dados
- JWT token válido

### Passos

#### 1. Obter Token JWT
```bash
# Criar usuário de teste
curl -X POST https://api.nexias.ai/api/auth/signup \
  -H "Content-Type: application/json" \
  -d '{
    "email": "test-webhook-'$(date +%s)'@nexias.ai",
    "password": "TestPassword123!",
    "name": "Test User"
  }'

# Resposta:
# {
#   "success": true,
#   "data": {
#     "user": { "id": "user_123", "email": "test@nexias.ai", "name": "Test User" },
#     "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9..."
#   }
# }

# Guardar o token em uma variável
export TOKEN="eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9..."
```

#### 2. Criar Assinatura
```bash
curl -X POST https://api.nexias.ai/api/billing/create-subscription \
  -H "Authorization: Bearer $TOKEN" \
  -H "Content-Type: application/json" \
  -d '{
    "planId": "growth",
    "interval": "month"
  }'

# Resposta esperada:
# {
#   "subscriptionId": "sub_1234567890",
#   "clientSecret": "pi_1234567890_secret_abcdef",
#   "customerId": "cus_1234567890"
# }
```

#### 3. Validar Resposta
```bash
# Verificar se subscriptionId foi criado no Stripe
stripe subscriptions list --customer cus_1234567890

# Verificar se clientSecret é válido
stripe payment_intents retrieve pi_1234567890
```

### Resultado Esperado
- ✅ Status HTTP 200
- ✅ `subscriptionId` começa com `sub_`
- ✅ `clientSecret` contém `_secret_`
- ✅ `customerId` começa com `cus_`

---

## 🧪 Teste 2: Simular Webhook com Stripe CLI

### Objetivo
Simular um evento `payment_intent.succeeded` e validar que os créditos foram atribuídos.

### Passos

#### 1. Iniciar Listener de Webhook
```bash
# Em um terminal, iniciar o listener
stripe listen --forward-to http://localhost:3001/webhooks/stripe

# Saída:
# > Ready! Your webhook signing secret is whsec_test_secret_abc123...
# > Forwarding events to http://localhost:3001/webhooks/stripe

# Guardar o signing secret
export WEBHOOK_SECRET="whsec_test_secret_abc123..."
```

#### 2. Simular Evento de Pagamento Bem-sucedido
```bash
# Em outro terminal, simular o evento
stripe trigger payment_intent.succeeded

# Saída:
# > Event created: evt_1234567890
# > Forwarded to http://localhost:3001/webhooks/stripe
```

#### 3. Verificar Logs do Backend
```bash
# Verificar logs do Kubernetes
kubectl logs -f deployment/backend-api -n ai-platform-production | grep "payment_intent"

# Saída esperada:
# [INFO] Received Stripe event: payment_intent.succeeded
# [INFO] Payment intent succeeded: pi_1234567890
# [INFO] Awarded 700 credits to user user_123. New balance: 700
```

#### 4. Validar Créditos no Banco de Dados
```bash
# Conectar ao banco de dados
psql postgresql://user:password@cloud-sql-proxy:5432/ai-platform

# Verificar saldo de créditos
SELECT * FROM "CreditBalance" WHERE "userId" = 'user_123';

# Resultado esperado:
# userId  | balance | createdAt | updatedAt
# --------|---------|-----------|----------
# user_123| 700     | 2026-01-12| 2026-01-12

# Verificar histórico de transações
SELECT * FROM "CreditTransaction" WHERE "userId" = 'user_123';

# Resultado esperado:
# id | userId  | amount | type     | description        | stripeId | createdAt
# ---|---------|--------|----------|-------------------|----------|----------
# 1  | user_123| 700    | PURCHASE | Compra do plano... | pi_1234  | 2026-01-12
```

### Resultado Esperado
- ✅ Webhook foi recebido e processado
- ✅ Créditos foram atribuídos (700 para Growth)
- ✅ Transação foi registrada no banco
- ✅ Logs mostram sucesso

---

## 🧪 Teste 3: Fluxo Completo com Cartão de Teste

### Objetivo
Testar o fluxo completo: criar assinatura → pagar com cartão → webhook → créditos.

### Pré-requisitos
- Página de checkout funcionando
- Stripe Elements carregando corretamente

### Passos

#### 1. Acessar Página de Checkout
```bash
# Abrir navegador
https://nexias.ai/pricing

# Clicar "Escolher Growth"
# Fazer login com Google
# Será redirecionado para /app/checkout
```

#### 2. Preencher Dados de Pagamento
```
Cartão: 4242 4242 4242 4242
Expiração: 12/25
CVC: 123
Nome: Test User
```

#### 3. Submeter Pagamento
- Clicar "Pagar"
- Aguardar processamento

#### 4. Validar Sucesso
```bash
# Verificar se foi redirecionado para /app?subscription=success
# Verificar se dashboard mostra "700 créditos"

# Verificar no Stripe Dashboard
# Stripe → Customers → Procurar por email
# Verificar se subscription está "active"
# Verificar se payment foi bem-sucedido
```

#### 5. Validar Webhook
```bash
# Verificar se webhook foi recebido
stripe events list | grep payment_intent.succeeded

# Verificar logs
kubectl logs -f deployment/backend-api -n ai-platform-production | grep "Awarded"
```

### Resultado Esperado
- ✅ Redirecionamento para sucesso
- ✅ Créditos aparecem no dashboard
- ✅ Subscription ativa no Stripe
- ✅ Webhook processado
- ✅ Créditos no banco de dados

---

## 🧪 Teste 4: Falha de Pagamento

### Objetivo
Validar que falhas de pagamento são tratadas corretamente.

### Cartões de Teste para Falha
```
Cartão: 4000 0000 0000 0002 (Recusado)
Cartão: 4000 0000 0000 0069 (Expirado)
Cartão: 4000 0000 0000 0127 (CVC inválido)
```

### Passos

#### 1. Tentar Pagar com Cartão Recusado
```bash
# Acessar /app/checkout
# Preencher com cartão 4000 0000 0000 0002
# Clicar "Pagar"
```

#### 2. Validar Erro
```bash
# Deve exibir erro: "Seu cartão foi recusado"
# Usuário deve poder tentar novamente
```

#### 3. Validar Webhook
```bash
# Verificar se webhook foi recebido
stripe events list | grep invoice.payment_failed

# Verificar logs
kubectl logs -f deployment/backend-api -n ai-platform-production | grep "payment_failed"
```

#### 4. Validar Banco de Dados
```bash
# Verificar se créditos NÃO foram atribuídos
SELECT * FROM "CreditBalance" WHERE "userId" = 'user_123';

# Resultado esperado: Sem alteração (ou saldo anterior)
```

### Resultado Esperado
- ✅ Erro exibido no frontend
- ✅ Webhook `invoice.payment_failed` processado
- ✅ Créditos NÃO foram atribuídos
- ✅ Usuário pode tentar novamente

---

## 🧪 Teste 5: Cupom de Desconto

### Objetivo
Validar que cupons são aplicados corretamente.

### Pré-requisitos
- Cupom criado no Stripe (ex: TEST95)

### Passos

#### 1. Criar Cupom no Stripe
```bash
# Criar cupom de 10% de desconto
stripe coupons create \
  --percent_off 10 \
  --duration repeating \
  --duration_in_months 1 \
  --id TEST95

# Resposta:
# {
#   "id": "TEST95",
#   "percent_off": 10,
#   "duration": "repeating",
#   "duration_in_months": 1
# }
```

#### 2. Criar Assinatura com Cupom
```bash
curl -X POST https://api.nexias.ai/api/billing/create-subscription \
  -H "Authorization: Bearer $TOKEN" \
  -H "Content-Type: application/json" \
  -d '{
    "planId": "growth",
    "interval": "month",
    "coupon": "TEST95"
  }'

# Resposta esperada:
# {
#   "subscriptionId": "sub_1234567890",
#   "clientSecret": "pi_1234567890_secret_abcdef",
#   "customerId": "cus_1234567890"
# }
```

#### 3. Validar Cupom no Stripe
```bash
# Verificar se cupom foi aplicado
stripe subscriptions retrieve sub_1234567890 | grep -i discount

# Resultado esperado:
# "discount": {
#   "coupon": {
#     "id": "TEST95",
#     "percent_off": 10
#   }
# }
```

#### 4. Validar Preço com Desconto
```bash
# Preço original: R$ 97,00
# Desconto 10%: R$ 9,70
# Preço final: R$ 87,30

stripe invoices list --customer cus_1234567890 | grep total
```

### Resultado Esperado
- ✅ Cupom aplicado com sucesso
- ✅ Preço reduzido corretamente
- ✅ Créditos atribuídos normalmente (700)

---

## 📊 Payload de Webhook Exemplo

### payment_intent.succeeded

```json
{
  "id": "evt_1234567890",
  "object": "event",
  "api_version": "2023-10-16",
  "created": 1673520000,
  "data": {
    "object": {
      "id": "pi_1234567890",
      "object": "payment_intent",
      "amount": 9700,
      "amount_capturable": 0,
      "amount_received": 9700,
      "charges": {
        "object": "list",
        "data": [
          {
            "id": "ch_1234567890",
            "object": "charge",
            "amount": 9700,
            "currency": "brl",
            "status": "succeeded"
          }
        ]
      },
      "client_secret": "pi_1234567890_secret_abcdef",
      "confirmation_method": "automatic",
      "created": 1673520000,
      "currency": "brl",
      "customer": "cus_1234567890",
      "description": null,
      "invoice": "in_1234567890",
      "last_payment_error": null,
      "livemode": true,
      "next_action": null,
      "on_behalf_of": null,
      "payment_method": "pm_1234567890",
      "payment_method_types": ["card"],
      "receipt_email": null,
      "setup_future_usage": null,
      "statement_descriptor": null,
      "status": "succeeded",
      "transfer_data": null,
      "transfer_group": null
    }
  },
  "livemode": true,
  "pending_webhooks": 1,
  "request": {
    "id": null,
    "idempotency_key": null
  },
  "type": "payment_intent.succeeded"
}
```

### invoice.payment_succeeded

```json
{
  "id": "evt_1234567890",
  "object": "event",
  "api_version": "2023-10-16",
  "created": 1673520000,
  "data": {
    "object": {
      "id": "in_1234567890",
      "object": "invoice",
      "account_country": "BR",
      "account_name": "Nexias.ai",
      "account_tax_ids": null,
      "amount_due": 9700,
      "amount_paid": 9700,
      "amount_remaining": 0,
      "application": null,
      "application_fee": null,
      "attempt_count": 1,
      "attempted": true,
      "auto_advance": true,
      "automatic_tax": {
        "enabled": false,
        "status": null
      },
      "billing_reason": "subscription_cycle",
      "charge": "ch_1234567890",
      "collection_method": "charge_automatically",
      "created": 1673520000,
      "currency": "brl",
      "custom_fields": null,
      "customer": "cus_1234567890",
      "customer_address": null,
      "customer_email": "user@example.com",
      "customer_name": "Test User",
      "customer_phone": null,
      "customer_tax_ids": [],
      "default_payment_method": null,
      "default_source": null,
      "default_tax_rates": [],
      "description": null,
      "discounts": [],
      "due_date": null,
      "ending_balance": 0,
      "footer": null,
      "from_invoice": null,
      "hosted_invoice_url": "https://invoice.stripe.com/i/acct_1234567890/test_YWNjdF8xMjM0NTY3ODkw0200hR8Z0Z8Z",
      "id": "in_1234567890",
      "invoice_pdf": "https://invoice.stripe.com/pdf/v3/acct_1234567890/test_YWNjdF8xMjM0NTY3ODkw0200hR8Z0Z8Z/invoice.pdf",
      "last_finalization_error": null,
      "latest_revision": null,
      "lines": {
        "object": "list",
        "data": [
          {
            "id": "il_1234567890",
            "object": "line_item",
            "amount": 9700,
            "amount_excluding_tax": 9700,
            "billing_details": null,
            "currency": "brl",
            "description": "1 × Growth (at R$97.00 / month)",
            "discount_amounts": [],
            "discountable": true,
            "discounts": [],
            "invoice_item": "ii_1234567890",
            "livemode": true,
            "metadata": {},
            "period": {
              "end": 1676198400,
              "start": 1673520000
            },
            "plan": {
              "id": "price_1SjWkn1pyIdUlbE1I3QICdwd",
              "object": "price",
              "active": true,
              "billing_scheme": "per_unit",
              "created": 1673520000,
              "currency": "brl",
              "custom_unit_amount": null,
              "livemode": true,
              "lookup_key": null,
              "metadata": {},
              "nickname": null,
              "product": "prod_TguZX4qVJHuT1O",
              "recurring": {
                "aggregate_usage": null,
                "interval": "month",
                "interval_count": 1,
                "trial_period_days": null,
                "usage_type": "licensed"
              },
              "tax_behavior": "unspecified",
              "tiers_mode": null,
              "transform_quantity": null,
              "type": "recurring",
              "unit_amount": 9700,
              "unit_amount_decimal": "9700"
            },
            "price": {
              "id": "price_1SjWkn1pyIdUlbE1I3QICdwd",
              "object": "price",
              "active": true,
              "billing_scheme": "per_unit",
              "created": 1673520000,
              "currency": "brl",
              "custom_unit_amount": null,
              "livemode": true,
              "lookup_key": null,
              "metadata": {},
              "nickname": null,
              "product": "prod_TguZX4qVJHuT1O",
              "recurring": {
                "aggregate_usage": null,
                "interval": "month",
                "interval_count": 1,
                "trial_period_days": null,
                "usage_type": "licensed"
              },
              "tax_behavior": "unspecified",
              "tiers_mode": null,
              "transform_quantity": null,
              "type": "recurring",
              "unit_amount": 9700,
              "unit_amount_decimal": "9700"
            },
            "proration": false,
            "proration_details": {
              "credited_items": null
            },
            "quantity": 1,
            "subscription": "sub_1234567890",
            "subscription_item": "si_1234567890",
            "tax_amounts": [],
            "type": "subscription",
            "unit_amount_excluding_tax": 9700
          }
        ],
        "has_more": false,
        "object": "list",
        "total_count": 1,
        "url": "/v1/invoices/in_1234567890/lines"
      },
      "livemode": true,
      "metadata": {
        "userId": "user_123",
        "planId": "growth"
      },
      "next_payment_attempt": null,
      "number": "0001",
      "on_behalf_of": null,
      "paid": true,
      "paid_out_of_band": false,
      "payment_intent": "pi_1234567890",
      "payment_settings": {
        "custom_fields": null,
        "default_mandate": null,
        "payment_method": null,
        "payment_method_options": null,
        "payment_method_types": null,
        "save_default_payment_method": "off"
      },
      "period_end": 1673520000,
      "period_start": 1673520000,
      "post_payment_actions": null,
      "pre_payment_actions": null,
      "quote": null,
      "receipt_number": null,
      "rendering": {
        "amount_due_format": "amount_due",
        "custom_fields": null,
        "description": null,
        "footer": null,
        "pdf": null
      },
      "rendering_options": null,
      "revision": null,
      "source_invoice": null,
      "starting_balance": 0,
      "statement_descriptor": null,
      "status": "paid",
      "status_transitions": {
        "finalized_at": 1673520000,
        "marked_uncollectible_at": null,
        "paid_at": 1673520000,
        "voided_at": null
      },
      "subscription": "sub_1234567890",
      "subtotal": 9700,
      "subtotal_excluding_tax": 9700,
      "tax": 0,
      "test_clock": null,
      "total": 9700,
      "total_discount_amounts": [],
      "total_excluding_tax": 9700,
      "total_tax_amounts": [],
      "transfer_data": null,
      "url": "https://invoice.stripe.com/i/acct_1234567890/test_YWNjdF8xMjM0NTY3ODkw0200hR8Z0Z8Z",
      "user_supplied_frm_data": null,
      "webhooks_delivered_at": 1673520000
    }
  },
  "livemode": true,
  "pending_webhooks": 0,
  "request": {
    "id": null,
    "idempotency_key": null
  },
  "type": "invoice.payment_succeeded"
}
```

---

## 🔍 Troubleshooting

### Webhook não está sendo recebido

**Problema**: Webhook não aparece nos logs

**Solução**:
```bash
# 1. Verificar se webhook está configurado no Stripe
stripe webhooks list

# 2. Verificar se URL está correta
stripe webhooks update whsec_... --url https://api.nexias.ai/api/webhooks/stripe

# 3. Verificar se endpoint está respondendo
curl -X POST https://api.nexias.ai/api/webhooks/stripe \
  -H "stripe-signature: test" \
  -H "Content-Type: application/json" \
  -d '{}'

# 4. Verificar logs do backend
kubectl logs -f deployment/backend-api -n ai-platform-production | grep webhook
```

### Créditos não estão sendo atribuídos

**Problema**: Webhook é recebido, mas créditos não aparecem

**Solução**:
```bash
# 1. Verificar se userId está no metadata do cliente
stripe customers retrieve cus_1234567890 | grep userId

# 2. Verificar se plano é válido
stripe subscriptions retrieve sub_1234567890 | grep price_id

# 3. Verificar se banco de dados está acessível
kubectl exec -it deployment/backend-api -n ai-platform-production -- \
  psql postgresql://user:password@cloud-sql-proxy:5432/ai-platform \
  -c "SELECT * FROM \"CreditBalance\" WHERE \"userId\" = 'user_123';"

# 4. Verificar logs detalhados
kubectl logs -f deployment/backend-api -n ai-platform-production --tail=100 | grep "Awarded"
```

### Erro: "Webhook signature verification failed"

**Problema**: Webhook não está sendo validado

**Solução**:
```bash
# 1. Verificar se STRIPE_WEBHOOK_SECRET está configurado
kubectl get secret stripe-credentials -n ai-platform-production -o yaml | grep webhook_secret

# 2. Verificar se secret está correto
# Comparar com o valor em: https://dashboard.stripe.com/webhooks

# 3. Se estiver usando Stripe CLI, usar o signing secret correto
stripe listen --forward-to http://localhost:3001/webhooks/stripe
# Copiar o signing secret exibido
```

---

## 📋 Checklist de Testes

- [ ] Teste 1: Criar assinatura com Payment Intent
- [ ] Teste 2: Simular webhook com Stripe CLI
- [ ] Teste 3: Fluxo completo com cartão de teste
- [ ] Teste 4: Falha de pagamento
- [ ] Teste 5: Cupom de desconto
- [ ] Validar créditos no banco de dados
- [ ] Validar logs do backend
- [ ] Validar webhook no Stripe Dashboard
- [ ] Testar com múltiplos usuários
- [ ] Testar com múltiplos planos (Growth e Scale)

---

## 📞 Contato

Para dúvidas ou problemas:
- Documentação Stripe: https://stripe.com/docs
- Stripe CLI: https://stripe.com/docs/stripe-cli
- Suporte: support@stripe.com

---

**Implementado por**: Manus AI  
**Data**: 12 de Janeiro de 2026  
**Status**: ✅ Pronto para Testes
