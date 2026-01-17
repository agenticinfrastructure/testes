# Arquitetura de Diretórios – vFinal (Produção)

## 1. Visão Geral da Arquitetura

### 1.1. Objetivo da Estrutura

Esta arquitetura foi projetada para suportar uma plataforma de IA de larga escala, com foco em:
- **Monorepo:** Gerenciamento centralizado de código com Turborepo e pnpm.
- **Escala:** Suporte a múltiplos times, serviços e domínios de negócio.
- **Multi-LLM:** Orquestração de múltiplos modelos de IA (Anthropic, Qwen, Nano Banana).
- **Agentes:** Lógica de agentes autônomos com planejamento, memória e verificação.
- **RAG:** Retrieval-Augmented Generation com File System as Context (FSaC).
- **Observabilidade:** Logging, métricas e tracing com OpenTelemetry.
- **Segurança:** Autenticação, autorização, compliance e safety para LLMs.

### 1.2. Princípios de Design

- **Fronteiras Claras:** Separação de responsabilidades entre `apps`, `core`, `features`, `services`, `platform` e `shared`.
- **Alta Coesão, Baixo Acoplamento:** Módulos são focados em uma única responsabilidade e se comunicam através de contratos bem definidos.
- **Ownership por Domínio:** Cada time é dono de um ou mais domínios de negócio.
- **Plataforma como Produto:** A camada `platform` é tratada como um produto interno para os times de produto.

## 2. Árvore de Diretórios Super Detalhada

*A árvore completa com mais de 800 linhas está no documento `ArquiteturaDiretoriosVFinal_ArvoreCompleta.md` gerado anteriormente.*

## 3. Descrição por Diretório

| Diretório | Responsabilidade | O que entra | Anti-patterns |
|---|---|---|---|
| `apps/` | Thin clients (Web, Mobile) | Componentes de UI, estado local | Lógica de negócio, acesso direto a DB |
| `packages/core/` | Lógica central e imutável | `agent-core` | Lógica de negócio específica |
| `packages/features/` | Domínios de negócio | `billing`, `affiliates` | Lógica de plataforma |
| `packages/services/` | Serviços de backend | `backend-api`, `orchestrator`, `workers` | Lógica de UI |
| `packages/platform/` | Capacidades de plataforma | `security`, `observability`, `data-governance` | Lógica de negócio |
| `packages/shared/` | Código compartilhado | `ui`, `config`, `schemas`, `types`, `database` | Lógica de negócio |

## 4. Convenções de Nomenclatura

- **Packages:** `@ai-platform/{package-name}` (ex: `@ai-platform/agent-core`)
- **Arquivos:** `kebab-case.ts` (ex: `billing.service.ts`)
- **Componentes:** `PascalCase.tsx` (ex: `ChatWindow.tsx`)
- **Adapters:** `*.adapter.ts` (ex: `anthropic.adapter.ts`)
- **Providers:** `*.provider.ts` (ex: `anthropic.provider.ts`)
- **Schemas:** `*.schema.ts` (ex: `auth.schema.ts`)
- **DTOs:** `*.dto.ts` (ex: `create-user.dto.ts`)

## 5. Organização de Testes

- **Unit:** `*.test.ts` dentro de cada package
- **Integration:** `packages/tests/integration/`
- **Contract:** `packages/tests/contract/`
- **E2E:** `packages/tests/e2e/` (Playwright)
- **Fixtures:** `packages/tests/fixtures/`
- **Golden Datasets:** `packages/platform/ai-evaluation/datasets/`

## 6. Infraestrutura, CI/CD e Observabilidade

- **IaC:** `packages/infra/provisioner/terraform/`
- **Kubernetes:** `packages/infra/provisioner/kubernetes/`
- **CI/CD:** `.github/workflows/`
- **Observabilidade:** `packages/platform/observability/` (OTel, Prometheus, Grafana, Loki)

## 7. Documentação e ADRs

- **Docs:** `docs/` com `architecture`, `guides`, `runbooks`
- **ADRs:** `docs/adrs/` com template e ADRs essenciais (monorepo, orchestrator, agent-core, etc.)

## 8. Extensibilidade e Evolução

- **Novos LLMs:** Adicionar novo provider em `services/orchestrator/providers/`
- **Novos Agentes:** Criar novo package em `core/` (ex: `research-agent-core`)
- **Novas Ferramentas:** Adicionar em `core/agent-core/execution/tools/`
- **Novos Domínios:** Criar novo package em `features/` (ex: `features/reporting/`)

## 9. Otimizações Detalhadas

### 9.1. 68 Critérios do Orquestrador

A implementação dos 68 critérios em `services/orchestrator/criteria/` será feita com classes individuais para cada critério, agrupadas por família. Exemplo:

```typescript
// packages/services/orchestrator/src/criteria/performance/latency.criterion.ts
import { Criterion } from '../base/criterion.interface';

export class LatencyCriterion implements Criterion {
  evaluate(context: any): number {
    // Lógica para calcular score de latência
    return 0.8;
  }
}
```

### 9.2. Integração dos Documentos 1-8

- **FSaC:** O `workspace.manager.ts` em `core/agent-core/workspace/` irá criar um diretório único por tarefa e fornecer métodos para o agente ler/escrever arquivos.
- **todo.md:** O `todo.manager.ts` em `core/agent-core/planning/` irá ler, escrever e atualizar o `todo.md` a cada passo do agente.
- **Compressão Restaurável:** O `compression.service.ts` em `core/agent-core/memory/` irá comprimir observações grandes (páginas web, documentos) em referências (URL, path) e o `restore.manager.ts` irá restaurá-las sob demanda.
- **Verificação Adaptativa:** O `adaptive.verifier.ts` em `core/agent-core/verification/` irá implementar a lógica do `adaptive_selective_verification.py`, usando o `relevance.analyzer.ts` para decidir o que restaurar e o `confidence.scorer.ts` para avaliar a confiança da resposta.

### 9.3. Configurações dos Providers

Cada provider em `services/orchestrator/providers/` terá um arquivo de configuração e um adapter:

- **Anthropic:** `anthropic.provider.ts`, `anthropic.adapter.ts`, `anthropic.types.ts`
- **Qwen:** `qwen.provider.ts`, `qwen.adapter.ts`, `qwen.types.ts`
- **Nano Banana:** `nano-banana.provider.ts`, `nano-banana.adapter.ts`, `nano-banana.types.ts`

O `anthropic.adapter.ts` irá traduzir as requisições do formato do orquestrador para o formato da API da Anthropic e vice-versa.
