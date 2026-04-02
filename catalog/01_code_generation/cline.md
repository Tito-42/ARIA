# Cline

> Agent de coding autonome dans VS Code, open source avec support multi-provider

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 01_code_generation |
| **URL** | https://cline.bot |
| **GitHub** | https://github.com/cline/cline |
| **Stars** | 59,700 |
| **License** | Apache 2.0 |
| **Pricing** | Free (open source, BYOK pour API) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Cline (anciennement Claude Dev) est un agent de coding autonome intégré à VS Code. Il peut créer/éditer des fichiers, exécuter des commandes terminal, utiliser un navigateur, et s'étendre via MCP. C'est l'extension VS Code d'IA la plus populaire (59.7K stars) et elle supporte une dizaine de providers IA.

## Key Features
- **Multi-API** : OpenRouter, Anthropic, OpenAI, Google Gemini, AWS Bedrock, Azure, GCP Vertex, Cerebras, Groq
- **Terminal execution** : commandes avec intégration shell VS Code
- **File operations** : création/édition avec diff previews
- **Browser automation** : screenshots + console log capture
- **MCP tools** : création d'outils custom
- **Context commands** : @url, @problems, @file, @folder
- **Checkpoints** : sauvegarder/restaurer l'état du workspace
- **Token tracking** : suivi des coûts API en temps réel
- **5,042 commits** : développement très actif

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | 59.7K stars, adoption massive |
| **Security** | 4 | BYOK, données restent locales, code open source auditable |
| **Scalability** | 3 | Extension VS Code, per-developer |
| **Support/Community** | 5 | Communauté très active, 5K+ commits |
| **Documentation** | 4 | Docs sur cline.bot |
| **Integration Ease** | 5 | Installation VS Code en 1 clic |

## Use Cases
1. **Coding quotidien** dans VS Code avec IA autonome
2. **Multi-provider** : utiliser le meilleur modèle selon la tâche
3. **Browser testing** : debugging avec capture d'écran automatique
4. **Custom tools** : étendre via MCP

## Getting Started
```
# VS Code Marketplace : chercher "Cline"
# Ou : code --install-extension cline.cline
# Configurer une API key (Anthropic, OpenAI, etc.)
```

## Strengths
- Open source Apache 2.0
- Support de 10+ providers IA (flexibilité maximale)
- Browser automation intégrée
- MCP pour extensibilité
- Checkpoints pour rollback

## Limitations
- VS Code uniquement (pas JetBrains natif)
- BYOK = gérer ses propres API keys
- Peut être coûteux en tokens pour les tâches longues
- Pas d'agent teams/multi-agent

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Roo Code | Modes multiples (Code, Architect, Debug), 22.9K stars |
| Continue.dev | Focus CI/CD, code review en PR |
| Cursor | IDE complet vs extension |
| Claude Code | Terminal + IDE, plus de features agentiques |

## References
- [cline.bot](https://cline.bot)
- [GitHub](https://github.com/cline/cline)
