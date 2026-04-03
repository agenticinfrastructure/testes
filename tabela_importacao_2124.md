# Tabela de Importação Completa — AI-Agent-Reference-main → Nexias

> **Repositório analisado:** AI-Agent-Reference-main (Claude Code CLI/Desktop)
> **Destino:** Nexias (TypeScript · Next.js · Fastify · Prisma · Cloud Run · Redis)
> **Total de arquivos no repositório:** 2.124
> **Arquivos classificados na tabela:** 2099
> **✅ Importar:** 741 | **⚠️ Importar parcialmente:** 408 | **❌ Não importar:** 881

**Legenda:**
- **✅** = Importar com adaptação mínima — lógica de negócio diretamente aproveitável
- **⚠️** = Importar parcialmente — conceito valioso, requer reescrita significativa
- **❌** = Não importar — específico de CLI/terminal/desktop/Bun

---

| Arquivo | Status | Destino no Nexias | Justificativa |
|:---|:---:|:---|:---|
| README.md | ❌     |         | Documento de texto, não código     |
| .gitignore | ❌ |  | Arquivo de configuração de git, não código fonte |
| bunfig.toml | ❌ |  | Configuração específica do Bun, não aplicável ao Nexias |
| config-ui/index.html | ❌     |                          | Arquivo HTML estático, UI web específica |
| config-ui/server.ts  | ⚠️     | packages/backend/src/config-ui/server.ts | Lógica servidor web leve, precisa adaptação |
| package.json | ❌     |         | Configuração de build e deps  |
| scripts/postinstall.sh | ❌     |         | Script shell específico de build  |
| tsconfig.json | ❌ |  | Configuração específica do projeto, não código reutilizável |
| src/QueryEngine.ts | ⚠️     | packages/core/agent-core/src/queryEngine.ts | Lógica de negócio valiosa, depende de Bun e APIs específicas |
| src/Task.ts   | ✅      | packages/core/agent-core/src/Task.ts | Tipos e lógica de estado de tarefas reutilizáveis |
| src/Tool.ts  | ✅      | packages/core/agent-core/src/Tool.ts | Lógica de negócio de ferramentas reutilizável |
| src/attributionTrailer.ts | ❌ |  | Arquivo vazio, sem lógica útil |
| src/bootstrap/state.ts | ⚠️ | packages/core/agent-core/src/bootstrap/state.ts | Contém lógica de estado e hooks, requer adaptação para Nexias |
| src/cachedMicrocompact.ts | ❌ |  | Arquivo vazio, sem lógica útil para importação |
| src/commands.ts | ❌ |  | Importa muitos comandos CLI específicos, não útil para web serverless |
| src/context.ts | ⚠️ | packages/core/agent-core/src/context.ts | Contém lógica de contexto com deps específicas, requer adaptação |
| src/cost-tracker.ts | ✅ | packages/core/agent-core/src/utils/cost-tracker.ts | Lógica de negócio para rastreamento de custos, sem deps de CLI/UI |
| src/costHook.ts   | ❌     |                          | Usa React hook e process.stdout (CLI) |
| src/coreTypes.generated.ts | ❌ |  | Arquivo vazio, sem lógica ou tipos úteis |
| src/devtools.ts | ❌ |  | Arquivo vazio, sem lógica relevante |
| src/dialogLaunchers.tsx | ❌     |                   | Componentes React/Ink para terminal |
| src/dream.ts  | ❌     |                                | Arquivo vazio, sem lógica   |
| src/entry.ts  | ❌      |                   | Específico de Bun, plugin runtime CLI |
| src/global.d.ts | ❌ |  | Apenas declaração global vazia, sem lógica útil |
| src/history.ts | ⚠️ | packages/core/agent-core/src/history.ts | Lógica de histórico útil, mas depende de fs e ambiente Node específico |
| src/hunter.ts | ❌      |                          | Arquivo vazio, sem lógica    |
| src/ink.ts    | ❌     |                                | Usa React Ink para UI de terminal    |
| src/interactiveHelpers.tsx | ❌ |  | Importa React e Ink, UI terminal específica |
| src/jobs/classifier.ts | ❌ |  | Stub vazio, sem lógica implementada |
| src/main.tsx  | ❌      |                       | Código de bootstrap específico de Bun/desktop |
| src/moreright/useMoreRight.tsx | ❌ |  | Stub sem lógica real, apenas placeholder para builds externos |
| src/outputStyles/loadOutputStylesDir.ts | ⚠️ | packages/core/agent-core/src/outputStyles/loadOutputStylesDir.ts | Lógica de carregamento de estilos, depende de fs e path, precisa adaptação |
| src/projectOnboardingState.ts | ⚠️ | packages/core/agent-core/src/projectOnboardingState.ts | Lógica onboarding útil, mas depende de fs e config específicos |
| src/protectedNamespace.ts | ❌ |  | Arquivo vazio, sem lógica relevante |
| src/query.ts  | ⚠️     | packages/core/agent-core/src/query.ts | Lógica de negócio valiosa, mas depende de features específicas e imports dinâmicos |
| src/replLauncher.tsx | ❌     |                   | Componente React/Ink para terminal |
| src/runSkillGenerator.ts | ❌ |  | Arquivo vazio, sem lógica útil |
| src/schemas/hooks.ts | ✅      | packages/core/agent-core/src/schemas/hooks.ts | Schemas Zod para hooks, útil para validação dados |
| src/setup.ts  | ⚠️     | packages/backend/src/setup.ts            | Inicialização e configuração, adaptações necessárias |
| src/ssh/createSSHSession.ts | ❌ |  | Stub sem lógica real |
| src/tasks.ts  | ⚠️      | packages/core/agent-core/src/tasks.ts | Lógica de tarefas, mas depende de Bun e require dinâmico |
| src/tools.ts  | ⚠️     | packages/core/agent-core/src/tools.ts | Importa várias ferramentas, adaptação necessária para Nexias |
| src/voice/voiceModeEnabled.ts | ⚠️ | packages/core/agent-core/src/utils/voiceModeEnabled.ts | Lógica de feature flag útil, mas depende de Bun e GrowthBook específicos |
| src/query/config.ts | ✅      | packages/core/agent-core/src/query/config.ts | Configuração imutável para query, lógica útil |
| src/query/deps.ts   | ✅      | packages/core/agent-core/src/query/deps.ts   | Injeção de dependências para query, lógica reutilizável |
| src/query/stopHooks.ts | ⚠️    | packages/core/agent-core/src/query/stopHooks.ts | Hooks de parada com deps específicas, requer adaptação |
| src/query/tokenBudget.ts | ✅  | packages/core/agent-core/src/query/tokenBudget.ts | Controle de orçamento de tokens, lógica aproveitável |
| src/services/AgentSummary/agentSummary.ts | ✅ | packages/core/agent-core/src/services/AgentSummary/agentSummary.ts | Lógica de resumo de agente reutilizável no backend Nexias |
| src/services/MagicDocs/magicDocs.ts | ✅ | packages/core/agent-core/src/services/MagicDocs/magicDocs.ts | Atualização automática de docs, lógica de negócio útil |
| src/services/MagicDocs/prompts.ts | ⚠️ | packages/core/agent-core/src/services/MagicDocs/prompts.ts | Prompt template útil, mas depende de fs e path (revisar) |
| src/services/PromptSuggestion/promptSuggestion.ts | ✅ | packages/core/agent-core/src/services/PromptSuggestion/promptSuggestion.ts | Lógica de sugestão de prompt aproveitável no Nexias |
| src/services/PromptSuggestion/speculation.ts | ⚠️ | packages/core/agent-core/src/services/PromptSuggestion/speculation.ts | Usa fs, crypto, lógica complexa, requer adaptação |
| src/services/SessionMemory/prompts.ts | ⚠️ | packages/core/agent-core/src/services/SessionMemory/prompts.ts | Templates úteis, mas dependem de fs e path (revisar) |
| src/services/SessionMemory/sessionMemory.ts | ✅ | packages/core/agent-core/src/services/SessionMemory/sessionMemory.ts | Lógica de memória de sessão reaproveitável no backend |
| src/services/SessionMemory/sessionMemoryUtils.ts | ✅ | packages/core/agent-core/src/services/SessionMemory/sessionMemoryUtils.ts | Utilitários de memória de sessão sem dependências UI |
| src/services/analytics/config.ts | ✅ | packages/core/analytics/src/config.ts | Configuração compartilhada de analytics reutilizável |
| src/services/analytics/datadog.ts | ✅ | packages/core/analytics/src/datadog.ts | Integração Datadog útil para Nexias backend |
| src/services/analytics/firstPartyEventLogger.ts | ✅ | packages/core/analytics/src/firstPartyEventLogger.ts | Logger de eventos 1P aproveitável no Nexias |
| src/services/analytics/firstPartyEventLoggingExporter.ts | ⚠️ | packages/core/analytics/src/firstPartyEventLoggingExporter.ts | Usa fs/promises, axios, precisa adaptação para Cloud Run |
| src/services/analytics/growthbook.ts | ✅ | packages/core/analytics/src/growthbook.ts | Integração Growthbook reutilizável no Nexias |
| src/services/analytics/index.ts | ✅ | packages/core/analytics/src/index.ts | API pública de analytics sem dependências UI |
| src/services/analytics/metadata.ts | ✅ | packages/core/analytics/src/metadata.ts | Metadados para analytics, lógica útil |
| src/services/analytics/sink.ts | ✅ | packages/core/analytics/src/sink.ts | Sink para roteamento de eventos, lógica reaproveitável |
| src/services/analytics/sinkKillswitch.ts | ✅ | packages/core/analytics/src/sinkKillswitch.ts | Controle de desligamento de analytics útil |
| src/services/api/adminRequests.ts | ✅ | packages/core/api/src/adminRequests.ts | Lógica API admin reutilizável no Nexias |
| src/services/api/bootstrap.ts | ✅ | packages/core/api/src/bootstrap.ts | Inicialização API, lógica backend útil |
| src/services/api/claude.ts | ✅ | packages/core/api/src/claude.ts | API específica Claude, lógica backend reaproveitável |
| src/services/api/client.ts | ✅ | packages/core/agent-core/src/services/api/client.ts | Cliente API com lógica reutilizável para Nexias |
| src/services/api/dumpPrompts.ts | ⚠️ | packages/core/agent-core/src/services/api/dumpPrompts.ts | Usa fs e path, precisa adaptação para serverless |
| src/services/api/emptyUsage.ts | ✅ | packages/core/agent-core/src/services/api/emptyUsage.ts | Constantes de uso sem dependências específicas |
| src/services/api/errorUtils.ts | ✅ | packages/core/agent-core/src/services/api/errorUtils.ts | Utilitários de erro genéricos reaproveitáveis |
| src/services/api/errors.ts | ✅ | packages/core/agent-core/src/services/api/errors.ts | Lógica de erros e tipos úteis para Nexias |
| src/services/api/filesApi.ts | ⚠️ | packages/core/agent-core/src/services/api/filesApi.ts | Usa fs, path, axios; precisa adaptação serverless |
| src/services/api/firstTokenDate.ts | ✅ | packages/core/agent-core/src/services/api/firstTokenDate.ts | Lógica fetch e config reutilizável no Nexias |
| src/services/api/grove.ts | ✅ | packages/core/agent-core/src/services/api/grove.ts | Lógica de analytics e auth útil para Nexias |
| src/services/api/logging.ts | ⚠️ | packages/core/agent-core/src/services/api/logging.ts | Usa bun:bundle e estado global, adaptação necessária |
| src/services/api/metricsOptOut.ts | ✅ | packages/core/agent-core/src/services/api/metricsOptOut.ts | Lógica de métricas e config reutilizável |
| src/services/api/overageCreditGrant.ts | ✅ | packages/core/agent-core/src/services/api/overageCreditGrant.ts | Lógica de crédito e API útil para Nexias |
| src/services/api/promptCacheBreakDetection.ts | ⚠️ | packages/core/agent-core/src/services/api/promptCacheBreakDetection.ts | Usa fs, path, diff; precisa adaptação serverless |
| src/services/api/referral.ts | ✅ | packages/core/agent-core/src/services/api/referral.ts | Lógica de referral e API reutilizável |
| src/services/api/sessionIngress.ts | ✅ | packages/core/agent-core/src/services/api/sessionIngress.ts | Lógica de sessão e API útil para Nexias |
| src/services/api/ultrareviewQuota.ts | ✅ | packages/core/agent-core/src/services/api/ultrareviewQuota.ts | Lógica de quota e API reutilizável |
| src/services/api/usage.ts | ✅ | packages/core/agent-core/src/services/api/usage.ts | Lógica de uso e autenticação útil para Nexias |
| src/services/api/withRetry.ts | ✅ | packages/core/agent-core/src/services/api/withRetry.ts | Middleware retry genérico reaproveitável |
| src/services/autoDream/autoDream.ts | ⚠️ | packages/core/agent-core/src/services/autoDream/autoDream.ts | Lógica de negócio, mas precisa adaptação |
| src/services/autoDream/config.ts | ✅ | packages/core/agent-core/src/services/autoDream/config.ts | Configuração reutilizável para Nexias |
| src/services/autoDream/consolidationLock.ts | ⚠️ | packages/core/agent-core/src/services/autoDream/consolidationLock.ts | Locking logic, precisa adaptação para Nexias |
| src/services/autoDream/consolidationPrompt.ts | ✅ | packages/core/agent-core/src/services/autoDream/consolidationPrompt.ts | Lógica de prompt reutilizável, sem deps CLI |
| src/services/awaySummary.ts | ✅ | packages/core/agent-core/src/services/awaySummary.ts | Lógica de resumo de sessão, útil para Nexias |
| src/services/claudeAiLimits.ts | ✅ | packages/core/agent-core/src/services/claudeAiLimits.ts | Controle de limites API, lógica de negócio |
| src/services/claudeAiLimitsHook.ts | ❌ |  | Hook React, dependente de UI React |
| src/services/compact/apiMicrocompact.ts | ✅ | packages/core/agent-core/src/services/compact/apiMicrocompact.ts | Configurações e constantes para compactação |
| src/services/compact/autoCompact.ts | ⚠️ | packages/core/agent-core/src/services/compact/autoCompact.ts | Usa Bun feature, precisa adaptação |
| src/services/compact/cachedMCConfig.ts | ❌ |  | Stub vazio, sem lógica |
| src/services/compact/cachedMicrocompact.ts | ❌ |  | Stub vazio, sem lógica |
| src/services/compact/compact.ts | ⚠️ | packages/core/agent-core/src/services/compact/compact.ts | Usa Bun feature, import condicional, adaptação |
| src/services/compact/compactWarningHook.ts | ❌ |  | Hook React, dependente de UI React |
| src/services/compact/compactWarningState.ts | ✅ | packages/core/agent-core/src/services/compact/compactWarningState.ts | Estado puro, sem UI, útil para Nexias |
| src/services/compact/grouping.ts | ✅ | packages/core/agent-core/src/services/compact/grouping.ts | Lógica de agrupamento de mensagens |
| src/services/compact/microCompact.ts | ⚠️ | packages/core/agent-core/src/services/compact/microCompact.ts | Usa Bun feature, adaptação necessária |
| src/services/compact/postCompactCleanup.ts | ⚠️ | packages/core/agent-core/src/services/compact/postCompactCleanup.ts | Usa Bun feature, limpeza lógica útil |
| src/services/compact/prompt.ts | ⚠️ | packages/core/agent-core/src/services/compact/prompt.ts | Usa Bun feature, import condicional, adaptação |
| src/services/contextCollapse/index.ts | ❌ |  | Exporta objeto vazio, sem lógica útil |
| src/services/contextCollapse/operations.ts | ❌ |  | Exporta vazio, sem lógica implementada |
| src/services/contextCollapse/persist.ts | ❌ |  | Exporta objeto vazio, sem lógica útil |
| src/services/diagnosticTracking.ts | ✅ | packages/core/agent-core/src/services/diagnosticTracking.ts | Lógica de tracking de diagnósticos reutilizável |
| src/services/extractMemories/extractMemories.ts | ⚠️ | packages/core/agent-core/src/services/extractMemories/extractMemories.ts | Lógica de memória com dependências Bun e FS |
| src/services/extractMemories/prompts.ts | ⚠️ | packages/core/agent-core/src/services/extractMemories/prompts.ts | Templates de prompt úteis, mas dependem de Bun |
| src/services/internalLogging.ts | ✅ | packages/core/agent-core/src/services/internalLogging.ts | Logging e memoize úteis para Nexias |
| src/services/lsp/LSPClient.ts | ✅ | packages/core/agent-core/src/services/lsp/LSPClient.ts | Cliente LSP com lógica reutilizável |
| src/services/lsp/LSPDiagnosticRegistry.ts | ✅ | packages/core/agent-core/src/services/lsp/LSPDiagnosticRegistry.ts | Registro de diagnósticos LSP útil |
| src/services/lsp/LSPServerInstance.ts | ✅ | packages/core/agent-core/src/services/lsp/LSPServerInstance.ts | Gerenciamento de instância LSP reutilizável |
| src/services/lsp/LSPServerManager.ts | ✅ | packages/core/agent-core/src/services/lsp/LSPServerManager.ts | Gerenciamento de múltiplos servidores LSP |
| src/services/lsp/config.ts | ✅ | packages/core/agent-core/src/services/lsp/config.ts | Configuração LSP via plugins útil |
| src/services/lsp/manager.ts | ✅ | packages/core/agent-core/src/services/lsp/manager.ts | Gerenciamento global do LSP reutilizável |
| src/services/lsp/passiveFeedback.ts | ✅ | packages/core/agent-core/src/services/lsp/passiveFeedback.ts | Feedback passivo LSP útil para Nexias |
| src/services/mcp/InProcessTransport.ts | ✅ | packages/core/agent-core/src/services/mcp/InProcessTransport.ts | Transporte MCP in-process reutilizável |
| src/services/mcp/MCPConnectionManager.tsx | ❌ |  | Componente React/Ink para terminal, UI CLI |
| src/services/mcp/SdkControlTransport.ts | ⚠️ | packages/core/agent-core/src/services/mcp/SdkControlTransport.ts | Transporte bridge MCP, precisa adaptação |
| src/services/mcp/auth.ts | ✅ | packages/core/agent-core/src/services/mcp/auth.ts | Autenticação MCP com lógica útil |
| src/services/mcp/channelAllowlist.ts | ✅ | packages/core/agent-core/src/services/mcp/channelAllowlist.ts | Controle de canais MCP reutilizável |
| src/services/mcp/channelNotification.ts | ✅ | packages/core/agent-core/src/services/mcp/channelNotification.ts | Notificações MCP com lógica útil |
| src/services/mcp/channelPermissions.ts | ✅ | packages/core/agent-core/src/services/mcp/channelPermissions.ts | Lógica de permissão para canais, útil para backend |
| src/services/mcp/claudeai.ts | ✅ | packages/core/agent-core/src/services/mcp/claudeai.ts | Cliente e lógica de autenticação MCP reutilizável |
| src/services/mcp/client.ts | ⚠️ | packages/core/agent-core/src/services/mcp/client.ts | Usa Bun e SDK MCP, requer adaptação para web |
| src/services/mcp/config.ts | ⚠️ | packages/core/agent-core/src/services/mcp/config.ts | Manipulação de arquivos e config, precisa reescrita |
| src/services/mcp/elicitationHandler.ts | ✅ | packages/core/agent-core/src/services/mcp/elicitationHandler.ts | Lógica de elicitação e hooks, aproveitável |
| src/services/mcp/envExpansion.ts | ✅ | packages/core/agent-core/src/utils/envExpansion.ts | Utilitário puro para expansão de variáveis ambiente |
| src/services/mcp/headersHelper.ts | ✅ | packages/core/agent-core/src/services/mcp/headersHelper.ts | Helpers para headers e segurança MCP, backend útil |
| src/services/mcp/mcpStringUtils.ts | ✅ | packages/core/agent-core/src/utils/mcpStringUtils.ts | Utilitários puros para parsing de strings MCP |
| src/services/mcp/normalization.ts | ✅ | packages/core/agent-core/src/utils/normalization.ts | Normalização de nomes MCP, lógica pura |
| src/services/mcp/oauthPort.ts | ✅ | packages/core/agent-core/src/services/mcp/oauthPort.ts | Helpers para portas OAuth, sem dependências UI |
| src/services/mcp/officialRegistry.ts | ✅ | packages/core/agent-core/src/services/mcp/officialRegistry.ts | Registro oficial MCP, lógica de rede reutilizável |
| src/services/mcp/types.ts | ✅ | packages/core/agent-core/src/services/mcp/types.ts | Tipos e schemas MCP, essenciais para integração |
| src/services/mcp/useManageMCPConnections.ts | ❌ |  | Usa React hooks e Bun, específico para UI/cliente |
| src/services/mcp/utils.ts | ✅ | packages/core/agent-core/src/services/mcp/utils.ts | Utilitários MCP diversos, lógica de negócio |
| src/services/mcp/vscodeSdkMcp.ts | ⚠️ | packages/core/agent-core/src/services/mcp/vscodeSdkMcp.ts | Integração VSCode, precisa adaptação para Nexias |
| src/services/mcp/xaa.ts | ⚠️ | packages/core/agent-core/src/services/mcp/xaa.ts | Possível lógica útil, mas depende de Bun/SDK |
| src/services/mcp/xaaIdpLogin.ts | ❌ |  | Login nativo e UI, específico para desktop/CLI |
| src/services/mcpServerApproval.tsx | ❌ |  | Componente React/Ink para terminal, UI terminal |
| src/services/mockRateLimits.ts | ✅ | packages/core/agent-core/src/services/mockRateLimits.ts | Mock para rate limits, útil para testes backend |
| src/services/notifier.ts | ✅ | packages/core/agent-core/src/services/notifier.ts | Serviço de notificações, lógica backend aproveitável |
| src/services/oauth/auth-code-listener.ts | ❌ |  | Específico de servidor HTTP local para OAuth CLI |
| src/services/oauth/client.ts | ✅ | packages/core/agent-core/src/services/oauth/client.ts | Lógica de cliente OAuth reutilizável para Nexias |
| src/services/oauth/crypto.ts | ✅ | packages/core/agent-core/src/services/oauth/crypto.ts | Geração de código PKCE sem dependências CLI |
| src/services/oauth/getOauthProfile.ts | ✅ | packages/core/agent-core/src/services/oauth/getOauthProfile.ts | Consulta perfil OAuth via API, lógica útil |
| src/services/oauth/index.ts | ✅ | packages/core/agent-core/src/services/oauth/index.ts | Exporta lógica OAuth, integra serviços reutilizáveis |
| src/services/plugins/PluginInstallationManager.ts | ⚠️ | packages/core/agent-core/src/services/plugins/PluginInstallationManager.ts | Conceito útil, precisa adaptação para Nexias |
| src/services/plugins/pluginCliCommands.ts | ❌ |  | CLI específico, saída console e processo exit |
| src/services/plugins/pluginOperations.ts | ✅ | packages/core/agent-core/src/services/plugins/pluginOperations.ts | Lógica core de plugins, sem efeitos CLI |
| src/services/policyLimits/index.ts | ⚠️ | packages/core/agent-core/src/services/policyLimits/index.ts | Lógica de limites útil, adaptações para Nexias |
| src/services/policyLimits/types.ts | ✅ | packages/core/agent-core/src/services/policyLimits/types.ts | Tipos e schemas reutilizáveis |
| src/services/preventSleep.ts | ❌ |  | Específico macOS, spawn child process CLI |
| src/services/rateLimitMessages.ts | ✅ | packages/core/agent-core/src/services/rateLimitMessages.ts | Mensagens centralizadas, lógica reutilizável |
| src/services/rateLimitMocking.ts | ✅ | packages/core/agent-core/src/services/rateLimitMocking.ts | Lógica mock rate limit útil para Nexias |
| src/services/remoteManagedSettings/index.ts | ⚠️ | packages/core/agent-core/src/services/remoteManagedSettings/index.ts | Lógica fetch/cache útil, precisa adaptação |
| src/services/remoteManagedSettings/securityCheck.tsx | ❌ |  | React/Ink UI para terminal, não web serverless |
| src/services/remoteManagedSettings/syncCache.ts | ⚠️ | packages/core/agent-core/src/services/remoteManagedSettings/syncCache.ts | Lógica cache útil, reescrita para Nexias |
| src/services/remoteManagedSettings/syncCacheState.ts | ⚠️ | packages/core/agent-core/src/services/remoteManagedSettings/syncCacheState.ts | Estado cache, adaptação necessária |
| src/services/remoteManagedSettings/types.ts | ✅ | packages/core/agent-core/src/services/remoteManagedSettings/types.ts | Tipos reutilizáveis para Nexias |
| src/services/sessionTranscript/sessionTranscript.ts | ⚠️ | packages/core/agent-core/src/services/sessionTranscript/sessionTranscript.ts | Lógica transcript útil, adaptação necessária |
| src/services/settingsSync/index.ts | ⚠️ | packages/core/agent-core/src/services/settingsSync/index.ts | Sincronização configurações, reescrita parcial |
| src/services/settingsSync/types.ts | ✅ | packages/core/agent-core/src/services/settingsSync/types.ts | Tipos e schemas Zod para API, útil para Nexias |
| src/services/skillSearch/featureCheck.ts | ❌ |  | Stub vazio, sem lógica |
| src/services/skillSearch/localSearch.ts | ❌ |  | Stub vazio, sem lógica |
| src/services/skillSearch/prefetch.ts | ❌ |  | Stub vazio, sem lógica |
| src/services/skillSearch/remoteSkillLoader.ts | ❌ |  | Stub vazio, sem lógica |
| src/services/skillSearch/remoteSkillState.ts | ❌ |  | Stub vazio, sem lógica |
| src/services/skillSearch/telemetry.ts | ❌ |  | Stub vazio, sem lógica |
| src/services/teamMemorySync/index.ts | ⚠️ | packages/core/agent-core/src/services/teamMemorySync/index.ts | Sync team memory, precisa adaptação para Nexias |
| src/services/teamMemorySync/secretScanner.ts | ⚠️ | packages/core/agent-core/src/services/teamMemorySync/secretScanner.ts | Scanner de segredos, lógica valiosa mas específica |
| src/services/teamMemorySync/teamMemSecretGuard.ts | ❌ |  | Usa bun:bundle, feature flag específica Bun |
| src/services/teamMemorySync/types.ts | ✅ | packages/core/agent-core/src/services/teamMemorySync/types.ts | Tipos e schemas Zod para team memory sync |
| src/services/teamMemorySync/watcher.ts | ❌ |  | Usa fs.watch, Bun feature, não serverless |
| src/services/tips/tipHistory.ts | ✅ | packages/core/agent-core/src/services/tips/tipHistory.ts | Histórico de dicas, lógica reutilizável |
| src/services/tips/tipRegistry.ts | ⚠️ | packages/core/agent-core/src/services/tips/tipRegistry.ts | Registro de dicas, depende de UI e config |
| src/services/tips/tipScheduler.ts | ✅ | packages/core/agent-core/src/services/tips/tipScheduler.ts | Lógica de seleção de dicas, útil para Nexias |
| src/services/tokenEstimation.ts | ⚠️ | packages/core/agent-core/src/services/tokenEstimation.ts | Estimativa tokens, depende de SDKs externos |
| src/services/toolUseSummary/toolUseSummaryGenerator.ts | ✅ | packages/core/agent-core/src/services/toolUseSummary/toolUseSummaryGenerator.ts | Geração de resumo de uso de ferramentas |
| src/services/tools/StreamingToolExecutor.ts | ⚠️ | packages/core/agent-core/src/services/tools/StreamingToolExecutor.ts | Executor de ferramentas, depende de contexto |
| src/services/tools/toolExecution.ts | ⚠️ | packages/core/agent-core/src/services/tools/toolExecution.ts | Execução de ferramentas, lógica complexa |
| src/services/tools/toolHooks.ts | ⚠️ | packages/core/agent-core/src/services/tools/toolHooks.ts | Hooks para ferramentas, depende de hooks Nexias |
| src/services/tools/toolOrchestration.ts | ✅     | packages/core/agent-core/src/services/toolOrchestration.ts | Lógica de orquestração de ferramentas reutilizável |
| src/services/vcr.ts              | ⚠️     | packages/core/agent-core/src/services/vcr.ts | Uso de fs e crypto, parte pode ser adaptada para serverless |
| src/services/voice.ts            | ❌     |                                          | Dependente de áudio nativo e processos locais      |
| src/services/voiceKeyterms.ts   | ✅     | packages/core/agent-core/src/services/voiceKeyterms.ts | Vocabulário para STT, lógica simples e reutilizável |
| src/services/voiceStreamSTT.ts  | ⚠️     | packages/core/agent-core/src/services/voiceStreamSTT.ts | Cliente WebSocket para STT, precisa adaptação para Nexias |
| src/tools/AgentTool/AgentTool.tsx | ❌ |  | React + Bun + CLI específico |
| src/tools/AgentTool/UI.tsx | ❌ |  | UI terminal React/Ink |
| src/tools/AgentTool/agentColorManager.ts | ✅ | packages/core/agent-core/src/tools/AgentTool/agentColorManager.ts | Utilitário de cores, sem deps CLI |
| src/tools/AgentTool/agentDisplay.ts | ✅ | packages/core/agent-core/src/tools/AgentTool/agentDisplay.ts | Lógica display agente reutilizável |
| src/tools/AgentTool/agentMemory.ts | ⚠️ | packages/core/agent-core/src/tools/AgentTool/agentMemory.ts | Usa fs/path, adaptação para Cloud Run |
| src/tools/AgentTool/agentMemorySnapshot.ts | ⚠️ | packages/core/agent-core/src/tools/AgentTool/agentMemorySnapshot.ts | FS async, precisa reescrita para serverless |
| src/tools/AgentTool/agentToolUtils.ts | ✅ | packages/core/agent-core/src/tools/AgentTool/agentToolUtils.ts | Lógica negócio ferramentas agente |
| src/tools/AgentTool/built-in/claudeCodeGuideAgent.ts | ✅ | packages/core/agent-core/src/tools/AgentTool/built-in/claudeCodeGuideAgent.ts | Definição agente built-in, lógica útil |
| src/tools/AgentTool/built-in/exploreAgent.ts | ✅ | packages/core/agent-core/src/tools/AgentTool/built-in/exploreAgent.ts | Definição agente built-in, lógica útil |
| src/tools/AgentTool/built-in/generalPurposeAgent.ts | ✅ | packages/core/agent-core/src/tools/AgentTool/built-in/generalPurposeAgent.ts | Definição agente built-in, lógica útil |
| src/tools/AgentTool/built-in/planAgent.ts | ✅ | packages/core/agent-core/src/tools/AgentTool/built-in/planAgent.ts | Definição agente built-in, lógica útil |
| src/tools/AgentTool/built-in/statuslineSetup.ts | ✅ | packages/core/agent-core/src/tools/AgentTool/built-in/statuslineSetup.ts | Definição agente built-in, lógica útil |
| src/tools/AgentTool/built-in/verificationAgent.ts | ✅ | packages/core/agent-core/src/tools/AgentTool/built-in/verificationAgent.ts | Definição agente built-in, lógica útil |
| src/tools/AgentTool/builtInAgents.ts | ✅ | packages/core/agent-core/src/tools/AgentTool/builtInAgents.ts | Registro agentes built-in, lógica útil |
| src/tools/AgentTool/constants.ts | ✅ | packages/core/agent-core/src/tools/AgentTool/constants.ts | Constantes reutilizáveis |
| src/tools/AgentTool/forkSubagent.ts | ⚠️ | packages/core/agent-core/src/tools/AgentTool/forkSubagent.ts | Possível lógica CLI/terminal, revisar |
| src/tools/AgentTool/loadAgentsDir.ts | ⚠️ | packages/core/agent-core/src/tools/AgentTool/loadAgentsDir.ts | Usa fs/path, adaptação para serverless |
| src/tools/AgentTool/prompt.ts | ✅ | packages/core/agent-core/src/tools/AgentTool/prompt.ts | Utilitários prompt, lógica negócio |
| src/tools/AgentTool/resumeAgent.ts | ⚠️ | packages/core/agent-core/src/tools/AgentTool/resumeAgent.ts | Pode conter lógica estado, revisar |
| src/tools/AgentTool/runAgent.ts | ⚠️ | packages/core/agent-core/src/tools/AgentTool/runAgent.ts | Provável lógica execução agente, revisar |
| src/tools/AskUserQuestionTool/AskUserQuestionTool.tsx | ❌ |  | UI terminal React/Ink, imports Box, Text do Ink |
| src/tools/AskUserQuestionTool/prompt.ts | ✅ | packages/core/agent-core/src/tools/AskUserQuestionTool/prompt.ts | Constantes e strings para ferramenta, sem UI |
| src/tools/BashTool/BashTool.tsx | ⚠️ | packages/core/agent-core/src/tools/BashTool/BashTool.ts | Lógica bash útil, mas depende de Bun e React |
| src/tools/BashTool/BashToolResultMessage.tsx | ❌ |  | Componente React/Ink para terminal |
| src/tools/BashTool/UI.tsx | ❌ |  | UI terminal React/Ink com keybindings |
| src/tools/BashTool/bashCommandHelpers.ts | ✅ | packages/core/agent-core/src/tools/BashTool/bashCommandHelpers.ts | Helpers bash sem UI, lógica reutilizável |
| src/tools/BashTool/bashPermissions.ts | ⚠️ | packages/core/agent-core/src/tools/BashTool/bashPermissions.ts | Lógica permissões bash, depende de Bun e analytics |
| src/tools/BashTool/bashSecurity.ts | ✅ | packages/core/agent-core/src/tools/BashTool/bashSecurity.ts | Segurança bash, lógica pura sem UI |
| src/tools/BashTool/commandSemantics.ts | ✅ | packages/core/agent-core/src/tools/BashTool/commandSemantics.ts | Semântica comandos bash, lógica reutilizável |
| src/tools/BashTool/commentLabel.ts | ✅ | packages/core/agent-core/src/tools/BashTool/commentLabel.ts | Função utilitária para extrair comentário bash |
| src/tools/BashTool/destructiveCommandWarning.ts | ✅ | packages/core/agent-core/src/tools/BashTool/destructiveCommandWarning.ts | Detecta comandos destrutivos, lógica pura |
| src/tools/BashTool/modeValidation.ts | ⚠️ | packages/core/agent-core/src/tools/BashTool/modeValidation.ts | Validação comandos bash, depende de tipos e contexto |
| src/tools/BashTool/pathValidation.ts | ✅ | packages/core/agent-core/src/tools/BashTool/pathValidation.ts | Validação de paths, lógica pura Node.js |
| src/tools/BashTool/prompt.ts | ✅ | packages/core/agent-core/src/tools/BashTool/prompt.ts | Constantes e strings para ferramenta bash |
| src/tools/BashTool/readOnlyValidation.ts | ✅ | packages/core/agent-core/src/tools/BashTool/readOnlyValidation.ts | Validação read-only, lógica reutilizável |
| src/tools/BashTool/sedEditParser.ts | ✅ | packages/core/agent-core/src/tools/BashTool/sedEditParser.ts | Parser para sed, lógica pura |
| src/tools/BashTool/sedValidation.ts | ✅ | packages/core/agent-core/src/tools/BashTool/sedValidation.ts | Validação para sed, lógica pura |
| src/tools/BashTool/shouldUseSandbox.ts | ✅ | packages/core/agent-core/src/tools/BashTool/shouldUseSandbox.ts | Lógica decisão uso sandbox, sem UI |
| src/tools/BashTool/toolName.ts | ✅ | packages/core/agent-core/src/tools/BashTool/toolName.ts | Constantes nome ferramenta bash |
| src/tools/BashTool/utils.ts | ✅ | packages/core/agent-core/src/tools/BashTool/utils.ts | Utilitários bash, lógica pura |
| src/tools/BriefTool/BriefTool.ts | ✅ | packages/core/agent-core/src/tools/BriefTool/BriefTool.ts | Lógica de negócio reutilizável, sem deps de UI/CLI |
| src/tools/BriefTool/UI.tsx | ❌ |  | Componente React/Ink para terminal |
| src/tools/BriefTool/attachments.ts | ✅ | packages/core/agent-core/src/tools/BriefTool/attachments.ts | Validação e resolução de anexos, lógica útil |
| src/tools/BriefTool/prompt.ts | ✅ | packages/core/agent-core/src/tools/BriefTool/prompt.ts | Constantes e prompt reutilizáveis |
| src/tools/BriefTool/upload.ts | ⚠️ | packages/core/agent-core/src/tools/BriefTool/upload.ts | Upload com axios e rede, precisa adaptação para web |
| src/tools/ConfigTool/ConfigTool.ts | ✅ | packages/core/agent-core/src/tools/ConfigTool/ConfigTool.ts | Lógica de configuração e analytics aproveitável |
| src/tools/ConfigTool/UI.tsx | ❌ |  | UI React/Ink para terminal |
| src/tools/ConfigTool/constants.ts | ✅ | packages/core/agent-core/src/tools/ConfigTool/constants.ts | Constantes simples, útil |
| src/tools/ConfigTool/prompt.ts | ✅ | packages/core/agent-core/src/tools/ConfigTool/prompt.ts | Geração de prompt, lógica reutilizável |
| src/tools/ConfigTool/supportedSettings.ts | ✅ | packages/core/agent-core/src/tools/ConfigTool/supportedSettings.ts | Configurações e validações úteis |
| src/tools/CtxInspectTool/CtxInspectTool.ts | ❌ |  | Stub vazio, sem lógica |
| src/tools/DiscoverSkillsTool/prompt.ts | ❌ |  | Stub vazio, sem lógica |
| src/tools/EnterPlanModeTool/EnterPlanModeTool.ts | ✅ | packages/core/agent-core/src/tools/EnterPlanModeTool/EnterPlanModeTool.ts | Lógica de negócio relevante |
| src/tools/EnterPlanModeTool/UI.tsx | ❌ |  | UI React/Ink para terminal |
| src/tools/EnterPlanModeTool/constants.ts | ✅ | packages/core/agent-core/src/tools/EnterPlanModeTool/constants.ts | Constantes simples, útil |
| src/tools/EnterPlanModeTool/prompt.ts | ✅ | packages/core/agent-core/src/tools/EnterPlanModeTool/prompt.ts | Prompt e lógica reutilizáveis |
| src/tools/EnterWorktreeTool/EnterWorktreeTool.ts | ✅ | packages/core/agent-core/src/tools/EnterWorktreeTool/EnterWorktreeTool.ts | Lógica de negócio relevante |
| src/tools/EnterWorktreeTool/UI.tsx | ❌ |  | UI React/Ink para terminal |
| src/tools/EnterWorktreeTool/constants.ts | ✅ | packages/core/agent-core/src/tools/EnterWorktreeTool/constants.ts | Constantes simples, útil |
| src/tools/EnterWorktreeTool/prompt.ts | ✅ | packages/core/agent-core/src/tools/EnterWorktreeTool/prompt.ts | Prompt e lógica reutilizáveis |
| src/tools/ExitPlanModeTool/ExitPlanModeV2Tool.ts | ✅ | packages/core/agent-core/src/tools/ExitPlanModeTool/ExitPlanModeV2Tool.ts | Lógica de negócio reutilizável, sem deps de UI ou CLI |
| src/tools/ExitPlanModeTool/UI.tsx | ❌ |  | UI terminal com Ink, React, Box, Text |
| src/tools/ExitPlanModeTool/constants.ts | ✅ | packages/core/agent-core/src/tools/ExitPlanModeTool/constants.ts | Constantes simples, úteis para lógica |
| src/tools/ExitPlanModeTool/prompt.ts | ✅ | packages/core/agent-core/src/tools/ExitPlanModeTool/prompt.ts | Texto de prompt, útil para web |
| src/tools/ExitWorktreeTool/ExitWorktreeTool.ts | ✅ | packages/core/agent-core/src/tools/ExitWorktreeTool/ExitWorktreeTool.ts | Lógica de ferramenta, sem UI/CLI |
| src/tools/ExitWorktreeTool/UI.tsx | ❌ |  | UI terminal com Ink, React, Box, Text |
| src/tools/ExitWorktreeTool/constants.ts | ✅ | packages/core/agent-core/src/tools/ExitWorktreeTool/constants.ts | Constantes simples, reutilizáveis |
| src/tools/ExitWorktreeTool/prompt.ts | ✅ | packages/core/agent-core/src/tools/ExitWorktreeTool/prompt.ts | Texto de prompt, útil para web |
| src/tools/FileEditTool/FileEditTool.ts | ✅ | packages/core/agent-core/src/tools/FileEditTool/FileEditTool.ts | Lógica de edição de arquivos, sem UI/CLI |
| src/tools/FileEditTool/UI.tsx | ❌ |  | UI terminal com Ink, React, Suspense |
| src/tools/FileEditTool/constants.ts | ✅ | packages/core/agent-core/src/tools/FileEditTool/constants.ts | Constantes úteis para lógica |
| src/tools/FileEditTool/prompt.ts | ✅ | packages/core/agent-core/src/tools/FileEditTool/prompt.ts | Texto de prompt, útil para web |
| src/tools/FileEditTool/types.ts | ✅ | packages/core/agent-core/src/tools/FileEditTool/types.ts | Tipos e schemas reutilizáveis |
| src/tools/FileEditTool/utils.ts | ✅ | packages/core/agent-core/src/tools/FileEditTool/utils.ts | Utilitários para edição de arquivos |
| src/tools/FileReadTool/FileReadTool.ts | ⚠️ | packages/core/agent-core/src/tools/FileReadTool/FileReadTool.ts | Lógica útil, mas pode precisar adaptação |
| src/tools/FileReadTool/UI.tsx | ❌ |  | UI terminal com Ink, React |
| src/tools/FileReadTool/imageProcessor.ts | ✅ | packages/core/agent-core/src/tools/FileReadTool/imageProcessor.ts | Processamento de imagens, lógica útil |
| src/tools/FileReadTool/limits.ts | ✅ | packages/core/agent-core/src/tools/FileReadTool/limits.ts | Limites e constantes, reutilizáveis |
| src/tools/FileReadTool/prompt.ts | ✅ | packages/core/agent-core/src/tools/FileReadTool/prompt.ts | Texto de prompt, útil para web |
| src/tools/FileWriteTool/FileWriteTool.ts | ✅ | packages/core/agent-core/src/tools/FileWriteTool/FileWriteTool.ts | Lógica de escrita de arquivos, sem UI/CLI |
| src/tools/FileWriteTool/UI.tsx | ❌ |  | UI terminal React/Ink, não serve para web serverless |
| src/tools/FileWriteTool/prompt.ts | ✅ | packages/core/agent-core/src/tools/FileWriteTool/prompt.ts | Lógica de descrição do tool, útil para Nexias |
| src/tools/GlobTool/GlobTool.ts | ✅ | packages/core/agent-core/src/tools/GlobTool/GlobTool.ts | Lógica de negócio para glob, aproveitável |
| src/tools/GlobTool/UI.tsx | ❌ |  | UI terminal React/Ink, não serve para web serverless |
| src/tools/GlobTool/prompt.ts | ✅ | packages/core/agent-core/src/tools/GlobTool/prompt.ts | Descrição do tool, útil para Nexias |
| src/tools/GrepTool/GrepTool.ts | ✅ | packages/core/agent-core/src/tools/GrepTool/GrepTool.ts | Lógica de negócio para grep, aproveitável |
| src/tools/GrepTool/UI.tsx | ❌ |  | UI terminal React/Ink, não serve para web serverless |
| src/tools/GrepTool/prompt.ts | ✅ | packages/core/agent-core/src/tools/GrepTool/prompt.ts | Descrição do tool, útil para Nexias |
| src/tools/LSPTool/LSPTool.ts | ✅ | packages/core/agent-core/src/tools/LSPTool/LSPTool.ts | Lógica LSP, relevante para Nexias |
| src/tools/LSPTool/UI.tsx | ❌ |  | UI terminal React/Ink, não serve para web serverless |
| src/tools/LSPTool/formatters.ts | ✅ | packages/core/agent-core/src/tools/LSPTool/formatters.ts | Formatação e utilitários LSP, aproveitável |
| src/tools/LSPTool/prompt.ts | ✅ | packages/core/agent-core/src/tools/LSPTool/prompt.ts | Descrição do tool LSP, útil para Nexias |
| src/tools/LSPTool/schemas.ts | ✅ | packages/core/agent-core/src/tools/LSPTool/schemas.ts | Schemas zod para LSP, aproveitável |
| src/tools/LSPTool/symbolContext.ts | ⚠️ | packages/core/agent-core/src/tools/LSPTool/symbolContext.ts | Lógica útil, mas pode precisar adaptação para Nexias |
| src/tools/ListMcpResourcesTool/ListMcpResourcesTool.ts | ⚠️ | packages/core/agent-core/src/tools/ListMcpResourcesTool/ListMcpResourcesTool.ts | Possível lógica de negócio, requer revisão |
| src/tools/ListMcpResourcesTool/UI.tsx | ❌ |  | UI terminal React/Ink, não serve para web serverless |
| src/tools/ListMcpResourcesTool/prompt.ts | ✅ | packages/core/agent-core/src/tools/ListMcpResourcesTool/prompt.ts | Descrição do tool, útil para Nexias |
| src/tools/ListPeersTool/ListPeersTool.ts | ⚠️ | packages/core/agent-core/src/tools/ListPeersTool/ListPeersTool.ts | Possível lógica de negócio, requer revisão |
| src/tools/MCPTool/MCPTool.ts | ⚠️ | packages/core/agent-core/src/tools/MCPTool/MCPTool.ts | Possível lógica de negócio, requer revisão |
| src/tools/MCPTool/UI.tsx | ❌ |  | UI terminal React/Ink, não serve para web serverless |
| src/tools/MCPTool/classifyForCollapse.ts | ✅ | packages/core/agent-core/src/tools/MCPTool/classifyForCollapse.ts | Lógica de classificação de ferramentas MCP reutilizável |
| src/tools/MCPTool/prompt.ts | ❌ |  | Stub sem lógica real, apenas strings vazias |
| src/tools/McpAuthTool/McpAuthTool.ts | ✅ | packages/core/agent-core/src/tools/McpAuthTool/McpAuthTool.ts | Lógica de autenticação MCP útil para Nexias |
| src/tools/MonitorTool/MonitorTool.ts | ❌ |  | Exporta objeto vazio, sem lógica |
| src/tools/NotebookEditTool/NotebookEditTool.ts | ✅ | packages/core/agent-core/src/tools/NotebookEditTool/NotebookEditTool.ts | Lógica de edição de notebook aproveitável |
| src/tools/NotebookEditTool/UI.tsx | ❌ |  | UI React/Ink para terminal, não web |
| src/tools/NotebookEditTool/constants.ts | ✅ | packages/core/agent-core/src/tools/NotebookEditTool/constants.ts | Constantes reutilizáveis sem dependências UI |
| src/tools/NotebookEditTool/prompt.ts | ✅ | packages/core/agent-core/src/tools/NotebookEditTool/prompt.ts | Prompt textual útil para lógica de ferramenta |
| src/tools/OverflowTestTool/OverflowTestTool.ts | ❌ |  | Exporta objeto vazio, sem lógica |
| src/tools/PowerShellTool/PowerShellTool.tsx | ⚠️ | packages/core/agent-core/src/tools/PowerShellTool/PowerShellTool.ts | Lógica útil, mas depende de React e Bun, precisa adaptação |
| src/tools/PowerShellTool/UI.tsx | ❌ |  | UI React/Ink para terminal, não web |
| src/tools/PowerShellTool/clmTypes.ts | ✅ | packages/core/agent-core/src/tools/PowerShellTool/clmTypes.ts | Tipos e listas úteis para segurança PowerShell |
| src/tools/PowerShellTool/commandSemantics.ts | ✅ | packages/core/agent-core/src/tools/PowerShellTool/commandSemantics.ts | Lógica de interpretação de códigos de saída PowerShell |
| src/tools/PowerShellTool/commonParameters.ts | ✅ | packages/core/agent-core/src/tools/PowerShellTool/commonParameters.ts | Parâmetros comuns PowerShell reutilizáveis |
| src/tools/PowerShellTool/destructiveCommandWarning.ts | ✅ | packages/core/agent-core/src/tools/PowerShellTool/destructiveCommandWarning.ts | Lógica de detecção de comandos destrutivos |
| src/tools/PowerShellTool/gitSafety.ts | ✅ | packages/core/agent-core/src/tools/PowerShellTool/gitSafety.ts | Lógica de segurança Git para sandbox |
| src/tools/PowerShellTool/modeValidation.ts | ✅ | packages/core/agent-core/src/tools/PowerShellTool/modeValidation.ts | Validação de modo PowerShell útil |
| src/tools/PowerShellTool/pathValidation.ts | ✅ | packages/core/agent-core/src/tools/PowerShellTool/pathValidation.ts | Validação de paths para PowerShell |
| src/tools/PowerShellTool/powershellPermissions.ts | ✅ | packages/core/agent-core/src/tools/PowerShellTool/powershellPermissions.ts | Lógica de permissões PowerShell |
| src/tools/PowerShellTool/powershellSecurity.ts | ✅ | packages/core/agent-core/src/tools/PowerShellTool/powershellSecurity.ts | Lógica de segurança PowerShell |
| src/tools/PowerShellTool/prompt.ts | ✅ | packages/core/agent-core/src/tools/PowerShellTool/prompt.ts | Lógica de timeout e constantes reutilizáveis |
| src/tools/PowerShellTool/readOnlyValidation.ts | ✅ | packages/core/agent-core/src/tools/PowerShellTool/readOnlyValidation.ts | Validação de comandos PowerShell útil para agentes |
| src/tools/PowerShellTool/toolName.ts | ✅ | packages/core/agent-core/src/tools/PowerShellTool/toolName.ts | Constante simples, evita dependências circulares |
| src/tools/PushNotificationTool/PushNotificationTool.ts | ❌ |  | Stub vazio, sem lógica |
| src/tools/REPLTool/REPLTool.ts | ❌ |  | Stub vazio, sem lógica |
| src/tools/REPLTool/constants.ts | ⚠️ | packages/core/agent-core/src/tools/REPLTool/constants.ts | Conceitos REPL úteis, mas dependente de CLI/terminal |
| src/tools/REPLTool/primitiveTools.ts | ⚠️ | packages/core/agent-core/src/tools/REPLTool/primitiveTools.ts | Conceito de ferramentas primitivas, reescrita necessária |
| src/tools/ReadMcpResourceTool/ReadMcpResourceTool.ts | ✅ | packages/core/agent-core/src/tools/ReadMcpResourceTool/ReadMcpResourceTool.ts | Lógica de ferramenta MCP com validação e storage |
| src/tools/ReadMcpResourceTool/UI.tsx | ❌ |  | UI React/Ink para terminal, não aplicável web |
| src/tools/ReadMcpResourceTool/prompt.ts | ✅ | packages/core/agent-core/src/tools/ReadMcpResourceTool/prompt.ts | Prompt textual, útil para documentação e uso |
| src/tools/RemoteTriggerTool/RemoteTriggerTool.ts | ✅ | packages/core/agent-core/src/tools/RemoteTriggerTool/RemoteTriggerTool.ts | Lógica de ferramenta com OAuth e API calls |
| src/tools/RemoteTriggerTool/UI.tsx | ❌ |  | UI React/Ink para terminal, não aplicável web |
| src/tools/RemoteTriggerTool/prompt.ts | ✅ | packages/core/agent-core/src/tools/RemoteTriggerTool/prompt.ts | Prompt textual para uso da ferramenta |
| src/tools/ReviewArtifactTool/ReviewArtifactTool.ts | ❌ |  | Stub vazio, sem lógica |
| src/tools/ScheduleCronTool/CronCreateTool.ts | ✅ | packages/core/agent-core/src/tools/ScheduleCronTool/CronCreateTool.ts | Lógica de criação de tarefas cron reutilizável |
| src/tools/ScheduleCronTool/CronDeleteTool.ts | ✅ | packages/core/agent-core/src/tools/ScheduleCronTool/CronDeleteTool.ts | Lógica de remoção de tarefas cron |
| src/tools/ScheduleCronTool/CronListTool.ts | ✅ | packages/core/agent-core/src/tools/ScheduleCronTool/CronListTool.ts | Lógica de listagem de tarefas cron |
| src/tools/ScheduleCronTool/UI.tsx | ❌ |  | UI React/Ink para terminal, não aplicável web |
| src/tools/ScheduleCronTool/prompt.ts | ✅ | packages/core/agent-core/src/tools/ScheduleCronTool/prompt.ts | Prompt textual para tarefas cron |
| src/tools/SendMessageTool/UI.tsx | ❌ |  | UI React/Ink para terminal |
| src/tools/SendMessageTool/constants.ts | ✅ | packages/core/agent-core/src/tools/SendMessageTool/constants.ts | Constantes simples, útil para lógica de ferramentas |
| src/tools/SendMessageTool/prompt.ts | ❌ |  | Usa bun:bundle, específico de Bun |
| src/tools/SendUserFileTool/SendUserFileTool.ts | ❌ |  | Stub vazio, sem lógica |
| src/tools/SendUserFileTool/prompt.ts | ❌ |  | Stub vazio, sem lógica |
| src/tools/SkillTool/SkillTool.ts | ⚠️ | packages/core/agent-core/src/tools/SkillTool/SkillTool.ts | Lógica complexa, depende de paths e libs específicas |
| src/tools/SkillTool/UI.tsx | ❌ |  | UI React/Ink para terminal |
| src/tools/SkillTool/constants.ts | ✅ | packages/core/agent-core/src/tools/SkillTool/constants.ts | Constantes simples, útil para lógica de ferramentas |
| src/tools/SkillTool/prompt.ts | ⚠️ | packages/core/agent-core/src/tools/SkillTool/prompt.ts | Lógica de prompt com memoize e analytics, precisa adaptação |
| src/tools/SleepTool/SleepTool.ts | ❌ |  | Stub vazio, sem lógica |
| src/tools/SleepTool/prompt.ts | ✅ | packages/core/agent-core/src/tools/SleepTool/prompt.ts | Texto de prompt, útil para lógica de ferramenta |
| src/tools/SnipTool/SnipTool.ts | ❌ |  | Stub vazio, sem lógica |
| src/tools/SnipTool/prompt.ts | ❌ |  | Stub vazio, sem lógica |
| src/tools/SubscribePRTool/SubscribePRTool.ts | ❌ |  | Stub vazio, sem lógica |
| src/tools/SuggestBackgroundPRTool/SuggestBackgroundPRTool.ts | ❌ |  | Stub vazio, sem lógica |
| src/tools/SyntheticOutputTool/SyntheticOutputTool.ts | ✅ | packages/core/agent-core/src/tools/SyntheticOutputTool/SyntheticOutputTool.ts | Lógica de schema e validação, útil para Nexias |
| src/tools/TaskCreateTool/TaskCreateTool.ts | ✅ | packages/core/agent-core/src/tools/TaskCreateTool/TaskCreateTool.ts | Lógica de criação de tarefas, aproveitável |
| src/tools/TaskCreateTool/constants.ts | ✅ | packages/core/agent-core/src/tools/TaskCreateTool/constants.ts | Constantes simples, útil para lógica de ferramentas |
| src/tools/TaskCreateTool/prompt.ts | ✅ | packages/core/agent-core/src/tools/TaskCreateTool/prompt.ts | Texto de prompt, útil para lógica de ferramenta |
| src/tools/TaskGetTool/TaskGetTool.ts | ✅ | packages/core/agent-core/src/tools/TaskGetTool/TaskGetTool.ts | Lógica de obtenção de tarefas, aproveitável |
| src/tools/TaskGetTool/constants.ts | ✅ | packages/core/agent-core/src/tools/TaskGetTool/constants.ts | Constantes simples, úteis para lógica de tarefas |
| src/tools/TaskGetTool/prompt.ts | ✅ | packages/core/agent-core/src/tools/TaskGetTool/prompt.ts | Texto de prompt reutilizável para agentes |
| src/tools/TaskListTool/TaskListTool.ts | ✅ | packages/core/agent-core/src/tools/TaskListTool/TaskListTool.ts | Lógica de listagem de tarefas aproveitável |
| src/tools/TaskListTool/constants.ts | ✅ | packages/core/agent-core/src/tools/TaskListTool/constants.ts | Constantes simples para ferramenta de tarefas |
| src/tools/TaskListTool/prompt.ts | ✅ | packages/core/agent-core/src/tools/TaskListTool/prompt.ts | Prompt com lógica condicional útil |
| src/tools/TaskOutputTool/TaskOutputTool.tsx | ❌ |  | UI React/Ink para terminal, não web |
| src/tools/TaskOutputTool/constants.ts | ✅ | packages/core/agent-core/src/tools/TaskOutputTool/constants.ts | Constantes simples para ferramenta |
| src/tools/TaskStopTool/TaskStopTool.ts | ⚠️ | packages/core/agent-core/src/tools/TaskStopTool/TaskStopTool.ts | Lógica útil, mas UI e deps precisam adaptação |
| src/tools/TaskStopTool/UI.tsx | ❌ |  | Componente React/Ink para terminal |
| src/tools/TaskStopTool/prompt.ts | ✅ | packages/core/agent-core/src/tools/TaskStopTool/prompt.ts | Prompt textual simples e reutilizável |
| src/tools/TaskUpdateTool/TaskUpdateTool.ts | ⚠️ | packages/core/agent-core/src/tools/TaskUpdateTool/TaskUpdateTool.ts | Lógica complexa, depende de Bun e analytics |
| src/tools/TaskUpdateTool/constants.ts | ✅ | packages/core/agent-core/src/tools/TaskUpdateTool/constants.ts | Constantes simples para ferramenta |
| src/tools/TaskUpdateTool/prompt.ts | ✅ | packages/core/agent-core/src/tools/TaskUpdateTool/prompt.ts | Prompt textual útil para atualização |
| src/tools/TeamCreateTool/TeamCreateTool.ts | ⚠️ | packages/core/agent-core/src/tools/TeamCreateTool/TeamCreateTool.ts | Lógica valiosa, mas depende de estado e analytics |
| src/tools/TeamCreateTool/UI.tsx | ❌ |  | Componente React para terminal |
| src/tools/TeamCreateTool/constants.ts | ✅ | packages/core/agent-core/src/tools/TeamCreateTool/constants.ts | Constantes simples para ferramenta |
| src/tools/TeamCreateTool/prompt.ts | ✅ | packages/core/agent-core/src/tools/TeamCreateTool/prompt.ts | Prompt textual reutilizável |
| src/tools/TeamDeleteTool/TeamDeleteTool.ts | ⚠️ | packages/core/agent-core/src/tools/TeamDeleteTool/TeamDeleteTool.ts | Lógica útil, mas depende de analytics e utils específicos |
| src/tools/TeamDeleteTool/UI.tsx | ❌ |  | Componente React para terminal |
| src/tools/TeamDeleteTool/constants.ts | ✅ | packages/core/agent-core/src/tools/TeamDeleteTool/constants.ts | Constantes simples para ferramenta |
| src/tools/TeamDeleteTool/prompt.ts | ✅ | packages/core/agent-core/src/tools/TeamDeleteTool/prompt.ts | Prompt string útil para ferramenta de limpeza de times |
| src/tools/TerminalCaptureTool/TerminalCaptureTool.ts | ❌ |  | Stub vazio, específico CLI/terminal |
| src/tools/TerminalCaptureTool/prompt.ts | ❌ |  | Stub vazio, específico CLI/terminal |
| src/tools/TodoWriteTool/TodoWriteTool.ts | ⚠️ | packages/core/agent-core/src/tools/TodoWriteTool/TodoWriteTool.ts | Lógica de tool, mas depende de Bun e estado CLI |
| src/tools/TodoWriteTool/constants.ts | ✅ | packages/core/agent-core/src/tools/TodoWriteTool/constants.ts | Constantes simples reutilizáveis |
| src/tools/TodoWriteTool/prompt.ts | ✅ | packages/core/agent-core/src/tools/TodoWriteTool/prompt.ts | Prompt textual para ferramenta de tarefas |
| src/tools/ToolSearchTool/ToolSearchTool.ts | ⚠️ | packages/core/agent-core/src/tools/ToolSearchTool/ToolSearchTool.ts | Lógica valiosa, mas depende de libs específicas |
| src/tools/ToolSearchTool/constants.ts | ✅ | packages/core/agent-core/src/tools/ToolSearchTool/constants.ts | Constantes simples reutilizáveis |
| src/tools/ToolSearchTool/prompt.ts | ⚠️ | packages/core/agent-core/src/tools/ToolSearchTool/prompt.ts | Usa bun:bundle e require dinâmico, reescrever |
| src/tools/TungstenTool/TungstenLiveMonitor.tsx | ❌ |  | Componente React para UI terminal, não importar |
| src/tools/TungstenTool/TungstenTool.ts | ❌ |  | Stub vazio, sem lógica real |
| src/tools/VerifyPlanExecutionTool/VerifyPlanExecutionTool.ts | ❌ |  | Stub vazio, sem lógica real |
| src/tools/VerifyPlanExecutionTool/constants.ts | ✅ | packages/core/agent-core/src/tools/VerifyPlanExecutionTool/constants.ts | Constantes simples reutilizáveis |
| src/tools/WebBrowserTool/WebBrowserPanel.tsx | ❌ |  | Componente React para UI terminal, não importar |
| src/tools/WebBrowserTool/WebBrowserTool.ts | ❌ |  | Stub vazio, sem lógica real |
| src/tools/WebFetchTool/UI.tsx | ❌ |  | UI React/Ink para terminal, não importar |
| src/tools/WebFetchTool/WebFetchTool.ts | ✅ | packages/core/agent-core/src/tools/WebFetchTool/WebFetchTool.ts | Lógica de negócio para fetch web reutilizável |
| src/tools/WebFetchTool/preapproved.ts | ✅ | packages/core/agent-core/src/tools/WebFetchTool/preapproved.ts | Lista de hosts pré-aprovados útil para Nexias |
| src/tools/WebFetchTool/prompt.ts | ✅ | packages/core/agent-core/src/tools/WebFetchTool/prompt.ts | Prompt textual para ferramenta WebFetch |
| src/tools/WebFetchTool/utils.ts | ✅ | packages/core/agent-core/src/tools/WebFetchTool/utils.ts | Utilitários para WebFetch sem dependências UI |
| src/tools/WebSearchTool/UI.tsx | ❌ |  | UI terminal React/Ink, não serve para web serverless |
| src/tools/WebSearchTool/WebSearchTool.ts | ✅ | packages/core/agent-core/src/tools/WebSearchTool.ts | Lógica de negócio de ferramenta web search aproveitável |
| src/tools/WebSearchTool/prompt.ts | ✅ | packages/core/agent-core/src/tools/WebSearchTool/prompt.ts | Prompt string reutilizável para ferramenta web search |
| src/tools/WorkflowTool/WorkflowPermissionRequest.tsx | ❌ |  | Componente React vazio, UI terminal irrelevante |
| src/tools/WorkflowTool/WorkflowTool.ts | ❌ |  | Exporta objeto vazio, sem lógica útil |
| src/tools/WorkflowTool/bundled/index.ts | ❌ |  | Exporta objeto vazio, sem lógica útil |
| src/tools/WorkflowTool/constants.ts | ✅ | packages/core/agent-core/src/tools/WorkflowTool/constants.ts | Constantes simples, reutilizáveis no Nexias |
| src/tools/WorkflowTool/createWorkflowCommand.ts | ❌ |  | Exporta objeto vazio, sem lógica útil |
| src/tools/shared/gitOperationTracking.ts | ✅ | packages/core/agent-core/src/tools/shared/gitOperationTracking.ts | Lógica de tracking git agnóstica ao shell útil |
| src/tools/shared/spawnMultiAgent.ts | ⚠️ | packages/core/agent-core/src/tools/shared/spawnMultiAgent.ts | Contém React e lógica complexa, precisa refatorar |
| src/tools/testing/TestingPermissionTool.tsx | ❌ |  | Componente React, ferramenta de teste UI |
| src/tools/utils.ts | ✅ | packages/core/agent-core/src/tools/utils.ts | Utilitário para taggear mensagens, lógica útil |
| src/memdir/findRelevantMemories.ts | ⚠️ | packages/core/agent-core/src/memdir/findRelevantMemories.ts | Lógica de seleção de memórias útil, mas depende de Bun e API cliente |
| src/memdir/memdir.ts | ❌ |  | Uso de Bun features, imports específicos de CLI/desktop |
| src/memdir/memoryAge.ts | ✅ | packages/core/agent-core/src/memdir/memoryAge.ts | Funções utilitárias para cálculo e formatação de idade de memória |
| src/memdir/memoryScan.ts | ✅ | packages/core/agent-core/src/memdir/memoryScan.ts | Escaneamento de diretórios e parsing de frontmatter, sem deps CLI |
| src/memdir/memoryShapeTelemetry.ts | ❌ |  | Arquivo vazio, sem lógica |
| src/memdir/memoryTypes.ts | ✅ | packages/core/agent-core/src/memdir/memoryTypes.ts | Definição de tipos e taxonomia de memórias, lógica reutilizável |
| src/memdir/paths.ts | ⚠️ | packages/core/agent-core/src/memdir/paths.ts | Uso de path/os, mas depende de estado e env específicos, adaptação necessária |
| src/memdir/teamMemPaths.ts | ⚠️ | packages/core/agent-core/src/memdir/teamMemPaths.ts | Validação e sanitização de paths, mas usa fs/promises e lógica específica |
| src/memdir/teamMemPrompts.ts | ⚠️ | packages/core/agent-core/src/memdir/teamMemPrompts.ts | Construção de prompts combinados, lógica útil porém dependente de outros módulos |
| src/tasks/DreamTask/DreamTask.ts | ✅ | packages/core/agent-core/src/tasks/DreamTask.ts | Lógica de tarefa background reutilizável, sem UI |
| src/tasks/InProcessTeammateTask/InProcessTeammateTask.tsx | ❌ |  | Componente React/Ink para terminal |
| src/tasks/InProcessTeammateTask/types.ts | ✅ | packages/core/agent-core/src/tasks/InProcessTeammateTask/types.ts | Tipos úteis para estado de tarefa de agente |
| src/tasks/LocalAgentTask/LocalAgentTask.tsx | ❌ |  | Contém React/Ink UI e terminal bindings |
| src/tasks/LocalMainSessionTask.ts | ✅ | packages/core/agent-core/src/tasks/LocalMainSessionTask.ts | Lógica de tarefa background, sem UI |
| src/tasks/LocalShellTask/LocalShellTask.tsx | ❌ |  | Usa React/Ink e Bun específico |
| src/tasks/LocalShellTask/guards.ts | ✅ | packages/core/agent-core/src/tasks/LocalShellTask/guards.ts | Tipos e guards puros, sem UI |
| src/tasks/LocalShellTask/killShellTasks.ts | ✅ | packages/core/agent-core/src/tasks/LocalShellTask/killShellTasks.ts | Lógica kill task sem UI, útil para Nexias |
| src/tasks/LocalWorkflowTask/LocalWorkflowTask.ts | ❌ |  | Arquivo stub vazio, sem lógica |
| src/tasks/MonitorMcpTask/MonitorMcpTask.ts | ❌ |  | Arquivo stub vazio, sem lógica |
| src/tasks/RemoteAgentTask/RemoteAgentTask.tsx | ❌ |  | Contém React/Ink UI e terminal bindings |
| src/tasks/pillLabel.ts | ✅ | packages/core/agent-core/src/tasks/pillLabel.ts | Utilitário para labels, sem UI dependências |
| src/tasks/stopTask.ts | ✅ | packages/core/agent-core/src/tasks/stopTask.ts | Lógica compartilhada para parar tarefas |
| src/tasks/types.ts | ⚠️ | packages/core/agent-core/src/tasks/types.ts | Tipos gerais, pode precisar adaptação para Nexias |
| src/types/command.ts | ✅ | packages/core/agent-core/src/types/command.ts | Tipos úteis para comandos e resultados de agentes |
| src/types/connectorText.ts | ⚠️ | packages/core/agent-core/src/types/connectorText.ts | Stub, mas conceito de bloco de texto pode ser útil |
| src/types/generated/events_mono/claude_code/v1/claude_code_internal_event.ts | ❌ |  | Código gerado específico, sem lógica de negócio |
| src/types/generated/events_mono/common/v1/auth.ts | ❌ |  | Código gerado, específico para autenticação interna |
| src/types/generated/events_mono/growthbook/v1/growthbook_experiment_event.ts | ❌ |  | Código gerado para eventos Growthbook, não relevante |
| src/types/generated/google/protobuf/timestamp.ts | ❌ |  | Código gerado protobuf, sem lógica aplicável |
| src/types/hooks.ts | ✅ | packages/core/agent-core/src/types/hooks.ts | Tipos e validações para hooks, útil para Nexias |
| src/types/ids.ts | ✅ | packages/core/agent-core/src/types/ids.ts | Tipos de ID com branding, útil para segurança de tipos |
| src/types/logs.ts | ✅ | packages/core/agent-core/src/types/logs.ts | Tipos para logs e mensagens serializadas, aproveitável |
| src/types/permissions.ts | ✅ | packages/core/agent-core/src/types/permissions.ts | Definições de permissões sem dependências runtime |
| src/types/plugin.ts | ✅ | packages/core/agent-core/src/types/plugin.ts | Tipos para plugins e metadados, aproveitável |
| src/types/textInputTypes.ts | ❌ |  | Importa React e Ink, UI terminal, não importar |
| src/constants/apiLimits.ts | ✅ | packages/core/agent-core/src/constants/apiLimits.ts | Constantes de limites API, sem dependências específicas |
| src/constants/betas.ts | ⚠️ | packages/core/agent-core/src/constants/betas.ts | Usa 'bun:bundle', requer adaptação para web |
| src/constants/common.ts | ✅ | packages/core/agent-core/src/constants/common.ts | Funções utilitárias independentes de CLI |
| src/constants/cyberRiskInstruction.ts | ✅ | packages/core/agent-core/src/constants/cyberRiskInstruction.ts | Texto de instrução de segurança reutilizável |
| src/constants/errorIds.ts | ✅ | packages/core/agent-core/src/constants/errorIds.ts | Constantes de erro para rastreamento |
| src/constants/figures.ts | ⚠️ | packages/core/agent-core/src/constants/figures.ts | Usa env.platform, pode precisar adaptação |
| src/constants/files.ts | ✅ | packages/core/agent-core/src/constants/files.ts | Lista de extensões binárias, útil para Nexias |
| src/constants/github-app.ts | ❌ |  | Específico para GitHub Actions, não relevante |
| src/constants/keys.ts | ✅ | packages/core/agent-core/src/constants/keys.ts | Função para chave GrowthBook, sem deps CLI |
| src/constants/messages.ts | ✅ | packages/core/agent-core/src/constants/messages.ts | Constantes simples de mensagens |
| src/constants/oauth.ts | ✅ | packages/core/agent-core/src/constants/oauth.ts | Configuração OAuth, lógica reutilizável |
| src/constants/outputStyles.ts | ⚠️ | packages/core/agent-core/src/constants/outputStyles.ts | Usa dependências específicas, requer adaptação |
| src/constants/product.ts | ✅ | packages/core/agent-core/src/constants/product.ts | URLs e funções utilitárias de ambiente |
| src/constants/prompts.ts | ⚠️ | packages/core/agent-core/src/constants/prompts.ts | Importa módulos CLI, precisa refatorar |
| src/constants/spinnerVerbs.ts | ✅ | packages/core/agent-core/src/constants/spinnerVerbs.ts | Lista e função utilitária, sem deps CLI |
| src/constants/system.ts | ⚠️ | packages/core/agent-core/src/constants/system.ts | Usa 'bun:bundle' e lógica específica CLI |
| src/constants/systemPromptSections.ts | ❌ |  | Provável conteúdo CLI/UI, não listado mas presumido |
| src/constants/toolLimits.ts | ❌ |  | Não fornecido, presumido específico CLI |
| src/constants/tools.ts | ❌ |  | Não fornecido, presumido específico CLI |
| src/constants/turnCompletionVerbs.ts | ❌ |  | Não fornecido, presumido específico CLI |
| src/constants/xml.ts | ❌ |  | Não fornecido, presumido específico CLI |
| src/context/QueuedMessageContext.tsx | ❌ |  | UI terminal React/Ink, contexto para layout terminal |
| src/context/fpsMetrics.tsx | ❌ |  | React context com UI terminal, depende de React/Ink |
| src/context/mailbox.tsx | ❌ |  | React context com UI terminal, depende de React/Ink |
| src/context/modalContext.tsx | ❌ |  | React context para UI terminal modal, React/Ink deps |
| src/context/notifications.tsx | ✅ | packages/core/agent-core/src/context/notifications.ts | Lógica de notificações, sem UI, útil para Nexias |
| src/context/overlayContext.tsx | ❌ |  | React context para overlays UI terminal, React/Ink |
| src/context/promptOverlayContext.tsx | ❌ |  | React context para UI terminal, React/Ink dependente |
| src/context/stats.tsx | ✅ | packages/core/agent-core/src/context/stats.ts | Lógica de métricas e estatísticas, sem UI terminal |
| src/context/voice.tsx | ❌ |  | React context para estado de voz com UI terminal deps |
| src/state/AppState.tsx | ❌ |  | React + Bun + UI terminal, contexto React específico |
| src/state/AppStateStore.ts | ⚠️ | packages/core/agent-core/src/state/AppStateStore.ts | Lógica de estado, mas dependências específicas e tipos próprios |
| src/state/onChangeAppState.ts | ✅ | packages/core/agent-core/src/state/onChangeAppState.ts | Lógica de negócio para atualização de estado e config |
| src/state/selectors.ts | ✅ | packages/core/agent-core/src/state/selectors.ts | Funções puras para derivar estado, sem side effects |
| src/state/store.ts | ✅ | packages/core/agent-core/src/state/store.ts | Implementação genérica de store sem dependências UI |
| src/state/teammateViewHelpers.ts | ⚠️ | packages/core/agent-core/src/state/teammateViewHelpers.ts | Helpers com lógica de negócio, mas dependências específicas |
| src/plugins/builtinPlugins.ts | ⚠️ | packages/core/agent-core/src/plugins/builtinPlugins.ts | Registro e gestão de plugins útil, mas CLI-dependente |
| src/plugins/bundled/index.ts | ⚠️ | packages/core/agent-core/src/plugins/bundled/index.ts | Inicialização de plugins, conceito útil, precisa adaptação |
| src/coordinator/coordinatorMode.ts | ⚠️     | packages/core/agent-core/src/coordinator/coordinatorMode.ts | Lógica de coordenação útil, mas depende de Bun e ferramentas específicas |
| src/coordinator/workerAgent.ts      | ❌     |                                 | Arquivo vazio, sem lógica real                      |
| src/remote/RemoteSessionManager.ts | ⚠️    | packages/core/agent-core/src/remote/RemoteSessionManager.ts | Gerenciamento sessão remoto, adaptação necessária |
| src/remote/SessionsWebSocket.ts | ❌    |                                                  | WebSocket específico, dependente TLS/proxy |
| src/remote/remotePermissionBridge.ts | ✅    | packages/core/agent-core/src/remote/remotePermissionBridge.ts | Lógica permissão remota, útil para Nexias  |
| src/remote/sdkMessageAdapter.ts | ✅    | packages/core/agent-core/src/remote/sdkMessageAdapter.ts | Adaptação mensagens SDK para Nexias         |
| src/sdk/runtimeTypes.ts | ❌     |                                | Arquivo vazio, sem lógica    |
| src/sdk/toolTypes.ts    | ❌     |                                | Arquivo vazio, sem lógica    |
| src/upstreamproxy/relay.ts | ⚠️ | packages/backend/src/upstreamproxy/relay.ts | Relay TCP-WebSocket útil, mas depende de Node net, adaptação necessária |
| src/upstreamproxy/upstreamproxy.ts | ⚠️ | packages/backend/src/upstreamproxy/upstreamproxy.ts | Configuração proxy container útil, mas depende fs/promises, adaptação requerida |
| src/assistant/AssistantSessionChooser.tsx | ❌ |  | Componente React vazio, UI terminal não aplicável |
| src/assistant/gate.ts | ❌ |  | Stub sem lógica, feature-gated específico |
| src/assistant/index.ts | ❌ |  | Stub sem lógica, feature-gated específico |
| src/assistant/sessionDiscovery.ts | ❌ |  | Interface stub, sem lógica implementada |
| src/assistant/sessionHistory.ts | ⚠️ | packages/core/agent-core/src/services/sessionHistory.ts | Lógica de histórico útil, mas depende de axios e OAuth, reescrita necessária |
| src/entrypoints/agentSdkTypes.ts | ✅ | packages/core/agent-core/src/entrypoints/agentSdkTypes.ts | Tipos SDK reutilizáveis, sem dependências CLI |
| src/entrypoints/cli.tsx | ❌ |  | Código específico CLI/terminal/Bun, ambiente desktop |
| src/entrypoints/init.ts | ⚠️ | packages/core/agent-core/src/entrypoints/init.ts | Inicialização com lógica útil, mas depende de serviços específicos |
| src/entrypoints/mcp.ts | ⚠️ | packages/core/agent-core/src/entrypoints/mcp.ts | Lógica servidor/CLI, precisa adaptação para Nexias |
| src/entrypoints/sandboxTypes.ts | ✅ | packages/core/agent-core/src/entrypoints/sandboxTypes.ts | Tipos e validações Zod úteis para configuração sandbox |
| src/entrypoints/sdk/controlSchemas.ts | ✅ | packages/core/agent-core/src/entrypoints/sdk/controlSchemas.ts | Schemas Zod para protocolo controle SDK, aproveitável |
| src/entrypoints/sdk/coreSchemas.ts | ✅ | packages/core/agent-core/src/entrypoints/sdk/coreSchemas.ts | Schemas Zod para tipos serializáveis SDK, reutilizável |
| src/entrypoints/sdk/coreTypes.generated.ts | ❌ |  | Arquivo vazio, sem lógica |
| src/entrypoints/sdk/coreTypes.ts | ✅ | packages/core/agent-core/src/entrypoints/sdk/coreTypes.ts | Tipos SDK gerados e utilitários, aproveitável |
| src/entrypoints/sdk/runtimeTypes.ts | ❌ |  | Arquivo vazio, sem lógica |
| src/entrypoints/sdk/toolTypes.ts | ❌ |  | Arquivo vazio, sem lógica |
| src/native-ts/color-diff/index.ts | ✅ | packages/core/agent-core/src/utils/color-diff.ts | Lógica de diff e syntax highlighting pura TS, útil para Nexias |
| src/native-ts/file-index/index.ts | ✅ | packages/core/agent-core/src/utils/file-index.ts | Algoritmo de busca fuzzy puro TS, aplicável em backend Nexias |
| src/native-ts/yoga-layout/enums.ts | ✅ | packages/core/agent-core/src/layout/yoga/enums.ts | Constantes TS puras, úteis para layout flexbox no Nexias |
| src/native-ts/yoga-layout/index.ts | ⚠️ | packages/core/agent-core/src/layout/yoga/index.ts | Flexbox engine TS, requer adaptação para uso web serverless |
| src/skills/bundled/batch.ts | ✅ | packages/core/agent-core/src/skills/bundled/batch.ts | Lógica de orquestração paralela aproveitável |
| src/skills/bundled/claude-api/SKILL.md | ❌ |  | Arquivo markdown stub, sem lógica |
| src/skills/bundled/claude-api/csharp/claude-api.md | ❌ |  | Arquivo markdown stub, sem lógica |
| src/skills/bundled/claude-api/curl/examples.md | ❌ |  | Arquivo markdown stub, sem lógica |
| src/skills/bundled/claude-api/go/claude-api.md | ❌ |  | Arquivo markdown stub, sem lógica |
| src/skills/bundled/claude-api/java/claude-api.md | ❌ |  | Arquivo markdown stub, sem lógica |
| src/skills/bundled/claude-api/php/claude-api.md | ❌ |  | Arquivo markdown stub, sem lógica |
| src/skills/bundled/claude-api/python/agent-sdk/README.md | ❌ |  | Arquivo markdown stub, sem lógica |
| src/skills/bundled/claude-api/python/agent-sdk/patterns.md | ❌ |  | Arquivo markdown stub, sem lógica |
| src/skills/bundled/claude-api/python/claude-api/README.md | ❌ |  | Arquivo markdown stub, sem lógica |
| src/skills/bundled/claude-api/python/claude-api/batches.md | ❌ |  | Arquivo markdown stub, sem lógica |
| src/skills/bundled/claude-api/python/claude-api/files-api.md | ❌ |  | Arquivo markdown stub, sem lógica |
| src/skills/bundled/claude-api/python/claude-api/streaming.md | ❌ |  | Arquivo markdown stub, sem lógica |
| src/skills/bundled/claude-api/python/claude-api/tool-use.md | ❌ |  | Arquivo markdown stub, sem lógica |
| src/skills/bundled/claude-api/ruby/claude-api.md | ❌ |  | Arquivo markdown stub, sem lógica |
| src/skills/bundled/claude-api/shared/error-codes.md | ❌ |  | Arquivo markdown stub, sem lógica |
| src/skills/bundled/claude-api/shared/live-sources.md | ❌ |  | Arquivo markdown stub, sem lógica |
| src/skills/bundled/claude-api/shared/models.md | ❌ |  | Arquivo markdown stub, sem lógica |
| src/skills/bundled/claude-api/shared/prompt-caching.md | ❌ |  | Arquivo markdown stub, sem lógica |
| src/skills/bundled/claude-api/shared/tool-use-concepts.md | ❌ |  | Arquivo markdown stub, sem lógica |
| src/skills/bundled/claude-api/typescript/agent-sdk/README.md | ❌ |  | Arquivo markdown stub, sem lógica |
| src/skills/bundled/claude-api/typescript/agent-sdk/patterns.md | ❌ |  | Arquivo markdown stub, sem lógica |
| src/skills/bundled/claude-api/typescript/claude-api/README.md | ❌ |  | Arquivo markdown stub, sem lógica |
| src/skills/bundled/claude-api/typescript/claude-api/batches.md | ❌ |  | Arquivo markdown stub, sem lógica |
| src/skills/bundled/claude-api/typescript/claude-api/files-api.md | ❌ |  | Arquivo markdown stub, sem lógica |
| src/skills/bundled/claude-api/typescript/claude-api/streaming.md | ❌ |  | Arquivo markdown stub, sem lógica |
| src/skills/bundled/claude-api/typescript/claude-api/tool-use.md | ❌ |  | Arquivo markdown stub, sem lógica |
| src/skills/bundled/claudeApi.ts | ⚠️ | packages/core/agent-core/src/skills/bundled/claudeApi.ts | Lógica de detecção linguagem, mas depende de Bun e fs |
| src/skills/bundled/claudeApiContent.ts | ❌ |  | Conteúdo .md injetado via Bun text loader |
| src/skills/bundled/claudeInChrome.ts | ❌ |  | Depende de browser e extensão Chrome |
| src/skills/bundled/debug.ts | ⚠️ | packages/core/agent-core/src/skills/bundled/debug.ts | Lógica debug útil, mas depende de fs/promises |
| src/skills/bundled/dream.ts | ❌ |  | Export default vazio, stub |
| src/skills/bundled/hunter.ts | ❌ |  | Export default vazio, stub |
| src/skills/bundled/index.ts | ⚠️ | packages/core/agent-core/src/skills/bundled/index.ts | Registro skills, mas depende de Bun e imports específicos |
| src/skills/bundled/keybindings.ts | ❌ |  | Relacionado a keybindings de terminal |
| src/skills/bundled/loop.ts | ✅ | packages/core/agent-core/src/skills/bundled/loop.ts | Lógica de agendamento de tarefas reutilizável |
| src/skills/bundled/loremIpsum.ts | ✅ | packages/core/agent-core/src/skills/bundled/loremIpsum.ts | Lista de palavras para tokenização, útil |
| src/skills/bundled/remember.ts | ✅ | packages/core/agent-core/src/skills/bundled/remember.ts | Lógica de memória e revisão aproveitável |
| src/skills/bundled/runSkillGenerator.ts | ❌ |  | Export default vazio, stub |
| src/skills/bundled/scheduleRemoteAgents.ts | ⚠️ | packages/core/agent-core/src/skills/bundled/scheduleRemoteAgents.ts | Lógica útil, mas depende de serviços específicos |
| src/skills/bundled/simplify.ts | ⚠️ | packages/core/agent-core/src/skills/bundled/simplify.ts | Possível lógica de simplificação, analisar conteúdo |
| src/skills/bundled/skillify.ts | ⚠️ | packages/core/agent-core/src/skills/bundled/skillify.ts | Possível lógica de skillify, analisar conteúdo |
| src/skills/bundled/stuck.ts | ⚠️ | packages/core/agent-core/src/skills/bundled/stuck.ts | Lógica de ajuda para bloqueios, analisar conteúdo |
| src/skills/bundled/updateConfig.ts | ⚠️ | packages/core/agent-core/src/skills/bundled/updateConfig.ts | Lógica de atualização config, analisar conteúdo |
| src/skills/bundled/verify.ts | ⚠️ | packages/core/agent-core/src/skills/bundled/verify.ts | Lógica de verificação, analisar conteúdo |
| src/skills/bundled/verify/SKILL.md | ❌ |  | Arquivo markdown stub |
| src/skills/bundled/verify/examples/cli.md | ❌ |  | Arquivo markdown stub |
| src/skills/bundled/verify/examples/server.md | ❌ |  | Arquivo markdown stub |
| src/skills/bundled/verifyContent.ts | ⚠️ | packages/core/agent-core/src/skills/bundled/verifyContent.ts | Conteúdo de verificação, analisar para adaptação |
| src/skills/bundledSkills.ts | ⚠️ | packages/core/agent-core/src/skills/bundledSkills.ts | Registro e utilitários, possível adaptação |
| src/skills/loadSkillsDir.ts | ⚠️ | packages/core/agent-core/src/skills/loadSkillsDir.ts | Lógica carregamento skills, depende fs |
| src/skills/mcpSkillBuilders.ts | ⚠️ | packages/core/agent-core/src/skills/mcpSkillBuilders.ts | Builders para MCP skills, analisar para adaptação |
| src/skills/mcpSkills.ts | ⚠️ | packages/core/agent-core/src/skills/mcpSkills.ts | Skills MCP, analisar para adaptação |
| src/commands/add-dir/add-dir.tsx | ❌ |  | UI terminal React/Ink, imports Box, Text, useEffect |
| src/commands/add-dir/index.ts | ✅ | packages/core/commands/add-dir/index.ts | Definição comando, lógica importável para Nexias |
| src/commands/add-dir/validation.ts | ✅ | packages/core/commands/add-dir/validation.ts | Validação diretórios, lógica reutilizável |
| src/commands/advisor.ts | ✅ | packages/core/commands/advisor.ts | Lógica negócio advisor, sem UI terminal |
| src/commands/agents/agents.tsx | ❌ |  | Componente React/Ink para terminal |
| src/commands/agents/index.ts | ✅ | packages/core/commands/agents/index.ts | Definição comando, lógica importável |
| src/commands/ant-trace/index.js | ❌ |  | Stub sem lógica real |
| src/commands/autofix-pr/index.js | ❌ |  | Stub sem lógica real |
| src/commands/backfill-sessions/index.js | ❌ |  | Stub sem lógica real |
| src/commands/branch/branch.ts | ⚠️ | packages/core/commands/branch/branch.ts | Lógica negócio branch, mas com deps fs/promises, precisa adaptação |
| src/commands/branch/index.ts | ✅ | packages/core/commands/branch/index.ts | Definição comando, lógica importável |
| src/commands/break-cache/index.js | ❌ |  | Stub sem lógica real |
| src/commands/bridge-kick.ts | ❌ |  | CLI bridge testing, terminal específico |
| src/commands/bridge/bridge.tsx | ❌ |  | UI terminal React/Ink, uso hooks e Box/Text |
| src/commands/bridge/index.ts | ⚠️ | packages/core/commands/bridge/index.ts | Lógica habilitação bridge, mas usa bun:bundle, precisa adaptação |
| src/commands/brief.ts | ✅ | packages/core/commands/brief.ts | Lógica negócio, sem UI terminal |
| src/commands/btw/btw.tsx | ❌ |  | UI terminal React/Ink, imports Box, Text, hooks |
| src/commands/btw/index.ts | ✅ | packages/core/agent-core/src/commands/btw/index.ts | Comando local, lógica de negócio aproveitável |
| src/commands/buddy/index.ts | ❌ |  | Stub vazio, sem lógica |
| src/commands/bughunter/index.js | ❌ |  | Stub sem funcionalidade real |
| src/commands/chrome/chrome.tsx | ❌ |  | UI React/Ink para terminal/desktop |
| src/commands/chrome/index.ts | ✅ | packages/core/agent-core/src/commands/chrome/index.ts | Comando local, lógica de negócio aproveitável |
| src/commands/clear/caches.ts | ⚠️ | packages/core/agent-core/src/commands/clear/caches.ts | Usa Bun e estado local, requer adaptação |
| src/commands/clear/clear.ts | ✅ | packages/core/agent-core/src/commands/clear/clear.ts | Lógica de negócio clara e reutilizável |
| src/commands/clear/conversation.ts | ⚠️ | packages/core/agent-core/src/commands/clear/conversation.ts | Depende de Bun e estado, adaptação necessária |
| src/commands/clear/index.ts | ✅ | packages/core/agent-core/src/commands/clear/index.ts | Metadata comando, lógica reaproveitável |
| src/commands/color/color.ts | ✅ | packages/core/agent-core/src/commands/color/color.ts | Lógica de negócio para cores reaproveitável |
| src/commands/color/index.ts | ✅ | packages/core/agent-core/src/commands/color/index.ts | Metadata comando, lógica reaproveitável |
| src/commands/commit-push-pr.ts | ✅ | packages/core/agent-core/src/commands/commit-push-pr.ts | Lógica de negócio para git e PR útil |
| src/commands/commit.ts | ✅ | packages/core/agent-core/src/commands/commit.ts | Lógica de negócio para commit git útil |
| src/commands/compact/compact.ts | ⚠️ | packages/core/agent-core/src/commands/compact/compact.ts | Usa Bun e estado, precisa adaptação |
| src/commands/compact/index.ts | ✅ | packages/core/agent-core/src/commands/compact/index.ts | Metadata comando, lógica reaproveitável |
| src/commands/config/config.tsx | ❌ |  | UI React/Ink para terminal/desktop |
| src/commands/config/index.ts | ✅ | packages/core/agent-core/src/commands/config/index.ts | Metadata comando, lógica reaproveitável |
| src/commands/context/context-noninteractive.ts | ✅ | packages/core/agent-core/src/commands/context/context-noninteractive.ts | Lógica de negócio sem UI, aproveitável |
| src/commands/context/context.tsx | ❌ |  | UI React/Ink para terminal/desktop |
| src/commands/context/index.ts | ⚠️ | packages/core/agent-core/src/commands/context/index.ts | Metadata comando, possível adaptação |
| src/commands/copy/copy.tsx | ❌ |  | UI terminal React/Ink, clipboard, terminal deps |
| src/commands/copy/index.ts | ✅ | packages/core/commands/src/copy/index.ts | Metadata comando, lazy load, lógica reutilizável |
| src/commands/cost/cost.ts | ✅ | packages/core/commands/src/cost/cost.ts | Lógica negócio custo, sem UI, adaptável |
| src/commands/cost/index.ts | ✅ | packages/core/commands/src/cost/index.ts | Metadata comando, lógica habilitação útil |
| src/commands/createMovedToPluginCommand.ts | ✅ | packages/core/commands/src/createMovedToPluginCommand.ts | Tipos e lógica comando plugin reutilizável |
| src/commands/ctx_viz/index.js | ❌ |  | Stub sem lógica real |
| src/commands/debug-tool-call/index.js | ❌ |  | Stub sem lógica real |
| src/commands/desktop/desktop.tsx | ❌ |  | UI React para desktop app, não web |
| src/commands/desktop/index.ts | ❌ |  | Plataforma desktop específica, CLI/desktop |
| src/commands/diff/diff.tsx | ❌ |  | UI React/Ink para terminal |
| src/commands/diff/index.ts | ✅ | packages/core/commands/src/diff/index.ts | Metadata comando, lazy load, lógica útil |
| src/commands/doctor/doctor.tsx | ❌ |  | UI React/Ink para terminal |
| src/commands/doctor/index.ts | ✅ | packages/core/commands/src/doctor/index.ts | Metadata comando, lógica habilitação útil |
| src/commands/effort/effort.tsx | ❌ |  | UI React/Ink, hooks, estado app terminal |
| src/commands/effort/index.ts | ✅ | packages/core/commands/src/effort/index.ts | Metadata comando, lógica habilitação útil |
| src/commands/env/index.js | ❌ |  | Stub sem lógica real |
| src/commands/exit/exit.tsx | ❌ |  | UI React/Ink, terminal, Bun, CLI deps |
| src/commands/exit/index.ts | ❌ |  | (não listado, presumido similar exit.tsx) |
| src/commands/export/export.tsx | ❌ |  | UI React/Ink, terminal, CLI deps |
| src/commands/export/index.ts | ✅ | packages/core/commands/src/export/index.ts | Metadata comando, lazy load, lógica útil |
| src/commands/extra-usage/extra-usage-core.ts | ✅ | packages/core/agent-core/src/commands/extra-usage-core.ts | Lógica negócio reutilizável, sem UI |
| src/commands/extra-usage/extra-usage-noninteractive.ts | ✅ | packages/core/agent-core/src/commands/extra-usage-noninteractive.ts | Lógica negócio reutilizável, sem UI |
| src/commands/extra-usage/extra-usage.tsx | ❌ |  | React/Ink UI para terminal |
| src/commands/extra-usage/index.ts | ✅ | packages/core/agent-core/src/commands/extra-usage-index.ts | Lógica ativação comando, sem UI |
| src/commands/fast/fast.tsx | ❌ |  | React/Ink UI para terminal |
| src/commands/fast/index.ts | ✅ | packages/core/agent-core/src/commands/fast-index.ts | Lógica comando, sem UI |
| src/commands/feedback/feedback.tsx | ❌ |  | React/Ink UI para terminal |
| src/commands/feedback/index.ts | ✅ | packages/core/agent-core/src/commands/feedback-index.ts | Lógica comando, sem UI |
| src/commands/files/files.ts | ✅ | packages/core/agent-core/src/commands/files.ts | Lógica negócio listagem arquivos |
| src/commands/files/index.ts | ✅ | packages/core/agent-core/src/commands/files-index.ts | Lógica comando, sem UI |
| src/commands/force-snip.ts | ❌ |  | Stub vazio |
| src/commands/fork/index.ts | ❌ |  | Stub vazio |
| src/commands/good-claude/index.js | ❌ |  | Stub vazio |
| src/commands/heapdump/heapdump.ts | ✅ | packages/core/agent-core/src/commands/heapdump.ts | Lógica negócio heapdump reutilizável |
| src/commands/heapdump/index.ts | ✅ | packages/core/agent-core/src/commands/heapdump-index.ts | Lógica comando, sem UI |
| src/commands/help/help.tsx | ❌ |  | React/Ink UI para terminal |
| src/commands/help/index.ts | ✅ | packages/core/agent-core/src/commands/help-index.ts | Lógica comando, sem UI |
| src/commands/hooks/hooks.tsx | ❌ |  | React/Ink UI para terminal |
| src/commands/hooks/index.ts | ⚠️ | packages/core/agent-core/src/commands/hooks-index.ts | Conceito útil, mas React UI e lógica misturadas |
| src/commands/ide/ide.tsx | ❌ |  | React/Ink UI para terminal |
| src/commands/ide/index.ts | ✅ | packages/core/agent-core/src/commands/ide/index.ts | Comando CLI com lógica de negócio reaproveitável |
| src/commands/init-verifiers.ts | ✅ | packages/core/agent-core/src/commands/init-verifiers.ts | Lógica de criação de skills para verificação automática |
| src/commands/init.ts | ✅ | packages/core/agent-core/src/commands/init.ts | Inicialização e onboarding do projeto, lógica útil |
| src/commands/insights.ts | ✅ | packages/core/agent-core/src/commands/insights.ts | Execução de comandos e análise, lógica reaproveitável |
| src/commands/install-github-app/ApiKeyStep.tsx | ❌ |  | UI terminal React/Ink, não aplicável para web |
| src/commands/install-github-app/CheckExistingSecretStep.tsx | ❌ |  | UI terminal React/Ink, não aplicável para web |
| src/commands/install-github-app/CheckGitHubStep.tsx | ❌ |  | UI terminal React/Ink, componente React para terminal |
| src/commands/install-github-app/ChooseRepoStep.tsx | ❌ |  | UI terminal React/Ink, componente React para terminal |
| src/commands/install-github-app/CreatingStep.tsx | ❌ |  | UI terminal React/Ink, componente React para terminal |
| src/commands/install-github-app/ErrorStep.tsx | ❌ |  | UI terminal React/Ink, componente React para terminal |
| src/commands/install-github-app/ExistingWorkflowStep.tsx | ❌ |  | UI terminal React/Ink, componente React para terminal |
| src/commands/install-github-app/InstallAppStep.tsx | ❌ |  | UI terminal React/Ink, componente React para terminal |
| src/commands/install-github-app/OAuthFlowStep.tsx | ❌ |  | UI terminal React/Ink, componente React para terminal |
| src/commands/install-github-app/SuccessStep.tsx | ❌ |  | UI terminal React/Ink, componente React para terminal |
| src/commands/install-github-app/WarningsStep.tsx | ❌ |  | UI terminal React/Ink, componente React para terminal |
| src/commands/install-github-app/index.ts | ✅ | packages/core/agent-core/src/commands/install-github-app/index.ts | Comando CLI, lógica de negócio reaproveitável |
| src/commands/install-github-app/install-github-app.tsx | ❌ |  | UI terminal React/Ink, componente React para terminal |
| src/commands/install-github-app/setupGitHubActions.ts | ✅ | packages/core/agent-core/src/commands/install-github-app/setupGitHubActions.ts | Lógica para setup de GitHub Actions, útil |
| src/commands/install-slack-app/index.ts | ✅ | packages/core/agent-core/src/commands/install-slack-app/index.ts | Comando CLI, lógica reaproveitável |
| src/commands/install-slack-app/install-slack-app.ts | ✅ | packages/core/agent-core/src/commands/install-slack-app/install-slack-app.ts | Lógica de instalação Slack App, aproveitável |
| src/commands/install.tsx | ❌ |  | UI terminal React/Ink, CLI específico |
| src/commands/issue/index.js | ❌ |  | Stub sem lógica real |
| src/commands/keybindings/index.ts | ❌ |  | CLI keybindings, terminal específico |
| src/commands/keybindings/keybindings.ts | ❌ |  | CLI keybindings, fs e editor CLI |
| src/commands/login/index.ts | ✅ | packages/core/agent-core/src/commands/login/index.ts | Lógica comando login, sem UI terminal |
| src/commands/login/login.tsx | ❌ |  | React/Ink UI terminal, CLI específico |
| src/commands/logout/index.ts | ✅ | packages/core/agent-core/src/commands/logout/index.ts | Lógica comando logout, sem UI terminal |
| src/commands/logout/logout.tsx | ❌ |  | React/Ink UI terminal, CLI específico |
| src/commands/mcp/addCommand.ts | ⚠️ | packages/core/agent-core/src/commands/mcp/addCommand.ts | Lógica MCP CLI, requer adaptação |
| src/commands/mcp/index.ts | ✅ | packages/core/agent-core/src/commands/mcp/index.ts | Registro comando MCP, sem UI |
| src/commands/mcp/mcp.tsx | ❌ |  | React/Ink UI terminal, MCP estado UI |
| src/commands/mcp/xaaIdpCommand.ts | ✅ | packages/core/agent-core/src/commands/mcp/xaaIdpCommand.ts | Lógica MCP IdP, sem UI terminal |
| src/commands/memory/index.ts | ✅ | packages/core/agent-core/src/commands/memory/index.ts | Registro comando memory, sem UI |
| src/commands/memory/memory.tsx | ❌ |  | React/Ink UI terminal, CLI específico |
| src/commands/mobile/index.ts | ✅ | packages/core/agent-core/src/commands/mobile/index.ts | Registro comando mobile, sem UI |
| src/commands/mobile/mobile.tsx | ❌ |  | React/Ink UI terminal, QR code CLI |
| src/commands/mock-limits/index.js | ❌ |  | Stub sem lógica real |
| src/commands/model/index.ts | ✅ | packages/core/agent-core/src/commands/model/index.ts | Registro comando model, sem UI |
| src/commands/model/model.tsx | ❌ |  | React/Ink UI terminal, CLI específico |
| src/commands/onboarding/index.js | ❌ |  | Stub sem lógica útil |
| src/commands/output-style/index.ts | ✅ | packages/core/agent-core/src/commands/output-style/index.ts | Comando com lógica mínima, pode ser adaptado |
| src/commands/passes/index.ts | ⚠️ | packages/core/agent-core/src/commands/passes/index.ts | Usa lógica de referral, precisa adaptação |
| src/commands/passes/passes.tsx | ❌ |  | React/Ink UI para terminal |
| src/commands/peers/index.ts | ❌ |  | Export vazio, sem lógica |
| src/commands/perf-issue/index.js | ❌ |  | Stub sem lógica útil |
| src/commands/permissions/index.ts | ✅ | packages/core/agent-core/src/commands/permissions/index.ts | Comando com lógica carregável |
| src/commands/permissions/permissions.tsx | ❌ |  | React/Ink UI para terminal |
| src/commands/plan/index.ts | ✅ | packages/core/agent-core/src/commands/plan/index.ts | Comando com lógica carregável |
| src/commands/plan/plan.tsx | ❌ |  | React/Ink UI para terminal |
| src/commands/plugin/AddMarketplace.tsx | ❌ |  | React/Ink UI para terminal |
| src/commands/plugin/BrowseMarketplace.tsx | ❌ |  | React/Ink UI para terminal |
| src/commands/plugin/DiscoverPlugins.tsx | ❌ |  | React/Ink UI para terminal |
| src/commands/plugin/ManageMarketplaces.tsx | ❌ |  | React/Ink UI para terminal |
| src/commands/plugin/ManagePlugins.tsx | ❌ |  | React/Ink UI para terminal |
| src/commands/plugin/PluginErrors.tsx | ❌ |  | React/Ink UI para terminal |
| src/commands/plugin/PluginOptionsDialog.tsx | ❌ |  | React/Ink UI para terminal |
| src/commands/plugin/PluginOptionsFlow.tsx | ❌ |  | React/Ink UI para terminal |
| src/commands/plugin/PluginSettings.tsx | ❌ |  | React/Ink UI para terminal |
| src/commands/plugin/PluginTrustWarning.tsx | ❌ |  | UI terminal Ink React |
| src/commands/plugin/UnifiedInstalledCell.tsx | ❌ |  | UI terminal Ink React |
| src/commands/plugin/ValidatePlugin.tsx | ❌ |  | UI terminal Ink React |
| src/commands/plugin/index.tsx | ✅ | packages/core/commands/src/plugin/index.ts | Registro comando, lógica aproveitável |
| src/commands/plugin/parseArgs.ts | ✅ | packages/core/commands/src/plugin/parseArgs.ts | Parsing args sem UI |
| src/commands/plugin/plugin.tsx | ❌ |  | React component UI terminal |
| src/commands/plugin/pluginDetailsHelpers.tsx | ❌ |  | UI terminal Ink React |
| src/commands/plugin/usePagination.ts | ✅ | packages/core/utils/src/usePagination.ts | Hook pagination reutilizável |
| src/commands/pr_comments/index.ts | ✅ | packages/core/plugins/pr-comments/index.ts | Lógica negócio plugin CLI |
| src/commands/privacy-settings/index.ts | ✅ | packages/core/commands/src/privacy-settings/index.ts | Registro comando, lógica aproveitável |
| src/commands/privacy-settings/privacy-settings.tsx | ❌ |  | React UI terminal Ink |
| src/commands/rate-limit-options/index.ts | ✅ | packages/core/commands/src/rate-limit-options/index.ts | Registro comando, lógica aproveitável |
| src/commands/rate-limit-options/rate-limit-options.tsx | ❌ |  | React UI terminal Ink |
| src/commands/release-notes/index.ts | ✅ | packages/core/commands/src/release-notes/index.ts | Registro comando, lógica aproveitável |
| src/commands/release-notes/release-notes.ts | ⚠️ | packages/core/commands/src/release-notes/release-notes.ts | Possível lógica negócio, reescrita necessária |
| src/commands/reload-plugins/index.ts | ⚠️ | packages/core/commands/src/reload-plugins/index.ts | Registro comando, possível adaptação |
| src/commands/reload-plugins/reload-plugins.ts | ⚠️ | packages/core/commands/src/reload-plugins/reload-plugins.ts | Lógica negócio, reescrita provável |
| src/commands/remote-env/index.ts | ⚠️ | packages/core/commands/src/remote-env/index.ts | Registro comando, adaptação necessária |
| src/commands/remote-env/remote-env.tsx | ❌ |  | React UI terminal Ink |
| src/commands/remote-setup/api.ts | ✅ | packages/core/agent-core/src/commands/remote-setup/api.ts | Lógica API reutilizável, sem UI ou CLI específica |
| src/commands/remote-setup/index.ts | ✅ | packages/core/agent-core/src/commands/remote-setup/index.ts | Registro comando, lógica de feature flag útil |
| src/commands/remote-setup/remote-setup.tsx | ❌ |  | UI React/Ink para terminal, não aplicável web serverless |
| src/commands/remoteControlServer/index.ts | ❌ |  | Exporta objeto vazio, sem lógica útil |
| src/commands/rename/generateSessionName.ts | ✅ | packages/core/agent-core/src/commands/rename/generateSessionName.ts | Lógica negócio para gerar nome sessão aproveitável |
| src/commands/rename/index.ts | ✅ | packages/core/agent-core/src/commands/rename/index.ts | Registro comando, padrão reutilizável |
| src/commands/rename/rename.ts | ⚠️ | packages/core/agent-core/src/commands/rename/rename.ts | Lógica negócio, mas depende de bridge e state específicos |
| src/commands/reset-limits/index.js | ❌ |  | Stub sem lógica real |
| src/commands/resume/index.ts | ✅ | packages/core/agent-core/src/commands/resume/index.ts | Registro comando, padrão reutilizável |
| src/commands/resume/resume.tsx | ❌ |  | UI React/Ink para terminal, não aplicável web serverless |
| src/commands/review.ts | ⚠️ | packages/core/agent-core/src/commands/review.ts | Definição comando e prompt, mas CLI específico |
| src/commands/review/UltrareviewOverageDialog.tsx | ❌ |  | UI React/Ink para terminal, não aplicável web serverless |
| src/commands/review/reviewRemote.ts | ✅ | packages/core/agent-core/src/commands/review/reviewRemote.ts | Lógica negócio para execução remota aproveitável |
| src/commands/review/ultrareviewCommand.tsx | ❌ |  | UI React/Ink para terminal, não aplicável web serverless |
| src/commands/review/ultrareviewEnabled.ts | ✅ | packages/core/agent-core/src/commands/review/ultrareviewEnabled.ts | Lógica feature flag reutilizável |
| src/commands/rewind/index.ts | ✅ | packages/core/agent-core/src/commands/rewind/index.ts | Registro comando, padrão reutilizável |
| src/commands/rewind/rewind.ts | ✅ | packages/core/agent-core/src/commands/rewind/rewind.ts | Lógica negócio simples, aproveitável |
| src/commands/sandbox-toggle/index.ts | ⚠️ | packages/core/agent-core/src/commands/sandbox-toggle/index.ts | Registro comando, depende sandbox adapter específico |
| src/commands/sandbox-toggle/sandbox-toggle.tsx | ❌ |  | UI React/Ink para terminal, não aplicável web serverless |
| src/commands/security-review.ts | ⚠️ | packages/core/agent-core/src/commands/security-review.ts | Possível lógica negócio, mas não detalhado aqui |
| src/commands/session/index.ts   | ✅     | packages/core/agent-core/src/commands/session/index.ts | Lógica comando, sem UI terminal            |
| src/commands/session/session.tsx| ❌     |                                          | Usa React/Ink UI terminal                   |
| src/commands/share/index.js     | ❌     |                                          | Stub sem lógica                             |
| src/commands/skills/index.ts    | ✅     | packages/core/agent-core/src/commands/skills/index.ts | Lógica comando, sem UI terminal            |
| src/commands/skills/skills.tsx  | ❌     |                                          | Componente React/Ink UI terminal           |
| src/commands/stats/index.ts     | ✅     | packages/core/agent-core/src/commands/stats/index.ts | Lógica comando, sem UI terminal            |
| src/commands/stats/stats.tsx    | ❌     |                                          | Componente React/Ink UI terminal           |
| src/commands/status/index.ts    | ✅     | packages/core/agent-core/src/commands/status/index.ts | Lógica comando, sem UI terminal            |
| src/commands/status/status.tsx  | ❌     |                                          | Componente React/Ink UI terminal           |
| src/commands/statusline.tsx     | ⚠️     | packages/core/agent-core/src/commands/statusline.ts | Lógica prompt útil, mas precisa adaptação  |
| src/commands/stickers/index.ts  | ✅     | packages/core/agent-core/src/commands/stickers/index.ts | Lógica comando, sem UI terminal            |
| src/commands/stickers/stickers.ts| ✅    | packages/core/agent-core/src/commands/stickers/stickers.ts | Lógica negócio abrir browser                |
| src/commands/summary/index.js   | ❌     |                                          | Stub sem lógica                             |
| src/commands/tag/index.ts       | ✅     | packages/core/agent-core/src/commands/tag/index.ts | Lógica comando, sem UI terminal            |
| src/commands/tag/tag.tsx        | ❌     |                                          | Componente React/Ink UI terminal           |
| src/commands/tasks/index.ts     | ✅     | packages/core/agent-core/src/commands/tasks/index.ts | Lógica comando, sem UI terminal            |
| src/commands/tasks/tasks.tsx    | ❌     |                                          | Componente React/Ink UI terminal           |
| src/commands/teleport/index.js  | ❌     |                                          | Stub sem lógica                             |
| src/commands/terminalSetup/index.ts | ✅ | packages/core/agent-core/src/commands/terminalSetup/index.ts | Lógica utilitária, sem UI terminal         |
| src/commands/terminalSetup/terminalSetup.tsx | ❌ |  | CLI/terminal setup, uso de chalk, fs, os, não web serverless |
| src/commands/theme/index.ts | ✅ | packages/core/commands/src/theme/index.ts | Registro comando, lógica aproveitável, sem UI |
| src/commands/theme/theme.tsx | ❌ |  | React/Ink UI para terminal |
| src/commands/thinkback-play/index.ts | ✅ | packages/core/commands/src/thinkback-play/index.ts | Registro comando, lógica negócio útil |
| src/commands/thinkback-play/thinkback-play.ts | ✅ | packages/core/commands/src/thinkback-play/thinkback-play.ts | Lógica de negócio para animação, sem UI |
| src/commands/thinkback/index.ts | ✅ | packages/core/commands/src/thinkback/index.ts | Registro comando, lógica negócio |
| src/commands/thinkback/thinkback.tsx | ❌ |  | React/Ink UI para terminal |
| src/commands/ultraplan.tsx | ❌ |  | React/Ink UI e lógica específica desktop/CLI |
| src/commands/upgrade/index.ts | ✅ | packages/core/commands/src/upgrade/index.ts | Registro comando, lógica negócio |
| src/commands/upgrade/upgrade.tsx | ❌ |  | React UI para terminal |
| src/commands/usage/index.ts | ✅ | packages/core/commands/src/usage/index.ts | Registro comando, lógica negócio |
| src/commands/usage/usage.tsx | ❌ |  | React UI para terminal |
| src/commands/version.ts | ✅ | packages/core/commands/src/version.ts | Lógica simples, sem UI, útil para Nexias |
| src/commands/vim/index.ts | ❌ |  | CLI/terminal, toggle modo vim, não web serverless |
| src/commands/vim/vim.ts | ❌ |  | Configuração global CLI, modo vim, não web serverless |
| src/commands/voice/index.ts | ❌ |  | CLI/terminal, voice native, não web serverless |
| src/commands/voice/voice.ts | ❌ |  | CLI/terminal, voice native, não web serverless |
| src/keybindings/KeybindingContext.tsx | ❌ |  | React/Ink terminal UI context |
| src/keybindings/KeybindingProviderSetup.tsx | ❌ |  | React/Ink terminal UI and hooks |
| src/keybindings/defaultBindings.ts | ✅ | packages/core/agent-core/src/keybindings/defaultBindings.ts | Default keybindings logic, no UI deps |
| src/keybindings/loadUserBindings.ts | ⚠️ | packages/core/agent-core/src/keybindings/loadUserBindings.ts | FS watcher, user config loader, needs adaptation |
| src/keybindings/match.ts | ✅ | packages/core/agent-core/src/keybindings/match.ts | Pure matching logic, no UI deps |
| src/keybindings/parser.ts | ✅ | packages/core/agent-core/src/keybindings/parser.ts | Parsing keystrokes, pure logic |
| src/keybindings/reservedShortcuts.ts | ✅ | packages/core/agent-core/src/keybindings/reservedShortcuts.ts | Reserved shortcuts data and logic |
| src/keybindings/resolver.ts | ✅ | packages/core/agent-core/src/keybindings/resolver.ts | Keybinding resolution logic |
| src/keybindings/schema.ts | ✅ | packages/core/agent-core/src/keybindings/schema.ts | Zod schema for validation |
| src/keybindings/shortcutFormat.ts | ⚠️ | packages/core/agent-core/src/keybindings/shortcutFormat.ts | Analytics and fallback logic, partial reuse |
| src/keybindings/template.ts | ✅ | packages/core/agent-core/src/keybindings/template.ts | Template generation logic |
| src/keybindings/useKeybinding.ts | ❌ |  | React/Ink hook for terminal input |
| src/keybindings/useShortcutDisplay.ts | ❌ |  | React hook for shortcut display |
| src/keybindings/validate.ts | ✅ | packages/core/agent-core/src/keybindings/validate.ts | Validation logic for keybindings |
| src/hooks/fileSuggestions.ts | ✅ | packages/core/agent-core/src/hooks/fileSuggestions.ts | Lógica de sugestão de arquivos, sem UI ou deps CLI |
| src/hooks/notifs/useAutoModeUnavailableNotification.ts | ❌ |  | Usa React, hooks e contexto UI de notificações |
| src/hooks/notifs/useCanSwitchToExistingSubscription.tsx | ❌ |  | React + Ink UI, hook de notificação para terminal |
| src/hooks/notifs/useDeprecationWarningNotification.tsx | ❌ |  | React + Ink UI para notificações no terminal |
| src/hooks/notifs/useFastModeNotification.tsx | ❌ |  | React + Ink UI, notificações específicas de app |
| src/hooks/notifs/useIDEStatusIndicator.tsx | ❌ |  | React + Ink UI, indicador status IDE no terminal |
| src/hooks/notifs/useInstallMessages.tsx | ❌ |  | React hook para notificações UI terminal |
| src/hooks/notifs/useLspInitializationNotification.tsx | ❌ |  | React + Ink UI, notificações LSP no terminal |
| src/hooks/notifs/useMcpConnectivityStatus.tsx | ❌ |  | React + Ink UI, notificações MCP no terminal |
| src/hooks/notifs/useModelMigrationNotifications.tsx | ❌ |  | React hook para notificações UI terminal |
| src/hooks/notifs/useNpmDeprecationNotification.tsx | ❌ |  | React hook para notificações UI terminal |
| src/hooks/notifs/usePluginAutoupdateNotification.tsx | ❌ |  | React + Ink UI, notificações plugins no terminal |
| src/hooks/notifs/usePluginInstallationStatus.tsx | ❌ |  | React + Ink UI, notificações plugins no terminal |
| src/hooks/notifs/useRateLimitWarningNotification.tsx | ❌ |  | React + Ink UI, notificações UI terminal |
| src/hooks/notifs/useSettingsErrors.tsx | ❌ |  | React + Ink UI, notificações UI terminal |
| src/hooks/notifs/useStartupNotification.ts | ❌ |  | React hook para notificações UI terminal |
| src/hooks/notifs/useTeammateShutdownNotification.ts | ❌ |  | React + Ink UI, notificações UI terminal |
| src/hooks/renderPlaceholder.ts | ❌ |  | Provável componente React UI terminal |
| src/hooks/toolPermission/PermissionContext.ts | ✅ | packages/core/agent-core/src/hooks/toolPermission/PermissionContext.ts | Contexto de permissão, lógica reutilizável |
| src/hooks/toolPermission/handlers/coordinatorHandler.ts | ✅ | packages/core/agent-core/src/hooks/toolPermission/handlers/coordinatorHandler.ts | Handler lógico, sem UI |
| src/hooks/toolPermission/handlers/interactiveHandler.ts | ✅ | packages/core/agent-core/src/hooks/toolPermission/handlers/interactiveHandler.ts | Handler lógico, sem UI |
| src/hooks/toolPermission/handlers/swarmWorkerHandler.ts | ✅ | packages/core/agent-core/src/hooks/toolPermission/handlers/swarmWorkerHandler.ts | Handler lógico, sem UI |
| src/hooks/toolPermission/permissionLogging.ts | ✅ | packages/core/agent-core/src/hooks/toolPermission/permissionLogging.ts | Logging de permissão, lógica útil |
| src/hooks/unifiedSuggestions.ts | ✅ | packages/core/agent-core/src/hooks/unifiedSuggestions.ts | Lógica de sugestões, sem UI |
| src/hooks/useAfterFirstRender.ts | ✅ | packages/core/agent-core/src/hooks/useAfterFirstRender.ts | Hook utilitário React sem UI terminal |
| src/hooks/useApiKeyVerification.ts | ✅ | packages/core/agent-core/src/hooks/useApiKeyVerification.ts | Verificação lógica de API key |
| src/hooks/useArrowKeyHistory.tsx | ❌ |  | Usa React + Ink UI terminal |
| src/hooks/useAssistantHistory.ts | ✅ | packages/core/agent-core/src/hooks/useAssistantHistory.ts | Lógica de histórico, sem UI terminal |
| src/hooks/useAwaySummary.ts | ✅ | packages/core/agent-core/src/hooks/useAwaySummary.ts | Lógica de resumo, sem UI terminal |
| src/hooks/useBackgroundTaskNavigation.ts | ✅ | packages/core/agent-core/src/hooks/useBackgroundTaskNavigation.ts | Lógica de navegação, sem UI terminal |
| src/hooks/useBlink.ts | ✅ | packages/core/agent-core/src/hooks/useBlink.ts | Hook utilitário, sem UI terminal |
| src/hooks/useCanUseTool.tsx | ❌ |  | React + Ink UI terminal |
| src/hooks/useCancelRequest.ts | ✅ | packages/core/agent-core/src/hooks/useCancelRequest.ts | Lógica cancelamento requisição |
| src/hooks/useChromeExtensionNotification.tsx | ❌ |  | React + Ink UI terminal |
| src/hooks/useClaudeCodeHintRecommendation.tsx | ❌ |  | React + Ink UI terminal |
| src/hooks/useClipboardImageHint.ts | ✅ | packages/core/agent-core/src/hooks/useClipboardImageHint.ts | Lógica de dica, sem UI terminal |
| src/hooks/useCommandKeybindings.tsx | ❌ |  | Keybindings CLI/terminal específicos |
| src/hooks/useCommandQueue.ts | ✅ | packages/core/agent-core/src/hooks/useCommandQueue.ts | Lógica de fila de comandos |
| src/hooks/useCopyOnSelect.ts | ✅ | packages/core/agent-core/src/hooks/useCopyOnSelect.ts | Lógica utilitária, sem UI terminal |
| src/hooks/useDeferredHookMessages.ts | ✅ | packages/core/agent-core/src/hooks/useDeferredHookMessages.ts | Lógica de mensagens adiadas |
| src/hooks/useDiffData.ts | ✅ | packages/core/agent-core/src/hooks/useDiffData.ts | Lógica de diff, sem UI terminal |
| src/hooks/useDiffInIDE.ts | ✅ | packages/core/agent-core/src/hooks/useDiffInIDE.ts | Lógica integração IDE, sem UI terminal |
| src/hooks/useDirectConnect.ts | ✅ | packages/core/agent-core/src/hooks/useDirectConnect.ts | Lógica conexão direta |
| src/hooks/useDoublePress.ts | ✅ | packages/core/agent-core/src/hooks/useDoublePress.ts | Hook utilitário, sem UI terminal |
| src/hooks/useDynamicConfig.ts | ✅ | packages/core/agent-core/src/hooks/useDynamicConfig.ts | Lógica configuração dinâmica |
| src/hooks/useElapsedTime.ts | ✅ | packages/core/agent-core/src/hooks/useElapsedTime.ts | Hook utilitário tempo |
| src/hooks/useExitOnCtrlCD.ts | ✅ | packages/core/agent-core/src/hooks/useExitOnCtrlCD.ts | Lógica saída no Ctrl+C, sem UI |
| src/hooks/useExitOnCtrlCDWithKeybindings.ts | ❌ |  | Usa keybindings CLI/terminal |
| src/hooks/useFileHistorySnapshotInit.ts | ✅ | packages/core/agent-core/src/hooks/useFileHistorySnapshotInit.ts | Lógica snapshot histórico arquivos |
| src/hooks/useGlobalKeybindings.tsx | ❌ |  | Keybindings CLI/terminal específicos |
| src/hooks/useHistorySearch.ts | ✅ | packages/core/agent-core/src/hooks/useHistorySearch.ts | Lógica busca em histórico |
| src/hooks/useIDEIntegration.tsx | ❌ |  | React + Ink UI terminal |
| src/hooks/useIdeAtMentioned.ts | ✅ | packages/core/agent-core/src/hooks/useIdeAtMentioned.ts | Lógica menção IDE, sem UI terminal |
| src/hooks/useIdeConnectionStatus.ts | ✅ | packages/core/agent-core/src/hooks/useIdeConnectionStatus.ts | Lógica status conexão IDE |
| src/hooks/useIdeLogging.ts | ✅ | packages/core/agent-core/src/hooks/useIdeLogging.ts | Logging IDE, sem UI terminal |
| src/hooks/useIdeSelection.ts | ✅ | packages/core/agent-core/src/hooks/useIdeSelection.ts | Lógica seleção IDE |
| src/hooks/useInboxPoller.ts | ✅ | packages/core/agent-core/src/hooks/useInboxPoller.ts | Polling inbox, sem UI terminal |
| src/hooks/useInputBuffer.ts | ✅ | packages/core/agent-core/src/hooks/useInputBuffer.ts | Buffer de input, sem UI terminal |
| src/hooks/useIssueFlagBanner.ts | ✅ | packages/core/agent-core/src/hooks/useIssueFlagBanner.ts | Lógica banner de issues, sem UI terminal |
| src/hooks/useLogMessages.ts | ✅ | packages/core/agent-core/src/hooks/useLogMessages.ts | Lógica mensagens log |
| src/hooks/useLspPluginRecommendation.tsx | ❌ |  | React + Ink UI terminal |
| src/hooks/useMailboxBridge.ts | ✅ | packages/core/agent-core/src/hooks/useMailboxBridge.ts | Lógica bridge mailbox, sem UI terminal |
| src/hooks/useMainLoopModel.ts | ✅ | packages/core/agent-core/src/hooks/useMainLoopModel.ts | Lógica loop principal |
| src/hooks/useManagePlugins.ts | ✅ | packages/core/agent-core/src/hooks/useManagePlugins.ts | Lógica gerenciamento plugins |
| src/hooks/useMemoryUsage.ts | ✅ | packages/core/agent-core/src/hooks/useMemoryUsage.ts | Lógica uso memória |
| src/hooks/useMergedClients.ts | ✅ | packages/core/agent-core/src/hooks/useMergedClients.ts | Lógica clientes mesclados |
| src/hooks/useMergedCommands.ts | ✅ | packages/core/agent-core/src/hooks/useMergedCommands.ts | Lógica comandos mesclados |
| src/hooks/useMergedTools.ts | ✅ | packages/core/agent-core/src/hooks/useMergedTools.ts | Lógica ferramentas mescladas |
| src/hooks/useMinDisplayTime.ts | ✅ | packages/core/agent-core/src/hooks/useMinDisplayTime.ts | Hook utilitário tempo mínimo |
| src/hooks/useNotifyAfterTimeout.ts | ✅ | packages/core/agent-core/src/hooks/useNotifyAfterTimeout.ts | Hook utilitário notificações |
| src/hooks/useOfficialMarketplaceNotification.tsx | ❌ |  | React + Ink UI terminal |
| src/hooks/usePasteHandler.ts | ✅ | packages/core/agent-core/src/hooks/usePasteHandler.ts | Lógica handler de paste |
| src/hooks/usePluginRecommendationBase.tsx | ❌ |  | React + Ink UI terminal |
| src/hooks/usePrStatus.ts | ✅ | packages/core/agent-core/src/hooks/usePrStatus.ts | Lógica status PR |
| src/hooks/usePromptSuggestion.ts | ✅ | packages/core/agent-core/src/hooks/usePromptSuggestion.ts | Lógica sugestão prompt |
| src/hooks/usePromptsFromClaudeInChrome.tsx | ❌ |  | React + Ink UI terminal |
| src/hooks/useQueueProcessor.ts | ✅ | packages/core/agent-core/src/hooks/useQueueProcessor.ts | Lógica processamento fila |
| src/hooks/useRemoteSession.ts | ✅ | packages/core/agent-core/src/hooks/useRemoteSession.ts | Lógica sessão remota |
| src/hooks/useReplBridge.tsx | ❌ |  | React + Ink UI terminal |
| src/hooks/useSSHSession.ts | ✅ | packages/core/agent-core/src/hooks/useSSHSession.ts | Lógica sessão SSH |
| src/hooks/useScheduledTasks.ts | ✅ | packages/core/agent-core/src/hooks/useScheduledTasks.ts | Lógica tarefas agendadas |
| src/hooks/useSearchInput.ts | ✅ | packages/core/agent-core/src/hooks/useSearchInput.ts | Lógica input busca |
| src/hooks/useSessionBackgrounding.ts | ✅ | packages/core/agent-core/src/hooks/useSessionBackgrounding.ts | Lógica backgrounding sessão |
| src/hooks/useSettings.ts | ✅ | packages/core/agent-core/src/hooks/useSettings.ts | Lógica configurações |
| src/hooks/useSettingsChange.ts | ✅ | packages/core/agent-core/src/hooks/useSettingsChange.ts | Lógica mudança configurações |
| src/hooks/useSkillImprovementSurvey.ts | ✅ | packages/core/agent-core/src/hooks/useSkillImprovementSurvey.ts | Lógica pesquisa melhoria skill |
| src/hooks/useSkillsChange.ts | ✅ | packages/core/agent-core/src/hooks/useSkillsChange.ts | Lógica mudança skills |
| src/hooks/useSwarmInitialization.ts | ✅ | packages/core/agent-core/src/hooks/useSwarmInitialization.ts | Lógica inicialização swarm |
| src/hooks/useSwarmPermissionPoller.ts | ✅ | packages/core/agent-core/src/hooks/useSwarmPermissionPoller.ts | Poller permissão swarm |
| src/hooks/useTaskListWatcher.ts | ✅ | packages/core/agent-core/src/hooks/useTaskListWatcher.ts | Observador lista tarefas |
| src/hooks/useTasksV2.ts | ✅ | packages/core/agent-core/src/hooks/useTasksV2.ts | Lógica tarefas v2 |
| src/hooks/useTeammateViewAutoExit.ts | ✅ | packages/core/agent-core/src/hooks/useTeammateViewAutoExit.ts | Lógica auto exit teammate view |
| src/hooks/useTeleportResume.tsx | ❌ |  | React + Ink UI terminal |
| src/hooks/useTerminalSize.ts | ✅ | packages/core/agent-core/src/hooks/useTerminalSize.ts | Hook utilitário tamanho terminal |
| src/hooks/useTextInput.ts | ✅ | packages/core/agent-core/src/hooks/useTextInput.ts | Hook utilitário input texto |
| src/hooks/useTimeout.ts | ✅ | packages/core/agent-core/src/hooks/useTimeout.ts | Hook utilitário timeout |
| src/hooks/useTurnDiffs.ts | ✅ | packages/core/agent-core/src/hooks/useTurnDiffs.ts | Lógica diffs de turnos |
| src/hooks/useTypeahead.tsx | ❌ |  | React + Ink UI terminal |
| src/hooks/useUpdateNotification.ts | ✅ | packages/core/agent-core/src/hooks/useUpdateNotification.ts | Lógica notificações atualização |
| src/hooks/useVimInput.ts | ❌ |  | Input vim CLI/terminal específico |
| src/hooks/useVirtualScroll.ts | ✅ | packages/core/agent-core/src/hooks/useVirtualScroll.ts | Hook utilitário scroll virtual |
| src/hooks/useVoice.ts | ✅ | packages/core/agent-core/src/hooks/useVoice.ts | Lógica voz, sem UI terminal |
| src/hooks/useVoiceEnabled.ts | ✅ | packages/core/agent-core/src/hooks/useVoiceEnabled.ts | Lógica voz habilitada |
| src/hooks/useVoiceIntegration.tsx | ❌ |  | React + Ink UI terminal |
| src/ink/Ansi.tsx | ❌ |  | UI terminal React/Ink |
| src/ink/bidi.ts | ✅ | packages/core/agent-core/src/utils/bidi.ts | Bidi text reordering logic, no UI deps |
| src/ink/clearTerminal.ts | ⚠️ | packages/core/agent-core/src/utils/clearTerminal.ts | Terminal clearing logic, platform-specific, adapt |
| src/ink/colorize.ts | ⚠️ | packages/core/agent-core/src/utils/colorize.ts | Chalk color level tweaks, partial reuse |
| src/ink/components/AlternateScreen.tsx | ❌ |  | Terminal UI React/Ink component |
| src/ink/components/App.tsx | ❌ |  | Terminal UI React/Ink component |
| src/ink/components/AppContext.ts | ❌ |  | React context for Ink app UI |
| src/ink/components/Box.tsx | ❌ |  | Terminal UI React/Ink component |
| src/ink/components/Button.tsx | ❌ |  | Terminal UI React/Ink component |
| src/ink/components/ClockContext.tsx | ❌ |  | React context with hooks for UI |
| src/ink/components/CursorDeclarationContext.ts | ❌ |  | React context for terminal cursor UI |
| src/ink/components/ErrorOverview.tsx | ❌ |  | React UI component for error display |
| src/ink/components/Link.tsx | ❌ |  | Terminal UI React/Ink component |
| src/ink/components/Newline.tsx | ❌ |  | Terminal UI React/Ink component |
| src/ink/components/NoSelect.tsx | ❌ |  | Terminal UI React/Ink component |
| src/ink/components/RawAnsi.tsx | ❌ |  | Terminal UI React/Ink component |
| src/ink/components/ScrollBox.tsx | ❌ |  | Terminal UI React/Ink component |
| src/ink/components/Spacer.tsx | ❌ |  | Terminal UI React/Ink component |
| src/ink/components/StdinContext.tsx | ❌ |  | React context for terminal stdin UI |
| src/ink/components/TerminalFocusContext.tsx | ❌ |  | React context for terminal focus UI |
| src/ink/components/TerminalSizeContext.tsx | ❌ |  | React context for terminal size UI |
| src/ink/components/Text.tsx | ❌ |  | Terminal UI React/Ink component |
| src/ink/constants.ts | ✅ | packages/core/agent-core/src/constants.ts | Constants, likely reusable |
| src/ink/devtools.ts | ❌ |  | Devtools UI or debugging for Ink |
| src/ink/dom.ts | ⚠️ | packages/core/agent-core/src/utils/dom.ts | DOM abstractions, partial reuse possible |
| src/ink/events/click-event.ts | ⚠️ | packages/core/agent-core/src/events/click-event.ts | Event types, partial reuse |
| src/ink/events/dispatcher.ts | ⚠️ | packages/core/agent-core/src/events/dispatcher.ts | Event dispatching logic, adapt needed |
| src/ink/events/emitter.ts | ✅ | packages/core/agent-core/src/events/emitter.ts | Generic event emitter logic |
| src/ink/events/event-handlers.ts | ⚠️ | packages/core/agent-core/src/events/event-handlers.ts | Event handlers, partial reuse |
| src/ink/events/event.ts | ✅ | packages/core/agent-core/src/events/event.ts | Event base types and logic |
| src/ink/events/focus-event.ts | ⚠️ | packages/core/agent-core/src/events/focus-event.ts | Focus event types, partial reuse |
| src/ink/events/input-event.ts | ⚠️ | packages/core/agent-core/src/events/input-event.ts | Input event types, partial reuse |
| src/ink/events/keyboard-event.ts | ⚠️ | packages/core/agent-core/src/events/keyboard-event.ts | Keyboard event types, partial reuse |
| src/ink/events/terminal-event.ts | ⚠️ | packages/core/agent-core/src/events/terminal-event.ts | Terminal event types, partial reuse |
| src/ink/events/terminal-focus-event.ts | ⚠️ | packages/core/agent-core/src/events/terminal-focus-event.ts | Terminal focus event types, partial reuse |
| src/ink/focus.ts | ⚠️ | packages/core/agent-core/src/utils/focus.ts | Focus management logic, adapt needed |
| src/ink/frame.ts | ⚠️ | packages/core/agent-core/src/utils/frame.ts | Frame/tick logic, partial reuse |
| src/ink/get-max-width.ts | ✅ | packages/core/agent-core/src/utils/get-max-width.ts | Utility for max width calculation |
| src/ink/global.d.ts | ❌ |  | Type declarations only |
| src/ink/hit-test.ts | ⚠️ | packages/core/agent-core/src/utils/hit-test.ts | Hit testing logic, partial reuse |
| src/ink/hooks/use-animation-frame.ts | ❌ |  | React hook for UI |
| src/ink/hooks/use-app.ts | ❌ |  | React hook for Ink app UI |
| src/ink/hooks/use-declared-cursor.ts | ❌ |  | React hook for cursor UI |
| src/ink/hooks/use-input.ts | ❌ |  | React hook for terminal input |
| src/ink/hooks/use-interval.ts | ❌ |  | React hook for UI intervals |
| src/ink/hooks/use-search-highlight.ts | ❌ |  | React hook for UI highlighting |
| src/ink/hooks/use-selection.ts | ❌ |  | React hook for UI selection |
| src/ink/hooks/use-stdin.ts | ❌ |  | React hook for stdin UI |
| src/ink/hooks/use-tab-status.ts | ❌ |  | React hook for UI tab status |
| src/ink/hooks/use-terminal-focus.ts | ❌ |  | React hook for terminal focus UI |
| src/ink/hooks/use-terminal-title.ts | ❌ |  | React hook for terminal title UI |
| src/ink/hooks/use-terminal-viewport.ts | ❌ |  | React hook for terminal viewport UI |
| src/ink/ink.tsx | ❌ |  | Ink React UI root |
| src/ink/instances.ts | ⚠️ | packages/core/agent-core/src/instances.ts | Ink instance management, partial reuse |
| src/ink/layout/engine.ts | ⚠️ | packages/core/agent-core/src/layout/engine.ts | Layout engine, partial reuse |
| src/ink/layout/geometry.ts | ✅ | packages/core/agent-core/src/layout/geometry.ts | Geometry utils, reusable |
| src/ink/layout/node.ts | ⚠️ | packages/core/agent-core/src/layout/node.ts | Layout node logic, partial reuse |
| src/ink/layout/yoga.ts | ⚠️ | packages/core/agent-core/src/layout/yoga.ts | Yoga layout integration, partial reuse |
| src/ink/line-width-cache.ts | ✅ | packages/core/agent-core/src/utils/line-width-cache.ts | Cache for line width calculations |
| src/ink/log-update.ts | ⚠️ | packages/core/agent-core/src/utils/log-update.ts | Terminal log update logic, adapt needed |
| src/ink/measure-element.ts | ⚠️ | packages/core/agent-core/src/utils/measure-element.ts | Element measurement, partial reuse |
| src/ink/measure-text.ts | ✅ | packages/core/agent-core/src/utils/measure-text.ts | Text measurement utilities |
| src/ink/node-cache.ts | ⚠️ | packages/core/agent-core/src/utils/node-cache.ts | Node caching logic, partial reuse |
| src/ink/optimizer.ts | ⚠️ | packages/core/agent-core/src/utils/optimizer.ts | Optimization logic, partial reuse |
| src/ink/output.ts | ⚠️ | packages/core/agent-core/src/utils/output.ts | Output formatting, partial reuse |
| src/ink/parse-keypress.ts | ⚠️ | packages/core/agent-core/src/utils/parse-keypress.ts | Keypress parsing, partial reuse |
| src/ink/reconciler.ts | ❌ |  | Ink React reconciler UI |
| src/ink/render-border.ts | ⚠️ | packages/core/agent-core/src/utils/render-border.ts | Border rendering logic, partial reuse |
| src/ink/render-node-to-output.ts | ⚠️ | packages/core/agent-core/src/utils/render-node-to-output.ts | Node rendering logic, partial reuse |
| src/ink/render-to-screen.ts | ❌ |  | Terminal UI rendering |
| src/ink/renderer.ts | ❌ |  | Terminal UI rendering |
| src/ink/root.ts | ❌ |  | Ink React root UI |
| src/ink/screen.ts | ⚠️ | packages/core/agent-core/src/utils/screen.ts | Screen management logic, partial reuse |
| src/ink/searchHighlight.ts | ⚠️ | packages/core/agent-core/src/utils/searchHighlight.ts | Search highlight logic, partial reuse |
| src/ink/selection.ts | ⚠️ | packages/core/agent-core/src/utils/selection.ts | Selection logic, partial reuse |
| src/ink/squash-text-nodes.ts | ✅ | packages/core/agent-core/src/utils/squash-text-nodes.ts | Text node merging utility |
| src/ink/stringWidth.ts | ✅ | packages/core/agent-core/src/utils/stringWidth.ts | String width calculation utility |
| src/ink/styles.ts | ✅ | packages/core/agent-core/src/styles.ts | Styles definitions, reusable |
| src/ink/supports-hyperlinks.ts | ✅ | packages/core/agent-core/src/utils/supports-hyperlinks.ts | Hyperlink support detection |
| src/ink/tabstops.ts | ⚠️ | packages/core/agent-core/src/utils/tabstops.ts | Tab stop logic, partial reuse |
| src/ink/terminal-focus-state.ts | ⚠️ | packages/core/agent-core/src/utils/terminal-focus-state.ts | Terminal focus state logic |
| src/ink/terminal-querier.ts | ⚠️ | packages/core/agent-core/src/utils/terminal-querier.ts | Terminal querying logic |
| src/ink/terminal.ts | ⚠️ | packages/core/agent-core/src/utils/terminal.ts | Terminal abstraction logic |
| src/ink/termio.ts | ⚠️ | packages/core/agent-core/src/utils/termio.ts | Terminal IO utilities |
| src/ink/termio/ansi.ts | ⚠️ | packages/core/agent-core/src/utils/termio/ansi.ts | ANSI parsing utilities |
| src/ink/termio/csi.ts | ⚠️ | packages/core/agent-core/src/utils/termio/csi.ts | CSI escape sequences utilities |
| src/ink/termio/dec.ts | ⚠️ | packages/core/agent-core/src/utils/termio/dec.ts | DEC escape sequences utilities |
| src/ink/termio/esc.ts | ⚠️ | packages/core/agent-core/src/utils/termio/esc.ts | ESC escape sequences utilities |
| src/ink/termio/osc.ts | ⚠️ | packages/core/agent-core/src/utils/termio/osc.ts | OSC escape sequences utilities |
| src/ink/termio/parser.ts | ⚠️ | packages/core/agent-core/src/utils/termio/parser.ts | Terminal escape parser logic |
| src/ink/termio/sgr.ts | ⚠️ | packages/core/agent-core/src/utils/termio/sgr.ts | SGR escape sequences utilities |
| src/ink/termio/tokenize.ts | ⚠️ | packages/core/agent-core/src/utils/termio/tokenize.ts | Tokenizer for terminal input |
| src/ink/termio/types.ts | ✅ | packages/core/agent-core/src/utils/termio/types.ts | Terminal IO types definitions |
| src/ink/useTerminalNotification.ts | ❌ |  | React hook for terminal notifications |
| src/ink/warn.ts | ✅ | packages/core/agent-core/src/utils/warn.ts | Warning utilities |
| src/ink/widest-line.ts | ✅ | packages/core/agent-core/src/utils/widest-line.ts | Utility to find widest line |
| src/ink/wrap-text.ts | ✅ | packages/core/agent-core/src/utils/wrap-text.ts | Text wrapping utilities |
| src/ink/wrapAnsi.ts | ✅ | packages/core/agent-core/src/utils/wrap-ansi.ts | ANSI-aware text wrapping utilities |
| src/components/AgentProgressLine.tsx | ❌ |  | UI terminal com Ink |
| src/components/App.tsx | ❌ |  | UI terminal com Ink |
| src/components/ApproveApiKey.tsx | ❌ |  | UI terminal com Ink |
| src/components/AutoModeOptInDialog.tsx | ❌ |  | UI terminal com Ink |
| src/components/AutoUpdater.tsx | ⚠️ | packages/core/agent-core/src/utils/autoUpdater.ts | Lógica atualização útil, UI terminal para remover |
| src/components/AutoUpdaterWrapper.tsx | ❌ |  | UI terminal e Bun específico |
| src/components/AwsAuthStatusBox.tsx | ❌ |  | UI terminal com Ink |
| src/components/BaseTextInput.tsx | ❌ |  | UI terminal com Ink |
| src/components/BashModeProgress.tsx | ❌ |  | UI terminal com Ink |
| src/components/BridgeDialog.tsx | ❌ |  | UI terminal com Ink e keybindings |
| src/components/BypassPermissionsModeDialog.tsx | ❌ |  | UI terminal com Ink |
| src/components/ChannelDowngradeDialog.tsx | ❌ |  | UI terminal com Ink |
| src/components/ClaudeCodeHint/PluginHintMenu.tsx | ❌ |  | UI terminal com Ink |
| src/components/ClaudeInChromeOnboarding.tsx | ❌ |  | UI terminal com Ink |
| src/components/ClaudeMdExternalIncludesDialog.tsx | ❌ |  | UI terminal com Ink |
| src/components/ClickableImageRef.tsx | ❌ |  | UI terminal com Ink |
| src/components/CompactSummary.tsx | ❌ |  | UI terminal com Ink |
| src/components/ConfigurableShortcutHint.tsx | ❌ |  | UI terminal com Ink |
| src/components/ConsoleOAuthFlow.tsx | ❌ |  | UI terminal com Ink |
| src/components/ContextSuggestions.tsx | ❌ |  | UI terminal com Ink |
| src/components/ContextVisualization.tsx | ❌ |  | UI terminal React/Ink |
| src/components/CoordinatorAgentStatus.tsx | ❌ |  | UI terminal React/Ink |
| src/components/CostThresholdDialog.tsx | ❌ |  | UI terminal React/Ink |
| src/components/CtrlOToExpand.tsx | ❌ |  | UI terminal React/Ink |
| src/components/CustomSelect/SelectMulti.tsx | ❌ |  | UI terminal React/Ink |
| src/components/CustomSelect/index.ts | ❌ |  | Reexporta UI terminal |
| src/components/CustomSelect/option-map.ts | ✅ | packages/core/agent-core/src/utils/option-map.ts | Lógica utilitária sem UI |
| src/components/CustomSelect/select-input-option.tsx | ❌ |  | UI terminal React/Ink |
| src/components/CustomSelect/select-option.tsx | ❌ |  | UI terminal React/Ink |
| src/components/CustomSelect/select.tsx | ❌ |  | UI terminal React/Ink |
| src/components/CustomSelect/use-multi-select-state.ts | ❌ |  | Usa hooks React/Ink UI |
| src/components/CustomSelect/use-select-input.ts | ❌ |  | Usa hooks React/Ink UI |
| src/components/CustomSelect/use-select-navigation.ts | ⚠️ | packages/core/agent-core/src/hooks/use-select-navigation.ts | Lógica de navegação, reescrita para web |
| src/components/CustomSelect/use-select-state.ts | ⚠️ | packages/core/agent-core/src/hooks/use-select-state.ts | Estado seleção, reescrita para web |
| src/components/DesktopHandoff.tsx | ❌ |  | UI terminal React/Ink + desktop bridge |
| src/components/DesktopUpsell/DesktopUpsellStartup.tsx | ❌ |  | UI terminal React/Ink |
| src/components/DevBar.tsx | ❌ |  | UI terminal React/Ink |
| src/components/DevChannelsDialog.tsx | ❌ |  | UI terminal React/Ink |
| src/components/DiagnosticsDisplay.tsx | ❌ |  | UI terminal React/Ink |
| src/components/EffortCallout.tsx | ❌ |  | UI terminal React/Ink |
| src/components/EffortIndicator.ts | ✅ | packages/core/agent-core/src/utils/effortIndicator.ts | Lógica de negócio reutilizável, sem UI terminal |
| src/components/ExitFlow.tsx | ❌ |  | Componente React para terminal, UI específica Ink |
| src/components/ExportDialog.tsx | ❌ |  | UI terminal com Ink, uso de terminal-specific hooks |
| src/components/FallbackToolUseErrorMessage.tsx | ❌ |  | Componente React Ink para terminal |
| src/components/FallbackToolUseRejectedMessage.tsx | ❌ |  | Componente React Ink para terminal |
| src/components/FastIcon.tsx | ❌ |  | UI terminal com Ink e React |
| src/components/Feedback.tsx | ❌ |  | Componente React Ink, UI terminal |
| src/components/FeedbackSurvey/FeedbackSurvey.tsx | ❌ |  | Componente React Ink para terminal |
| src/components/FeedbackSurvey/FeedbackSurveyView.tsx | ❌ |  | Componente React Ink para terminal |
| src/components/FeedbackSurvey/TranscriptSharePrompt.tsx | ❌ |  | Componente React Ink para terminal |
| src/components/FeedbackSurvey/submitTranscriptShare.ts | ✅ | packages/core/agent-core/src/services/feedback/submitTranscriptShare.ts | Lógica de negócio para envio, sem UI |
| src/components/FeedbackSurvey/useDebouncedDigitInput.ts | ✅ | packages/core/agent-core/src/hooks/useDebouncedDigitInput.ts | Hook React sem UI terminal, lógica reutilizável |
| src/components/FeedbackSurvey/useFeedbackSurvey.tsx | ❌ |  | Hook React com dependências de Ink/terminal UI |
| src/components/FeedbackSurvey/useMemorySurvey.tsx | ⚠️ | packages/core/agent-core/src/hooks/useMemorySurvey.ts | Hook React, lógica valiosa, reescrita necessária |
| src/components/FeedbackSurvey/usePostCompactSurvey.tsx | ⚠️ | packages/core/agent-core/src/hooks/usePostCompactSurvey.ts | Hook React, lógica valiosa, reescrita necessária |
| src/components/FeedbackSurvey/useSurveyState.tsx | ⚠️ | packages/core/agent-core/src/hooks/useSurveyState.ts | Hook React, lógica valiosa, reescrita necessária |
| src/components/FileEditToolDiff.tsx | ❌ |  | Componente React Ink para terminal |
| src/components/FileEditToolUpdatedMessage.tsx | ❌ |  | Componente React Ink para terminal |
| src/components/FileEditToolUseRejectedMessage.tsx | ❌ |  | Componente React Ink para terminal |
| src/components/FilePathLink.tsx | ❌ |  | Componente React Ink para terminal |
| src/components/FullscreenLayout.tsx | ❌ |  | UI terminal com Ink e Box/Text |
| src/components/GlobalSearchDialog.tsx | ❌ |  | UI terminal com Ink e Box/Text |
| src/components/HelpV2/Commands.tsx | ❌ |  | UI terminal com Ink e Box/Text |
| src/components/HelpV2/General.tsx | ❌ |  | UI terminal com Ink e Box/Text |
| src/components/HelpV2/HelpV2.tsx | ❌ |  | UI terminal com Ink e Box/Text |
| src/components/HighlightedCode.tsx | ⚠️ | packages/core/agent-core/src/components/HighlightedCode.tsx | Lógica de destaque útil, mas depende de Ink e hooks React |
| src/components/HighlightedCode/Fallback.tsx | ⚠️ | packages/core/agent-core/src/components/HighlightedCodeFallback.tsx | Lógica de fallback para destaque, reescrita necessária |
| src/components/HistorySearchDialog.tsx | ❌ |  | UI terminal com Ink e Box/Text |
| src/components/IdeAutoConnectDialog.tsx | ❌ |  | UI terminal com Ink e Box/Text |
| src/components/IdeOnboardingDialog.tsx | ❌ |  | UI terminal com Ink e Box/Text |
| src/components/IdeStatusIndicator.tsx | ❌ |  | UI terminal com Ink e Box/Text |
| src/components/IdleReturnDialog.tsx | ❌ |  | UI terminal com Ink e Box/Text |
| src/components/InterruptedByUser.tsx | ❌ |  | UI terminal com Ink e Box/Text |
| src/components/InvalidConfigDialog.tsx | ❌ |  | UI terminal com Ink e Box/Text |
| src/components/InvalidSettingsDialog.tsx | ❌ |  | UI terminal com Ink e Box/Text |
| src/components/KeybindingWarnings.tsx | ❌ |  | UI terminal com Ink e Box/Text |
| src/components/LanguagePicker.tsx | ❌ |  | UI terminal com Ink e Box/Text |
| src/components/LogSelector.tsx | ❌ |  | UI terminal com Ink e Box/Text |
| src/components/LogoV2/AnimatedAsterisk.tsx | ❌ |  | UI terminal com Ink e Box/Text |
| src/components/LogoV2/AnimatedClawd.tsx | ❌ |  | UI terminal com Ink e Box/Text |
| src/components/LogoV2/ChannelsNotice.tsx | ❌ |  | UI terminal Ink, React |
| src/components/LogoV2/Clawd.tsx | ❌ |  | Componente React/Ink terminal |
| src/components/LogoV2/CondensedLogo.tsx | ❌ |  | UI terminal Ink, React |
| src/components/LogoV2/EmergencyTip.tsx | ❌ |  | UI terminal Ink, React |
| src/components/LogoV2/Feed.tsx | ❌ |  | UI terminal Ink, React |
| src/components/LogoV2/FeedColumn.tsx | ❌ |  | UI terminal Ink, React |
| src/components/LogoV2/GuestPassesUpsell.tsx | ❌ |  | UI terminal Ink, React |
| src/components/LogoV2/LogoV2.tsx | ❌ |  | UI terminal Ink, React |
| src/components/LogoV2/Opus1mMergeNotice.tsx | ❌ |  | UI terminal Ink, React |
| src/components/LogoV2/OverageCreditUpsell.tsx | ❌ |  | UI terminal Ink, React |
| src/components/LogoV2/VoiceModeNotice.tsx | ❌ |  | UI terminal Ink, React |
| src/components/LogoV2/WelcomeV2.tsx | ❌ |  | UI terminal Ink, React |
| src/components/LogoV2/feedConfigs.tsx | ⚠️ | packages/core/agent-core/src/utils/feedConfigs.ts | Lógica feed útil, mas React + Ink misturado |
| src/components/LspRecommendation/LspRecommendationMenu.tsx | ❌ |  | UI terminal Ink, React |
| src/components/MCPServerApprovalDialog.tsx | ❌ |  | UI terminal Ink, React |
| src/components/MCPServerDesktopImportDialog.tsx | ❌ |  | UI terminal Ink, React + desktop bridge |
| src/components/MCPServerDialogCopy.tsx | ❌ |  | UI terminal Ink, React |
| src/components/MCPServerMultiselectDialog.tsx | ❌ |  | UI terminal Ink, React |
| src/components/ManagedSettingsSecurityDialog/ManagedSettingsSecurityDialog.tsx | ❌ |  | UI terminal Ink, React |
| src/components/ManagedSettingsSecurityDialog/utils.ts | ✅ | packages/core/agent-core/src/utils/managedSettingsSecurityUtils.ts | Utilitários puros TS, sem UI |
| src/components/Markdown.tsx | ❌ |  | UI React/Ink para terminal |
| src/components/MarkdownTable.tsx | ❌ |  | UI React/Ink para terminal |
| src/components/MemoryUsageIndicator.tsx | ❌ |  | UI React/Ink para terminal |
| src/components/Message.tsx | ❌ |  | UI React/Ink para terminal |
| src/components/MessageModel.tsx | ❌ |  | UI React/Ink para terminal |
| src/components/MessageResponse.tsx | ❌ |  | UI React/Ink para terminal |
| src/components/MessageRow.tsx | ❌ |  | UI React/Ink para terminal |
| src/components/MessageSelector.tsx | ❌ |  | UI React/Ink para terminal |
| src/components/MessageTimestamp.tsx | ❌ |  | UI React/Ink para terminal |
| src/components/Messages.tsx | ❌ |  | UI React/Ink para terminal |
| src/components/ModelPicker.tsx | ❌ |  | UI React/Ink para terminal |
| src/components/MonitorMcpDetailDialog.tsx | ❌ |  | Stub sem lógica real |
| src/components/MonitorPermissionRequest/MonitorPermissionRequest.tsx | ❌ |  | Stub sem lógica real |
| src/components/NativeAutoUpdater.tsx | ❌ |  | UI React/Ink para terminal |
| src/components/NotebookEditToolUseRejectedMessage.tsx | ❌ |  | UI React/Ink para terminal |
| src/components/OffscreenFreeze.tsx | ❌ |  | UI React/Ink para terminal |
| src/components/Onboarding.tsx | ❌ |  | UI React/Ink para terminal |
| src/components/OutputStylePicker.tsx | ❌ |  | UI React/Ink para terminal |
| src/components/PackageManagerAutoUpdater.tsx | ❌ |  | UI React/Ink para terminal |
| src/components/Passes/Passes.tsx | ❌ |  | UI React/Ink para terminal |
| src/components/PrBadge.tsx | ❌ |  | UI terminal React/Ink, não serve para web serverless |
| src/components/PressEnterToContinue.tsx | ❌ |  | UI terminal React/Ink, não serve para web serverless |
| src/components/PromptInput/HistorySearchInput.tsx | ❌ |  | UI terminal React/Ink, não serve para web serverless |
| src/components/PromptInput/IssueFlagBanner.tsx | ❌ |  | Componente React vazio, UI terminal específico |
| src/components/PromptInput/Notifications.tsx | ❌ |  | UI terminal React/Ink, uso de hooks React específicos |
| src/components/PromptInput/PromptInput.tsx | ❌ |  | UI terminal React/Ink, lógica misturada com UI |
| src/components/PromptInput/PromptInputFooter.tsx | ❌ |  | UI terminal React/Ink, uso de hooks e contexto UI |
| src/components/PromptInput/PromptInputFooterLeftSide.tsx | ❌ |  | UI terminal React/Ink, uso de hooks e contexto UI |
| src/components/PromptInput/PromptInputFooterSuggestions.tsx | ❌ |  | UI terminal React/Ink, componente visual terminal |
| src/components/PromptInput/PromptInputHelpMenu.tsx | ❌ |  | UI terminal React/Ink, menu ajuda terminal |
| src/components/PromptInput/PromptInputModeIndicator.tsx | ❌ |  | UI terminal React/Ink, indicador modo input |
| src/components/PromptInput/PromptInputQueuedCommands.tsx | ❌ |  | UI terminal React/Ink, comandos enfileirados UI |
| src/components/PromptInput/PromptInputStashNotice.tsx | ❌ |  | UI terminal React/Ink, aviso stash UI |
| src/components/PromptInput/SandboxPromptFooterHint.tsx | ❌ |  | UI terminal React/Ink, dica footer UI |
| src/components/PromptInput/ShimmeredInput.tsx | ❌ |  | UI terminal React/Ink, input com efeito shimmer |
| src/components/PromptInput/VoiceIndicator.tsx | ❌ |  | UI terminal React/Ink, indicador voz UI |
| src/components/PromptInput/inputModes.ts | ⚠️ | packages/core/agent-core/src/utils/inputModes.ts | Conceitos de modos input úteis, precisa adaptação |
| src/components/PromptInput/inputPaste.ts | ⚠️ | packages/core/agent-core/src/utils/inputPaste.ts | Lógica de manipulação de paste, reescrita necessária |
| src/components/PromptInput/useMaybeTruncateInput.ts | ⚠️ | packages/core/agent-core/src/hooks/useMaybeTruncateInput.ts | Hook utilitário, adaptação para ambiente web |
| src/components/PromptInput/usePromptInputPlaceholder.ts | ⚠️ | packages/core/agent-core/src/hooks/usePromptInputPlaceholder.ts | Hook utilitário, adaptação para ambiente web |
| src/components/PromptInput/useShowFastIconHint.ts | ❌ |  | Hook React UI terminal específico |
| src/components/PromptInput/useSwarmBanner.ts | ❌ |  | React + terminal UI + swarm específico |
| src/components/PromptInput/utils.ts | ❌ |  | Usa keybindings e terminal concepts |
| src/components/QuickOpenDialog.tsx | ❌ |  | Componente React Ink terminal UI |
| src/components/RemoteCallout.tsx | ❌ |  | React Ink UI + bridge desktop |
| src/components/RemoteEnvironmentDialog.tsx | ❌ |  | React Ink UI terminal + keybindings |
| src/components/ResumeTask.tsx | ❌ |  | React Ink UI + terminal hooks |
| src/components/ReviewArtifactPermissionRequest/ReviewArtifactPermissionRequest.tsx | ❌ |  | Stub sem lógica real |
| src/components/SandboxViolationExpandedView.tsx | ❌ |  | React Ink UI + sandbox adapter |
| src/components/ScrollKeybindingHandler.tsx | ❌ |  | React Ink + terminal keybindings |
| src/components/SearchBox.tsx | ❌ |  | React Ink terminal UI componente |
| src/components/SentryErrorBoundary.ts | ⚠️ | packages/core/agent-core/src/components/SentryErrorBoundary.ts | Boundary React genérico, reescrever para web |
| src/components/SessionBackgroundHint.tsx | ❌ |  | React Ink UI + terminal keybindings |
| src/components/SessionPreview.tsx | ❌ |  | React Ink UI + terminal keybindings |
| src/components/Settings/Config.tsx | ❌ |  | React Ink UI + bun bundle config |
| src/components/Settings/Settings.tsx | ❌ |  | React Ink UI terminal configurações |
| src/components/Settings/Status.tsx | ❌ |  | React Ink UI terminal configurações |
| src/components/Settings/Usage.tsx | ❌ |  | React Ink UI terminal configurações |
| src/components/ShowInIDEPrompt.tsx | ❌ |  | React Ink UI terminal prompt |
| src/components/SkillImprovementSurvey.tsx | ❌ |  | React Ink UI terminal survey |
| src/components/Spinner.tsx | ❌ |  | UI terminal Ink/React |
| src/components/Spinner/FlashingChar.tsx | ❌ |  | UI terminal Ink/React |
| src/components/Spinner/GlimmerMessage.tsx | ❌ |  | UI terminal Ink/React |
| src/components/Spinner/ShimmerChar.tsx | ❌ |  | UI terminal Ink/React |
| src/components/Spinner/SpinnerAnimationRow.tsx | ❌ |  | UI terminal Ink/React |
| src/components/Spinner/SpinnerGlyph.tsx | ❌ |  | UI terminal Ink/React |
| src/components/Spinner/TeammateSpinnerLine.tsx | ❌ |  | UI terminal Ink/React |
| src/components/Spinner/TeammateSpinnerTree.tsx | ❌ |  | UI terminal Ink/React |
| src/components/Spinner/index.ts | ❌ |  | Reexporta UI terminal Ink/React |
| src/components/Spinner/teammateSelectHint.ts | ❌ |  | Texto UI terminal específico |
| src/components/Spinner/useShimmerAnimation.ts | ❌ |  | Hook com deps Ink/terminal |
| src/components/Spinner/useStalledAnimation.ts | ⚠️ | packages/core/agent-core/src/hooks/useStalledAnimation.ts | Hook lógica útil, adaptação para web |
| src/components/Spinner/utils.ts | ⚠️ | packages/core/agent-core/src/utils/spinnerUtils.ts | Utilidades cores e chars, adaptação |
| src/components/Stats.tsx | ❌ |  | UI terminal Ink/React |
| src/components/StatusLine.tsx | ❌ |  | UI terminal Ink/React |
| src/components/StatusNotices.tsx | ❌ |  | UI terminal Ink/React |
| src/components/StructuredDiff.tsx | ❌ |  | UI terminal Ink/React |
| src/components/StructuredDiff/Fallback.tsx | ❌ |  | UI terminal Ink/React |
| src/components/StructuredDiff/colorDiff.ts | ⚠️ | packages/core/agent-core/src/utils/colorDiff.ts | Lógica diff cores, adaptação necessária |
| src/components/StructuredDiffList.tsx | ❌ |  | UI terminal Ink/React |
| src/components/TagTabs.tsx | ❌ |  | UI terminal Ink/Box/Text |
| src/components/TaskListV2.tsx | ❌ |  | UI terminal Ink/Box/Text |
| src/components/TeammateViewHeader.tsx | ❌ |  | UI terminal Ink/Box/Text |
| src/components/TeleportError.tsx | ❌ |  | UI terminal Ink/Box/Text |
| src/components/TeleportProgress.tsx | ❌ |  | UI terminal Ink/Box/Text |
| src/components/TeleportRepoMismatchDialog.tsx | ❌ |  | UI terminal Ink/Box/Text |
| src/components/TeleportResumeWrapper.tsx | ❌ |  | UI terminal Ink/Box/Text |
| src/components/TeleportStash.tsx | ❌ |  | UI terminal Ink/Box/Text |
| src/components/TextInput.tsx | ❌ |  | UI terminal Ink/Box/Text + Bun bundle |
| src/components/ThemePicker.tsx | ❌ |  | UI terminal Ink/Box/Text |
| src/components/ThinkingToggle.tsx | ❌ |  | UI terminal Ink/Box/Text |
| src/components/TokenWarning.tsx | ❌ |  | UI terminal Ink/Box/Text |
| src/components/ToolUseLoader.tsx | ❌ |  | UI terminal Ink/Box/Text |
| src/components/TrustDialog/TrustDialog.tsx | ❌ |  | UI terminal Ink/Box/Text |
| src/components/TrustDialog/utils.ts | ⚠️ | packages/core/agent-core/src/utils/trustDialogUtils.ts | Utilitários lógicos, requer adaptação |
| src/components/UserCrossSessionMessage.tsx | ❌ |  | UI terminal Ink/Box/Text |
| src/components/UserForkBoilerplateMessage.tsx | ❌ |  | UI terminal Ink/Box/Text |
| src/components/UserGitHubWebhookMessage.tsx | ❌ |  | UI terminal Ink/Box/Text |
| src/components/ValidationErrorsList.tsx | ❌ |  | UI terminal Ink/Box/Text |
| src/components/VimTextInput.tsx | ❌ |  | UI terminal Ink/Box/Text + Vim bindings |
| src/components/VirtualMessageList.tsx | ❌ |  | UI terminal Ink, uso de Box, Text, hooks Ink |
| src/components/WorkflowDetailDialog.tsx | ❌ |  | Componente React stub sem lógica |
| src/components/WorkflowMultiselectDialog.tsx | ❌ |  | UI terminal Ink, Box, Text, SelectMulti |
| src/components/WorktreeExitDialog.tsx | ❌ |  | UI terminal Ink, Box, Text, Spinner |
| src/components/agents/AgentDetail.tsx | ❌ |  | UI terminal Ink, Box, Text, React |
| src/components/agents/AgentEditor.tsx | ❌ |  | UI terminal Ink, Box, Text, React |
| src/components/agents/AgentNavigationFooter.tsx | ❌ |  | UI terminal Ink, Box, Text, keybindings |
| src/components/agents/AgentsList.tsx | ❌ |  | UI terminal Ink, Box, Text, Dialog |
| src/components/agents/AgentsMenu.tsx | ❌ |  | UI terminal Ink, Box, Text, Dialog |
| src/components/agents/ColorPicker.tsx | ❌ |  | UI terminal Ink, Box, Text, React |
| src/components/agents/ModelSelector.tsx | ❌ |  | UI terminal Ink, Box, Text, React |
| src/components/agents/SnapshotUpdateDialog.tsx | ❌ |  | Componente React stub sem lógica |
| src/components/agents/ToolSelector.tsx | ❌ |  | UI terminal Ink, Box, Text, React |
| src/components/agents/agentFileUtils.ts | ✅ | packages/core/agent-core/src/utils/agentFileUtils.ts | Utilitários de arquivos agentes, sem UI |
| src/components/agents/generateAgent.ts | ⚠️ | packages/core/agent-core/src/generateAgent.ts | Lógica geração agente, precisa adaptação |
| src/components/agents/new-agent-creation/CreateAgentWizard.tsx | ❌ |  | UI terminal Ink, React wizard |
| src/components/agents/new-agent-creation/wizard-steps/ColorStep.tsx | ❌ |  | UI terminal Ink, React wizard step |
| src/components/agents/new-agent-creation/wizard-steps/ConfirmStep.tsx | ❌ |  | UI terminal Ink, React wizard step |
| src/components/agents/new-agent-creation/wizard-steps/ConfirmStepWrapper.tsx | ❌ |  | UI terminal Ink, React wizard step |
| src/components/agents/new-agent-creation/wizard-steps/DescriptionStep.tsx | ❌ |  | UI terminal Ink, React wizard step |
| src/components/agents/new-agent-creation/wizard-steps/GenerateStep.tsx | ❌ |  | UI terminal React/Ink, uso de Box, Text, hooks de input |
| src/components/agents/new-agent-creation/wizard-steps/LocationStep.tsx | ❌ |  | UI terminal React/Ink, uso de Box, Select, hooks de input |
| src/components/agents/new-agent-creation/wizard-steps/MemoryStep.tsx | ❌ |  | UI terminal React/Ink, uso de Box, Select, hooks de input |
| src/components/agents/new-agent-creation/wizard-steps/MethodStep.tsx | ❌ |  | UI terminal React/Ink, uso de Box, Select, hooks de input |
| src/components/agents/new-agent-creation/wizard-steps/ModelStep.tsx | ❌ |  | UI terminal React/Ink, uso de componentes React/Ink |
| src/components/agents/new-agent-creation/wizard-steps/PromptStep.tsx | ❌ |  | UI terminal React/Ink, uso de Box, TextInput, hooks de input |
| src/components/agents/new-agent-creation/wizard-steps/ToolsStep.tsx | ❌ |  | UI terminal React/Ink, uso de Box, ToolSelector, hooks de input |
| src/components/agents/new-agent-creation/wizard-steps/TypeStep.tsx | ❌ |  | UI terminal React/Ink, uso de Box, TextInput, hooks de input |
| src/components/agents/types.ts | ✅ | packages/core/agent-core/src/components/agents/types.ts | Tipos TS reutilizáveis para agentes, sem dependências UI |
| src/components/agents/utils.ts | ✅ | packages/core/agent-core/src/components/agents/utils.ts | Utilitários puros para agentes, sem dependências UI |
| src/components/agents/validateAgent.ts | ✅ | packages/core/agent-core/src/components/agents/validateAgent.ts | Validação de agentes, lógica de negócio reutilizável |
| src/components/design-system/Byline.tsx | ❌ |  | Componente UI React/Ink para terminal |
| src/components/design-system/Dialog.tsx | ❌ |  | Componente UI React/Ink para terminal |
| src/components/design-system/Divider.tsx | ❌ |  | Componente UI React/Ink para terminal |
| src/components/design-system/FuzzyPicker.tsx | ❌ |  | Componente UI React/Ink para terminal |
| src/components/design-system/KeyboardShortcutHint.tsx | ❌ |  | Componente UI React/Ink para terminal |
| src/components/design-system/ListItem.tsx | ❌ |  | Componente UI React/Ink para terminal |
| src/components/design-system/LoadingState.tsx | ❌ |  | Componente UI React/Ink para terminal |
| src/components/design-system/Pane.tsx | ❌ |  | Componente UI React/Ink para terminal |
| src/components/design-system/ProgressBar.tsx | ❌ |  | Componente UI React/Ink para terminal |
| src/components/design-system/Ratchet.tsx | ❌ |  | UI terminal Ink, React, hooks específicos CLI |
| src/components/design-system/StatusIcon.tsx | ❌ |  | UI terminal Ink, React, figuras, Text Ink |
| src/components/design-system/Tabs.tsx | ❌ |  | UI terminal Ink, React, keybindings CLI |
| src/components/design-system/ThemeProvider.tsx | ❌ |  | UI terminal Ink, React, stdin, config global |
| src/components/design-system/ThemedBox.tsx | ❌ |  | UI terminal Ink, React, Box Ink, tema UI |
| src/components/design-system/ThemedText.tsx | ❌ |  | UI terminal Ink, React, Text Ink, tema UI |
| src/components/design-system/color.ts | ✅ | packages/core/agent-core/src/utils/color.ts | Utilitário de cor tema, sem dependência UI |
| src/components/diff/DiffDetailView.tsx | ❌ |  | UI terminal Ink, React, Box, Text, hooks CLI |
| src/components/diff/DiffDialog.tsx | ❌ |  | UI terminal Ink, React, keybindings, dialog CLI |
| src/components/diff/DiffFileList.tsx | ❌ |  | UI terminal Ink, React, Box, Text, figuras CLI |
| src/components/grove/Grove.tsx | ❌ |  | UI terminal Ink, React, input, dialog CLI |
| src/components/hooks/HooksConfigMenu.tsx | ❌ |  | UI terminal Ink, React, Box, Text CLI |
| src/components/hooks/PromptDialog.tsx | ❌ |  | UI terminal Ink, React, dialog, keybinding CLI |
| src/components/hooks/SelectEventMode.tsx | ❌ |  | UI terminal Ink, React, Box, Text CLI |
| src/components/hooks/SelectHookMode.tsx | ❌ |  | UI terminal Ink, React, Box, Text CLI |
| src/components/hooks/SelectMatcherMode.tsx | ❌ |  | UI terminal Ink, React, Box, Text CLI |
| src/components/hooks/ViewHookMode.tsx | ❌ |  | UI terminal Ink, React, Box, Text CLI |
| src/components/mcp/CapabilitiesSection.tsx | ❌ |  | UI terminal Ink, React, Box, Text CLI |
| src/components/mcp/ElicitationDialog.tsx | ❌ |  | UI terminal Ink, React, dialog CLI |
| src/components/mcp/MCPAgentServerMenu.tsx | ❌ |  | UI terminal Ink, React, menu CLI |
| src/components/mcp/MCPListPanel.tsx | ❌ |  | UI terminal React/Ink |
| src/components/mcp/MCPReconnect.tsx | ❌ |  | UI terminal React/Ink |
| src/components/mcp/MCPRemoteServerMenu.tsx | ❌ |  | UI terminal React/Ink |
| src/components/mcp/MCPSettings.tsx | ❌ |  | UI terminal React/Ink |
| src/components/mcp/MCPStdioServerMenu.tsx | ❌ |  | UI terminal React/Ink |
| src/components/mcp/MCPToolDetailView.tsx | ❌ |  | UI terminal React/Ink |
| src/components/mcp/MCPToolListView.tsx | ❌ |  | UI terminal React/Ink |
| src/components/mcp/McpParsingWarnings.tsx | ❌ |  | UI terminal React/Ink |
| src/components/mcp/index.ts | ❌ |  | Reexporta componentes UI terminal |
| src/components/mcp/utils/reconnectHelpers.tsx | ✅ | packages/core/agent-core/src/services/mcp/utils/reconnectHelpers.ts | Lógica de negócio reaproveitável, sem UI |
| src/components/memory/MemoryFileSelector.tsx | ❌ |  | UI terminal React/Ink + Bun API |
| src/components/memory/MemoryUpdateNotification.tsx | ❌ |  | UI terminal React/Ink |
| src/components/messageActions.tsx | ❌ |  | UI terminal React/Ink |
| src/components/messages/AdvisorMessage.tsx | ❌ |  | UI terminal React/Ink |
| src/components/messages/AssistantRedactedThinkingMessage.tsx | ❌ |  | UI terminal React/Ink |
| src/components/messages/AssistantTextMessage.tsx | ❌ |  | UI terminal React/Ink |
| src/components/messages/AssistantThinkingMessage.tsx | ❌ |  | UI terminal React/Ink |
| src/components/messages/AssistantToolUseMessage.tsx | ❌ |  | UI terminal React/Ink |
| src/components/messages/AttachmentMessage.tsx | ❌ |  | UI terminal React/Ink |
| src/components/messages/CollapsedReadSearchContent.tsx | ❌ |  | UI terminal React/Ink |
| src/components/messages/CompactBoundaryMessage.tsx | ❌ |  | UI terminal Ink, Box, Text, useShortcutDisplay |
| src/components/messages/GroupedToolUseContent.tsx | ❌ |  | React component UI terminal Ink |
| src/components/messages/HighlightedThinkingText.tsx | ❌ |  | React Ink UI terminal component |
| src/components/messages/HookProgressMessage.tsx | ❌ |  | React Ink UI terminal component |
| src/components/messages/PlanApprovalMessage.tsx | ❌ |  | React Ink UI terminal component |
| src/components/messages/RateLimitMessage.tsx | ❌ |  | React Ink UI terminal component |
| src/components/messages/ShutdownMessage.tsx | ❌ |  | React Ink UI terminal component |
| src/components/messages/SnipBoundaryMessage.tsx | ❌ |  | Placeholder sem lógica real |
| src/components/messages/SystemAPIErrorMessage.tsx | ❌ |  | React Ink UI terminal component |
| src/components/messages/SystemTextMessage.tsx | ❌ |  | React Ink UI terminal component |
| src/components/messages/TaskAssignmentMessage.tsx | ❌ |  | React Ink UI terminal component |
| src/components/messages/UserAgentNotificationMessage.tsx | ❌ |  | React Ink UI terminal component |
| src/components/messages/UserBashInputMessage.tsx | ❌ |  | React Ink UI terminal component |
| src/components/messages/UserBashOutputMessage.tsx | ❌ |  | React Ink UI terminal component |
| src/components/messages/UserChannelMessage.tsx | ❌ |  | React Ink UI terminal component |
| src/components/messages/UserCommandMessage.tsx | ❌ |  | React Ink UI terminal component |
| src/components/messages/UserCrossSessionMessage.tsx | ❌ |  | React Ink UI terminal component |
| src/components/messages/UserForkBoilerplateMessage.tsx | ❌ |  | React Ink UI terminal component |
| src/components/messages/UserGitHubWebhookMessage.tsx | ❌ |  | React Ink UI terminal component |
| src/components/messages/UserImageMessage.tsx | ❌ |  | React Ink UI terminal component |
| src/components/messages/UserLocalCommandOutputMessage.tsx | ❌ |  | UI terminal Ink/Box/Text |
| src/components/messages/UserMemoryInputMessage.tsx | ❌ |  | UI terminal Ink/Box/Text |
| src/components/messages/UserPlanMessage.tsx | ❌ |  | UI terminal Ink/Box/Text |
| src/components/messages/UserPromptMessage.tsx | ❌ |  | UI terminal Ink/Box/Text |
| src/components/messages/UserResourceUpdateMessage.tsx | ❌ |  | UI terminal Ink/Box/Text |
| src/components/messages/UserTeammateMessage.tsx | ❌ |  | UI terminal Ink/Box/Text |
| src/components/messages/UserTextMessage.tsx | ❌ |  | UI terminal Ink/Box/Text |
| src/components/messages/UserToolResultMessage/RejectedPlanMessage.tsx | ❌ |  | UI terminal Ink/Box/Text |
| src/components/messages/UserToolResultMessage/RejectedToolUseMessage.tsx | ❌ |  | UI terminal Ink/Box/Text |
| src/components/messages/UserToolResultMessage/UserToolCanceledMessage.tsx | ❌ |  | UI terminal Ink/Box/Text |
| src/components/messages/UserToolResultMessage/UserToolErrorMessage.tsx | ❌ |  | UI terminal Ink/Box/Text |
| src/components/messages/UserToolResultMessage/UserToolRejectMessage.tsx | ❌ |  | UI terminal Ink/Box/Text |
| src/components/messages/UserToolResultMessage/UserToolResultMessage.tsx | ❌ |  | UI terminal Ink/Box/Text |
| src/components/messages/UserToolResultMessage/UserToolSuccessMessage.tsx | ❌ |  | UI terminal Ink/Box/Text |
| src/components/messages/UserToolResultMessage/utils.tsx | ⚠️ | packages/core/agent-core/src/components/messages/UserToolResultMessage/utils.tsx | Possível lógica útil, mas depende de UI e reescrita |
| src/components/messages/nullRenderingAttachments.ts | ⚠️ | packages/core/agent-core/src/components/messages/nullRenderingAttachments.ts | Pode conter lógica útil, mas precisa adaptação |
| src/components/messages/teamMemCollapsed.tsx | ❌ |  | UI terminal Ink/Box/Text |
| src/components/messages/teamMemSaved.ts | ❌ |  | UI terminal Ink/Box/Text |
| src/components/permissions/AskUserQuestionPermissionRequest/AskUserQuestionPermissionRequest.tsx | ❌ |  | UI terminal Ink/Box/Text |
| src/components/permissions/AskUserQuestionPermissionRequest/PreviewBox.tsx | ❌ |  | UI terminal Ink/Box/Text |
| src/components/permissions/AskUserQuestionPermissionRequest/PreviewQuestionView.tsx | ❌ |  | UI terminal Ink/React |
| src/components/permissions/AskUserQuestionPermissionRequest/QuestionNavigationBar.tsx | ❌ |  | UI terminal Ink/React |
| src/components/permissions/AskUserQuestionPermissionRequest/QuestionView.tsx | ❌ |  | UI terminal Ink/React |
| src/components/permissions/AskUserQuestionPermissionRequest/SubmitQuestionsView.tsx | ❌ |  | UI terminal Ink/React |
| src/components/permissions/AskUserQuestionPermissionRequest/use-multiple-choice-state.ts | ✅ | packages/core/agent-core/src/hooks/use-multiple-choice-state.ts | Lógica estado perguntas, sem UI |
| src/components/permissions/BashPermissionRequest/BashPermissionRequest.tsx | ❌ |  | UI terminal Ink/React e Bun bundle |
| src/components/permissions/BashPermissionRequest/bashToolUseOptions.tsx | ✅ | packages/core/agent-core/src/utils/bashToolUseOptions.ts | Lógica opções uso Bash tool |
| src/components/permissions/ComputerUseApproval/ComputerUseApproval.tsx | ❌ |  | UI terminal Ink/React |
| src/components/permissions/EnterPlanModePermissionRequest/EnterPlanModePermissionRequest.tsx | ❌ |  | UI terminal Ink/React |
| src/components/permissions/ExitPlanModePermissionRequest/ExitPlanModePermissionRequest.tsx | ❌ |  | UI terminal Ink/React |
| src/components/permissions/FallbackPermissionRequest.tsx | ❌ |  | UI terminal Ink/React |
| src/components/permissions/FileEditPermissionRequest/FileEditPermissionRequest.tsx | ❌ |  | UI terminal Ink/React |
| src/components/permissions/FilePermissionDialog/FilePermissionDialog.tsx | ❌ |  | UI terminal Ink/React |
| src/components/permissions/FilePermissionDialog/ideDiffConfig.ts | ⚠️ | packages/core/agent-core/src/utils/ideDiffConfig.ts | Config IDE/diff, adaptação necessária |
| src/components/permissions/FilePermissionDialog/permissionOptions.tsx | ✅ | packages/core/agent-core/src/utils/permissionOptions.ts | Opções permissão, lógica reutilizável |
| src/components/permissions/FilePermissionDialog/useFilePermissionDialog.ts | ❌ |  | Hook UI terminal Ink/React |
| src/components/permissions/FilePermissionDialog/usePermissionHandler.ts | ⚠️ | packages/core/agent-core/src/hooks/usePermissionHandler.ts | Hook lógica permissão, adaptação |
| src/components/permissions/FileWritePermissionRequest/FileWritePermissionRequest.tsx | ❌ |  | UI terminal Ink/React |
| src/components/permissions/FileWritePermissionRequest/FileWriteToolDiff.tsx | ⚠️ | packages/core/agent-core/src/utils/fileWriteToolDiff.ts | Lógica diff escrita, adaptação |
| src/components/permissions/FilesystemPermissionRequest/FilesystemPermissionRequest.tsx | ❌ |  | UI terminal Ink/React |
| src/components/permissions/MonitorPermissionRequest/MonitorPermissionRequest.tsx | ❌ |  | Componente React vazio, UI terminal |
| src/components/permissions/NotebookEditPermissionRequest/NotebookEditPermissionRequest.tsx | ❌ |  | Usa Ink/React terminal UI |
| src/components/permissions/NotebookEditPermissionRequest/NotebookEditToolDiff.tsx | ❌ |  | Usa Ink/React terminal UI |
| src/components/permissions/PermissionDecisionDebugInfo.tsx | ❌ |  | Usa Ink/React terminal UI |
| src/components/permissions/PermissionDialog.tsx | ❌ |  | Usa Ink/React terminal UI |
| src/components/permissions/PermissionExplanation.tsx | ❌ |  | Usa Ink/React terminal UI |
| src/components/permissions/PermissionPrompt.tsx | ❌ |  | Usa Ink/React terminal UI e keybindings |
| src/components/permissions/PermissionRequest.tsx | ❌ |  | Usa React e keybindings, UI terminal |
| src/components/permissions/PermissionRequestTitle.tsx | ❌ |  | Usa Ink/React terminal UI |
| src/components/permissions/PermissionRuleExplanation.tsx | ❌ |  | Usa Ink/React terminal UI |
| src/components/permissions/PowerShellPermissionRequest/PowerShellPermissionRequest.tsx | ❌ |  | Usa Ink/React terminal UI e keybindings |
| src/components/permissions/PowerShellPermissionRequest/powershellToolUseOptions.tsx | ⚠️ | packages/core/agent-core/src/utils/powershellToolUseOptions.ts | Lógica de opções útil, sem UI, precisa adaptação |
| src/components/permissions/ReviewArtifactPermissionRequest/ReviewArtifactPermissionRequest.tsx | ❌ |  | Componente React terminal UI |
| src/components/permissions/SandboxPermissionRequest.tsx | ❌ |  | Provável UI terminal (padrão pasta) |
| src/components/permissions/SedEditPermissionRequest/SedEditPermissionRequest.tsx | ❌ |  | Provável UI terminal (padrão pasta) |
| src/components/permissions/SkillPermissionRequest/SkillPermissionRequest.tsx | ❌ |  | Provável UI terminal (padrão pasta) |
| src/components/permissions/WebFetchPermissionRequest/WebFetchPermissionRequest.tsx | ❌ |  | Provável UI terminal (padrão pasta) |
| src/components/permissions/WorkerBadge.tsx | ❌ |  | Componente UI terminal |
| src/components/permissions/WorkerPendingPermission.tsx | ❌ |  | Componente UI terminal |
| src/components/permissions/hooks.ts | ⚠️ | packages/core/agent-core/src/hooks/permissionsHooks.ts | Hooks podem conter lógica útil, adaptação necessária |
| src/components/permissions/rules/AddPermissionRules.tsx | ❌ |  | UI terminal React/Ink, não serve para web |
| src/components/permissions/rules/AddWorkspaceDirectory.tsx | ❌ |  | UI terminal React/Ink, uso de hooks de terminal |
| src/components/permissions/rules/PermissionRuleDescription.tsx | ❌ |  | Componente React/Ink para terminal |
| src/components/permissions/rules/PermissionRuleInput.tsx | ❌ |  | UI terminal React/Ink, depende de hooks de terminal |
| src/components/permissions/rules/PermissionRuleList.tsx | ❌ |  | UI terminal React/Ink, uso de hooks e componentes Ink |
| src/components/permissions/rules/RecentDenialsTab.tsx | ❌ |  | UI terminal React/Ink, uso de useInput e Ink |
| src/components/permissions/rules/RemoveWorkspaceDirectory.tsx | ❌ |  | UI terminal React/Ink, componente React para terminal |
| src/components/permissions/rules/WorkspaceTab.tsx | ❌ |  | UI terminal React/Ink, uso de hooks e componentes Ink |
| src/components/permissions/shellPermissionHelpers.tsx | ⚠️ | packages/core/agent-core/src/utils/shellPermissionHelpers.ts | Contém lógica útil, mas inclui React, precisa refatorar |
| src/components/permissions/useShellPermissionFeedback.ts | ❌ |  | Hook React para UI, não aplicável para backend Nexias |
| src/components/permissions/utils.ts | ✅ | packages/core/agent-core/src/utils/permissionsUtils.ts | Funções utilitárias sem dependência de UI |
| src/components/sandbox/SandboxConfigTab.tsx | ❌ |  | Componente React/Ink para terminal |
| src/components/sandbox/SandboxDependenciesTab.tsx | ❌ |  | Componente React/Ink para terminal |
| src/components/sandbox/SandboxDoctorSection.tsx | ❌ |  | Componente React/Ink para terminal |
| src/components/sandbox/SandboxOverridesTab.tsx | ❌ |  | Componente React/Ink para terminal |
| src/components/sandbox/SandboxSettings.tsx | ❌ |  | Componente React/Ink para terminal |
| src/components/shell/ExpandShellOutputContext.tsx | ❌ |  | Componente React/Ink para terminal |
| src/components/shell/OutputLine.tsx | ❌ |  | Componente React/Ink para terminal |
| src/components/shell/ShellProgressMessage.tsx | ❌ |  | Componente React/Ink para terminal |
| src/components/shell/ShellTimeDisplay.tsx | ❌ |  | Componente React/Ink para terminal |
| src/components/skills/SkillsMenu.tsx | ❌ |  | UI terminal Ink, React CLI |
| src/components/tasks/AsyncAgentDetailDialog.tsx | ❌ |  | UI terminal Ink, React CLI |
| src/components/tasks/BackgroundTask.tsx | ❌ |  | UI terminal Ink, React CLI |
| src/components/tasks/BackgroundTaskStatus.tsx | ❌ |  | UI terminal Ink, React CLI |
| src/components/tasks/BackgroundTasksDialog.tsx | ❌ |  | UI terminal Ink, React CLI |
| src/components/tasks/DreamDetailDialog.tsx | ❌ |  | UI terminal Ink, React CLI |
| src/components/tasks/InProcessTeammateDetailDialog.tsx | ❌ |  | UI terminal Ink, React CLI |
| src/components/tasks/MonitorMcpDetailDialog.tsx | ❌ |  | Stub sem lógica |
| src/components/tasks/RemoteSessionDetailDialog.tsx | ❌ |  | UI terminal Ink, React CLI |
| src/components/tasks/RemoteSessionProgress.tsx | ❌ |  | UI terminal Ink, React CLI |
| src/components/tasks/ShellDetailDialog.tsx | ❌ |  | UI terminal Ink, React CLI |
| src/components/tasks/ShellProgress.tsx | ❌ |  | UI terminal Ink, React CLI |
| src/components/tasks/WorkflowDetailDialog.tsx | ❌ |  | UI terminal Ink, React CLI |
| src/components/tasks/renderToolActivity.tsx | ❌ |  | UI terminal Ink, React CLI |
| src/components/tasks/taskStatusUtils.tsx | ✅ | packages/core/agent-core/src/tasks/taskStatusUtils.ts | Lógica utilitária de status de tarefas, sem UI |
| src/components/teams/TeamStatus.tsx | ❌ |  | UI terminal Ink, React CLI |
| src/components/teams/TeamsDialog.tsx | ❌ |  | UI terminal Ink, React CLI |
| src/components/ui/OrderedList.tsx | ❌ |  | UI terminal Ink, React CLI |
| src/components/ui/OrderedListItem.tsx | ❌ |  | UI terminal Ink, React CLI |
| src/components/ui/TreeSelect.tsx | ❌ |  | UI terminal Ink, React CLI |
| src/components/wizard/WizardDialogLayout.tsx | ❌ |  | UI React para diálogo, não serve para backend web |
| src/components/wizard/WizardNavigationFooter.tsx | ❌ |  | UI terminal com Ink, não aplicável no Nexias |
| src/components/wizard/WizardProvider.tsx | ❌ |  | React context provider para UI, não backend |
| src/components/wizard/index.ts | ❌ |  | Reexporta componentes React, não útil no Nexias |
| src/components/wizard/useWizard.ts | ❌ |  | Hook React para contexto UI, não aplicável |
| src/screens/Doctor.tsx | ❌ |  | UI terminal React/Ink, imports Box, Text, hooks Ink |
| src/screens/REPL.tsx | ❌ |  | UI terminal React/Ink, uso intenso de hooks e componentes Ink |
| src/screens/ResumeConversation.tsx | ❌ |  | UI terminal React/Ink, uso de Box, Text e hooks Ink |
| src/vim/motions.ts  | ❌      |                                  | Específico de vim motions, CLI/terminal |
| src/vim/operators.ts| ❌      |                                  | Lógica específica de vim operators CLI |
| src/vim/textObjects.ts | ❌   |                                  | Vim text objects, terminal-specific   |
| src/vim/transitions.ts | ❌    |                                  | Vim state transitions, CLI/terminal   |
| src/vim/types.ts    | ❌      |                                  | Tipos específicos para vim state machine |
| src/bridge/bridgeApi.ts | ✅ | packages/core/agent-core/src/bridge/bridgeApi.ts | Lógica API HTTP reutilizável, sem deps CLI/terminal |
| src/bridge/bridgeConfig.ts | ✅ | packages/core/agent-core/src/bridge/bridgeConfig.ts | Configuração auth/URL reutilizável, sem UI |
| src/bridge/bridgeDebug.ts | ⚠️ | packages/core/agent-core/src/bridge/bridgeDebug.ts | Debug/fault injection específico, adaptar para Nexias |
| src/bridge/bridgeEnabled.ts | ✅ | packages/core/agent-core/src/bridge/bridgeEnabled.ts | Lógica feature flag e auth, útil para Nexias |
| src/bridge/bridgeMain.ts | ⚠️ | packages/core/agent-core/src/bridge/bridgeMain.ts | Contém lógica complexa, mistura analytics e utilidades |
| src/bridge/bridgeMessaging.ts | ✅ | packages/core/agent-core/src/bridge/bridgeMessaging.ts | Transporte e parsing mensagens, lógica pura |
| src/bridge/bridgePermissionCallbacks.ts | ✅ | packages/core/agent-core/src/bridge/bridgePermissionCallbacks.ts | Callbacks permissão, lógica reutilizável |
| src/bridge/bridgePointer.ts | ⚠️ | packages/core/agent-core/src/bridge/bridgePointer.ts | Manipulação FS específica, adaptar para cloud |
| src/bridge/bridgeStatusUtil.ts | ⚠️ | packages/core/agent-core/src/bridge/bridgeStatusUtil.ts | Utilitários status com deps UI (stringWidth) |
| src/bridge/bridgeUI.ts | ❌ |  | UI terminal (chalk, qrcode), não importar |
| src/bridge/capacityWake.ts | ✅ | packages/core/agent-core/src/bridge/capacityWake.ts | Controle sinais abort, lógica pura útil |
| src/bridge/codeSessionApi.ts | ✅ | packages/core/agent-core/src/bridge/codeSessionApi.ts | Wrapper HTTP para API, sem deps UI |
| src/bridge/createSession.ts | ✅ | packages/core/agent-core/src/bridge/createSession.ts | Lógica criação sessão, sem UI |
| src/bridge/debugUtils.ts | ✅ | packages/core/agent-core/src/bridge/debugUtils.ts | Utilitários debug, sem UI |
| src/bridge/envLessBridgeConfig.ts | ✅ | packages/core/agent-core/src/bridge/envLessBridgeConfig.ts | Configuração para modo env-less, lógica pura |
| src/bridge/flushGate.ts | ⚠️ | packages/core/agent-core/src/bridge/flushGate.ts | Não analisado, provável utilitário, adaptar |
| src/bridge/inboundAttachments.ts | ⚠️ | packages/core/agent-core/src/bridge/inboundAttachments.ts | Provável manipulação arquivos, adaptar para cloud |
| src/bridge/inboundMessages.ts | ✅ | packages/core/agent-core/src/bridge/inboundMessages.ts | Lógica mensagens recebidas, sem UI |
| src/bridge/initReplBridge.ts | ❌ |  | CLI/REPL específico, não importar |
| src/bridge/jwtUtils.ts | ✅ | packages/core/agent-core/src/bridge/jwtUtils.ts | Utilitários JWT, lógica pura |
| src/bridge/peerSessions.ts | ⚠️ | packages/core/agent-core/src/bridge/peerSessions.ts | Sessões peer, adaptar para Nexias |
| src/bridge/pollConfig.ts | ✅ | packages/core/agent-core/src/bridge/pollConfig.ts | Configuração polling, lógica pura |
| src/bridge/pollConfigDefaults.ts | ✅ | packages/core/agent-core/src/bridge/pollConfigDefaults.ts | Defaults polling, lógica pura |
| src/bridge/remoteBridgeCore.ts | ⚠️ | packages/core/agent-core/src/bridge/remoteBridgeCore.ts | Core bridge remoto, adaptar para Nexias |
| src/bridge/replBridge.ts | ❌ |  | REPL/CLI específico, não importar |
| src/bridge/replBridgeHandle.ts | ❌ |  | REPL/CLI específico, não importar |
| src/bridge/replBridgeTransport.ts | ❌ |  | REPL/CLI específico, não importar |
| src/bridge/sessionIdCompat.ts | ✅ | packages/core/agent-core/src/bridge/sessionIdCompat.ts | Compatibilidade sessionId, lógica pura |
| src/bridge/sessionRunner.ts | ⚠️ | packages/core/agent-core/src/bridge/sessionRunner.ts | Runner sessão, adaptar para Nexias |
| src/bridge/trustedDevice.ts | ⚠️ | packages/core/agent-core/src/bridge/trustedDevice.ts | Lógica trusted device, adaptar para Nexias |
| src/bridge/types.ts | ✅ | packages/core/agent-core/src/bridge/types.ts | Tipos TS, reutilizáveis |
| src/bridge/workSecret.ts | ⚠️ | packages/core/agent-core/src/bridge/workSecret.ts | Manipulação secrets, adaptar para cloud |
| src/server/backends/dangerousBackend.ts | ❌ |  | Stub sem lógica útil |
| src/server/connectHeadless.ts | ❌ |  | Stub sem lógica útil |
| src/server/createDirectConnectSession.ts | ⚠️ | packages/backend/directConnect/createDirectConnectSession.ts | Lógica de sessão direta, precisa adaptação para Nexias |
| src/server/directConnectManager.ts | ⚠️ | packages/backend/directConnect/directConnectManager.ts | Gerenciamento conexão direta, reescrita para Nexias necessária |
| src/server/lockfile.ts | ❌ |  | Stub sem lógica útil |
| src/server/parseConnectUrl.ts | ❌ |  | Stub sem lógica útil |
| src/server/server.ts | ❌ |  | Stub sem lógica útil |
| src/server/serverBanner.ts | ❌ |  | Stub sem lógica útil |
| src/server/serverLog.ts | ❌ |  | Stub sem lógica útil |
| src/server/sessionManager.ts | ❌ |  | Stub sem lógica útil |
| src/server/types.ts | ✅ | packages/core/agent-core/src/server/types.ts | Tipos e schemas úteis, sem dependências específicas |
| src/cli/exit.ts | ❌ |  | Específico de CLI, usa process.exit |
| src/cli/handlers/agents.ts | ⚠️ | packages/backend/src/agents/handlers.ts | Lógica de agentes útil, mas acoplada a CLI |
| src/cli/handlers/auth.ts | ⚠️ | packages/backend/src/auth/handlers.ts | Lógica auth valiosa, mas com saída CLI |
| src/cli/handlers/autoMode.ts | ⚠️ | packages/backend/src/autoMode/handlers.ts | Lógica regras auto mode, saída CLI |
| src/cli/handlers/mcp.tsx | ❌ |  | React/Ink UI e CLI, não serve para Nexias |
| src/cli/handlers/plugins.ts | ⚠️ | packages/backend/src/plugins/handlers.ts | Lógica plugins útil, mas CLI dependente |
| src/cli/handlers/util.tsx | ❌ |  | React/Ink UI e CLI, não serve para Nexias |
| src/cli/ndjsonSafeStringify.ts | ✅ | packages/core/src/utils/ndjsonSafeStringify.ts | Utilitário JSON sem dependências CLI |
| src/cli/print.ts | ❌ |  | Usa Bun e CLI específicos |
| src/cli/remoteIO.ts | ⚠️ | packages/core/src/io/remoteIO.ts | Lógica IO útil, mas depende de streams Node |
| src/cli/structuredIO.ts | ✅ | packages/core/src/io/structuredIO.ts | Lógica de IO estruturado aproveitável |
| src/cli/transports/HybridTransport.ts | ⚠️ | packages/core/src/transports/HybridTransport.ts | Lógica transporte híbrido valiosa, adaptação |
| src/cli/transports/SSETransport.ts | ⚠️ | packages/core/src/transports/SSETransport.ts | Transporte SSE útil, depende axios e utils |
| src/cli/transports/SerialBatchEventUploader.ts | ⚠️ | packages/core/src/transports/SerialBatchEventUploader.ts | Lógica uploader útil, adaptação necessária |
| src/cli/transports/WebSocketTransport.ts | ✅ | packages/core/src/transports/WebSocketTransport.ts | Transporte WebSocket reutilizável |
| src/cli/transports/WorkerStateUploader.ts | ⚠️ | packages/core/src/transports/WorkerStateUploader.ts | Lógica uploader worker, adaptação necessária |
| src/cli/transports/ccrClient.ts | ⚠️ | packages/core/src/transports/ccrClient.ts | Cliente CCR útil, mas depende utils CLI |
| src/cli/transports/transportUtils.ts | ✅ | packages/core/src/transports/transportUtils.ts | Utilitários transporte sem dependências CLI |
| src/cli/update.ts | ❌ |  | Provavelmente CLI update, não útil para Nexias |
| src/migrations/migrateAutoUpdatesToSettings.ts | ❌ |  | Migration específica, config local CLI/desktop |
| src/migrations/migrateBypassPermissionsAcceptedToSettings.ts | ❌ |  | Migration específica, config local CLI/desktop |
| src/migrations/migrateEnableAllProjectMcpServersToSettings.ts | ❌ |  | Migration específica, config local CLI/desktop |
| src/migrations/migrateFennecToOpus.ts | ❌ |  | Migration específica, config local CLI/desktop |
| src/migrations/migrateLegacyOpusToCurrent.ts | ❌ |  | Migration específica, config local CLI/desktop |
| src/migrations/migrateOpusToOpus1m.ts | ❌ |  | Migration específica, config local CLI/desktop |
| src/migrations/migrateReplBridgeEnabledToRemoteControlAtStartup.ts | ❌ |  | Migration específica, config local CLI/desktop |
| src/migrations/migrateSonnet1mToSonnet45.ts | ❌ |  | Migration específica, config local CLI/desktop |
| src/migrations/migrateSonnet45ToSonnet46.ts | ❌ |  | Migration específica, config local CLI/desktop |
| src/migrations/resetAutoModeOptInForDefaultOffer.ts | ❌ |  | Migration específica, config local CLI/desktop |
| src/migrations/resetProToOpusDefault.ts | ❌ |  | Migration específica, config local CLI/desktop |
| src/stubs/ant-packages/@ant/claude-for-chrome-mcp/index.js | ❌ |  | Stub sem lógica útil |
| src/stubs/ant-packages/@ant/claude-for-chrome-mcp/package.json | ❌ |  | Arquivo de configuração de pacote |
| src/stubs/ant-packages/@ant/computer-use-input/index.js | ❌ |  | Stub vazio |
| src/stubs/ant-packages/@ant/computer-use-input/package.json | ❌ |  | Arquivo de configuração de pacote |
| src/stubs/ant-packages/@ant/computer-use-mcp/index.js | ❌ |  | Stub sem lógica real, específico interno |
| src/stubs/ant-packages/@ant/computer-use-mcp/package.json | ❌ |  | Arquivo de configuração de pacote |
| src/stubs/ant-packages/@ant/computer-use-mcp/sentinelApps/index.js | ❌ |  | Stub sem lógica útil |
| src/stubs/ant-packages/@ant/computer-use-mcp/types/index.js | ❌ |  | Stub sem tipos reais |
| src/stubs/ant-packages/@ant/computer-use-swift/index.js | ❌ |  | Stub vazio, macOS only |
| src/stubs/ant-packages/@ant/computer-use-swift/package.json | ❌ |  | Arquivo de configuração de pacote |
| src/stubs/ant-packages/@anthropic-ai/bedrock-sdk/index.js | ❌ |  | Classe vazia, stub |
| src/stubs/ant-packages/@anthropic-ai/bedrock-sdk/package.json | ❌ |  | Arquivo de configuração de pacote |
| src/stubs/ant-packages/@anthropic-ai/foundry-sdk/index.js | ❌ |  | Classe vazia, stub |
| src/stubs/ant-packages/@anthropic-ai/foundry-sdk/package.json | ❌ |  | Arquivo de configuração de pacote |
| src/stubs/ant-packages/@anthropic-ai/vertex-sdk/index.js | ❌ |  | Classe vazia, stub |
| src/stubs/ant-packages/@anthropic-ai/vertex-sdk/package.json | ❌ |  | Arquivo de configuração de pacote |
| src/stubs/ant-packages/@aws-sdk/client-bedrock/index.js | ❌ |  | Export vazio |
| src/stubs/ant-packages/@aws-sdk/client-bedrock/package.json | ❌ |  | Arquivo de configuração de pacote |
| src/stubs/ant-packages/@aws-sdk/client-sts/index.js | ❌ |  | Export vazio |
| src/stubs/ant-packages/@aws-sdk/client-sts/package.json | ❌ |  | Arquivo de configuração de pacote |
| src/stubs/ant-packages/@azure/identity/index.js | ⚠️ | packages/core/azure-identity/ | Classes vazias, possível adaptação parcial |
| src/stubs/ant-packages/@azure/identity/package.json | ❌ |  | Arquivo de configuração de pacote |
| src/stubs/ant-packages/@opentelemetry/exporter-logs-otlp-grpc/index.js | ❌ |  | Export vazio |
| src/stubs/ant-packages/@opentelemetry/exporter-logs-otlp-grpc/package.json | ❌ |  | Arquivo de configuração de pacote |
| src/stubs/ant-packages/@opentelemetry/exporter-logs-otlp-http/index.js | ❌ |  | Export vazio |
| src/stubs/ant-packages/@opentelemetry/exporter-logs-otlp-http/package.json | ❌ |  | Arquivo de configuração de pacote |
| src/stubs/ant-packages/@opentelemetry/exporter-logs-otlp-proto/index.js | ❌ |  | Export vazio |
| src/stubs/ant-packages/@opentelemetry/exporter-logs-otlp-proto/package.json | ❌ |  | Arquivo de configuração de pacote |
| src/stubs/ant-packages/@opentelemetry/exporter-metrics-otlp-grpc/index.js | ❌ |  | Export vazio |
| src/stubs/ant-packages/@opentelemetry/exporter-metrics-otlp-grpc/package.json | ❌ |  | Arquivo de configuração de pacote |
| src/stubs/ant-packages/@opentelemetry/exporter-metrics-otlp-http/index.js | ❌ |  | Export vazio |
| src/stubs/ant-packages/@opentelemetry/exporter-metrics-otlp-http/package.json | ❌ |  | Arquivo de configuração de pacote |
| src/stubs/ant-packages/@opentelemetry/exporter-metrics-otlp-proto/index.js | ❌ |  | Export vazio |
| src/stubs/ant-packages/@opentelemetry/exporter-metrics-otlp-proto/package.json | ❌ |  | Arquivo de configuração de pacote |
| src/stubs/ant-packages/@opentelemetry/exporter-prometheus/index.js | ❌ |  | Export vazio |
| src/stubs/ant-packages/@opentelemetry/exporter-prometheus/package.json | ❌ |  | Arquivo de configuração de pacote |
| src/stubs/ant-packages/@opentelemetry/exporter-trace-otlp-grpc/index.js | ❌ |  | Export vazio |
| src/stubs/ant-packages/@opentelemetry/exporter-trace-otlp-grpc/package.json | ❌ |  | Arquivo de configuração de pacote |
| src/stubs/ant-packages/@opentelemetry/exporter-trace-otlp-http/index.js | ❌ |  | Export vazio |
| src/stubs/ant-packages/@opentelemetry/exporter-trace-otlp-http/package.json | ❌ |  | Arquivo de configuração de pacote |
| src/stubs/ant-packages/@opentelemetry/exporter-trace-otlp-proto/index.js | ❌ |  | Export vazio |
| src/stubs/ant-packages/@opentelemetry/exporter-trace-otlp-proto/package.json | ❌ |  | Arquivo de configuração de pacote |
| src/stubs/ant-packages/audio-capture-napi/index.js | ❌ |  | Stub vazio, native addon |
| src/stubs/ant-packages/audio-capture-napi/package.json | ❌ |  | Arquivo de configuração de pacote |
| src/stubs/ant-packages/color-diff-napi/index.js | ⚠️ | packages/core/color-diff/ | Classe com métodos vazios, possível adaptação parcial |
| src/stubs/ant-packages/color-diff-napi/package.json | ❌ |  | Arquivo de configuração de pacote |
| src/stubs/ant-packages/modifiers-napi/index.js | ❌ |  | Stub CommonJS, native addon |
| src/stubs/ant-packages/modifiers-napi/package.json | ❌ |  | Arquivo de configuração de pacote |
| src/stubs/ant-packages/sharp/index.js | ⚠️ | packages/core/sharp-adapter/ | Mock sharp, adaptação parcial possível |
| src/stubs/ant-packages/sharp/package.json | ❌ |  | Arquivo de configuração de pacote |
| src/stubs/ant-packages/turndown/index.js | ⚠️ | packages/core/turndown-adapter/ | Classe com método básico, adaptação parcial |
| src/stubs/ant-packages/turndown/package.json | ❌ |  | Arquivo de configuração de pacote |
| src/stubs/bun-bundle-preload.ts | ❌ |  | Código específico Bun |
| src/stubs/bun-bundle-runtime.ts | ❌ |  | Código específico Bun |
| src/stubs/bun-bundle.d.ts | ❌ |  | Declaração Bun específica |
| src/stubs/bun-ffi.d.ts | ❌ |  | Declaração Bun específica |
| src/buddy/CompanionSprite.tsx | ❌     |                                          | Componente React/Ink para terminal         |
| src/buddy/companion.ts       | ✅     | packages/core/agent-core/src/buddy/companion.ts | Lógica de negócio para companions          |
| src/buddy/prompt.ts          | ⚠️     | packages/core/agent-core/src/buddy/prompt.ts      | Conceito valioso, mas depende de Bun/CLI   |
| src/buddy/sprites.ts         | ✅     | packages/core/agent-core/src/buddy/sprites.ts     | Dados e lógica de sprites reutilizáveis    |
| src/buddy/types.ts           | ✅     | packages/core/agent-core/src/buddy/types.ts       | Tipos e constantes reutilizáveis            |
| src/buddy/useBuddyNotification.tsx | ❌     |                                          | React/Ink UI e hooks específicos de terminal|
| src/proactive/index.ts  | ❌     |         | Stub sem lógica real           |
| src/proactive/useProactive.ts | ❌     |         | Stub sem lógica real           |
| src/yolo-classifier-prompts/auto_mode_system_prompt.txt | ❌ |  | Arquivo vazio ou binário, sem lógica aproveitável |
| src/yolo-classifier-prompts/permissions_anthropic.txt | ❌ |  | Arquivo vazio ou binário, sem lógica aproveitável |
| src/yolo-classifier-prompts/permissions_external.txt | ❌ |  | Arquivo vazio ou binário, sem lógica aproveitável |
| src/utils/CircularBuffer.ts | ✅ | packages/core/agent-core/src/utils/CircularBuffer.ts | Estrutura genérica útil para buffers circulares |
| src/utils/Cursor.ts | ❌ |  | Depende de 'ink', terminal UI e manipulação de texto CLI |
| src/utils/QueryGuard.ts | ✅ | packages/core/agent-core/src/utils/QueryGuard.ts | Máquina de estados para ciclo de queries, lógica reutilizável |
| src/utils/Shell.ts | ❌ |  | Uso intensivo de child_process e fs, específico para CLI |
| src/utils/ShellCommand.ts | ⚠️ | packages/core/agent-core/src/utils/ShellCommand.ts | Execução de comandos shell, precisa adaptação para serverless |
| src/utils/abortController.ts | ✅ | packages/core/agent-core/src/utils/abortController.ts | Criação de AbortController com limites, utilitário genérico |
| src/utils/activityManager.ts | ✅ | packages/core/agent-core/src/utils/activityManager.ts | Gerenciamento de atividade, lógica de negócio reaproveitável |
| src/utils/advisor.ts | ✅ | packages/core/agent-core/src/utils/advisor.ts | Tipos e lógica para advisor, útil para Nexias |
| src/utils/agentContext.ts | ✅ | packages/core/agent-core/src/utils/agentContext.ts | Contexto assíncrono para agentes, importante para Nexias |
| src/utils/agentId.ts | ✅ | packages/core/agent-core/src/utils/agentId.ts | Sistema determinístico de IDs, lógica reutilizável |
| src/utils/agentSwarmsEnabled.ts | ⚠️ | packages/core/agent-core/src/utils/agentSwarmsEnabled.ts | Verificação de flags CLI, precisa adaptação para Nexias |
| src/utils/agenticSessionSearch.ts | ✅ | packages/core/agent-core/src/utils/agenticSessionSearch.ts | Busca em sessões, lógica de negócio relevante |
| src/utils/analyzeContext.ts | ⚠️ | packages/core/agent-core/src/utils/analyzeContext.ts | Usa bun:bundle e imports específicos, requer adaptação |
| src/utils/ansiToPng.ts | ❌ |  | Renderização ANSI para PNG, específico para terminal/desktop |
| src/utils/ansiToSvg.ts | ❌ |  | Conversão ANSI para SVG, foco em terminal UI |
| src/utils/api.ts | ⚠️ | packages/core/agent-core/src/utils/api.ts | Integração com SDKs e contexto, adaptação necessária |
| src/utils/apiPreconnect.ts | ⚠️ | packages/core/agent-core/src/utils/apiPreconnect.ts | Pré-conexão API, depende de ambiente específico |
| src/utils/appleTerminalBackup.ts | ❌ |  | Backup terminal Apple, específico para desktop/CLI |
| src/utils/argumentSubstitution.ts | ✅ | packages/core/agent-core/src/utils/argumentSubstitution.ts | Substituição de argumentos, utilitário genérico |
| src/utils/array.ts | ✅ | packages/core/agent-core/src/utils/array.ts | Funções utilitárias para arrays, genérico e reutilizável |
| src/utils/asciicast.ts | ❌ |  | Específico para gravação terminal, fs/promises, Bun |
| src/utils/attachments.ts | ✅ | packages/core/agent-core/src/utils/attachments.ts | Utilitários para manipulação de arquivos e ferramentas |
| src/utils/attribution.ts | ⚠️ | packages/core/agent-core/src/utils/attribution.ts | Lógica de atribuição, mas depende de estado e constantes específicas |
| src/utils/attributionHooks.ts | ❌ |  | Exporta objeto vazio, stub sem lógica |
| src/utils/attributionTrailer.ts | ❌ |  | Exporta string vazia, stub sem lógica |
| src/utils/auth.ts | ⚠️ | packages/core/agent-core/src/utils/auth.ts | Autenticação com dependências específicas (chalk, execa) |
| src/utils/authFileDescriptor.ts | ⚠️ | packages/core/agent-core/src/utils/authFileDescriptor.ts | Manipulação de tokens via arquivos, fs sync, ambiente específico |
| src/utils/authPortable.ts | ✅ | packages/core/agent-core/src/utils/authPortable.ts | Funções portáveis para manipulação de API keys |
| src/utils/autoModeDenials.ts | ✅ | packages/core/agent-core/src/utils/autoModeDenials.ts | Lógica de negação de comandos, sem dependências UI |
| src/utils/autoRunIssue.tsx | ❌ |  | Componente React/Ink para terminal |
| src/utils/autoUpdater.ts | ⚠️ | packages/core/agent-core/src/utils/autoUpdater.ts | Atualizador com fs, axios, lógica complexa, precisa adaptação |
| src/utils/aws.ts | ✅ | packages/core/agent-core/src/utils/aws.ts | Tipos e funções utilitárias AWS, sem UI |
| src/utils/awsAuthStatusManager.ts | ✅ | packages/core/agent-core/src/utils/awsAuthStatusManager.ts | Gerenciamento estado auth, sem UI, útil para Nexias |
| src/utils/background/remote/preconditions.ts | ✅ | packages/core/agent-core/src/utils/background/remote/preconditions.ts | Lógica pré-condições para sessões remotas, aproveitável |
| src/utils/background/remote/remoteSession.ts | ✅ | packages/core/agent-core/src/utils/background/remote/remoteSession.ts | Tipos e lógica para sessões remotas, sem UI |
| src/utils/backgroundHousekeeping.ts | ⚠️ | packages/core/agent-core/src/utils/backgroundHousekeeping.ts | Lógica background com imports condicionais Bun, precisa adaptação |
| src/utils/bash/ParsedCommand.ts | ✅ | packages/core/agent-core/src/utils/bash/ParsedCommand.ts | Parsing de comandos shell, lógica reutilizável |
| src/utils/bash/ShellSnapshot.ts | ⚠️ | packages/core/agent-core/src/utils/bash/ShellSnapshot.ts | Execução shell, fs, child_process, precisa adaptação para serverless |
| src/utils/bash/ast.ts | ✅ | packages/core/agent-core/src/utils/bash/ast.ts | AST para bash, lógica pura, útil para Nexias |
| src/utils/bash/bashParser.ts | ✅ | packages/core/agent-core/src/utils/bash/bashParser.ts | Parser bash, lógica reutilizável sem UI |
| src/utils/bash/bashPipeCommand.ts | ✅ | packages/core/agent-core/src/utils/bash/bashPipeCommand.ts | Lógica de manipulação de comandos shell reutilizável |
| src/utils/bash/commands.ts | ✅ | packages/core/agent-core/src/utils/bash/commands.ts | Geração segura de placeholders para comandos shell |
| src/utils/bash/heredoc.ts | ✅ | packages/core/agent-core/src/utils/bash/heredoc.ts | Utilitários para extração/restauração de heredocs shell |
| src/utils/bash/parser.ts | ⚠️ | packages/core/agent-core/src/utils/bash/parser.ts | Parser bash com dependência Bun, requer adaptação |
| src/utils/bash/prefix.ts | ✅ | packages/core/agent-core/src/utils/bash/prefix.ts | Lógica para extrair e validar prefixos de comandos |
| src/utils/bash/registry.ts | ✅ | packages/core/agent-core/src/utils/bash/registry.ts | Registro e tipos de especificações de comandos shell |
| src/utils/bash/shellCompletion.ts | ⚠️ | packages/core/agent-core/src/utils/bash/shellCompletion.ts | Completação shell com dependências UI, adaptar lógica |
| src/utils/bash/shellPrefix.ts | ✅ | packages/core/agent-core/src/utils/bash/shellPrefix.ts | Formatação segura de prefixos de comandos shell |
| src/utils/bash/shellQuote.ts | ✅ | packages/core/agent-core/src/utils/bash/shellQuote.ts | Wrappers seguros para parsing e citação shell-quote |
| src/utils/bash/shellQuoting.ts | ✅ | packages/core/agent-core/src/utils/bash/shellQuoting.ts | Detecção de padrões heredoc em comandos shell |
| src/utils/bash/specs/alias.ts | ✅ | packages/core/agent-core/src/utils/bash/specs/alias.ts | Definição reutilizável de comando alias shell |
| src/utils/bash/specs/index.ts | ✅ | packages/core/agent-core/src/utils/bash/specs/index.ts | Agregador de specs shell para uso centralizado |
| src/utils/bash/specs/nohup.ts | ✅ | packages/core/agent-core/src/utils/bash/specs/nohup.ts | Definição reutilizável de comando nohup shell |
| src/utils/bash/specs/pyright.ts | ✅ | packages/core/agent-core/src/utils/bash/specs/pyright.ts | Definição reutilizável de comando pyright shell |
| src/utils/bash/specs/sleep.ts | ✅ | packages/core/agent-core/src/utils/bash/specs/sleep.ts | Definição reutilizável de comando sleep shell |
| src/utils/bash/specs/srun.ts | ✅ | packages/core/agent-core/src/utils/bash/specs/srun.ts | Definição reutilizável de comando srun shell |
| src/utils/bash/specs/time.ts | ✅ | packages/core/agent-core/src/utils/bash/specs/time.ts | Definição reutilizável de comando time shell |
| src/utils/bash/specs/timeout.ts | ✅ | packages/core/agent-core/src/utils/bash/specs/timeout.ts | Definição reutilizável de comando timeout shell |
| src/utils/bash/treeSitterAnalysis.ts | ⚠️ | packages/core/agent-core/src/utils/bash/treeSitterAnalysis.ts | Análise AST bash, depende tree-sitter, adaptar |
| src/utils/betas.ts | ❌ |  | Depende Bun e lógica específica de feature flags CLI |
| src/utils/billing.ts | ✅ | packages/core/agent-core/src/utils/billing.ts | Lógica de negócio para controle de billing, sem deps CLI |
| src/utils/binaryCheck.ts | ✅ | packages/core/agent-core/src/utils/binaryCheck.ts | Verificação de binários, utilitário genérico útil |
| src/utils/browser.ts | ✅ | packages/core/agent-core/src/utils/browser.ts | Validação e manipulação de URLs, lógica reutilizável |
| src/utils/bufferedWriter.ts | ✅ | packages/core/agent-core/src/utils/bufferedWriter.ts | Buffer para escrita, utilitário genérico sem deps CLI |
| src/utils/bundledMode.ts | ✅ | packages/core/agent-core/src/utils/bundledMode.ts | Detecta runtime Bun, pode ajudar em deploys serverless |
| src/utils/caCerts.ts | ✅ | packages/core/agent-core/src/utils/caCerts.ts | Gerenciamento de certificados TLS, útil para conexões HTTPS |
| src/utils/caCertsConfig.ts | ✅ | packages/core/agent-core/src/utils/caCertsConfig.ts | Configuração de certificados, lógica de negócio pura |
| src/utils/cachePaths.ts | ✅ | packages/core/agent-core/src/utils/cachePaths.ts | Gerenciamento de paths para cache, utilitário genérico |
| src/utils/classifierApprovals.ts | ⚠️ | packages/core/agent-core/src/utils/classifierApprovals.ts | Usa bun:bundle e sinais, precisa adaptação para Nexias |
| src/utils/classifierApprovalsHook.ts | ❌ |  | React hook para terminal/React, não serve para backend |
| src/utils/claudeCodeHints.ts | ⚠️ | packages/core/agent-core/src/utils/claudeCodeHints.ts | Parser e store de hints, React depende, reescrita parcial |
| src/utils/claudeDesktop.ts | ⚠️ | packages/core/agent-core/src/utils/claudeDesktop.ts | Integração desktop, fs e platform específicos, adaptar |
| src/utils/claudeInChrome/chromeNativeHost.ts | ❌ |  | Server TCP e fs, específico para Chrome Native Host CLI |
| src/utils/claudeInChrome/common.ts | ⚠️ | packages/core/agent-core/src/utils/claudeInChrome/common.ts | Utilitários fs/os, parte pode ser reaproveitada com adaptação |
| src/utils/claudeInChrome/mcpServer.ts | ❌ |  | Usa MCP server e libs específicas, não para Nexias backend |
| src/utils/claudeInChrome/prompt.ts | ❌ |  | Texto estático para CLI/browser, não útil para backend |
| src/utils/claudeInChrome/setup.ts | ❌ |  | Provavelmente React/CLI, não listado mas provável UI |
| src/utils/claudeInChrome/setupPortable.ts | ⚠️ | packages/core/agent-core/src/utils/claudeInChrome/setupPortable.ts | Tipos e setup portable, pode ser adaptado parcialmente |
| src/utils/claudemd.ts | ⚠️ | packages/core/agent-core/src/utils/claudemd.ts | Parser Markdown custom, pode ser útil com adaptação |
| src/utils/cleanup.ts | ⚠️ | packages/core/agent-core/src/utils/cleanup.ts | Contém lógica de limpeza, mas depende de fs e ambiente local |
| src/utils/cleanupRegistry.ts | ✅ | packages/core/agent-core/src/utils/cleanupRegistry.ts | Registro global para funções de limpeza reutilizável |
| src/utils/cliArgs.ts | ❌ |  | Parsing CLI args específico para terminal/CLI |
| src/utils/cliHighlight.ts | ⚠️ | packages/core/agent-core/src/utils/cliHighlight.ts | Lógica de destaque CLI, mas depende de ambiente terminal |
| src/utils/codeIndexing.ts | ✅ | packages/core/agent-core/src/utils/codeIndexing.ts | Tipos e lógica para ferramentas de indexação de código |
| src/utils/collapseBackgroundBashNotifications.ts | ❌ |  | Específico para mensagens de terminal/bash |
| src/utils/collapseHookSummaries.ts | ✅ | packages/core/agent-core/src/utils/collapseHookSummaries.ts | Lógica de agregação de mensagens reutilizável |
| src/utils/collapseReadSearch.ts | ⚠️ | packages/core/agent-core/src/utils/collapseReadSearch.ts | Lógica complexa, depende de ferramentas específicas |
| src/utils/collapseTeammateShutdowns.ts | ✅ | packages/core/agent-core/src/utils/collapseTeammateShutdowns.ts | Lógica de agregação de mensagens útil para Nexias |
| src/utils/combinedAbortSignal.ts | ✅ | packages/core/agent-core/src/utils/combinedAbortSignal.ts | Combinação de sinais Abort reutilizável em web |
| src/utils/commandLifecycle.ts | ✅ | packages/core/agent-core/src/utils/commandLifecycle.ts | Gerenciamento de ciclo de vida de comandos genérico |
| src/utils/commitAttribution.ts | ⚠️ | packages/core/agent-core/src/utils/commitAttribution.ts | Lógica Git complexa, pode precisar adaptação |
| src/utils/completionCache.ts | ❌ |  | Uso de fs e terminal, não adequado para serverless |
| src/utils/computerUse/appNames.ts | ✅ | packages/core/agent-core/src/utils/computerUse/appNames.ts | Sanitização de nomes de apps, lógica útil |
| src/utils/computerUse/cleanup.ts | ❌ |  | Dependente de bloqueios e hotkeys de desktop/CLI |
| src/utils/computerUse/common.ts | ⚠️ | packages/core/agent-core/src/utils/computerUse/common.ts | Normalização e env, pode precisar adaptação |
| src/utils/computerUse/computerUseLock.ts | ❌ |  | Lock baseado em arquivo, específico para desktop |
| src/utils/computerUse/drainRunLoop.ts | ❌ |  | Controle de loop de execução específico desktop/CLI |
| src/utils/computerUse/escHotkey.ts | ❌ |  | Hotkey ESC para terminal, não aplicável no Nexias |
| src/utils/computerUse/executor.ts | ❌ |  | Executor ligado a ambiente desktop/CLI |
| src/utils/computerUse/gates.ts | ⚠️ | packages/core/agent-core/src/utils/computerUse/gates.ts | Lógica de feature gates, depende de analytics e auth, adaptação necessária |
| src/utils/computerUse/hostAdapter.ts | ⚠️ | packages/core/agent-core/src/utils/computerUse/hostAdapter.ts | Adapter com logger e execuções, depende de CLI e debug, reescrita parcial |
| src/utils/computerUse/inputLoader.ts | ⚠️ | packages/core/agent-core/src/utils/computerUse/inputLoader.ts | Loader de API nativa, macOS-only, adaptação para serverless necessária |
| src/utils/computerUse/mcpServer.ts | ❌ |  | Server MCP específico, usa StdioServerTransport, não aplicável a Cloud Run |
| src/utils/computerUse/setup.ts | ⚠️ | packages/core/agent-core/src/utils/computerUse/setup.ts | Setup de ferramentas MCP, depende de paths e config, reescrita parcial |
| src/utils/computerUse/swiftLoader.ts | ⚠️ | packages/core/agent-core/src/utils/computerUse/swiftLoader.ts | Loader macOS-only, native module, adaptação para serverless necessária |
| src/utils/computerUse/toolRendering.tsx | ❌ |  | React/Ink UI para terminal, não aplicável a Nexias web serverless |
| src/utils/computerUse/wrapper.tsx | ❌ |  | React + MCP binding, UI/terminal específico, não importar |
| src/utils/concurrentSessions.ts | ⚠️ | packages/core/agent-core/src/utils/concurrentSessions.ts | Gerenciamento sessões com FS, adaptação para ambiente serverless necessária |
| src/utils/config.ts | ⚠️ | packages/core/agent-core/src/utils/config.ts | Config geral com FS e bun:bundle, reescrita para Nexias necessária |
| src/utils/configConstants.ts | ✅ | packages/core/agent-core/src/utils/configConstants.ts | Constantes puras, sem dependências, importação direta |
| src/utils/contentArray.ts | ✅ | packages/core/agent-core/src/utils/contentArray.ts | Utilitário puro para manipulação de arrays de conteúdo |
| src/utils/context.ts | ✅ | packages/core/agent-core/src/utils/context.ts | Constantes e funções para contexto de modelo, lógica reutilizável |
| src/utils/contextAnalysis.ts | ✅ | packages/core/agent-core/src/utils/contextAnalysis.ts | Análise de contexto e tokens, lógica de negócio útil |
| src/utils/contextSuggestions.ts | ⚠️ | packages/core/agent-core/src/utils/contextSuggestions.ts | Sugestões baseadas em contexto, lógica útil mas pode precisar adaptação |
| src/utils/controlMessageCompat.ts | ✅ | packages/core/agent-core/src/utils/controlMessageCompat.ts | Compatibilidade mensagens controle, lógica reutilizável |
| src/utils/conversationRecovery.ts | ⚠️ | packages/core/agent-core/src/utils/conversationRecovery.ts | Recuperação conversa, lógica útil mas depende de estado e FS |
| src/utils/cron.ts | ✅ | packages/core/agent-core/src/utils/cron.ts | Utilitário cron puro, pode ser usado para agendamento no Nexias |
| src/utils/cronJitterConfig.ts | ✅ | packages/core/agent-core/src/utils/cronJitterConfig.ts | Configuração de jitter para cron, utilitário puro |
| src/utils/cronScheduler.ts | ⚠️ | packages/core/agent-core/src/utils/cronScheduler.ts | Scheduler cron, pode precisar adaptação para ambiente serverless |
| src/utils/cronTasks.ts | ⚠️ | packages/core/agent-core/src/utils/cronTasks.ts | Lógica de agendamento, mas depende de fs e estado local |
| src/utils/cronTasksLock.ts | ❌ |  | Lock via fs e PID, específico para ambiente local CLI |
| src/utils/crossProjectResume.ts | ⚠️ | packages/core/agent-core/src/utils/crossProjectResume.ts | Conceito útil, mas depende de paths e estado local |
| src/utils/crypto.ts | ✅ | packages/core/agent-core/src/utils/crypto.ts | Abstração de crypto, útil e sem dependências CLI |
| src/utils/cwd.ts | ⚠️ | packages/core/agent-core/src/utils/cwd.ts | AsyncLocalStorage útil, mas depende de estado local |
| src/utils/debug.ts | ⚠️ | packages/core/agent-core/src/utils/debug.ts | Logging avançado, mas depende de fs e estado local |
| src/utils/debugFilter.ts | ✅ | packages/core/agent-core/src/utils/debugFilter.ts | Parsing de filtros, sem dependências externas |
| src/utils/deepLink/banner.ts | ❌ |  | UI terminal e interação, específico CLI/desktop |
| src/utils/deepLink/parseDeepLink.ts | ⚠️ | packages/core/agent-core/src/utils/deepLink/parseDeepLink.ts | Parsing URI útil, mas contexto CLI/desktop |
| src/utils/deepLink/protocolHandler.ts | ❌ |  | Manipulação de terminal e OS, específico CLI |
| src/utils/deepLink/registerProtocol.ts | ❌ |  | Registro OS de protocolo, não aplicável web |
| src/utils/deepLink/terminalLauncher.ts | ❌ |  | Lançamento terminal nativo, CLI/desktop only |
| src/utils/deepLink/terminalPreference.ts | ❌ |  | Preferências terminal, CLI/desktop específico |
| src/utils/desktopDeepLink.ts | ❌ |  | Execução e versão desktop, não serverless |
| src/utils/detectRepository.ts | ✅ | packages/core/agent-core/src/utils/detectRepository.ts | Detecta repositório git, útil para Nexias |
| src/utils/diagLogs.ts | ⚠️ | packages/core/agent-core/src/utils/diagLogs.ts | Logging diagnóstico, depende fs e estado local |
| src/utils/diff.ts | ✅ | packages/core/agent-core/src/utils/diff.ts | Utilitário diff genérico, sem dependências CLI |
| src/utils/directMemberMessage.ts | ⚠️ | packages/core/agent-core/src/utils/directMemberMessage.ts | Lógica de mensagens, pode precisar adaptação |
| src/utils/displayTags.ts | ✅ | packages/core/agent-core/src/utils/displayTags.ts | Utilitário para tags, sem dependências CLI |
| src/utils/doctorContextWarnings.ts | ⚠️ | packages/core/agent-core/src/utils/doctorContextWarnings.ts | Lógica de warnings, pode precisar adaptação |
| src/utils/doctorDiagnostic.ts | ⚠️ | packages/core/agent-core/src/utils/doctorDiagnostic.ts | Usa fs/promises e execa, adaptação para serverless necessária |
| src/utils/dxt/helpers.ts | ✅ | packages/core/agent-core/src/utils/dxt/helpers.ts | Validação de manifest JSON, lógica reutilizável para backend |
| src/utils/dxt/zip.ts | ✅ | packages/core/agent-core/src/utils/dxt/zip.ts | Validação de zip, lógica de negócio sem dependências UI |
| src/utils/earlyInput.ts | ❌ |  | Captura input terminal pré-REPL, específico CLI/terminal |
| src/utils/editor.ts | ❌ |  | Spawn de processos e interação terminal, não serverless |
| src/utils/effort.ts | ✅ | packages/core/agent-core/src/utils/effort.ts | Tipos e lógica de esforço, sem dependências UI |
| src/utils/embeddedTools.ts | ⚠️ | packages/core/agent-core/src/utils/embeddedTools.ts | Lógica de build-time e env, adaptação para Nexias |
| src/utils/env.ts | ✅ | packages/core/agent-core/src/utils/env.ts | Config e paths, memoização, útil para backend |
| src/utils/envDynamic.ts | ⚠️ | packages/core/agent-core/src/utils/envDynamic.ts | Usa execFileNoThrow, async, adaptação para serverless |
| src/utils/envUtils.ts | ✅ | packages/core/agent-core/src/utils/envUtils.ts | Funções utilitárias de ambiente, memoização |
| src/utils/envValidation.ts | ✅ | packages/core/agent-core/src/utils/envValidation.ts | Validação de variáveis de ambiente, lógica pura |
| src/utils/errorLogSink.ts | ⚠️ | packages/core/agent-core/src/utils/errorLogSink.ts | Logging com axios e fs, adaptação para cloud necessária |
| src/utils/errors.ts | ✅ | packages/core/agent-core/src/utils/errors.ts | Definição de erros customizados, lógica reutilizável |
| src/utils/exampleCommands.ts | ⚠️ | packages/core/agent-core/src/utils/exampleCommands.ts | Usa execFile, git, lógica parcial para Nexias |
| src/utils/execFileNoThrow.ts | ⚠️ | packages/core/agent-core/src/utils/execFileNoThrow.ts | Wrapper execa, adaptação para serverless e Nexias |
| src/utils/execFileNoThrowPortable.ts | ⚠️ | packages/core/agent-core/src/utils/execFileNoThrowPortable.ts | Exec sync deprecated, adaptação necessária |
| src/utils/execSyncWrapper.ts | ⚠️ | packages/core/agent-core/src/utils/execSyncWrapper.ts | Exec sync wrapper, não ideal para serverless |
| src/utils/extraUsage.ts | ❌ |  | Possível UI ou CLI, sem lógica clara reaproveitável |
| src/utils/fastMode.ts | ⚠️ | packages/core/agent-core/src/utils/fastMode.ts | Lógica de modo rápido, possível adaptação necessária |
| src/utils/file.ts | ⚠️ | packages/core/agent-core/src/utils/file.ts | Usa fs/promises e analytics, adaptação para serverless necessária |
| src/utils/fileHistory.ts | ⚠️ | packages/core/agent-core/src/utils/fileHistory.ts | Lógica de histórico de arquivos, depende de VSCode e estado CLI |
| src/utils/fileOperationAnalytics.ts | ✅ | packages/core/agent-core/src/utils/fileOperationAnalytics.ts | Hashing para analytics, lógica pura reaproveitável |
| src/utils/filePersistence/filePersistence.ts | ❌ |  | Usa 'bun:bundle' e lógica específica de desktop/CLI |
| src/utils/filePersistence/outputsScanner.ts | ⚠️ | packages/core/agent-core/src/utils/filePersistence/outputsScanner.ts | Scanner de arquivos modificado, depende de fs/promises |
| src/utils/filePersistence/types.ts | ❌ |  | Stub sem lógica real |
| src/utils/fileRead.ts | ✅ | packages/core/agent-core/src/utils/fileRead.ts | Leitura de arquivos síncrona, sem deps de UI |
| src/utils/fileReadCache.ts | ✅ | packages/core/agent-core/src/utils/fileReadCache.ts | Cache de leitura de arquivos, lógica pura |
| src/utils/fileStateCache.ts | ✅ | packages/core/agent-core/src/utils/fileStateCache.ts | Cache LRU para estado de arquivos, lógica reaproveitável |
| src/utils/findExecutable.ts | ✅ | packages/core/agent-core/src/utils/findExecutable.ts | Busca executável no PATH, utilitário puro |
| src/utils/fingerprint.ts | ✅ | packages/core/agent-core/src/utils/fingerprint.ts | Funções de fingerprint, lógica pura |
| src/utils/forkedAgent.ts | ⚠️ | packages/core/agent-core/src/utils/forkedAgent.ts | Gerenciamento de agentes forked, adaptação para Nexias |
| src/utils/format.ts | ✅ | packages/core/agent-core/src/utils/format.ts | Formatação de dados, sem UI |
| src/utils/formatBriefTimestamp.ts | ✅ | packages/core/agent-core/src/utils/formatBriefTimestamp.ts | Formatação de timestamps, lógica pura |
| src/utils/fpsTracker.ts | ❌ |  | Métricas de FPS, dependente de performance.now() ambiente UI |
| src/utils/frontmatterParser.ts | ✅ | packages/core/agent-core/src/utils/frontmatterParser.ts | Parser YAML frontmatter, lógica reaproveitável |
| src/utils/fsOperations.ts | ⚠️ | packages/core/agent-core/src/utils/fsOperations.ts | Wrapper fs, adaptação para ambiente serverless necessária |
| src/utils/fullscreen.ts | ❌ |  | Usa child_process e heurísticas de terminal interativo |
| src/utils/generatedFiles.ts | ❌ |  | Não listado no conteúdo, presumido UI/CLI específico |
| src/utils/generators.ts | ❌ |  | Não listado no conteúdo, presumido UI/CLI específico |
| src/utils/genericProcessUtils.ts | ✅ | packages/core/agent-core/src/utils/genericProcessUtils.ts | Utilitário genérico para processos, sem deps CLI |
| src/utils/getWorktreePaths.ts | ⚠️ | packages/core/agent-core/src/utils/getWorktreePaths.ts | Usa analytics e CLI, requer adaptação para Nexias |
| src/utils/getWorktreePathsPortable.ts | ✅ | packages/core/agent-core/src/utils/getWorktreePathsPortable.ts | Implementação portátil sem deps CLI, útil para Nexias |
| src/utils/ghPrStatus.ts | ⚠️ | packages/core/agent-core/src/utils/ghPrStatus.ts | Lógica GitHub PR, mas depende execFileNoThrow, adaptar |
| src/utils/git.ts | ✅ | packages/core/agent-core/src/utils/git.ts | Lógica git central, sem UI, útil para Nexias |
| src/utils/git/gitConfigParser.ts | ✅ | packages/core/agent-core/src/utils/git/gitConfigParser.ts | Parser git config leve, útil para Nexias |
| src/utils/git/gitFilesystem.ts | ✅ | packages/core/agent-core/src/utils/git/gitFilesystem.ts | Leitura git via FS, sem subprocessos, valioso |
| src/utils/git/gitignore.ts | ⚠️ | packages/core/agent-core/src/utils/git/gitignore.ts | Usa execFileNoThrowWithCwd, adaptação necessária |
| src/utils/gitDiff.ts | ⚠️ | packages/core/agent-core/src/utils/gitDiff.ts | Usa execFileNoThrow, lógica útil mas adaptar |
| src/utils/gitSettings.ts | ✅ | packages/core/agent-core/src/utils/gitSettings.ts | Configurações git baseadas em env e settings |
| src/utils/github/ghAuthStatus.ts | ⚠️ | packages/core/agent-core/src/utils/github/ghAuthStatus.ts | Usa execa e which, adaptação para Nexias necessária |
| src/utils/githubRepoPathMapping.ts | ✅ | packages/core/agent-core/src/utils/githubRepoPathMapping.ts | Gerenciamento mapeamento paths GitHub, útil |
| src/utils/glob.ts | ✅ | packages/core/agent-core/src/utils/glob.ts | Utilitário glob, sem deps CLI, aproveitável |
| src/utils/gracefulShutdown.ts | ❌ |  | Usa ink, terminal, UI e signal-exit, não web |
| src/utils/groupToolUses.ts | ✅ | packages/core/agent-core/src/utils/groupToolUses.ts | Lógica agrupamento mensagens, sem UI, útil |
| src/utils/handlePromptSubmit.ts | ⚠️ | packages/core/agent-core/src/utils/handlePromptSubmit.ts | Usa analytics e componentes UI, adaptar lógica |
| src/utils/hash.ts | ✅ | packages/core/agent-core/src/utils/hash.ts | Utilitário hash, sem deps CLI, aproveitável |
| src/utils/headlessProfiler.ts | ⚠️ | packages/core/agent-core/src/utils/headlessProfiler.ts | Provável uso específico, adaptar para Nexias |
| src/utils/heapDumpService.ts | ⚠️ | packages/core/agent-core/src/utils/heapDumpService.ts | Serviço heap dump, depende ambiente, adaptar |
| src/utils/heatmap.ts | ❌ |  | Provável UI ou terminal, não aplicável para Nexias |
| src/utils/highlightMatch.tsx | ❌ |  | Usa React e Ink, UI terminal |
| src/utils/hooks.ts | ⚠️ | packages/core/agent-core/src/utils/hooks.ts | Lógica shell hooks, adaptações para web |
| src/utils/hooks/AsyncHookRegistry.ts | ✅ | packages/core/agent-core/src/utils/hooks/AsyncHookRegistry.ts | Registro async hooks, lógica reutilizável |
| src/utils/hooks/apiQueryHookHelper.ts | ✅ | packages/core/agent-core/src/utils/hooks/apiQueryHookHelper.ts | Helpers para query API, lógica útil |
| src/utils/hooks/execAgentHook.ts | ✅ | packages/core/agent-core/src/utils/hooks/execAgentHook.ts | Execução hooks agente, lógica negócio |
| src/utils/hooks/execHttpHook.ts | ✅ | packages/core/agent-core/src/utils/hooks/execHttpHook.ts | Execução hooks HTTP, lógica reutilizável |
| src/utils/hooks/execPromptHook.ts | ✅ | packages/core/agent-core/src/utils/hooks/execPromptHook.ts | Execução hooks prompt, lógica negócio |
| src/utils/hooks/fileChangedWatcher.ts | ⚠️ | packages/core/agent-core/src/utils/hooks/fileChangedWatcher.ts | Watcher arquivos, adaptação para serverless |
| src/utils/hooks/hookEvents.ts | ✅ | packages/core/agent-core/src/utils/hooks/hookEvents.ts | Sistema eventos hooks, lógica útil |
| src/utils/hooks/hookHelpers.ts | ✅ | packages/core/agent-core/src/utils/hooks/hookHelpers.ts | Helpers para hooks, lógica reutilizável |
| src/utils/hooks/hooksConfigManager.ts | ✅ | packages/core/agent-core/src/utils/hooks/hooksConfigManager.ts | Gerenciamento config hooks, lógica negócio |
| src/utils/hooks/hooksConfigSnapshot.ts | ✅ | packages/core/agent-core/src/utils/hooks/hooksConfigSnapshot.ts | Snapshot config hooks, lógica útil |
| src/utils/hooks/hooksSettings.ts | ✅ | packages/core/agent-core/src/utils/hooks/hooksSettings.ts | Configurações hooks, lógica negócio |
| src/utils/hooks/postSamplingHooks.ts | ✅ | packages/core/agent-core/src/utils/hooks/postSamplingHooks.ts | Tipos e lógica pós-sampling hooks |
| src/utils/hooks/registerFrontmatterHooks.ts | ⚠️ | packages/core/agent-core/src/utils/hooks/registerFrontmatterHooks.ts | Registro hooks frontmatter, reescrita |
| src/utils/hooks/registerSkillHooks.ts | ⚠️ | packages/core/agent-core/src/utils/hooks/registerSkillHooks.ts | Registro skill hooks, adaptação necessária |
| src/utils/hooks/sessionHooks.ts | ✅ | packages/core/agent-core/src/utils/hooks/sessionHooks.ts | Hooks de sessão, lógica negócio |
| src/utils/hooks/skillImprovement.ts | ⚠️ | packages/core/agent-core/src/utils/hooks/skillImprovement.ts | Melhoria skill, conceito útil, reescrever |
| src/utils/hooks/ssrfGuard.ts | ✅ | packages/core/agent-core/src/utils/hooks/ssrfGuard.ts | Proteção SSRF, lógica reutilizável |
| src/utils/horizontalScroll.ts | ❌ |  | Provável UI/terminal, sem valor web serverless |
| src/utils/http.ts | ✅ | packages/core/agent-core/src/utils/http.ts | HTTP helpers com axios, útil para backend Nexias |
| src/utils/hyperlink.ts | ❌ |  | Terminal hyperlink com ANSI e chalk, não web |
| src/utils/iTermBackup.ts | ❌ |  | Específico para iTerm2 e fs local, não serverless |
| src/utils/ide.ts | ⚠️ | packages/core/agent-core/src/utils/ide.ts | Lógica IDE útil, mas depende de execa e net, reescrever |
| src/utils/idePathConversion.ts | ✅ | packages/core/agent-core/src/utils/idePathConversion.ts | Conversão de paths, lógica reutilizável no Nexias |
| src/utils/idleTimeout.ts | ✅ | packages/core/agent-core/src/utils/idleTimeout.ts | Gerenciamento de timeout idle, útil para SDK Nexias |
| src/utils/imagePaste.ts | ⚠️ | packages/core/agent-core/src/utils/imagePaste.ts | Usa Bun e execa, lógica imagem útil, reescrever |
| src/utils/imageResizer.ts | ✅ | packages/core/agent-core/src/utils/imageResizer.ts | Redimensionamento de imagens, lógica aproveitável |
| src/utils/imageStore.ts | ⚠️ | packages/core/agent-core/src/utils/imageStore.ts | Armazenamento local de imagens, adaptar para cloud |
| src/utils/imageValidation.ts | ✅ | packages/core/agent-core/src/utils/imageValidation.ts | Validação de imagens, lógica pura reutilizável |
| src/utils/immediateCommand.ts | ✅ | packages/core/agent-core/src/utils/immediateCommand.ts | Lógica de feature flag, simples e útil |
| src/utils/inProcessTeammateHelpers.ts | ✅ | packages/core/agent-core/src/utils/inProcessTeammateHelpers.ts | Helpers de teammate, lógica de negócio aproveitável |
| src/utils/ink.ts | ❌ |  | Relacionado a Ink (terminal UI), não importar |
| src/utils/intl.ts | ✅ | packages/core/agent-core/src/utils/intl.ts | Intl caching, utilitário puro e reutilizável |
| src/utils/jetbrains.ts | ⚠️ | packages/core/agent-core/src/utils/jetbrains.ts | Lógica IDE Jetbrains, depende de fs local, adaptar |
| src/utils/json.ts | ✅ | packages/core/agent-core/src/utils/json.ts | Parsing JSON com cache, utilitário valioso |
| src/utils/jsonRead.ts | ✅ | packages/core/agent-core/src/utils/jsonRead.ts | stripBOM para JSON, utilitário puro e útil |
| src/utils/keyboardShortcuts.ts | ❌ |  | Provável ligado a terminal/CLI, não importar |
| src/utils/lazySchema.ts | ⚠️ | packages/core/agent-core/src/utils/lazySchema.ts | Schema lazy loading, conceito útil, reescrever |
| src/utils/listSessionsImpl.ts | ⚠️ | packages/core/agent-core/src/utils/listSessionsImpl.ts | Listagem de sessões, depende de estado local, adaptar |
| src/utils/localInstaller.ts | ⚠️ | packages/core/agent-core/src/utils/localInstaller.ts | Usa fs/promises, adaptação para ambiente serverless necessária |
| src/utils/lockfile.ts | ⚠️ | packages/core/agent-core/src/utils/lockfile.ts | Lazy load de proper-lockfile, depende de monkey-patching fs |
| src/utils/log.ts | ⚠️ | packages/core/agent-core/src/utils/log.ts | Lógica de logs, mas depende de Bun e estado global |
| src/utils/logoV2Utils.ts | ⚠️ | packages/core/agent-core/src/utils/logoV2Utils.ts | Utilitários de formatação e estado, adaptação para Nexias |
| src/utils/mailbox.ts | ✅ | packages/core/agent-core/src/utils/mailbox.ts | Classe Mailbox, lógica de fila de mensagens reutilizável |
| src/utils/managedEnv.ts | ⚠️ | packages/core/agent-core/src/utils/managedEnv.ts | Gerenciamento de variáveis ambiente, depende de serviços internos |
| src/utils/managedEnvConstants.ts | ✅ | packages/core/agent-core/src/utils/managedEnvConstants.ts | Constantes de variáveis ambiente, útil para Nexias |
| src/utils/markdown.ts | ⚠️ | packages/core/agent-core/src/utils/markdown.ts | Parser markdown com deps de terminal, precisa adaptação |
| src/utils/markdownConfigLoader.ts | ⚠️ | packages/core/agent-core/src/utils/markdownConfigLoader.ts | Carregamento config markdown, usa fs e memoize, adaptar |
| src/utils/mcp/dateTimeParser.ts | ✅ | packages/core/agent-core/src/utils/mcp/dateTimeParser.ts | Parser de data/hora natural, lógica pura reaproveitável |
| src/utils/mcp/elicitationValidation.ts | ✅ | packages/core/agent-core/src/utils/mcp/elicitationValidation.ts | Validação de schema, lógica de negócio útil |
| src/utils/mcpInstructionsDelta.ts | ✅ | packages/core/agent-core/src/utils/mcpInstructionsDelta.ts | Tipos e lógica para instruções MCP, aproveitável |
| src/utils/mcpOutputStorage.ts | ⚠️ | packages/core/agent-core/src/utils/mcpOutputStorage.ts | Usa fs para salvar arquivos, adaptar para Cloud Run |
| src/utils/mcpValidation.ts | ✅ | packages/core/agent-core/src/utils/mcpValidation.ts | Validação MCP, contagem tokens, lógica reutilizável |
| src/utils/mcpWebSocketTransport.ts | ✅ | packages/core/agent-core/src/utils/mcpWebSocketTransport.ts | Transporte WebSocket, lógica útil para Nexias |
| src/utils/memoize.ts | ✅ | packages/core/agent-core/src/utils/memoize.ts | Memoização com LRU, lógica pura reaproveitável |
| src/utils/memory/types.ts | ✅ | packages/core/agent-core/src/utils/memory/types.ts | Tipos TS, reutilizáveis sem adaptação |
| src/utils/memory/versions.ts | ✅ | packages/core/agent-core/src/utils/memory/versions.ts | Controle de versões, lógica pura reaproveitável |
| src/utils/memoryFileDetection.ts | ⚠️ | packages/core/agent-core/src/utils/memoryFileDetection.ts | Detecta arquivos, usa fs, adaptar para serverless |
| src/utils/messagePredicates.ts | ✅ | packages/core/agent-core/src/utils/messagePredicates.ts | Predicados para mensagens, lógica pura reaproveitável |
| src/utils/messageQueueManager.ts | ✅ | packages/core/agent-core/src/utils/messageQueueManager.ts | Gerenciamento de fila, lógica reutilizável sem deps CLI |
| src/utils/messages.ts | ✅ | packages/core/agent-core/src/utils/messages.ts | Manipulação de mensagens, lógica de negócio pura |
| src/utils/messages/mappers.ts | ✅ | packages/core/agent-core/src/utils/messages/mappers.ts | Mapeamento de mensagens, útil para integração SDK |
| src/utils/messages/systemInit.ts | ⚠️ | packages/core/agent-core/src/utils/messages/systemInit.ts | Inicialização sistema, depende de estado CLI, adaptar |
| src/utils/model/agent.ts | ✅ | packages/core/agent-core/src/utils/model/agent.ts | Modelos de agente, lógica de negócio pura |
| src/utils/model/aliases.ts | ✅ | packages/core/agent-core/src/utils/model/aliases.ts | Alias de modelos, utilitário simples e reutilizável |
| src/utils/model/antModels.ts | ✅ | packages/core/agent-core/src/utils/model/antModels.ts | Definições de modelos, dados e tipos úteis |
| src/utils/model/bedrock.ts | ⚠️ | packages/core/agent-core/src/utils/model/bedrock.ts | AWS Bedrock client, adaptação para ambiente serverless |
| src/utils/model/check1mAccess.ts | ✅ | packages/core/agent-core/src/utils/model/check1mAccess.ts | Verificação de acesso, lógica reutilizável |
| src/utils/model/configs.ts | ✅ | packages/core/agent-core/src/utils/model/configs.ts | Configurações de modelos, dados estáticos úteis |
| src/utils/model/contextWindowUpgradeCheck.ts | ✅ | packages/core/agent-core/src/utils/model/contextWindowUpgradeCheck.ts | Lógica de upgrade de contexto, negócio puro |
| src/utils/model/deprecation.ts | ✅ | packages/core/agent-core/src/utils/model/deprecation.ts | Utilitários de depreciação, lógica reutilizável |
| src/utils/model/model.ts | ✅ | packages/core/agent-core/src/utils/model/model.ts | Lógica central de modelos, negócio puro |
| src/utils/model/modelAllowlist.ts | ✅ | packages/core/agent-core/src/utils/model/modelAllowlist.ts | Controle de allowlist, lógica reutilizável |
| src/utils/model/modelCapabilities.ts | ⚠️ | packages/core/agent-core/src/utils/model/modelCapabilities.ts | Manipulação arquivos e cache, adaptar para serverless |
| src/utils/model/modelOptions.ts | ✅ | packages/core/agent-core/src/utils/model/modelOptions.ts | Opções de modelos, lógica de negócio pura |
| src/utils/model/modelStrings.ts | ⚠️ | packages/core/agent-core/src/utils/model/modelStrings.ts | Estado global e logs, requer adaptação significativa |
| src/utils/model/modelSupportOverrides.ts | ⚠️ | packages/core/agent-core/src/utils/model/modelSupportOverrides.ts | Overrides específicos, adaptar para Nexias |
| src/utils/model/providers.ts | ✅ | packages/core/agent-core/src/utils/model/providers.ts | Provedores API, lógica reutilizável |
| src/utils/model/validateModel.ts | ✅ | packages/core/agent-core/src/utils/model/validateModel.ts | Validação de modelos, lógica pura e útil |
| src/utils/modelCost.ts | ✅ | packages/core/agent-core/src/utils/modelCost.ts | Lógica de custo de modelo reutilizável em backend |
| src/utils/modifiers.ts | ❌ |  | Código específico para macOS e módulo nativo |
| src/utils/mtls.ts | ✅ | packages/core/agent-core/src/utils/mtls.ts | Configuração TLS/MTLS útil para conexões seguras |
| src/utils/nativeInstaller/download.ts | ❌ |  | Código específico para desktop/Bun e downloads nativos |
| src/utils/nativeInstaller/index.ts | ❌ |  | API de instalador nativo específico para desktop |
| src/utils/nativeInstaller/installer.ts | ❌ |  | Gerenciamento de instalação nativa, desktop-only |
| src/utils/nativeInstaller/packageManagers.ts | ❌ |  | Detecção de package managers para CLI desktop |
| src/utils/nativeInstaller/pidLock.ts | ❌ |  | Locking baseado em PID para processos desktop |
| src/utils/notebook.ts | ⚠️ | packages/core/agent-core/src/utils/notebook.ts | Lógica de notebook útil, mas depende de fs e paths |
| src/utils/objectGroupBy.ts | ✅ | packages/core/agent-core/src/utils/objectGroupBy.ts | Utilitário genérico para agrupar objetos |
| src/utils/pasteStore.ts | ⚠️ | packages/core/agent-core/src/utils/pasteStore.ts | Armazenamento local, precisa adaptação para cloud |
| src/utils/path.ts | ✅ | packages/core/agent-core/src/utils/path.ts | Utilitários de path portáveis para backend |
| src/utils/pdf.ts | ⚠️ | packages/core/agent-core/src/utils/pdf.ts | Lógica PDF útil, mas depende de fs e execFile |
| src/utils/pdfUtils.ts | ✅ | packages/core/agent-core/src/utils/pdfUtils.ts | Utilitários para manipulação de PDFs |
| src/utils/peerAddress.ts | ✅ | packages/core/agent-core/src/utils/peerAddress.ts | Parsing de endereços útil para comunicação |
| src/utils/permissions/PermissionMode.ts | ⚠️ | packages/core/agent-core/src/utils/permissions/PermissionMode.ts | Tipos e schemas, mas usa bun:bundle e zod |
| src/utils/permissions/PermissionPromptToolResultSchema.ts | ⚠️ | packages/core/agent-core/src/utils/permissions/PermissionPromptToolResultSchema.ts | Schema e lógica de permissão, depende de zod |
| src/utils/permissions/PermissionResult.ts | ✅ | packages/core/agent-core/src/utils/permissions/PermissionResult.ts | Tipos de permissão reutilizáveis no backend |
| src/utils/permissions/PermissionRule.ts | ⚠️ | packages/core/agent-core/src/utils/permissions/PermissionRule.ts | Regras de permissão, lógica valiosa porém complexa |
| src/utils/permissions/PermissionUpdate.ts | ⚠️ | packages/core/agent-core/src/utils/permissions/PermissionUpdate.ts | Atualizações de permissão, requer adaptação |
| src/utils/permissions/PermissionUpdateSchema.ts | ✅ | packages/core/agent-core/src/utils/permissions/PermissionUpdateSchema.ts | Zod schemas para permissões, sem deps CLI |
| src/utils/permissions/autoModeState.ts | ✅ | packages/core/agent-core/src/utils/permissions/autoModeState.ts | Estado auto mode, lógica reutilizável |
| src/utils/permissions/bashClassifier.ts | ⚠️ | packages/core/agent-core/src/utils/permissions/bashClassifier.ts | Lógica classifier, mas stub e específica bash |
| src/utils/permissions/bypassPermissionsKillswitch.ts | ❌ |  | Usa React, hooks, ambiente desktop/CLI |
| src/utils/permissions/classifierDecision.ts | ❌ |  | Importa ferramentas específicas, ambiente Bun |
| src/utils/permissions/classifierShared.ts | ✅ | packages/core/agent-core/src/utils/permissions/classifierShared.ts | Infraestrutura compartilhada, lógica pura |
| src/utils/permissions/dangerousPatterns.ts | ✅ | packages/core/agent-core/src/utils/permissions/dangerousPatterns.ts | Listas padrões perigosos, lógica pura |
| src/utils/permissions/denialTracking.ts | ✅ | packages/core/agent-core/src/utils/permissions/denialTracking.ts | Estado e lógica tracking, sem deps CLI |
| src/utils/permissions/filesystem.ts | ⚠️ | packages/core/agent-core/src/utils/permissions/filesystem.ts | Usa Bun, crypto, lodash, mas lógica útil |
| src/utils/permissions/getNextPermissionMode.ts | ⚠️ | packages/core/agent-core/src/utils/permissions/getNextPermissionMode.ts | Usa feature flags Bun, lógica permission mode |
| src/utils/permissions/pathValidation.ts | ✅ | packages/core/agent-core/src/utils/permissions/pathValidation.ts | Validação paths, lógica reutilizável |
| src/utils/permissions/permissionExplainer.ts | ✅ | packages/core/agent-core/src/utils/permissions/permissionExplainer.ts | Explicação permissão, lógica sem UI |
| src/utils/permissions/permissionRuleParser.ts | ⚠️ | packages/core/agent-core/src/utils/permissions/permissionRuleParser.ts | Usa Bun feature, mas lógica parser útil |
| src/utils/permissions/permissionSetup.ts | ⚠️ | packages/core/agent-core/src/utils/permissions/permissionSetup.ts | Lógica complexa, usa Bun feature e paths |
| src/utils/permissions/permissions.ts | ⚠️ | packages/core/agent-core/src/utils/permissions/permissions.ts | Lógica negócio, mas depende Bun e hooks |
| src/utils/permissions/permissionsLoader.ts | ❌ |  | Não fornecido, provável loader específico CLI |
| src/utils/permissions/shadowedRuleDetection.ts | ❌ |  | Não fornecido, provável lógica específica CLI |
| src/utils/permissions/shellRuleMatching.ts | ❌ |  | Não fornecido, provável lógica shell específica |
| src/utils/permissions/yoloClassifier.ts | ⚠️ | packages/core/agent-core/src/utils/yoloClassifier.ts | Lógica de permissão útil, depende de Bun e fs/promises |
| src/utils/planModeV2.ts | ✅ | packages/core/agent-core/src/utils/planModeV2.ts | Lógica de negócio para planos, sem deps de UI |
| src/utils/plans.ts | ⚠️ | packages/core/agent-core/src/utils/plans.ts | Lógica de planos com fs, precisa adaptação para Cloud Run |
| src/utils/platform.ts | ✅ | packages/core/agent-core/src/utils/platform.ts | Detecta plataforma, útil para Nexias sem UI |
| src/utils/plugins/addDirPluginSettings.ts | ✅ | packages/core/plugins/src/utils/addDirPluginSettings.ts | Lógica de leitura de configurações, sem UI |
| src/utils/plugins/cacheUtils.ts | ⚠️ | packages/core/plugins/src/utils/cacheUtils.ts | Gerenciamento cache plugins, fs intensivo, adaptar para serverless |
| src/utils/plugins/dependencyResolver.ts | ✅ | packages/core/plugins/src/utils/dependencyResolver.ts | Lógica pura de resolução de dependências |
| src/utils/plugins/fetchTelemetry.ts | ✅ | packages/core/plugins/src/utils/fetchTelemetry.ts | Telemetria útil para Nexias, sem UI |
| src/utils/plugins/gitAvailability.ts | ✅ | packages/core/plugins/src/utils/gitAvailability.ts | Verifica disponibilidade git, útil para Nexias |
| src/utils/plugins/headlessPluginInstall.ts | ⚠️ | packages/core/plugins/src/utils/headlessPluginInstall.ts | Instalação headless, fs e estado, adaptar para Nexias |
| src/utils/plugins/hintRecommendation.ts | ⚠️ | packages/core/plugins/src/utils/hintRecommendation.ts | Lógica de recomendação, depende de analytics, adaptar |
| src/utils/plugins/installCounts.ts | ⚠️ | packages/core/plugins/src/utils/installCounts.ts | Cache e fetch counts, fs e rede, adaptar para serverless |
| src/utils/plugins/installedPluginsManager.ts | ⚠️ | packages/core/plugins/src/utils/installedPluginsManager.ts | Gerencia estado instalação plugins, fs intensivo |
| src/utils/plugins/loadPluginAgents.ts | ⚠️ | packages/core/plugins/src/utils/loadPluginAgents.ts | Carregamento agentes plugins, lógica complexa, adaptar |
| src/utils/plugins/loadPluginCommands.ts | ⚠️ | packages/core/plugins/src/utils/loadPluginCommands.ts | Carregamento comandos plugins, lógica complexa, adaptar |
| src/utils/plugins/loadPluginHooks.ts | ⚠️ | packages/core/plugins/src/utils/loadPluginHooks.ts | Carregamento hooks plugins, lógica complexa, adaptar |
| src/utils/plugins/loadPluginOutputStyles.ts | ⚠️ | packages/core/plugins/src/utils/loadPluginOutputStyles.ts | Carregamento estilos saída, lógica complexa, adaptar |
| src/utils/plugins/lspPluginIntegration.ts | ⚠️ | packages/core/plugins/src/utils/lspPluginIntegration.ts | Integração LSP, lógica valiosa, adaptar para Nexias |
| src/utils/plugins/lspRecommendation.ts | ⚠️ | packages/core/plugins/src/utils/lspRecommendation.ts | Recomendação LSP, lógica valiosa, adaptar para Nexias |
| src/utils/plugins/managedPlugins.ts | ✅ | packages/core/agent-core/src/utils/plugins/managedPlugins.ts | Lógica de política de plugins reutilizável, sem deps CLI |
| src/utils/plugins/marketplaceHelpers.ts | ✅ | packages/core/agent-core/src/utils/plugins/marketplaceHelpers.ts | Helpers para marketplace, lógica de negócio pura |
| src/utils/plugins/marketplaceManager.ts | ⚠️ | packages/core/agent-core/src/utils/plugins/marketplaceManager.ts | Gerenciamento marketplace, precisa adaptação para Nexias |
| src/utils/plugins/mcpPluginIntegration.ts | ⚠️ | packages/core/agent-core/src/utils/plugins/mcpPluginIntegration.ts | Integração MCP, lógica útil mas depende ajustes |
| src/utils/plugins/mcpbHandler.ts | ⚠️ | packages/core/agent-core/src/utils/plugins/mcpbHandler.ts | Manipulação MCPB, uso de fs e rede, adaptar para serverless |
| src/utils/plugins/officialMarketplace.ts | ✅ | packages/core/agent-core/src/utils/plugins/officialMarketplace.ts | Constantes marketplace oficial, lógica simples |
| src/utils/plugins/officialMarketplaceGcs.ts | ⚠️ | packages/core/agent-core/src/utils/plugins/officialMarketplaceGcs.ts | Download e extração zip, adaptar para ambiente cloud |
| src/utils/plugins/officialMarketplaceStartupCheck.ts | ⚠️ | packages/core/agent-core/src/utils/plugins/officialMarketplaceStartupCheck.ts | Startup checks, lógica valiosa mas com deps fs/git |
| src/utils/plugins/orphanedPluginFilter.ts | ⚠️ | packages/core/agent-core/src/utils/plugins/orphanedPluginFilter.ts | Filtros glob para plugins órfãos, depende ripgrep/fs |
| src/utils/plugins/parseMarketplaceInput.ts | ✅ | packages/core/agent-core/src/utils/plugins/parseMarketplaceInput.ts | Parsing input marketplace, lógica pura e útil |
| src/utils/plugins/pluginAutoupdate.ts | ✅ | packages/core/agent-core/src/utils/plugins/pluginAutoupdate.ts | Atualização automática plugins, lógica de negócio |
| src/utils/plugins/pluginBlocklist.ts | ✅ | packages/core/agent-core/src/utils/plugins/pluginBlocklist.ts | Detecção e remoção plugins bloqueados, lógica útil |
| src/utils/plugins/pluginDirectories.ts | ⚠️ | packages/core/agent-core/src/utils/plugins/pluginDirectories.ts | Config dirs plugins, depende fs, adaptar para cloud |
| src/utils/plugins/pluginFlagging.ts | ⚠️ | packages/core/agent-core/src/utils/plugins/pluginFlagging.ts | Flagging plugins, lógica valiosa mas precisa adaptação |
| src/utils/plugins/pluginIdentifier.ts | ✅ | packages/core/agent-core/src/utils/plugins/pluginIdentifier.ts | Identificação plugins, lógica pura e reutilizável |
| src/utils/plugins/pluginInstallationHelpers.ts | ⚠️ | packages/core/agent-core/src/utils/plugins/pluginInstallationHelpers.ts | Helpers instalação plugins, depende fs, adaptar |
| src/utils/plugins/pluginLoader.ts | ⚠️ | packages/core/agent-core/src/utils/plugins/pluginLoader.ts | Loader plugins, lógica importante mas com fs |
| src/utils/plugins/pluginOptionsStorage.ts | ⚠️ | packages/core/agent-core/src/utils/plugins/pluginOptionsStorage.ts | Armazenamento opções plugins, depende fs, adaptar |
| src/utils/plugins/pluginPolicy.ts | ✅ | packages/core/agent-core/src/utils/plugins/pluginPolicy.ts | Política plugins, lógica de negócio pura |
| src/utils/plugins/pluginStartupCheck.ts | ✅ | packages/core/agent-core/src/utils/plugins/pluginStartupCheck.ts | Lógica de inicialização de plugins reutilizável no Nexias |
| src/utils/plugins/pluginVersioning.ts | ✅ | packages/core/agent-core/src/utils/plugins/pluginVersioning.ts | Cálculo de versão de plugins sem dependências específicas |
| src/utils/plugins/reconciler.ts | ✅ | packages/core/agent-core/src/utils/plugins/reconciler.ts | Reconciliador de marketplace útil para gestão de plugins |
| src/utils/plugins/refresh.ts | ✅ | packages/core/agent-core/src/utils/plugins/refresh.ts | Atualização ativa de plugins aplicável no Nexias |
| src/utils/plugins/schemas.ts | ✅ | packages/core/agent-core/src/utils/plugins/schemas.ts | Schemas de validação de plugins úteis para Nexias |
| src/utils/plugins/validatePlugin.ts | ✅ | packages/core/agent-core/src/utils/plugins/validatePlugin.ts | Validação de plugins com lógica reutilizável |
| src/utils/plugins/walkPluginMarkdown.ts | ✅ | packages/core/agent-core/src/utils/plugins/walkPluginMarkdown.ts | Caminhamento recursivo de markdown em plugins útil |
| src/utils/plugins/zipCache.ts | ⚠️ | packages/core/agent-core/src/utils/plugins/zipCache.ts | Cache ZIP específico, requer adaptação para serverless |
| src/utils/plugins/zipCacheAdapters.ts | ⚠️ | packages/core/agent-core/src/utils/plugins/zipCacheAdapters.ts | Helpers ZIP dependem de FS local, adaptação necessária |
| src/utils/powershell/dangerousCmdlets.ts | ✅ | packages/core/agent-core/src/utils/powershell/dangerousCmdlets.ts | Constantes para segurança PowerShell reutilizáveis |
| src/utils/powershell/parser.ts | ✅ | packages/core/agent-core/src/utils/powershell/parser.ts | Parser PowerShell útil para análise de comandos |
| src/utils/powershell/staticPrefix.ts | ✅ | packages/core/agent-core/src/utils/powershell/staticPrefix.ts | Extração estática de prefixos para segurança |
| src/utils/preflightChecks.tsx | ❌ |  | Componente React/Ink para terminal, UI CLI |
| src/utils/privacyLevel.ts | ✅ | packages/core/agent-core/src/utils/privacyLevel.ts | Controle de nível de privacidade sem dependências UI |
| src/utils/process.ts | ⚠️ | packages/core/agent-core/src/utils/process.ts | Lida com streams e erros, adaptação para serverless |
| src/utils/processUserInput/processBashCommand.tsx | ❌ |  | UI React/Ink para terminal, não aplicável Nexias |
| src/utils/processUserInput/processSlashCommand.tsx | ❌ |  | UI React/Ink para terminal, não aplicável Nexias |
| src/utils/processUserInput/processTextPrompt.ts | ✅ | packages/core/agent-core/src/utils/processUserInput/processTextPrompt.ts | Lógica de processamento de texto reutilizável |
| src/utils/processUserInput/processUserInput.ts | ✅ | packages/core/agent-core/src/utils/processUserInput/processUserInput.ts | Processamento geral de input reutilizável |
| src/utils/profilerBase.ts | ✅ | packages/core/agent-core/src/utils/profilerBase.ts | Base para profiling sem dependências UI |
| src/utils/promptCategory.ts | ✅ | packages/core/agent-core/src/utils/promptCategory.ts | Lógica de categorização de prompt reutilizável |
| src/utils/promptEditor.ts | ❌ |  | Depende de CLI/editor local, execSync, fs específico |
| src/utils/promptShellExecution.ts | ⚠️ | packages/core/agent-core/src/utils/promptShellExecution.ts | Lógica shell útil, mas adaptações para serverless |
| src/utils/proxy.ts | ⚠️ | packages/core/network/src/utils/proxy.ts | Lógica proxy valiosa, mas depende de libs node específicas |
| src/utils/queryContext.ts | ✅ | packages/core/agent-core/src/utils/queryContext.ts | Helpers contexto query, sem deps CLI |
| src/utils/queryHelpers.ts | ✅ | packages/core/agent-core/src/utils/queryHelpers.ts | Helpers para orquestração de tools e mensagens |
| src/utils/queryProfiler.ts | ⚠️ | packages/core/agent-core/src/utils/queryProfiler.ts | Profiling útil, mas depende de Node.js performance API |
| src/utils/queueProcessor.ts | ✅ | packages/core/agent-core/src/utils/queueProcessor.ts | Processamento de fila reutilizável para comandos |
| src/utils/readEditContext.ts | ⚠️ | packages/core/agent-core/src/utils/readEditContext.ts | Leitura de arquivo com contexto, depende fs/promises |
| src/utils/readFileInRange.ts | ⚠️ | packages/core/agent-core/src/utils/readFileInRange.ts | Leitura eficiente de arquivo, depende fs e streams |
| src/utils/releaseNotes.ts | ⚠️ | packages/core/utils/src/releaseNotes.ts | Fetch changelog via axios, adaptação para web |
| src/utils/renderOptions.ts | ❌ |  | Depende de tty, stdin streams, ambiente CLI |
| src/utils/ripgrep.ts | ⚠️ | packages/core/utils/src/ripgrep.ts | Execução ripgrep via child_process, adaptação necessária |
| src/utils/sandbox/sandbox-adapter.ts | ⚠️ | packages/core/agent-core/src/utils/sandbox-adapter.ts | Adapter CLI para sandbox, precisa reescrita |
| src/utils/sandbox/sandbox-ui-utils.ts | ❌ |  | UI utils para sandbox, dependente de terminal/CLI |
| src/utils/sanitization.ts | ✅ | packages/core/agent-core/src/utils/sanitization.ts | Sanitização genérica, sem deps CLI |
| src/utils/screenshotClipboard.ts | ❌ |  | Screenshot e clipboard dependem desktop/CLI |
| src/utils/sdkEventQueue.ts | ✅ | packages/core/agent-core/src/utils/sdkEventQueue.ts | Fila de eventos SDK, lógica reutilizável |
| src/utils/secureStorage/fallbackStorage.ts | ⚠️ | packages/core/security/src/secureStorage/fallbackStorage.ts | Storage fallback, depende ambiente, adaptação necessária |
| src/utils/secureStorage/index.ts | ✅ | packages/core/agent-core/src/utils/secureStorage/index.ts | Abstração multiplataforma para armazenamento seguro |
| src/utils/secureStorage/keychainPrefetch.ts | ⚠️ | packages/core/agent-core/src/utils/secureStorage/keychainPrefetch.ts | Prefetch macOS keychain, depende de execSync, adaptação necessária |
| src/utils/secureStorage/macOsKeychainHelpers.ts | ⚠️ | packages/core/agent-core/src/utils/secureStorage/macOsKeychainHelpers.ts | Helpers macOS sem execa, mas dependente de os/crypto |
| src/utils/secureStorage/macOsKeychainStorage.ts | ❌ |  | Uso pesado de execa e execFile, específico macOS CLI |
| src/utils/secureStorage/plainTextStorage.ts | ✅ | packages/core/agent-core/src/utils/secureStorage/plainTextStorage.ts | Armazenamento simples em arquivo, útil para fallback |
| src/utils/semanticBoolean.ts | ✅ | packages/core/agent-core/src/utils/semanticBoolean.ts | Validação zod para booleanos com strings |
| src/utils/semanticNumber.ts | ✅ | packages/core/agent-core/src/utils/semanticNumber.ts | Validação zod para números com strings numéricas |
| src/utils/semver.ts | ✅ | packages/core/agent-core/src/utils/semver.ts | Utilitário semver com fallback para Node.js |
| src/utils/sequential.ts | ✅ | packages/core/agent-core/src/utils/sequential.ts | Wrapper para execução sequencial de async functions |
| src/utils/sessionActivity.ts | ✅ | packages/core/agent-core/src/utils/sessionActivity.ts | Gerenciamento de atividade de sessão com heartbeat |
| src/utils/sessionEnvVars.ts | ✅ | packages/core/agent-core/src/utils/sessionEnvVars.ts | Gerenciamento de variáveis de ambiente de sessão |
| src/utils/sessionEnvironment.ts | ✅ | packages/core/agent-core/src/utils/sessionEnvironment.ts | Gerenciamento de ambiente de sessão com FS async |
| src/utils/sessionFileAccessHooks.ts | ⚠️ | packages/core/agent-core/src/utils/sessionFileAccessHooks.ts | Hooks de analytics, depende de bun:bundle, adaptação |
| src/utils/sessionIngressAuth.ts | ✅ | packages/core/agent-core/src/utils/sessionIngressAuth.ts | Autenticação de token para sessão via arquivo |
| src/utils/sessionRestore.ts | ⚠️ | packages/core/agent-core/src/utils/sessionRestore.ts | Lógica de restauração de sessão, possível adaptação |
| src/utils/sessionStart.ts | ⚠️ | packages/core/agent-core/src/utils/sessionStart.ts | Inicialização de sessão, depende de estado global |
| src/utils/sessionState.ts | ✅ | packages/core/agent-core/src/utils/sessionState.ts | Gerenciamento de estado de sessão em memória |
| src/utils/sessionStorage.ts | ✅ | packages/core/agent-core/src/utils/sessionStorage.ts | Armazenamento de sessão, abstração útil para Nexias |
| src/utils/sessionStoragePortable.ts | ✅ | packages/core/agent-core/src/utils/sessionStoragePortable.ts | Versão portátil de sessionStorage, sem deps nativas |
| src/utils/sessionTitle.ts | ✅ | packages/core/agent-core/src/utils/sessionTitle.ts | Utilitário para título de sessão, lógica simples |
| src/utils/sessionUrl.ts | ✅ | packages/core/agent-core/src/utils/sessionUrl.ts | Parsing session URLs, no CLI deps |
| src/utils/set.ts | ✅ | packages/core/agent-core/src/utils/set.ts | Set operations, generic utility |
| src/utils/settings/allErrors.ts | ⚠️ | packages/core/agent-core/src/utils/settings/allErrors.ts | Combines errors, depends on MCP service |
| src/utils/settings/applySettingsChange.ts | ⚠️ | packages/core/agent-core/src/utils/settings/applySettingsChange.ts | Applies settings, depends on app state |
| src/utils/settings/changeDetector.ts | ⚠️ | packages/core/agent-core/src/utils/settings/changeDetector.ts | File watching, partial logic reusable |
| src/utils/settings/constants.ts | ✅ | packages/core/agent-core/src/utils/settings/constants.ts | Constants, no CLI deps |
| src/utils/settings/internalWrites.ts | ✅ | packages/core/agent-core/src/utils/settings/internalWrites.ts | Tracks internal writes, no CLI deps |
| src/utils/settings/managedPath.ts | ✅ | packages/core/agent-core/src/utils/settings/managedPath.ts | Path utils, no CLI deps |
| src/utils/settings/mdm/constants.ts | ✅ | packages/core/agent-core/src/utils/settings/mdm/constants.ts | MDM constants, no heavy deps |
| src/utils/settings/mdm/rawRead.ts | ⚠️ | packages/core/agent-core/src/utils/settings/mdm/rawRead.ts | Subprocess reads, platform specific |
| src/utils/settings/mdm/settings.ts | ⚠️ | packages/core/agent-core/src/utils/settings/mdm/settings.ts | MDM parsing logic, platform specific |
| src/utils/settings/permissionValidation.ts | ✅ | packages/core/agent-core/src/utils/settings/permissionValidation.ts | Validation logic, no CLI deps |
| src/utils/settings/pluginOnlyPolicy.ts | ✅ | packages/core/agent-core/src/utils/settings/pluginOnlyPolicy.ts | Policy logic, no CLI deps |
| src/utils/settings/schemaOutput.ts | ✅ | packages/core/agent-core/src/utils/settings/schemaOutput.ts | JSON schema generation, no CLI deps |
| src/utils/settings/settings.ts | ⚠️ | packages/core/agent-core/src/utils/settings/settings.ts | Complex settings logic, Bun-specific imports |
| src/utils/settings/settingsCache.ts | ✅ | packages/core/agent-core/src/utils/settings/settingsCache.ts | Cache logic, no CLI deps |
| src/utils/settings/toolValidationConfig.ts | ✅ | packages/core/agent-core/src/utils/settings/toolValidationConfig.ts | Validation config, no CLI deps |
| src/utils/settings/types.ts | ✅ | packages/core/agent-core/src/utils/settings/types.ts | Types only, reusable |
| src/utils/settings/validateEditTool.ts | ✅ | packages/core/agent-core/src/utils/settings/validateEditTool.ts | Validation logic, no CLI deps |
| src/utils/settings/validation.ts | ✅ | packages/core/agent-core/src/utils/settings/validation.ts | Validation logic, no CLI deps |
| src/utils/settings/validationTips.ts | ✅ | packages/core/agent-core/src/utils/settings/validationTips.ts | Tipos e dados para validação, sem dependências CLI |
| src/utils/shell/bashProvider.ts | ❌ |  | Depende de Bun, fs/promises, shell e ambiente local |
| src/utils/shell/outputLimits.ts | ✅ | packages/core/agent-core/src/utils/shell/outputLimits.ts | Lógica de limites para shell, útil para controle output |
| src/utils/shell/powershellDetection.ts | ⚠️ | packages/core/agent-core/src/utils/shell/powershellDetection.ts | Lógica de detecção PowerShell, precisa adaptação para Nexias |
| src/utils/shell/powershellProvider.ts | ⚠️ | packages/core/agent-core/src/utils/shell/powershellProvider.ts | Construção args PowerShell, adaptação para ambiente serverless |
| src/utils/shell/prefix.ts | ⚠️ | packages/core/agent-core/src/utils/shell/prefix.ts | Lógica de prefixo shell com dependências API e analytics |
| src/utils/shell/readOnlyCommandValidation.ts | ✅ | packages/core/agent-core/src/utils/shell/readOnlyCommandValidation.ts | Mapas de comandos read-only, lógica reutilizável |
| src/utils/shell/resolveDefaultShell.ts | ✅ | packages/core/agent-core/src/utils/shell/resolveDefaultShell.ts | Lógica simples para shell default, sem dependências CLI |
| src/utils/shell/shellProvider.ts | ⚠️ | packages/core/agent-core/src/utils/shell/shellProvider.ts | Interface e lógica shell, precisa adaptação para Nexias |
| src/utils/shell/shellToolUtils.ts | ⚠️ | packages/core/agent-core/src/utils/shell/shellToolUtils.ts | Lógica runtime para shell tools, depende de plataforma |
| src/utils/shell/specPrefix.ts | ✅ | packages/core/agent-core/src/utils/shell/specPrefix.ts | Extração prefixo comando, lógica pura reutilizável |
| src/utils/shellConfig.ts | ⚠️ | packages/core/agent-core/src/utils/shellConfig.ts | Gerenciamento arquivos config shell, depende fs/promises |
| src/utils/sideQuery.ts | ✅ | packages/core/agent-core/src/utils/sideQuery.ts | Lógica de query lateral, integra API e analytics |
| src/utils/sideQuestion.ts | ✅ | packages/core/agent-core/src/utils/sideQuestion.ts | Lógica de side question, sem UI, útil para Nexias |
| src/utils/signal.ts | ✅ | packages/core/agent-core/src/utils/signal.ts | Implementação simples de sinais/eventos, genérico |
| src/utils/sinks.ts | ⚠️ | packages/core/agent-core/src/utils/sinks.ts | Inicialização de sinks analytics e logs, depende serviços |
| src/utils/skills/skillChangeDetector.ts | ⚠️ | packages/core/agent-core/src/utils/skills/skillChangeDetector.ts | Detecta mudanças em skills, lógica adaptável |
| src/utils/slashCommandParsing.ts | ✅ | packages/core/agent-core/src/utils/slashCommandParsing.ts | Parsing de comandos slash, lógica pura reutilizável |
| src/utils/sleep.ts | ✅ | packages/core/agent-core/src/utils/sleep.ts | Função sleep simples, genérica e útil |
| src/utils/sliceAnsi.ts | ✅ | packages/core/agent-core/src/utils/sliceAnsi.ts | Manipulação de strings ANSI, sem dependências CLI |
| src/utils/slowOperations.ts | ✅ | packages/core/agent-core/src/utils/slowOperations.ts | Lógica de operações lentas, sem deps CLI |
| src/utils/standaloneAgent.ts | ✅ | packages/core/agent-core/src/utils/standaloneAgent.ts | Lógica de agentes standalone reaproveitável |
| src/utils/startupProfiler.ts | ✅ | packages/core/agent-core/src/utils/startupProfiler.ts | Utilitário de profiling sem deps CLI |
| src/utils/staticRender.tsx | ❌ |  | Usa React/Ink para UI terminal |
| src/utils/stats.ts | ✅ | packages/core/agent-core/src/utils/stats.ts | Lógica de estatísticas e manipulação de dados |
| src/utils/statsCache.ts | ✅ | packages/core/agent-core/src/utils/statsCache.ts | Cache de estatísticas, lógica útil |
| src/utils/status.tsx | ❌ |  | Componente React/Ink para terminal |
| src/utils/statusNoticeDefinitions.tsx | ❌ |  | UI React/Ink para terminal |
| src/utils/statusNoticeHelpers.ts | ✅ | packages/core/agent-core/src/utils/statusNoticeHelpers.ts | Helpers para tokens, lógica reaproveitável |
| src/utils/stream.ts | ✅ | packages/core/agent-core/src/utils/stream.ts | Classe utilitária de stream async |
| src/utils/streamJsonStdoutGuard.ts | ✅ | packages/core/agent-core/src/utils/streamJsonStdoutGuard.ts | Guard para stdout JSON, lógica útil |
| src/utils/streamlinedTransform.ts | ✅ | packages/core/agent-core/src/utils/streamlinedTransform.ts | Transformação de mensagens SDK |
| src/utils/stringUtils.ts | ✅ | packages/core/agent-core/src/utils/stringUtils.ts | Utilitários gerais de string |
| src/utils/subprocessEnv.ts | ✅ | packages/core/agent-core/src/utils/subprocessEnv.ts | Sanitização de env para subprocessos |
| src/utils/suggestions/commandSuggestions.ts | ⚠️ | packages/core/agent-core/src/utils/suggestions/commandSuggestions.ts | Conceito útil, precisa adaptação |
| src/utils/suggestions/directoryCompletion.ts | ⚠️ | packages/core/agent-core/src/utils/suggestions/directoryCompletion.ts | Conceito útil, precisa adaptação |
| src/utils/suggestions/shellHistoryCompletion.ts | ⚠️ | packages/core/agent-core/src/utils/suggestions/shellHistoryCompletion.ts | Conceito útil, precisa adaptação |
| src/utils/suggestions/skillUsageTracking.ts | ✅ | packages/core/agent-core/src/utils/suggestions/skillUsageTracking.ts | Lógica de tracking reaproveitável |
| src/utils/suggestions/slackChannelSuggestions.ts | ⚠️ | packages/core/agent-core/src/utils/suggestions/slackChannelSuggestions.ts | Conceito útil, precisa adaptação |
| src/utils/swarm/It2SetupPrompt.tsx | ❌ |  | Componente React/Ink para terminal |
| src/utils/swarm/backends/ITermBackend.ts | ❌ |  | Específico para iTerm2, CLI/terminal dependente |
| src/utils/swarm/backends/InProcessBackend.ts | ✅ | packages/core/agent-core/src/utils/swarm/backends/InProcessBackend.ts | Lógica de backend in-process reutilizável para Nexias |
| src/utils/swarm/backends/PaneBackendExecutor.ts | ⚠️ | packages/core/agent-core/src/utils/swarm/backends/PaneBackendExecutor.ts | Conceito útil, mas depende de terminal panes, reescrita necessária |
| src/utils/swarm/backends/TmuxBackend.ts | ❌ |  | Específico para tmux, terminal dependente |
| src/utils/swarm/backends/detection.ts | ⚠️ | packages/core/agent-core/src/utils/swarm/backends/detection.ts | Detecção ambiente terminal, pode ser adaptado para Nexias |
| src/utils/swarm/backends/it2Setup.ts | ❌ |  | Setup específico para iTerm2, CLI/terminal dependente |
| src/utils/swarm/backends/registry.ts | ⚠️ | packages/core/agent-core/src/utils/swarm/backends/registry.ts | Registro backends, parte pode ser reaproveitada com adaptação |
| src/utils/swarm/backends/teammateModeSnapshot.ts | ✅ | packages/core/agent-core/src/utils/swarm/backends/teammateModeSnapshot.ts | Lógica de captura modo teammate útil para Nexias |
| src/utils/swarm/backends/types.ts | ✅ | packages/core/agent-core/src/utils/swarm/backends/types.ts | Tipos reutilizáveis para backends de agentes |
| src/utils/swarm/constants.ts | ✅ | packages/core/agent-core/src/utils/swarm/constants.ts | Constantes gerais sem dependência de terminal |
| src/utils/swarm/inProcessRunner.ts | ✅ | packages/core/agent-core/src/utils/swarm/inProcessRunner.ts | Execução in-process de agentes, lógica de negócio útil |
| src/utils/swarm/leaderPermissionBridge.ts | ✅ | packages/core/agent-core/src/utils/swarm/leaderPermissionBridge.ts | Bridge para permissões, lógica reutilizável |
| src/utils/swarm/permissionSync.ts | ✅ | packages/core/agent-core/src/utils/swarm/permissionSync.ts | Sincronização de permissões entre agentes, útil para Nexias |
| src/utils/swarm/reconnection.ts | ✅ | packages/core/agent-core/src/utils/swarm/reconnection.ts | Lógica de reconexão e contexto de swarm reaproveitável |
| src/utils/swarm/spawnInProcess.ts | ✅ | packages/core/agent-core/src/utils/swarm/spawnInProcess.ts | Spawn in-process teammates, lógica aplicável |
| src/utils/swarm/spawnUtils.ts | ⚠️ | packages/core/agent-core/src/utils/swarm/spawnUtils.ts | Utilitários de spawn, pode precisar adaptação |
| src/utils/swarm/teamHelpers.ts | ✅ | packages/core/agent-core/src/utils/swarm/teamHelpers.ts | Helpers para manipulação de times, útil para Nexias |
| src/utils/swarm/teammateInit.ts | ✅ | packages/core/agent-core/src/utils/swarm/teammateInit.ts | Inicialização de teammates, lógica de negócio reaproveitável |
| src/utils/swarm/teammateLayoutManager.ts | ⚠️ | packages/core/agent-core/src/utils/swarm/teammateLayoutManager.ts | Layout de teammates, depende de UI terminal, adaptação necessária |
| src/utils/swarm/teammateModel.ts | ✅ | packages/core/agent-core/src/utils/swarm/teammateModel.ts | Modelo de dados teammates, útil para Nexias |
| src/utils/swarm/teammatePromptAddendum.ts | ✅ | packages/core/agent-core/src/utils/swarm/teammatePromptAddendum.ts | Prompt de sistema para comunicação entre agentes em time |
| src/utils/systemDirectories.ts | ⚠️ | packages/core/agent-core/src/utils/systemDirectories.ts | Código depende de Node.js, adaptação para ambiente serverless |
| src/utils/systemPrompt.ts | ⚠️ | packages/core/agent-core/src/utils/systemPrompt.ts | Lógica de prompt com dependência de Bun e lazy require |
| src/utils/systemPromptType.ts | ✅ | packages/core/agent-core/src/utils/systemPromptType.ts | Tipo e função utilitária para system prompt, sem deps externas |
| src/utils/systemTheme.ts | ❌ |  | Código específico para terminal, detecção de tema via terminal |
| src/utils/systemThemeWatcher.ts | ❌ |  | Export default vazio, provavelmente placeholder para terminal |
| src/utils/taggedId.ts | ✅ | packages/core/agent-core/src/utils/taggedId.ts | Codificação de IDs compatível com backend, lógica pura |
| src/utils/task/TaskOutput.ts | ⚠️ | packages/core/agent-core/src/utils/task/TaskOutput.ts | Manipulação de arquivos e buffers, depende fs/promises |
| src/utils/task/diskOutput.ts | ⚠️ | packages/core/agent-core/src/utils/task/diskOutput.ts | Operações de arquivo com segurança, fs/promises dependente |
| src/utils/task/framework.ts | ✅ | packages/core/agent-core/src/utils/task/framework.ts | Lógica de framework de tarefas, eventos e estados |
| src/utils/task/outputFormatting.ts | ✅ | packages/core/agent-core/src/utils/task/outputFormatting.ts | Formatação e truncamento de saída de tarefas |
| src/utils/task/sdkProgress.ts | ✅ | packages/core/agent-core/src/utils/task/sdkProgress.ts | Emissão de eventos de progresso para SDK |
| src/utils/taskSummary.ts | ❌ |  | Export default vazio, sem lógica implementada |
| src/utils/tasks.ts | ⚠️ | packages/core/agent-core/src/utils/tasks.ts | Manipulação de arquivos e diretórios, fs/promises dependente |
| src/utils/teamDiscovery.ts | ✅ | packages/core/agent-core/src/utils/teamDiscovery.ts | Utilitários para descoberta de times e status |
| src/utils/teamMemoryOps.ts | ✅ | packages/core/agent-core/src/utils/teamMemoryOps.ts | Funções para operações em memória de time |
| src/utils/teammate.ts | ✅ | packages/core/agent-core/src/utils/teammate.ts | Utilitários para contexto e identidade de teammates |
| src/utils/teammateContext.ts | ✅ | packages/core/agent-core/src/utils/teammateContext.ts | Contexto runtime para teammates com AsyncLocalStorage |
| src/utils/teammateMailbox.ts | ⚠️ | packages/core/agent-core/src/utils/teammateMailbox.ts | Sistema de mensagens baseado em arquivos, fs dependente |
| src/utils/telemetry/bigqueryExporter.ts | ✅ | packages/core/agent-core/src/utils/telemetry/bigqueryExporter.ts | Exportador telemetry para BigQuery, lógica reutilizável serverless |
| src/utils/telemetry/events.ts | ✅ | packages/core/agent-core/src/utils/telemetry/events.ts | Gerenciamento de eventos telemetry, sem UI, útil para Nexias |
| src/utils/telemetry/instrumentation.ts | ✅ | packages/core/agent-core/src/utils/telemetry/instrumentation.ts | Configuração OpenTelemetry, lógica de negócio aplicável |
| src/utils/telemetry/logger.ts | ✅ | packages/core/agent-core/src/utils/telemetry/logger.ts | Logger customizado para telemetry, sem dependência UI |
| src/utils/telemetry/perfettoTracing.ts | ⚠️ | packages/core/agent-core/src/utils/telemetry/perfettoTracing.ts | Tracing perfetto específico, requer adaptação para Nexias |
| src/utils/telemetry/pluginTelemetry.ts | ✅ | packages/core/agent-core/src/utils/telemetry/pluginTelemetry.ts | Helpers telemetry para plugins, lógica reutilizável |
| src/utils/telemetry/sessionTracing.ts | ⚠️ | packages/core/agent-core/src/utils/telemetry/sessionTracing.ts | Usa Bun feature, AsyncLocalStorage, precisa reescrita |
| src/utils/telemetry/skillLoadedEvent.ts | ✅ | packages/core/agent-core/src/utils/telemetry/skillLoadedEvent.ts | Evento analytics para skills, lógica útil para Nexias |
| src/utils/telemetryAttributes.ts | ✅ | packages/core/agent-core/src/utils/telemetryAttributes.ts | Construção de atributos telemetry, sem UI, útil |
| src/utils/teleport/api.ts | ✅ | packages/core/agent-core/src/utils/teleport/api.ts | Cliente API teleport, lógica de negócio reutilizável |
| src/utils/teleport/environmentSelection.ts | ✅ | packages/core/agent-core/src/utils/teleport/environmentSelection.ts | Lógica seleção ambientes, sem UI, útil para Nexias |
| src/utils/teleport/environments.ts | ✅ | packages/core/agent-core/src/utils/teleport/environments.ts | Modelos e API ambientes, lógica reutilizável |
| src/utils/teleport/gitBundle.ts | ⚠️ | packages/core/agent-core/src/utils/teleport/gitBundle.ts | Git bundle upload, depende fs/promises, adaptar para Cloud Run |
| src/utils/tempfile.ts | ✅ | packages/core/agent-core/src/utils/tempfile.ts | Utilitário arquivos temporários, lógica útil serverless |
| src/utils/terminal.ts | ❌ |  | Utilitários terminal, dependente CLI/terminal, não importar |
| src/utils/terminalPanel.ts | ❌ |  | Componente UI terminal, React/Ink, não importar |
| src/utils/textHighlighting.ts | ✅ | packages/core/agent-core/src/utils/textHighlighting.ts | Utilitário destaque texto, sem UI terminal, útil |
| src/utils/theme.ts | ❌ |  | Tema UI para terminal/desktop, não aplicar em Nexias |
| src/utils/thinking.ts | ❌ |  | UI/efeitos para terminal, dependente Ink, não importar |
| src/utils/timeouts.ts | ✅ | packages/core/agent-core/src/utils/timeouts.ts | Timeout config util, sem dependências de CLI |
| src/utils/tmuxSocket.ts | ⚠️ | packages/core/agent-core/src/utils/tmuxSocket.ts | Lógica tmux isolada, mas específica para terminal |
| src/utils/todo/types.ts | ✅ | packages/core/agent-core/src/utils/todo/types.ts | Tipos e validação zod reutilizáveis |
| src/utils/tokenBudget.ts | ✅ | packages/core/agent-core/src/utils/tokenBudget.ts | Parsing orçamentos tokens, lógica pura |
| src/utils/tokens.ts | ✅ | packages/core/agent-core/src/utils/tokens.ts | Contagem tokens, sem deps de UI |
| src/utils/toolErrors.ts | ✅ | packages/core/agent-core/src/utils/toolErrors.ts | Formatação erros, lógica reutilizável |
| src/utils/toolPool.ts | ⚠️ | packages/core/agent-core/src/utils/toolPool.ts | Lógica ferramentas, mas usa bun:bundle |
| src/utils/toolResultStorage.ts | ⚠️ | packages/core/agent-core/src/utils/toolResultStorage.ts | Persistência resultados, fs depende de node |
| src/utils/toolSchemaCache.ts | ✅ | packages/core/agent-core/src/utils/toolSchemaCache.ts | Cache schemas ferramentas, lógica pura |
| src/utils/toolSearch.ts | ✅ | packages/core/agent-core/src/utils/toolSearch.ts | Busca ferramentas, lógica reutilizável |
| src/utils/transcriptSearch.ts | ✅ | packages/core/agent-core/src/utils/transcriptSearch.ts | Busca texto em mensagens, lógica pura |
| src/utils/treeify.ts | ⚠️ | packages/core/agent-core/src/utils/treeify.ts | Usa figures e cores, adaptação para web |
| src/utils/truncate.ts | ❌ |  | Usa ink/stringWidth, UI terminal dependente |
| src/utils/udsClient.ts | ❌ |  | Export vazio, sem lógica útil |
| src/utils/udsMessaging.ts | ❌ |  | Export vazio, sem lógica útil |
| src/utils/ultraplan/ccrSession.ts | ✅ | packages/core/agent-core/src/utils/ultraplan/ccrSession.ts | Polling sessão, lógica negócio pura |
| src/utils/ultraplan/keyword.ts | ✅ | packages/core/agent-core/src/utils/ultraplan/keyword.ts | Parsing keywords, lógica reutilizável |
| src/utils/unaryLogging.ts | ❌ |  | Código truncado, sem análise possível |
| src/utils/undercover.ts | ❌ |  | Não listado no conteúdo, presumido irrelevante |
| src/utils/user.ts | ⚠️ | packages/core/agent-core/src/utils/user.ts | Usa execa, lógica útil mas depende de CLI e estado global |
| src/utils/userAgent.ts | ✅ | packages/core/agent-core/src/utils/userAgent.ts | String User-Agent simples, sem dependências externas |
| src/utils/userPromptKeywords.ts | ✅ | packages/core/agent-core/src/utils/userPromptKeywords.ts | Funções utilitárias para análise de texto simples |
| src/utils/uuid.ts | ✅ | packages/core/agent-core/src/utils/uuid.ts | Validação e geração UUID, lógica reutilizável |
| src/utils/warningHandler.ts | ⚠️ | packages/core/agent-core/src/utils/warningHandler.ts | Lógica de warnings útil, mas depende de analytics e paths |
| src/utils/which.ts | ⚠️ | packages/core/agent-core/src/utils/which.ts | Usa execa, lógica para localizar executáveis, adaptação necessária |
| src/utils/windowsPaths.ts | ⚠️ | packages/core/agent-core/src/utils/windowsPaths.ts | Usa execSync, lógica Windows específica, adaptação necessária |
| src/utils/withResolvers.ts | ✅ | packages/core/agent-core/src/utils/withResolvers.ts | Polyfill Promise.withResolvers, útil e sem dependências |
| src/utils/words.ts | ✅ | packages/core/agent-core/src/utils/words.ts | Gerador de palavras aleatórias, lógica pura e reutilizável |
| src/utils/workloadContext.ts | ⚠️ | packages/core/agent-core/src/utils/workloadContext.ts | Usa AsyncLocalStorage, útil mas Node.js específico |
| src/utils/worktree.ts | ⚠️ | packages/core/agent-core/src/utils/worktree.ts | Usa fs, child_process, lógica complexa, adaptação necessária |
| src/utils/worktreeModeEnabled.ts | ✅ | packages/core/agent-core/src/utils/worktreeModeEnabled.ts | Função simples, lógica reutilizável |
| src/utils/xdg.ts | ⚠️ | packages/core/agent-core/src/utils/xdg.ts | Lida com paths e ambiente, adaptação para serverless necessária |
| src/utils/xml.ts | ✅ | packages/core/agent-core/src/utils/xml.ts | Funções utilitárias para escape XML, sem dependências |
| src/utils/yaml.ts | ⚠️ | packages/core/agent-core/src/utils/yaml.ts | Usa Bun e require dinâmico, adaptação para Nexias necessária |
| src/utils/zodToJsonSchema.ts | ✅ | packages/core/agent-core/src/utils/zodToJsonSchema.ts | Conversão Zod para JSON Schema, lógica reutilizável |