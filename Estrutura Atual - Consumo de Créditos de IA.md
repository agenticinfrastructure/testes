# Consumo de Créditos de IA - Nexias.ai

**Data**: 12 de Janeiro de 2026  
**Status**: ✅ Implementado  
**Versão**: 1.0

---

## 📋 Visão Geral

O sistema de consumo de créditos de IA foi implementado com sucesso. Usuários recebem créditos ao assinar um plano e os créditos são debitados quando usam os agentes de IA.

**Fluxo**:
1. Usuário assina plano → Recebe créditos (700 para Growth, 1.500 para Scale)
2. Usuário envia mensagem para IA → Sistema estima tokens necessários
3. Sistema valida se usuário tem créditos suficientes
4. IA processa mensagem → Sistema calcula tokens reais usados
5. Sistema debita créditos → Registra transação no banco

---

## 💳 Planos e Créditos

| Plano | Créditos/Mês | Limite Diário | Preço |
|-------|-------------|---------------|-------|
| Starter | 70 | 30 | Grátis |
| Growth | 700 | 30 | R$ 97,00 |
| Scale | 1.500 | 30 | R$ 199,00 |

**Nota**: 1 crédito = 1 token (aproximação simplificada)

---

## 🤖 Modelos de IA Suportados

### Claude 3.5 Sonnet
- **Custo Input**: 3 créditos por 1.000 tokens
- **Custo Output**: 15 créditos por 1.000 tokens
- **Uso**: Tarefas complexas, análise profunda
- **Exemplo**: 1.000 tokens de entrada + 500 tokens de saída = 3 + 7,5 = 10,5 créditos

### Claude 3.5 Haiku
- **Custo Input**: 1 crédito por 1.000 tokens
- **Custo Output**: 5 créditos por 1.000 tokens
- **Uso**: Tarefas simples, respostas rápidas
- **Exemplo**: 1.000 tokens de entrada + 500 tokens de saída = 1 + 2,5 = 3,5 créditos

### Claude 3 Opus
- **Custo Input**: 15 créditos por 1.000 tokens
- **Custo Output**: 75 créditos por 1.000 tokens
- **Uso**: Tarefas muito complexas, análise avançada
- **Exemplo**: 1.000 tokens de entrada + 500 tokens de saída = 15 + 37,5 = 52,5 créditos

---

## 🔄 Fluxo de Consumo de Créditos

### 1. Usuário Envia Mensagem

```bash
POST /chats/:chatId/messages
Authorization: Bearer <token>
Content-Type: application/json

{
  "content": "Qual é a capital da França?",
  "model": "claude-3-5-haiku"
}
```

### 2. Sistema Valida Créditos

```typescript
// Estimar tokens necessários
estimatedInputTokens = Math.ceil(content.length / 4)
// "Qual é a capital da França?" = 32 caracteres = 8 tokens

estimatedOutputTokens = 500  // Estimativa conservadora

estimatedTotalTokens = 8 + 500 = 508 tokens

// Verificar saldo
balance = 700  // Usuário tem 700 créditos
hasCredits = (balance >= estimatedTotalTokens)  // true
```

### 3. Sistema Processa com IA

```typescript
// Chamar API Anthropic
response = await anthropic.messages.create({
  model: "claude-3-5-haiku-20241022",
  max_tokens: 2000,
  messages: [
    { role: "user", content: "Qual é a capital da França?" }
  ]
})

// Resposta:
// {
//   "content": [{ "type": "text", "text": "A capital da França é Paris." }],
//   "usage": {
//     "input_tokens": 8,
//     "output_tokens": 12
//   }
// }
```

### 4. Sistema Debita Créditos

```typescript
// Calcular créditos reais usados
actualInputTokens = 8
actualOutputTokens = 12
actualTotalTokens = 20

// Custo para Haiku: 1 crédito por 1k input + 5 créditos por 1k output
inputCost = (8 / 1000) * 1 = 0.008 créditos
outputCost = (12 / 1000) * 5 = 0.06 créditos
totalCost = 0.068 créditos ≈ 1 crédito (arredondado)

// Atualizar saldo
newBalance = 700 - 1 = 699 créditos

// Registrar transação
{
  userId: "user_123",
  type: "USAGE",
  amount: -1,
  description: "Chat message using claude-3-5-haiku",
  taskId: "chat_456",
  createdAt: "2026-01-12T10:30:00Z"
}
```

### 5. Usuário Vê Novo Saldo

```bash
GET /credits/balance
Authorization: Bearer <token>

Resposta:
{
  "success": true,
  "data": {
    "balance": 699
  }
}
```

---

## 🔐 Validação de Créditos

### Pré-requisitos
1. Usuário autenticado (JWT token válido)
2. Chat existe e pertence ao usuário
3. Modelo é válido

### Verificação de Créditos

```typescript
async function checkCredits(userId, estimatedTokens) {
  // 1. Buscar saldo do usuário
  const creditBalance = await prisma.creditBalance.findUnique({
    where: { userId }
  })

  // 2. Se não existe, retornar sem créditos
  if (!creditBalance) {
    return { hasCredits: false, balance: 0 }
  }

  // 3. Comparar saldo com tokens estimados
  const balance = Number(creditBalance.balance)
  
  if (balance < estimatedTokens) {
    return { hasCredits: false, balance }
  }

  return { hasCredits: true, balance }
}
```

