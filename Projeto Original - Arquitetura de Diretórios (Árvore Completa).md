# Arquitetura de Diretórios – vFinal (Produção)

## Árvore de Diretórios Super Detalhada (Referência Completa)

Esta seção apresenta a estrutura de diretórios completa, servindo como referência visual para a implementação. O nível de detalhe inclui todos os arquivos e subpastas necessários para uma plataforma de IA de larga escala.

```plaintext
ai-platform/
│
├── .github/                                      # CI/CD e automação do repositório
│   ├── workflows/                                # Workflows do GitHub Actions
│   │   ├── ci.yml                                # Pipeline de Integração Contínua
│   │   ├── deploy-staging.yml                    # Deploy para ambiente de Staging
│   │   ├── deploy-production.yml                 # Deploy para ambiente de Produção
│   │   ├── security-scan.yml                     # Varredura de vulnerabilidades
│   │   └── ai-evaluation.yml                     # Avaliação de performance do agente
│   ├── ISSUE_TEMPLATE/                           # Templates para issues
│   │   ├── bug_report.md
│   │   └── feature_request.md
│   └── PULL_REQUEST_TEMPLATE.md
│
├── apps/                                         # Aplicações de entrada (thin clients)
│   │
│   ├── web/                                      # Aplicação Web (Next.js 14+)
│   │   ├── app/                                  # App Router (Next.js)
│   │   │   ├── (auth)/                           # Grupo de rotas de autenticação
│   │   │   │   ├── login/
│   │   │   │   │   └── page.tsx
│   │   │   │   ├── signup/
│   │   │   │   │   └── page.tsx
│   │   │   │   └── forgot-password/
│   │   │   │       └── page.tsx
│   │   │   ├── (app)/                            # Grupo de rotas da aplicação principal
│   │   │   │   ├── dashboard/
│   │   │   │   │   └── page.tsx
│   │   │   │   ├── chat/
│   │   │   │   │   ├── [id]/
│   │   │   │   │   │   └── page.tsx
│   │   │   │   │   └── page.tsx
│   │   │   │   ├── tasks/
│   │   │   │   │   ├── [id]/
│   │   │   │   │   │   └── page.tsx
│   │   │   │   │   └── page.tsx
│   │   │   │   ├── documents/
│   │   │   │   │   └── page.tsx
│   │   │   │   ├── billing/
│   │   │   │   │   └── page.tsx
│   │   │   │   └── settings/
│   │   │   │       └── page.tsx
│   │   │   ├── api/                              # API Routes (Next.js)
│   │   │   │   └── health/
│   │   │   │       └── route.ts
│   │   │   ├── layout.tsx
│   │   │   └── globals.css
│   │   ├── components/                           # Componentes React reutilizáveis
│   │   │   ├── common/                           # Componentes genéricos
│   │   │   │   ├── Header.tsx
│   │   │   │   ├── Sidebar.tsx
│   │   │   │   ├── Footer.tsx
│   │   │   │   ├── LoadingSpinner.tsx
│   │   │   │   └── ErrorBoundary.tsx
│   │   │   ├── chat/                             # Componentes do domínio de Chat
│   │   │   │   ├── ChatWindow.tsx
│   │   │   │   ├── MessageList.tsx
│   │   │   │   ├── MessageInput.tsx
│   │   │   │   ├── AgentStatus.tsx
│   │   │   │   └── ToolExecution.tsx
│   │   │   ├── task/                             # Componentes do domínio de Tarefas
│   │   │   │   ├── TaskCard.tsx
│   │   │   │   ├── TaskList.tsx
│   │   │   │   ├── TaskProgress.tsx
│   │   │   │   └── TaskDetails.tsx
│   │   │   ├── billing/                          # Componentes do domínio de Billing
│   │   │   │   ├── CreditBalance.tsx
│   │   │   │   ├── PlanSelector.tsx
│   │   │   │   ├── PaymentForm.tsx
│   │   │   │   └── UsageChart.tsx
│   │   │   └── workspace/                        # Componentes do Workspace (FSaC)
│   │   │       ├── FileExplorer.tsx
│   │   │       ├── FileViewer.tsx
│   │   │       └── TodoViewer.tsx
│   │   ├── hooks/                                # Custom React Hooks
│   │   │   ├── useAuth.ts
│   │   │   ├── useChat.ts
│   │   │   ├── useTask.ts
│   │   │   ├── useWebSocket.ts
│   │   │   └── useCredits.ts
│   │   ├── store/                                # Gerenciamento de estado (Redux Toolkit)
│   │   │   ├── store.ts                          # Configuração do store
│   │   │   ├── hooks.ts                          # Typed hooks (useAppDispatch, useAppSelector)
│   │   │   └── features/                         # Slices do Redux
│   │   │       ├── auth/
│   │   │       │   └── authSlice.ts
│   │   │       ├── chat/
│   │   │       │   └── chatSlice.ts
│   │   │       ├── task/
│   │   │       │   └── taskSlice.ts
│   │   │       └── billing/
│   │   │           └── billingSlice.ts
│   │   ├── services/                             # Clientes de API e WebSocket
│   │   │   ├── api.ts                            # Cliente base (Axios/Fetch)
│   │   │   ├── auth.service.ts
│   │   │   ├── chat.service.ts
│   │   │   ├── task.service.ts
│   │   │   ├── billing.service.ts
│   │   │   └── websocket.service.ts
│   │   ├── types/                                # Tipos TypeScript do frontend
│   │   │   ├── auth.types.ts
│   │   │   ├── chat.types.ts
│   │   │   ├── task.types.ts
│   │   │   └── billing.types.ts
│   │   ├── utils/                                # Funções utilitárias do frontend
│   │   │   ├── formatters.ts
│   │   │   ├── validators.ts
│   │   │   └── constants.ts
│   │   ├── styles/                               # Estilos globais
│   │   │   └── tailwind.config.ts
│   │   ├── public/                               # Assets estáticos
│   │   │   ├── favicon.ico
│   │   │   └── images/
│   │   ├── tests/                                # Testes do frontend
│   │   │   ├── unit/
│   │   │   └── integration/
│   │   ├── next.config.js
│   │   ├── package.json
│   │   └── tsconfig.json
│   │
│   └── mobile/                                   # Aplicação Mobile (React Native/Expo)
│       ├── app/                                  # Rotas do app (Expo Router)
│       │   ├── (auth)/
│       │   │   ├── login.tsx
│       │   │   └── signup.tsx
│       │   ├── (tabs)/
│       │   │   ├── index.tsx
│       │   │   ├── chat.tsx
│       │   │   ├── tasks.tsx
│       │   │   └── settings.tsx
│       │   └── _layout.tsx
│       ├── components/                           # Componentes React Native
│       │   ├── common/
│       │   ├── chat/
│       │   └── task/
│       ├── hooks/
│       ├── store/
│       ├── services/
│       ├── types/
│       ├── utils/
│       ├── app.json
│       ├── package.json
│       └── tsconfig.json
│
├── packages/
│   │
│   ├── core/                                     # Lógica central e imutável
│   │   │
│   │   └── agent-core/                           # O cérebro do agente de IA
│   │       ├── src/
│   │       │   ├── main.ts                       # Loop principal do agente
│   │       │   ├── types.ts                      # Tipos centrais (AgentState, etc.)
│   │       │   │
│   │       │   ├── workspace/                    # [FSaC] File System as Context
│   │       │   │   ├── workspace.manager.ts      # Gerenciador de workspaces
│   │       │   │   ├── file.utils.ts             # Utilitários de arquivo
│   │       │   │   └── workspace.types.ts
│   │       │   │
│   │       │   ├── planning/                     # Gerenciamento de todo.md
│   │       │   │   ├── planner.service.ts        # Serviço de planejamento
│   │       │   │   ├── todo.manager.ts           # Gerenciador de todo.md
│   │       │   │   ├── replanning.service.ts     # Serviço de replanejamento
│   │       │   │   └── planning.types.ts
│   │       │   │
│   │       │   ├── memory/                       # Compressão Restaurável
│   │       │   │   ├── observation.processor.ts  # Processador de observações
│   │       │   │   ├── compression.service.ts    # Serviço de compressão
│   │       │   │   ├── restore.manager.ts        # Gerenciador de restauração
│   │       │   │   ├── cache/                    # Cache de contexto
│   │       │   │   │   ├── kv-cache.ts           # KV-Cache para LLMs
│   │       │   │   │   └── cache.types.ts
│   │       │   │   └── memory.types.ts
│   │       │   │
│   │       │   ├── reasoning/                    # Chain-of-thought, Self-consistency
│   │       │   │   ├── chain-of-thought.ts       # Implementação de CoT
│   │       │   │   ├── self-consistency.ts       # Implementação de SC
│   │       │   │   └── reasoning.types.ts
│   │       │   │
│   │       │   ├── execution/                    # Executor de ferramentas
│   │       │   │   ├── tool.executor.ts          # Executor principal
│   │       │   │   ├── state-machine.ts          # Máquina de estados para ferramentas
│   │       │   │   ├── tools/                    # Definição de ferramentas
│   │       │   │   │   ├── tool.interface.ts     # Interface base de ferramenta
│   │       │   │   │   ├── browser/              # Ferramentas de browser
│   │       │   │   │   │   ├── browser.tool.ts
│   │       │   │   │   │   ├── navigate.ts
│   │       │   │   │   │   ├── click.ts
│   │       │   │   │   │   └── input.ts
│   │       │   │   │   ├── shell/                # Ferramentas de shell
│   │       │   │   │   │   ├── shell.tool.ts
│   │       │   │   │   │   └── exec.ts
│   │       │   │   │   ├── file/                 # Ferramentas de arquivo
│   │       │   │   │   │   ├── file.tool.ts
│   │       │   │   │   │   ├── read.ts
│   │       │   │   │   │   ├── write.ts
│   │       │   │   │   │   └── edit.ts
│   │       │   │   │   └── search/               # Ferramentas de busca
│   │       │   │   │       ├── search.tool.ts
│   │       │   │   │       └── web-search.ts
│   │       │   │   └── execution.types.ts
│   │       │   │
│   │       │   └── verification/                 # Verificação Adaptativa
│   │       │       ├── orchestrator.ts           # Orquestrador de verificação
│   │       │       ├── relevance.analyzer.ts     # Analisador de relevância
│   │       │       ├── adaptive.verifier.ts      # Verificador adaptativo (do .py)
│   │       │       ├── confidence.scorer.ts      # Calculador de confiança
│   │       │       ├── strategies/               # Estratégias de verificação
│   │       │       │   ├── strategy.interface.ts
│   │       │       │   ├── self-consistency.strategy.ts
│   │       │       │   └── chain-of-verification.strategy.ts
│   │       │       └── verification.types.ts
│   │       │
│   │       ├── tests/
│   │       │   ├── unit/
│   │       │   └── integration/
│   │       ├── package.json
│   │       └── tsconfig.json
│   │
│   ├── features/                                 # Domínios de negócio independentes
│   │   │
│   │   ├── billing/                              # Créditos, planos, Stripe
│   │   │   ├── src/
│   │   │   │   ├── index.ts                      # Barrel export
│   │   │   │   ├── billing.module.ts             # Módulo de billing
│   │   │   │   │
│   │   │   │   ├── credits/                      # Gerenciamento de créditos
│   │   │   │   │   ├── credit.service.ts
│   │   │   │   │   ├── credit.repository.ts
│   │   │   │   │   └── credit.types.ts
│   │   │   │   │
│   │   │   │   ├── plans/                        # Planos de assinatura
│   │   │   │   │   ├── plan.service.ts
│   │   │   │   │   ├── plan.repository.ts
│   │   │   │   │   └── plan.types.ts
│   │   │   │   │
│   │   │   │   ├── stripe/                       # Integração com Stripe
│   │   │   │   │   ├── stripe.adapter.ts
│   │   │   │   │   ├── stripe.webhooks.ts
│   │   │   │   │   └── stripe.types.ts
│   │   │   │   │
│   │   │   │   └── limits/                       # Verificação de limites
│   │   │   │       ├── limit-checker.service.ts
│   │   │   │       └── limit.types.ts
│   │   │   │
│   │   │   ├── tests/
│   │   │   ├── package.json
│   │   │   └── tsconfig.json
│   │   │
│   │   └── affiliates/                           # Programa de afiliados
│   │       ├── src/
│   │       │   ├── index.ts
│   │       │   ├── affiliate.service.ts
│   │       │   ├── affiliate.repository.ts
│   │       │   ├── commission/
│   │       │   │   ├── commission.service.ts
│   │       │   │   └── commission.types.ts
│   │       │   └── referral/
│   │       │       ├── referral.service.ts
│   │       │       └── referral.types.ts
│   │       │
│   │       ├── tests/
│   │       ├── package.json
│   │       └── tsconfig.json
│   │
│   ├── services/                                 # Serviços de backend
│   │   │
│   │   ├── backend-api/                          # API Gateway para os apps
│   │   │   ├── src/
│   │   │   │   ├── main.ts                       # Ponto de entrada
│   │   │   │   ├── app.ts                        # Configuração do Fastify
│   │   │   │   │
│   │   │   │   ├── routes/                       # Definição de endpoints
│   │   │   │   │   ├── v1/                       # Versão 1 da API
│   │   │   │   │   │   ├── index.ts
│   │   │   │   │   │   ├── auth.routes.ts
│   │   │   │   │   │   ├── chat.routes.ts
│   │   │   │   │   │   ├── task.routes.ts
│   │   │   │   │   │   ├── billing.routes.ts
│   │   │   │   │   │   └── health.routes.ts
│   │   │   │   │   └── v2/                       # Versão 2 da API (futuro)
│   │   │   │   │       └── index.ts
│   │   │   │   │
│   │   │   │   ├── controllers/                  # Orquestração de requests
│   │   │   │   │   ├── auth.controller.ts
│   │   │   │   │   ├── chat.controller.ts
│   │   │   │   │   ├── task.controller.ts
│   │   │   │   │   └── billing.controller.ts
│   │   │   │   │
│   │   │   │   ├── services/                     # Lógica de negócio
│   │   │   │   │   ├── auth.service.ts
│   │   │   │   │   ├── chat.service.ts
│   │   │   │   │   ├── task.service.ts
│   │   │   │   │   └── agent-client.service.ts   # Cliente para o agent-core
│   │   │   │   │
│   │   │   │   ├── repositories/                 # Abstração de acesso a dados
│   │   │   │   │   ├── base/
│   │   │   │   │   │   ├── repository.interface.ts
│   │   │   │   │   │   └── repository.base.ts
│   │   │   │   │   ├── user.repository.ts
│   │   │   │   │   ├── chat.repository.ts
│   │   │   │   │   ├── task.repository.ts
│   │   │   │   │   └── audit.repository.ts
│   │   │   │   │
│   │   │   │   ├── middleware/                   # Middlewares
│   │   │   │   │   ├── auth.middleware.ts
│   │   │   │   │   ├── rate-limit.middleware.ts
│   │   │   │   │   └── error-handler.middleware.ts
│   │   │   │   │
│   │   │   │   ├── config/                       # Configurações
│   │   │   │   │   ├── env.ts
│   │   │   │   │   └── database.ts
│   │   │   │   │
│   │   │   │   └── types/                        # Tipos TypeScript
│   │   │   │       └── index.ts
│   │   │   │
│   │   │   ├── tests/
│   │   │   ├── Dockerfile
│   │   │   ├── package.json
│   │   │   └── tsconfig.json
│   │   │
│   │   ├── orchestrator/                         # Serviço de Orquestração de LLMs
│   │   │   ├── src/
│   │   │   │   ├── main.ts
│   │   │   │   ├── engine.ts                     # Núcleo de decisão
│   │   │   │   │
│   │   │   │   ├── criteria/                     # 68 critérios organizados por família
│   │   │   │   │   ├── base/
│   │   │   │   │   │   └── criterion.interface.ts
│   │   │   │   │   ├── performance/              # 8 critérios de performance
│   │   │   │   │   │   ├── latency.criterion.ts
│   │   │   │   │   │   ├── throughput.criterion.ts
│   │   │   │   │   │   ├── ttft.criterion.ts     # Time to First Token
│   │   │   │   │   │   ├── tps.criterion.ts      # Tokens per Second
│   │   │   │   │   │   ├── concurrency.criterion.ts
│   │   │   │   │   │   ├── queue-time.criterion.ts
│   │   │   │   │   │   ├── cold-start.criterion.ts
│   │   │   │   │   │   └── batch-efficiency.criterion.ts
│   │   │   │   │   ├── quality/                  # 12 critérios de qualidade
│   │   │   │   │   │   ├── accuracy.criterion.ts
│   │   │   │   │   │   ├── hallucination.criterion.ts
│   │   │   │   │   │   ├── coherence.criterion.ts
│   │   │   │   │   │   ├── relevance.criterion.ts
│   │   │   │   │   │   ├── completeness.criterion.ts
│   │   │   │   │   │   ├── factuality.criterion.ts
│   │   │   │   │   │   ├── reasoning.criterion.ts
│   │   │   │   │   │   ├── instruction-following.criterion.ts
│   │   │   │   │   │   ├── format-compliance.criterion.ts
│   │   │   │   │   │   ├── language-quality.criterion.ts
│   │   │   │   │   │   ├── creativity.criterion.ts
│   │   │   │   │   │   └── consistency.criterion.ts
│   │   │   │   │   ├── cost/                     # 7 critérios de custo
│   │   │   │   │   │   ├── token-cost.criterion.ts
│   │   │   │   │   │   ├── input-cost.criterion.ts
│   │   │   │   │   │   ├── output-cost.criterion.ts
│   │   │   │   │   │   ├── cache-cost.criterion.ts
│   │   │   │   │   │   ├── budget-remaining.criterion.ts
│   │   │   │   │   │   ├── cost-per-quality.criterion.ts
│   │   │   │   │   │   └── roi.criterion.ts
│   │   │   │   │   ├── security/                 # 9 critérios de segurança
│   │   │   │   │   │   ├── risk-score.criterion.ts
│   │   │   │   │   │   ├── content-safety.criterion.ts
│   │   │   │   │   │   ├── pii-detection.criterion.ts
│   │   │   │   │   │   ├── injection-risk.criterion.ts
│   │   │   │   │   │   ├── data-residency.criterion.ts
│   │   │   │   │   │   ├── compliance.criterion.ts
│   │   │   │   │   │   ├── audit-trail.criterion.ts
│   │   │   │   │   │   ├── encryption.criterion.ts
│   │   │   │   │   │   └── access-control.criterion.ts
│   │   │   │   │   ├── user-experience/          # 8 critérios de UX
│   │   │   │   │   │   ├── response-time.criterion.ts
│   │   │   │   │   │   ├── streaming.criterion.ts
│   │   │   │   │   │   ├── interactivity.criterion.ts
│   │   │   │   │   │   ├── personalization.criterion.ts
│   │   │   │   │   │   ├── tone.criterion.ts
│   │   │   │   │   │   ├── verbosity.criterion.ts
│   │   │   │   │   │   ├── accessibility.criterion.ts
│   │   │   │   │   │   └── localization.criterion.ts
│   │   │   │   │   ├── operational/              # 8 critérios operacionais
│   │   │   │   │   │   ├── availability.criterion.ts
│   │   │   │   │   │   ├── rate-limit.criterion.ts
│   │   │   │   │   │   ├── quota.criterion.ts
│   │   │   │   │   │   ├── health.criterion.ts
│   │   │   │   │   │   ├── load.criterion.ts
│   │   │   │   │   │   ├── failover.criterion.ts
│   │   │   │   │   │   ├── retry.criterion.ts
│   │   │   │   │   │   └── circuit-breaker.criterion.ts
│   │   │   │   │   ├── external/                 # 6 critérios externos
│   │   │   │   │   │   ├── time-of-day.criterion.ts
│   │   │   │   │   │   ├── region.criterion.ts
│   │   │   │   │   │   ├── provider-status.criterion.ts
│   │   │   │   │   │   ├── market-conditions.criterion.ts
│   │   │   │   │   │   ├── regulatory.criterion.ts
│   │   │   │   │   │   └── seasonal.criterion.ts
│   │   │   │   │   ├── task/                     # 5 critérios de tarefa
│   │   │   │   │   │   ├── task-type.criterion.ts
│   │   │   │   │   │   ├── complexity.criterion.ts
│   │   │   │   │   │   ├── domain.criterion.ts
│   │   │   │   │   │   ├── context-length.criterion.ts
│   │   │   │   │   │   └── multimodal.criterion.ts
│   │   │   │   │   └── learning/                 # 5 critérios de aprendizado
│   │   │   │   │       ├── feedback.criterion.ts
│   │   │   │   │       ├── historical.criterion.ts
│   │   │   │   │       ├── ab-test.criterion.ts
│   │   │   │   │       ├── exploration.criterion.ts
│   │   │   │   │       └── model-drift.criterion.ts
│   │   │   │   │
│   │   │   │   ├── strategies/                   # Estratégias de seleção
│   │   │   │   │   ├── strategy.interface.ts
│   │   │   │   │   ├── weighted-score.strategy.ts
│   │   │   │   │   ├── cost-optimized.strategy.ts
│   │   │   │   │   ├── quality-first.strategy.ts
│   │   │   │   │   ├── latency-first.strategy.ts
│   │   │   │   │   └── balanced.strategy.ts
│   │   │   │   │
│   │   │   │   ├── providers/                    # Providers de LLM
│   │   │   │   │   ├── provider.interface.ts
│   │   │   │   │   ├── anthropic/                # Anthropic (Claude)
│   │   │   │   │   │   ├── anthropic.provider.ts
│   │   │   │   │   │   ├── anthropic.adapter.ts
│   │   │   │   │   │   └── anthropic.types.ts
│   │   │   │   │   ├── qwen/                     # Qwen
│   │   │   │   │   │   ├── qwen.provider.ts
│   │   │   │   │   │   ├── qwen.adapter.ts
│   │   │   │   │   │   └── qwen.types.ts
│   │   │   │   │   └── nano-banana/              # Nano Banana
│   │   │   │   │       ├── nano-banana.provider.ts
│   │   │   │   │       ├── nano-banana.adapter.ts
│   │   │   │   │       └── nano-banana.types.ts
│   │   │   │   │
│   │   │   │   ├── layers/                       # Camadas transversais
│   │   │   │   │   ├── routing/                  # Roteamento inicial
│   │   │   │   │   │   └── router.ts
│   │   │   │   │   ├── verification/             # Verificação de output
│   │   │   │   │   │   └── output-verifier.ts
│   │   │   │   │   └── fallback/                 # Estratégias de fallback
│   │   │   │   │       └── fallback.ts
│   │   │   │   │
│   │   │   │   ├── cache/                        # Cache de decisões
│   │   │   │   │   └── decision-cache.ts
│   │   │   │   │
│   │   │   │   ├── metrics/                      # Métricas do orquestrador
│   │   │   │   │   └── orchestrator-metrics.ts
│   │   │   │   │
│   │   │   │   ├── config/
│   │   │   │   │   └── orchestrator.config.ts
│   │   │   │   │
│   │   │   │   └── types/
│   │   │   │       └── orchestrator.types.ts
│   │   │   │
│   │   │   ├── tests/
│   │   │   ├── Dockerfile
│   │   │   ├── package.json
│   │   │   └── tsconfig.json
│   │   │
│   │   └── workers/                              # Processamento Assíncrono
│   │       ├── src/
│   │       │   ├── main.ts
│   │       │   │
│   │       │   ├── queue/                        # Implementação de filas
│   │       │   │   ├── queue.interface.ts
│   │       │   │   ├── rabbitmq.queue.ts
│   │       │   │   └── redis.queue.ts
│   │       │   │
│   │       │   ├── consumers/                    # Consumidores de filas
│   │       │   │   ├── consumer.interface.ts
│   │       │   │   ├── task.consumer.ts
│   │       │   │   ├── document.consumer.ts
│   │       │   │   └── wide-research.consumer.ts # Wide Research (Manus AI)
│   │       │   │
│   │       │   ├── jobs/                         # Definição de jobs
│   │       │   │   ├── long-running/             # Jobs de longa duração
│   │       │   │   │   ├── document-analysis.job.ts
│   │       │   │   │   ├── task-execution.job.ts
│   │       │   │   │   └── wide-research.job.ts  # Wide Research (Manus AI)
│   │       │   │   ├── scheduled/                # Jobs agendados (cron)
│   │       │   │   │   ├── cleanup.job.ts
│   │       │   │   │   └── metrics-aggregation.job.ts
│   │       │   │   └── maintenance/              # Jobs de manutenção
│   │       │   │       └── cache-invalidation.job.ts
│   │       │   │
│   │       │   ├── schedulers/                   # Agendadores de jobs
│   │       │   │   └── cron.scheduler.ts
│   │       │   │
│   │       │   ├── retries/                      # Estratégias de retry
│   │       │   │   └── exponential-backoff.ts
│   │       │   │
│   │       │   ├── deadletter/                   # Tratamento de falhas
│   │       │   │   └── deadletter.handler.ts
│   │       │   │
│   │       │   ├── monitoring/                   # Monitoramento de workers
│   │       │   │   └── worker-metrics.ts
│   │       │   │
│   │       │   ├── config/
│   │       │   └── types/
│   │       │
│   │       ├── tests/
│   │       ├── Dockerfile
│   │       ├── package.json
│   │       └── tsconfig.json
│   │
│   ├── platform/                                 # Capacidades de plataforma
│   │   │
│   │   ├── security/                             # Auth, RBAC, compliance, safety
│   │   │   ├── src/
│   │   │   │   ├── index.ts
│   │   │   │   │
│   │   │   │   ├── auth/                         # Autenticação
│   │   │   │   │   ├── jwt.service.ts
│   │   │   │   │   ├── session.service.ts
│   │   │   │   │   ├── oauth.service.ts
│   │   │   │   │   └── auth.types.ts
│   │   │   │   │
│   │   │   │   ├── rbac/                         # Autorização (RBAC)
│   │   │   │   │   ├── roles.ts
│   │   │   │   │   ├── permissions.ts
│   │   │   │   │   ├── policies.ts
│   │   │   │   │   └── rbac.types.ts
│   │   │   │   │
│   │   │   │   ├── encryption/                   # Criptografia
│   │   │   │   │   ├── encrypt.service.ts
│   │   │   │   │   ├── hash.service.ts
│   │   │   │   │   └── encryption.types.ts
│   │   │   │   │
│   │   │   │   ├── audit/                        # Auditoria
│   │   │   │   │   ├── audit-logger.ts
│   │   │   │   │   └── audit.types.ts
│   │   │   │   │
│   │   │   │   ├── safety/                       # Safety para LLMs
│   │   │   │   │   ├── content-filter.ts
│   │   │   │   │   ├── pii-detector.ts
│   │   │   │   │   ├── injection-detector.ts
│   │   │   │   │   └── safety.types.ts
│   │   │   │   │
│   │   │   │   ├── compliance/                   # Compliance
│   │   │   │   │   ├── gdpr.service.ts
│   │   │   │   │   ├── lgpd.service.ts
│   │   │   │   │   └── compliance.types.ts
│   │   │   │   │
│   │   │   │   └── middleware/                   # Middlewares de segurança
│   │   │   │       ├── auth.middleware.ts
│   │   │   │       ├── rbac.middleware.ts
│   │   │   │       └── rate-limit.middleware.ts
│   │   │   │
│   │   │   ├── tests/
│   │   │   ├── package.json
│   │   │   └── tsconfig.json
│   │   │
│   │   ├── observability/                        # OTel, tracing, metrics, logs
│   │   │   ├── src/
│   │   │   │   ├── index.ts
│   │   │   │   │
│   │   │   │   ├── logging/                      # Logging estruturado
│   │   │   │   │   ├── logger.ts
│   │   │   │   │   ├── transports/
│   │   │   │   │   │   ├── console.transport.ts
│   │   │   │   │   │   └── file.transport.ts
│   │   │   │   │   └── formatters/
│   │   │   │   │       └── json.formatter.ts
│   │   │   │   │
│   │   │   │   ├── metrics/                      # Métricas (Prometheus)
│   │   │   │   │   ├── metrics.ts
│   │   │   │   │   ├── collectors/
│   │   │   │   │   │   ├── http.collector.ts
│   │   │   │   │   │   └── agent.collector.ts
│   │   │   │   │   └── exporters/
│   │   │   │   │       └── prometheus.exporter.ts
│   │   │   │   │
│   │   │   │   ├── tracing/                      # Tracing distribuído (OpenTelemetry)
│   │   │   │   │   ├── tracer.ts
│   │   │   │   │   ├── context.ts
│   │   │   │   │   └── spans/
│   │   │   │   │       ├── http.span.ts
│   │   │   │   │       └── agent.span.ts
│   │   │   │   │
│   │   │   │   ├── health/                       # Health checks
│   │   │   │   │   ├── health-check.ts
│   │   │   │   │   └── probes/
│   │   │   │   │       ├── liveness.probe.ts
│   │   │   │   │       └── readiness.probe.ts
│   │   │   │   │
│   │   │   │   ├── alerts/                       # Alertas
│   │   │   │   │   ├── alert.service.ts
│   │   │   │   │   └── rules/
│   │   │   │   │       ├── error-rate.rule.ts
│   │   │   │   │       └── latency.rule.ts
│   │   │   │   │
│   │   │   │   └── dashboards/                   # Configs de dashboards
│   │   │   │       └── grafana/
│   │   │   │           ├── agent-dashboard.json
│   │   │   │           └── api-dashboard.json
│   │   │   │
│   │   │   ├── tests/
│   │   │   ├── package.json
│   │   │   └── tsconfig.json
│   │   │
│   │   ├── data-governance/                      # Governança de dados e linhagem
│   │   │   ├── src/
│   │   │   │   ├── index.ts
│   │   │   │   ├── lineage/                      # Linhagem de dados
│   │   │   │   │   └── lineage.service.ts
│   │   │   │   ├── quality/                      # Qualidade de dados
│   │   │   │   │   └── quality.service.ts
│   │   │   │   ├── catalog/                      # Catálogo de dados
│   │   │   │   │   └── catalog.service.ts
│   │   │   │   └── access/                       # Controle de acesso a dados
│   │   │   │       └── data-access.service.ts
│   │   │   │
│   │   │   ├── tests/
│   │   │   ├── package.json
│   │   │   └── tsconfig.json
│   │   │
│   │   ├── experimentation/                      # Testes A/B, feature flags
│   │   │   ├── src/
│   │   │   │   ├── index.ts
│   │   │   │   ├── feature-flags/                # Feature flags
│   │   │   │   │   ├── flag.service.ts
│   │   │   │   │   └── flag.types.ts
│   │   │   │   ├── ab-testing/                   # Testes A/B
│   │   │   │   │   ├── experiment.service.ts
│   │   │   │   │   ├── variant.service.ts
│   │   │   │   │   └── ab.types.ts
│   │   │   │   └── rollout/                      # Rollout gradual
│   │   │   │       └── rollout.service.ts
│   │   │   │
│   │   │   ├── tests/
│   │   │   ├── package.json
│   │   │   └── tsconfig.json
│   │   │
│   │   └── ai-evaluation/                        # Avaliação de performance de agentes
│   │       ├── src/
│   │       │   ├── index.ts
│   │       │   │
│   │       │   ├── evaluators/                   # Avaliadores
│   │       │   │   ├── evaluator.interface.ts
│   │       │   │   ├── accuracy.evaluator.ts
│   │       │   │   ├── latency.evaluator.ts
│   │       │   │   ├── cost.evaluator.ts
│   │       │   │   └── quality.evaluator.ts
│   │       │   │
│   │       │   ├── suites/                       # Suítes de avaliação
│   │       │   │   ├── suite.interface.ts
│   │       │   │   ├── coding.suite.ts
│   │       │   │   ├── reasoning.suite.ts
│   │       │   │   └── research.suite.ts
│   │       │   │
│   │       │   ├── datasets/                     # Golden datasets
│   │       │   │   ├── coding/
│   │       │   │   ├── reasoning/
│   │       │   │   └── research/
│   │       │   │
│   │       │   ├── reporters/                    # Relatórios de avaliação
│   │       │   │   ├── reporter.interface.ts
│   │       │   │   ├── json.reporter.ts
│   │       │   │   └── html.reporter.ts
│   │       │   │
│   │       │   └── runners/                      # Executores de avaliação
│   │       │       ├── runner.interface.ts
│   │       │       └── parallel.runner.ts
│   │       │
│   │       ├── tests/
│   │       ├── package.json
│   │       └── tsconfig.json
│   │
│   ├── shared/                                   # Código compartilhado
│   │   │
│   │   ├── ui/                                   # Componentes React compartilhados
│   │   │   ├── src/
│   │   │   │   ├── index.ts
│   │   │   │   ├── components/
│   │   │   │   │   ├── Button.tsx
│   │   │   │   │   ├── Input.tsx
│   │   │   │   │   ├── Modal.tsx
│   │   │   │   │   ├── Card.tsx
│   │   │   │   │   └── Table.tsx
│   │   │   │   └── hooks/
│   │   │   │       └── useTheme.ts
│   │   │   │
│   │   │   ├── package.json
│   │   │   └── tsconfig.json
│   │   │
│   │   ├── config/                               # Configurações de ambiente
│   │   │   ├── src/
│   │   │   │   ├── index.ts
│   │   │   │   ├── env.ts
│   │   │   │   ├── env.schema.ts
│   │   │   │   └── environments/
│   │   │   │       ├── development.ts
│   │   │   │       ├── staging.ts
│   │   │   │       └── production.ts
│   │   │   │
│   │   │   ├── package.json
│   │   │   └── tsconfig.json
│   │   │
│   │   ├── schemas/                              # Schemas Zod para validação
│   │   │   ├── src/
│   │   │   │   ├── index.ts
│   │   │   │   ├── api/                          # Schemas de API
│   │   │   │   │   ├── auth.schema.ts
│   │   │   │   │   ├── chat.schema.ts
│   │   │   │   │   ├── task.schema.ts
│   │   │   │   │   └── billing.schema.ts
│   │   │   │   ├── database/                     # Schemas de banco
│   │   │   │   │   ├── user.schema.ts
│   │   │   │   │   └── task.schema.ts
│   │   │   │   └── business/                     # Schemas de domínio
│   │   │   │       └── agent.schema.ts
│   │   │   │
│   │   │   ├── package.json
│   │   │   └── tsconfig.json
│   │   │
│   │   ├── types/                                # Tipos TypeScript compartilhados
│   │   │   ├── src/
│   │   │   │   ├── index.ts
│   │   │   │   ├── common.types.ts
│   │   │   │   ├── api.types.ts
│   │   │   │   ├── agent.types.ts
│   │   │   │   └── llm.types.ts
│   │   │   │
│   │   │   ├── package.json
│   │   │   └── tsconfig.json
│   │   │
│   │   ├── database/                             # Migrations e clientes de DB
│   │   │   ├── src/
│   │   │   │   ├── index.ts
│   │   │   │   ├── client.ts                     # Cliente Prisma/Drizzle
│   │   │   │   ├── migrations/
│   │   │   │   │   ├── 0001_initial.sql
│   │   │   │   │   └── 0002_add_credits.sql
│   │   │   │   ├── seeds/
│   │   │   │   │   ├── users.seed.ts
│   │   │   │   │   └── plans.seed.ts
│   │   │   │   └── models/
│   │   │   │       ├── user.model.ts
│   │   │   │       ├── task.model.ts
│   │   │   │       └── chat.model.ts
│   │   │   │
│   │   │   ├── package.json
│   │   │   └── tsconfig.json
│   │   │
│   │   ├── contracts/                            # Contratos de API (OpenAPI, gRPC)
│   │   │   ├── src/
│   │   │   │   ├── index.ts
│   │   │   │   ├── openapi/
│   │   │   │   │   └── api.yaml
│   │   │   │   ├── grpc/
│   │   │   │   │   └── agent.proto
│   │   │   │   └── interfaces/
│   │   │   │       ├── i-llm-provider.ts
│   │   │   │       ├── i-repository.ts
│   │   │   │       └── i-service.ts
│   │   │   │
│   │   │   ├── package.json
│   │   │   └── tsconfig.json
│   │   │
│   │   ├── errors/                               # Classes de erro padronizadas
│   │   │   ├── src/
│   │   │   │   ├── index.ts
│   │   │   │   ├── base.error.ts
│   │   │   │   ├── api/
│   │   │   │   │   ├── not-found.error.ts
│   │   │   │   │   ├── unauthorized.error.ts
│   │   │   │   │   └── validation.error.ts
│   │   │   │   ├── business/
│   │   │   │   │   ├── insufficient-credits.error.ts
│   │   │   │   │   └── task-failed.error.ts
│   │   │   │   └── infrastructure/
│   │   │   │       ├── database.error.ts
│   │   │   │       └── llm.error.ts
│   │   │   │
│   │   │   ├── package.json
│   │   │   └── tsconfig.json
│   │   │
│   │   ├── utils/                                # Utilitários genéricos
│   │   │   ├── src/
│   │   │   │   ├── index.ts
│   │   │   │   ├── formatters.ts
│   │   │   │   ├── validators.ts
│   │   │   │   ├── retry.ts
│   │   │   │   └── async.ts
│   │   │   │
│   │   │   ├── package.json
│   │   │   └── tsconfig.json
│   │   │
│   │   └── constants/                            # Constantes globais
│   │       ├── src/
│   │       │   ├── index.ts
│   │       │   ├── http-status.ts
│   │       │   └── error-codes.ts
│   │       │
│   │       ├── package.json
│   │       └── tsconfig.json
│   │
│   ├── infra/                                    # Infraestrutura como Código
│   │   │
│   │   └── provisioner/
│   │       ├── terraform/
│   │       │   ├── environments/
│   │       │   │   ├── dev/
│   │       │   │   │   ├── main.tf
│   │       │   │   │   ├── variables.tf
│   │       │   │   │   └── outputs.tf
│   │       │   │   ├── staging/
│   │       │   │   │   ├── main.tf
│   │       │   │   │   ├── variables.tf
│   │       │   │   │   └── outputs.tf
│   │       │   │   └── production/
│   │       │   │       ├── main.tf
│   │       │   │       ├── variables.tf
│   │       │   │       └── outputs.tf
│   │       │   └── modules/
│   │       │       ├── vpc/
│   │       │       │   ├── main.tf
│   │       │       │   ├── variables.tf
│   │       │       │   └── outputs.tf
│   │       │       ├── eks/
│   │       │       │   ├── main.tf
│   │       │       │   ├── variables.tf
│   │       │       │   └── outputs.tf
│   │       │       ├── rds/
│   │       │       │   ├── main.tf
│   │       │       │   ├── variables.tf
│   │       │       │   └── outputs.tf
│   │       │       └── redis/
│   │       │           ├── main.tf
│   │       │           ├── variables.tf
│   │       │           └── outputs.tf
│   │       │
│   │       ├── kubernetes/
│   │       │   ├── base/
│   │       │   │   ├── namespace.yaml
│   │       │   │   ├── configmap.yaml
│   │       │   │   └── secrets.yaml
│   │       │   ├── overlays/
│   │       │   │   ├── dev/
│   │       │   │   │   └── kustomization.yaml
│   │       │   │   ├── staging/
│   │       │   │   │   └── kustomization.yaml
│   │       │   │   └── production/
│   │       │   │       └── kustomization.yaml
│   │       │   └── deployments/
│   │       │       ├── backend-api/
│   │       │       │   ├── deployment.yaml
│   │       │       │   ├── service.yaml
│   │       │       │   └── ingress.yaml
│   │       │       ├── orchestrator/
│   │       │       │   ├── deployment.yaml
│   │       │       │   └── service.yaml
│   │       │       └── workers/
│   │       │           └── deployment.yaml
│   │       │
│   │       ├── docker/
│   │       │   └── docker-compose.dev.yml
│   │       │
│   │       ├── monitoring/
│   │       │   ├── prometheus/
│   │       │   │   └── prometheus.yml
│   │       │   ├── grafana/
│   │       │   │   └── provisioning/
│   │       │   │       └── dashboards/
│   │       │   └── loki/
│   │       │       └── loki.yml
│   │       │
│   │       └── scripts/
│   │           ├── setup-dev.sh
│   │           └── deploy.sh
│   │
│   └── tests/                                    # Testes globais
│       │
│       ├── e2e/                                  # Testes End-to-End (Playwright)
│       │   ├── specs/
│       │   │   ├── auth.spec.ts
│       │   │   ├── chat.spec.ts
│       │   │   └── task.spec.ts
│       │   ├── fixtures/
│       │   │   └── test-data.ts
│       │   ├── playwright.config.ts
│       │   ├── package.json
│       │   └── tsconfig.json
│       │
│       ├── integration/                          # Testes de integração
│       │   ├── api/
│       │   │   ├── auth.integration.test.ts
│       │   │   └── chat.integration.test.ts
│       │   ├── package.json
│       │   └── tsconfig.json
│       │
│       ├── contract/                             # Testes de contrato
│       │   ├── pacts/
│       │   ├── package.json
│       │   └── tsconfig.json
│       │
│       ├── load/                                 # Testes de carga
│       │   ├── scenarios/
│       │   │   └── chat-load.js
│       │   └── k6.config.js
│       │
│       ├── fixtures/                             # Dados de teste reutilizáveis
│       │   ├── users.fixture.ts
│       │   └── tasks.fixture.ts
│       │
│       └── mocks/                                # Mocks de serviços externos
│           ├── llm.mock.ts
│           └── stripe.mock.ts
│
├── docs/                                         # Documentação
│   ├── architecture/
│   │   ├── overview.md
│   │   └── diagrams/
│   │       ├── system-context.mmd
│   │       └── container.mmd
│   │
│   ├── adrs/                                     # Architecture Decision Records
│   │   ├── ADR-001-monorepo.md
│   │   ├── ADR-002-orchestrator.md
│   │   ├── ADR-003-agent-core.md
│   │   ├── ADR-004-context-engineering.md
│   │   ├── ADR-005-billing.md
│   │   └── ADR-006-observability.md
│   │
│   ├── api/
│   │   └── openapi.yaml
│   │
│   ├── guides/
│   │   ├── getting-started.md
│   │   ├── development.md
│   │   └── deployment.md
│   │
│   ├── runbooks/
│   │   ├── incident-response.md
│   │   └── scaling.md
│   │
│   └── onboarding/
│       └── new-developer.md
│
├── pnpm-workspace.yaml                           # Definição do monorepo
├── turbo.json                                    # Configuração do Turborepo
├── tsconfig.base.json                            # TypeScript base config
├── docker-compose.yml                            # Orquestração local
├── .env.example
├── .gitignore
├── .eslintrc.js
├── .prettierrc
└── README.md
```

---

**Fim da Árvore Detalhada**
