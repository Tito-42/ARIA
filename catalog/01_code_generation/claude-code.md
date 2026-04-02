# Claude Code

> Outil de codage agentique par Anthropic qui vit dans le terminal, l'IDE, le desktop et le navigateur

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 01_code_generation |
| **URL** | https://code.claude.com |
| **GitHub** | https://github.com/anthropics/claude-code |
| **Stars** | 95,100 |
| **License** | Proprietary (Anthropic Commercial ToS) |
| **Pricing** | Freemium - usage via API Anthropic ou abonnement Claude |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Claude Code est l'outil de codage agentique officiel d'Anthropic. Il comprend l'intégralité d'une codebase, édite des fichiers, exécute des commandes et s'intègre aux outils de développement via le langage naturel. Disponible en CLI terminal, extensions VS Code et JetBrains, application desktop (macOS/Windows), web (claude.ai/code) et même sur iOS.

C'est l'un des outils de code generation IA les plus complets du marché, avec 95K+ stars GitHub et un écosystème d'extensions massif incluant MCP, hooks, agents, skills et intégrations CI/CD.

## Key Features
- **Multi-plateforme** : Terminal CLI, VS Code, JetBrains, Desktop App, Web, iOS
- **Compréhension codebase** : analyse multi-fichiers complète
- **Git workflow** : commits, branches, PRs automatisés
- **MCP Integration** : connexion à des outils externes via Model Context Protocol
- **Système de sous-agents** : agents intégrés (Explore, Plan, General-purpose) + custom
- **Agent Teams** (experimental) : collaboration multi-agents avec task lists partagées
- **Hooks** : PreToolUse, PostToolUse, SessionStart, Stop pour automation
- **Skills** : capacités domain-specific chargeables dynamiquement
- **CLAUDE.md** : fichiers mémoire persistants pour instructions projet
- **Custom commands** : via `.claude/commands/`
- **Scheduled tasks** : tâches récurrentes (cloud et desktop)
- **Channels** : intégration Telegram, Discord, iMessage, webhooks
- **Slack** : mentions @Claude
- **GitHub Actions / GitLab CI/CD** : intégration native
- **Chrome extension** : debugging d'applications web live

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | Utilisé massivement en production, 95K+ stars |
| **Security** | 4 | Système de permissions granulaire, hooks de validation |
| **Scalability** | 5 | Multi-plateforme, CI/CD, remote sessions |
| **Support/Community** | 5 | Support Anthropic + communauté massive |
| **Documentation** | 5 | Documentation exhaustive sur code.claude.com/docs |
| **Integration Ease** | 5 | CLI simple, extensions IDE, MCP, GitHub Actions |

## Use Cases
1. **Développement quotidien** : écriture, refactoring, debugging de code assisté par IA
2. **Code review automatisé** : via GitHub Actions et claude-code-action
3. **Migration de codebase** : refactoring à grande échelle multi-fichiers
4. **Onboarding développeur** : comprendre rapidement une codebase existante
5. **CI/CD intelligent** : automatisation de tests, docs, et déploiement

## Getting Started
```bash
# Installation macOS/Linux
curl -fsSL https://claude.ai/install.sh | bash

# Installation Windows
irm https://claude.ai/install.ps1 | iex

# Homebrew
brew install claude-code

# Lancement
claude
```

## Architecture / How It Works
```
User → CLI/IDE/Desktop/Web
         ↓
    Claude Code Engine
         ↓
    ┌────┴────┐
    │ Tools   │ → Read, Write, Edit, Bash, Glob, Grep, WebSearch...
    │ Agents  │ → Explore, Plan, General-purpose, Custom subagents
    │ MCP     │ → Connexion à N serveurs MCP externes
    │ Hooks   │ → PreToolUse, PostToolUse, Stop, SessionStart
    │ Skills  │ → Capacités domain-specific chargeables
    └─────────┘
         ↓
    Claude API (Opus 4.6 / Sonnet 4.6 / Haiku 4.5)
```

## Strengths
- Écosystème le plus complet de tous les outils de code gen IA
- Agent Teams pour collaboration multi-agents (unique sur le marché)
- MCP pour extensibilité illimitée
- Hooks pour customisation et validation
- Disponible sur toutes les plateformes

## Limitations
- Propriétaire (pas open-source)
- Coût API Anthropic (tokens)
- Agent Teams encore expérimental
- Pas de support offline (nécessite API cloud)

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Cursor | IDE complet avec IA intégrée, UI plus riche |
| GitHub Copilot | Intégré VS Code/JetBrains, plus simple mais moins agentique |
| Aider | Open source, terminal-only, multi-model |
| Cline | Extension VS Code open source, plus léger |

## References
- [Documentation officielle](https://code.claude.com/docs/en/overview)
- [GitHub](https://github.com/anthropics/claude-code)
- [Claude Code Action](https://github.com/anthropics/claude-code-action)
- [Agent Teams docs](https://code.claude.com/docs/en/agent-teams)

## Notes
- Version actuelle : 2.1.89 (573+ commits, développement très actif)
- L'Agent Teams (Cowork) est activable via `CLAUDE_CODE_EXPERIMENTAL_AGENT_TEAMS=1`
- Skills repo (108K stars) est le repo Anthropic le plus populaire