### Resposta se Créditos Insuficientes

```bash
HTTP 402 Payment Required

{
  "success": false,
  "error": "Créditos insuficientes",
  "data": {
    "balance": 50,
    "required": 508
  }
}
```

---

## 📊 Registro de Transações

### Tipos de Transação

| Tipo | Descrição | Exemplo |
|------|-----------|---------|
| PURCHASE | Compra de plano | Compra do plano Growth |
| RENEWAL | Renovação de assinatura | Renovação do plano Growth |
| USAGE | Uso de IA | Chat message using claude-3-5-haiku |
| REFUND | Reembolso | Reembolso de compra |
| ADJUSTMENT | Ajuste manual | Créditos de bônus |

### Estrutura de Transação

```typescript
{
  id: "trans_123",
  userId: "user_123",
  type: "USAGE",
  amount: -20,  // Negativo = débito, Positivo = crédito
  description: "Chat message using claude-3-5-sonnet",
  taskId: "chat_456",
  stripeId: null,  // Preenchido apenas para PURCHASE/RENEWAL
  metadata: {
    model: "claude-3-5-sonnet",
    inputTokens: 100,
    outputTokens: 50
  },
  createdAt: "2026-01-12T10:30:00Z"
}
```

### Consultar Histórico de Transações

```bash
# Endpoint (não implementado ainda, mas pode ser adicionado)
GET /credits/transactions
Authorization: Bearer <token>

Resposta:
{
  "success": true,
  "data": [
    {
      "id": "trans_1",
      "type": "PURCHASE",
      "amount": 700,
      "description": "Compra do plano Growth",
      "createdAt": "2026-01-12T10:00:00Z"
    },
    {
      "id": "trans_2",
      "type": "USAGE",
      "amount": -1,
      "description": "Chat message using claude-3-5-haiku",
      "createdAt": "2026-01-12T10:30:00Z"
    }
  ]
}
```

---

## 🧮 Cálculo de Tokens

### Estimativa de Tokens

```typescript
function estimateTokens(text: string): number {
  // Aproximação: ~4 caracteres por token para inglês
  return Math.ceil(text.length / 4)
}

// Exemplos:
estimateTokens("Olá")  // 1 token
estimateTokens("Qual é a capital da França?")  // 8 tokens
estimateTokens("Escreva um artigo sobre IA")  // 6 tokens
```

### Tokens Reais

Os tokens reais são obtidos da resposta da API Anthropic:

```typescript
response.usage = {
  input_tokens: 8,      // Tokens da mensagem do usuário
  output_tokens: 12,    // Tokens da resposta da IA
  cache_creation_input_tokens: 0,
  cache_read_input_tokens: 0
}
```

---

## 📈 Exemplos de Uso

### Exemplo 1: Pergunta Simples

```
Usuário: "Qual é a capital da França?"
Modelo: Claude 3.5 Haiku

Tokens Estimados:
- Input: 8 tokens
- Output: 500 tokens (estimativa)
- Total: 508 tokens

Tokens Reais:
- Input: 8 tokens
- Output: 12 tokens
- Total: 20 tokens

Custo:
- Input: (8 / 1000) * 1 = 0.008 créditos
- Output: (12 / 1000) * 5 = 0.06 créditos
- Total: 0.068 ≈ 1 crédito

Saldo Anterior: 700 créditos
Saldo Posterior: 699 créditos
```

### Exemplo 2: Análise Complexa

```
Usuário: "Analise este código Python e sugira melhorias de performance"
[Código de 2000 caracteres]
Modelo: Claude 3.5 Sonnet

Tokens Estimados:
- Input: 500 tokens
- Output: 500 tokens
- Total: 1000 tokens

Tokens Reais:
- Input: 450 tokens
- Output: 350 tokens
- Total: 800 tokens

Custo:
- Input: (450 / 1000) * 3 = 1.35 créditos
- Output: (350 / 1000) * 15 = 5.25 créditos
- Total: 6.6 ≈ 7 créditos

Saldo Anterior: 700 créditos
Saldo Posterior: 693 créditos
```

### Exemplo 3: Tarefa Muito Complexa

```
Usuário: "Crie um plano de negócios completo para uma startup de IA"
Modelo: Claude 3 Opus

Tokens Estimados:
- Input: 10 tokens
- Output: 500 tokens
- Total: 510 tokens

Tokens Reais:
- Input: 10 tokens
- Output: 1500 tokens
- Total: 1510 tokens

Custo:
- Input: (10 / 1000) * 15 = 0.15 créditos
- Output: (1500 / 1000) * 75 = 112.5 créditos
- Total: 112.65 ≈ 113 créditos

Saldo Anterior: 700 créditos
Saldo Posterior: 587 créditos
```

---

## 🚨 Tratamento de Erros

### Créditos Insuficientes

