# Aider

> AI pair programming open source en terminal, git-first, multi-model, 5.7M+ installs

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 01_code_generation |
| **URL** | https://aider.chat |
| **GitHub** | https://github.com/paul-gauthier/aider |
| **Stars** | 42,600 |
| **License** | Apache 2.0 |
| **Pricing** | Free (open source, BYOK) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Aider est l'outil de pair programming IA en terminal le plus établi. Approche git-first avec commits automatiques, support de 100+ langages, cloud et local LLMs. Top 20 sur OpenRouter avec 5.7M+ installations PyPI et 15B tokens/semaine. 88% de son propre code a été écrit par Aider lui-même.

## Key Features
- **Git-first** : commits automatiques avec messages pertinents
- **100+ langages** de programmation
- **Multi-model** : Claude, DeepSeek, GPT-4o, o1, o3-mini, modèles locaux
- **Codebase mapping** : cartographie automatique pour gros projets
- **IDE integration** : via commentaires de code
- **Multimodal** : support images et pages web
- **Voice-to-code** : coding vocal
- **Auto-lint/test** : linting et tests automatiques avec fix d'erreurs
- **5.7M+ installs PyPI**, 15B tokens/semaine

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | 42.6K stars, 5.7M installs, très mature |
| **Security** | 4 | BYOK, local execution, Apache 2.0 |
| **Scalability** | 3 | Outil individuel, pas de collaboration native |
| **Support/Community** | 4 | Communauté active, documentation excellente |
| **Documentation** | 5 | aider.chat - docs exhaustives |
| **Integration Ease** | 5 | pip install aider-chat, BYOK simple |

## Use Cases
1. **Pair programming** quotidien en terminal
2. **Refactoring** multi-fichiers avec git tracking
3. **Multi-model** : tester différents LLMs sur la même tâche
4. **Modèles locaux** : coding privé avec LLMs on-premise

## Getting Started
```bash
pip install aider-chat
# Avec Claude
export ANTHROPIC_API_KEY=xxx
aider --model claude-sonnet-4-6-20250514

# Avec modèle local (Ollama)
aider --model ollama/deepseek-coder
```

## Strengths
- Le plus mature des CLI de coding IA
- Git-first = historique propre
- Multi-model = pas de lock-in
- 88% self-written = dogfooding ultime
- Apache 2.0

## Limitations
- Terminal uniquement (pas de GUI native)
- Pas d'agent teams/multi-agent
- Pas de browser automation
- Moins de features agentiques que Claude Code ou Cline

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Claude Code | Plus de features (teams, hooks, MCP), mais lié à Claude |
| Gemini CLI | Gratuit, Google-backed, mais mono-model |
| Crush | TUI plus riche (Charm ecosystem) |
| Plandex | Sandbox pour gros projets, 2M context |

## References
- [aider.chat](https://aider.chat)
- [GitHub](https://github.com/paul-gauthier/aider)
