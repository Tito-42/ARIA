# 03 - MCP (Model Context Protocol)

> Standard ouvert pour connecter l'IA aux systèmes externes - SDKs, serveurs, connecteurs

## Vue d'ensemble
MCP est le protocole standardisé pour connecter les applications IA (Claude, ChatGPT, VS Code, Cursor...) aux outils et données externes. C'est le "USB-C de l'IA" avec un écosystème massif de serveurs communautaires.

## Contenu Catalogué

### Spécification
- [MCP Protocol Overview](specification/mcp-protocol-overview.md) - Le protocole complet

### Serveurs
- [Registre des serveurs](servers/registry.md) - Tous les serveurs MCP connus

### Guides
(à documenter)

## SDKs Disponibles (8 langages)

| SDK | Stars | Collaborateur |
|-----|-------|---------------|
| Python | 22,445 | - |
| TypeScript | 12,065 | - |
| Go | 4,272 | Google |
| C# | 4,159 | Microsoft |
| Java | 3,323 | Spring AI |
| PHP | 1,429 | PHP Foundation |
| Kotlin | 1,318 | JetBrains |
| Ruby | 758 | - |

## À Documenter
- [ ] Guide construction serveur MCP Python
- [ ] Guide construction serveur MCP TypeScript
- [ ] Patterns de serveurs MCP
- [ ] Serveurs communautaires populaires (fiches individuelles)
- [ ] Intégrations enterprise

## Cas d'Usage Enterprise

| Besoin | Serveur MCP |
|--------|------------|
| Accès base de données | PostgreSQL, MongoDB, Redis |
| Gestion de projet | Jira, Linear, Notion |
| Communication | Slack, Discord, Email |
| CI/CD | GitHub, GitLab |
| Monitoring | Grafana, Sentry, DataDog |
| Browser automation | Playwright, Puppeteer |
| Recherche web | Tavily, Brave Search |