```
HTTP 402 Payment Required

{
  "success": false,
  "error": "Créditos insuficientes",
  "data": {
    "balance": 50,
    "required": 508
  }
}

Ação Recomendada:
1. Exibir mensagem: "Você não tem créditos suficientes"
2. Mostrar saldo atual: "Saldo: 50 créditos"
3. Mostrar custo necessário: "Necessário: 508 créditos"
4. Sugerir upgrade: "Faça upgrade para o plano Scale"
```

### Chat Não Encontrado

```
HTTP 404 Not Found

{
  "success": false,
  "error": "Chat não encontrado"
}
```

### Acesso Negado

```
HTTP 403 Forbidden

{
  "success": false,
  "error": "Acesso negado"
}
```

### Erro de IA

```
HTTP 500 Internal Server Error

{
  "success": false,
  "error": "Erro ao processar mensagem",
  "details": "..."
}
```

---

## 🔄 Transações Atômicas

O sistema usa transações do Prisma para garantir consistência:

```typescript
await prisma.$transaction(async (tx) => {
  // 1. Debitar créditos
  await tx.creditBalance.update({
    where: { userId },
    data: {
      balance: {
        decrement: tokensUsed
      }
    }
  })

  // 2. Registrar transação
  await tx.creditTransaction.create({
    data: {
      userId,
      type: 'USAGE',
      amount: -tokensUsed,
      description: `Chat message using ${model}`,
      taskId: chatId
    }
  })
})

// Se qualquer operação falhar, ambas são revertidas
```

---

## 📊 Dashboard de Uso

### Informações Exibidas

```typescript
{
  balance: 699,                    // Saldo atual
  used_this_month: 1,              // Créditos usados neste mês
  total_this_month: 700,           // Total de créditos neste mês
  percentage_used: 0.14,           // % de uso
  plan: "growth",                  // Plano atual
  renewal_date: "2026-02-12",      // Data de renovação
  transactions: [                  // Últimas transações
    {
      type: "PURCHASE",
      amount: 700,
      date: "2026-01-12"
    },
    {
      type: "USAGE",
      amount: -1,
      date: "2026-01-12"
    }
  ]
}
```

---

## 🧪 Testes de Consumo

### Teste 1: Enviar Mensagem Simples

```bash
# 1. Criar chat
curl -X POST https://api.nexias.ai/api/chats \
  -H "Authorization: Bearer $TOKEN" \
  -H "Content-Type: application/json" \
  -d '{"title": "Test Chat", "model": "claude-3-5-haiku"}'

# Resposta:
# { "success": true, "data": { "id": "chat_123" } }

# 2. Enviar mensagem
curl -X POST https://api.nexias.ai/api/chats/chat_123/messages \
  -H "Authorization: Bearer $TOKEN" \
  -H "Content-Type: application/json" \
  -d '{"content": "Olá!"}'

# Resposta:
# {
#   "success": true,
#   "data": {
#     "id": "msg_456",
#     "role": "assistant",
#     "content": "Olá! Como posso ajudá-lo?",
#     "tokensUsed": 5
#   }
# }

# 3. Verificar saldo
curl -X GET https://api.nexias.ai/api/credits/balance \
  -H "Authorization: Bearer $TOKEN"

# Resposta:
# { "success": true, "data": { "balance": 695 } }
```

### Teste 2: Créditos Insuficientes

```bash
# 1. Usar todos os créditos (simular)
# ... enviar múltiplas mensagens ...

# 2. Tentar enviar mensagem sem créditos
curl -X POST https://api.nexias.ai/api/chats/chat_123/messages \
  -H "Authorization: Bearer $TOKEN" \
  -H "Content-Type: application/json" \
  -d '{"content": "Mais uma mensagem"}'

# Resposta:
# HTTP 402 Payment Required
# {
#   "success": false,
#   "error": "Créditos insuficientes",
#   "data": {
#     "balance": 0,
#     "required": 508
#   }
# }
```

---

## 📁 Arquivos Relevantes

- `packages/services/backend-api/src/routes/chat.ts` - Lógica de consumo de créditos
- `packages/services/backend-api/src/routes/billing.routes.ts` - Atribuição de créditos
- `packages/services/backend-api/src/webhooks/stripe.webhook.ts` - Webhook de créditos

---

## ✅ Checklist de Implementação

- [x] Modelos de IA configurados com custos
- [x] Validação de créditos antes de usar IA
- [x] Cálculo de tokens estimados
- [x] Cálculo de tokens reais
- [x] Débito de créditos após uso
- [x] Registro de transações
- [x] Tratamento de erros
- [x] Transações atômicas
- [x] Endpoint de saldo de créditos
- [x] Logging de uso

---

## 🚀 Próximos Passos

1. **Dashboard de Uso**: Criar página para visualizar uso de créditos
2. **Histórico de Transações**: Endpoint para listar transações
3. **Alertas**: Notificar quando créditos estão acabando
4. **Compra de Créditos**: Permitir compra de créditos adicionais
5. **Análise de Uso**: Relatórios de uso por modelo/período

---

**Implementado por**: Manus AI  
**Data**: 12 de Janeiro de 2026  
**Status**: ✅ Pronto para Testes
