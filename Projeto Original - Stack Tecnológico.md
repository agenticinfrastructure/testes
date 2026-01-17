# Stack Tecnológico Completo (vFinal)

Este documento detalha o stack tecnológico completo considerado ao projetar a arquitetura de diretórios vFinal. As escolhas foram feitas com base em performance, escalabilidade, ecossistema e alinhamento com as melhores práticas de mercado para plataformas de IA de larga escala, incluindo as práticas da Manus AI.

---

## 1. Monorepo & Tooling

| Tecnologia | Propósito | Justificativa |
|---|---|---|
| **pnpm** | Gerenciador de Pacotes | Eficiente no uso de disco (store compartilhado), rápido e com suporte nativo a workspaces. |
| **Turborepo** | Orquestrador de Monorepo | Build caching de alta performance, paralelização de tarefas e gerenciamento de dependências. |
| **TypeScript** | Linguagem Principal | Tipagem estática para todo o monorepo, garantindo segurança e manutenibilidade. |
| **ESLint** | Linter | Padronização de código e detecção de problemas. |
| **Prettier** | Formatador de Código | Formatação de código consistente em todo o repositório. |

---

## 2. Frontend (apps/)

| Camada | Tecnologia | Propósito | Justificativa |
|---|---|---|---|
| **Web** | **Next.js** | Framework React | SSR, App Router, otimizações de build e ecossistema robusto. |
| **Mobile** | **Expo / React Native** | Framework Mobile | Desenvolvimento multiplataforma (iOS/Android) com compartilhamento de lógica com a web. |
| **UI** | **React** | Biblioteca de UI | Padrão de mercado, ecossistema vasto e modelo de componentes. |
| **Estilização** | **Tailwind CSS** | Framework CSS | Utility-first para desenvolvimento rápido e consistente. |
| **Estado Global** | **Redux Toolkit** | Gerenciamento de Estado | Padrão previsível, devtools maduras e escalável para aplicações complexas. |
| **Estado de Servidor** | **React Query** | Cache de API | Gerenciamento de cache, retries e sincronização de dados com o backend. |

---

## 3. Backend & Services (packages/services/)

| Camada | Tecnologia | Propósito | Justificativa |
|---|---|---|---|
| **API Gateway** | **Fastify** | Framework Node.js | Alta performance e baixo overhead, ideal para um gateway que recebe alto tráfego. |
| **Comunicação** | **REST/HTTP** | Padrão de API | Padrão universal, bem compreendido e com vasto suporte de ferramentas. |
| **Fila de Mensagens** | **RabbitMQ** | Message Broker | Suporte a padrões complexos de roteamento, retries e dead-lettering para workers. |
| **Orquestrador de LLM** | **TypeScript/Node.js** | Lógica de Orquestração | Manter a consistência da linguagem no monorepo e facilitar o compartilhamento de tipos. |

---

## 4. Agent & Core AI (packages/core/)

| Camada | Tecnologia | Propósito | Justificativa |
|---|---|---|---|
| **Lógica do Agente** | **TypeScript/Node.js** | Implementação do Agente | Consistência da linguagem, compartilhamento de tipos com o backend e ecossistema NPM. |
| **Validação de Dados** | **Zod** | Schema Validation | Validação de dados de entrada e saída com inferência de tipos em TypeScript. |

---

## 5. Platform (packages/platform/)

| Camada | Tecnologia | Propósito | Justificativa |
|---|---|---|---|
| **Observabilidade** | **OpenTelemetry (OTel)** | Padrão de Telemetria | Padrão aberto e vendor-neutral para logs, métricas e traces. Alinhado com práticas da Manus AI. |
| **Segurança** | **JWT** | Autenticação | Padrão stateless para autenticação entre serviços e com o frontend. |

---

## 6. Shared Libraries (packages/shared/)

| Camada | Tecnologia | Propósito | Justificativa |
|---|---|---|---|
| **Banco de Dados** | **PostgreSQL** | Banco de Dados Relacional | Robusto, confiável e com suporte a tipos de dados complexos. |
| **ORM** | **Prisma** | Acesso a Dados | ORM com tipagem segura, excelente DX e ecossistema maduro. Decisão registrada em ADR-001. |
| **Cache** | **Redis** | Cache em Memória | Cache de alta performance para sessões, decisões do orquestrador e dados frequentes. |

---

## 7. Infraestrutura & DevOps

| Camada | Tecnologia | Propósito | Justificativa |
|---|---|---|---|
| **IaC** | **Terraform** | Infraestrutura como Código | Padrão de mercado para provisionamento de infraestrutura em múltiplos clouds. |
| **Orquestração de Contêineres** | **Kubernetes (EKS)** | Orquestração | Padrão de mercado para deploy e gerenciamento de contêineres em escala. |
| **CI/CD** | **GitHub Actions** | Automação de CI/CD | Integração nativa com o GitHub, fácil de configurar e com um grande marketplace de ações. |
| **Monitoramento** | **Prometheus, Grafana, Loki** | Stack de Monitoramento | Coleta de métricas, visualização em dashboards e agregação de logs. |

---

## 8. Testing

| Camada | Tecnologia | Propósito | Justificativa |
|---|---|---|---|
| **Test Runner** | **Vitest** | Framework de Testes | Rápido, compatível com a API do Jest e com boa integração com Vite/TypeScript. |
| **Testes E2E** | **Playwright** | Testes End-to-End | Robusto, rápido e com suporte a múltiplos browsers. Alinhado com práticas da Manus AI. |
| **Testes de Contrato** | **Pact** | Testes de Contrato | Garante que serviços se comunicam corretamente sem a necessidade de integração completa. |
| **Testes de Carga** | **k6** | Testes de Carga | Ferramenta moderna para testes de carga, com scripts em JavaScript/TypeScript. |
