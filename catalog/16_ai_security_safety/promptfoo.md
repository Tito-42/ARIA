# Promptfoo

> Framework de test et red-teaming de prompts/LLMs — OWASP LLM Top 10 intégré, le plus populaire.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 16 - AI Security & Safety / Red-teaming |
| **URL** | https://promptfoo.dev |
| **GitHub** | https://github.com/promptfoo/promptfoo |
| **Stars** | ~19,000 |
| **License** | MIT |
| **Pricing** | Free (OSS) / Enterprise (Paid) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Promptfoo est le framework le plus populaire pour tester et red-teamer les prompts et les applications LLM. Il automatise la détection des vulnérabilités OWASP LLM Top 10 (prompt injection, data leakage, etc.) avec une CLI et une UI web. Multi-provider, il teste contre OpenAI, Anthropic, Ollama, et bien d'autres.

## Key Features
- **Red-teaming automatisé**: Génération d'attaques automatiques
- **OWASP LLM Top 10**: Détection intégrée
- **Multi-provider**: OpenAI, Anthropic, Ollama, Azure, etc.
- **CLI + UI**: Interface web et ligne de commande
- **Assertions**: Tests automatisés avec assertions
- **CI/CD**: Intégration dans les pipelines

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | Standard du marché |
| **Security** | 5 | MIT, conçu pour la sécurité |
| **Scalability** | 4 | CLI et CI/CD |
| **Support/Community** | 5 | 19k stars, très actif |
| **Documentation** | 5 | Docs excellentes |
| **Integration Ease** | 5 | npx promptfoo pour démarrer |

## Use Cases
1. **Red-teaming LLM** — Tester les vulnérabilités des applications LLM
2. **Prompt testing** — Comparer et évaluer des prompts
3. **CI/CD security** — Tests automatisés de sécurité dans le pipeline

## Getting Started
```bash
npx promptfoo@latest init
npx promptfoo@latest eval
npx promptfoo@latest view  # UI web
```

## Architecture / How It Works
Promptfoo exécute des prompts contre des providers LLM avec des datasets de test, applique des assertions (exactes, contient, LLM-graded), et génère des rapports. Le mode red-team génère automatiquement des attaques basées sur OWASP LLM Top 10.

## Strengths
- Le plus populaire dans sa catégorie (19k stars)
- OWASP LLM Top 10 intégré
- Multi-provider
- MIT licence

## Limitations
- Focus principalement prompt-level
- Nécessite des API keys pour tester
- Enterprise features payantes

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Garak | NVIDIA, plus de types d'attaques, ralenti |
| PyRIT | Microsoft, red-teaming sophistiqué |
| DeepTeam | Confident AI, intégré avec DeepEval |

## References
- https://promptfoo.dev
- https://github.com/promptfoo/promptfoo
