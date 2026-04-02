# DeepTeam (Confident AI)

> Red-teaming LLM open-source — attaques automatisées et métriques de vulnérabilité, intégré DeepEval.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 16 - AI Security & Safety / Red-teaming |
| **URL** | https://github.com/confident-ai/deepteam |
| **GitHub** | https://github.com/confident-ai/deepteam |
| **Stars** | ~1,400 |
| **License** | Apache 2.0 |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Beta |

## What It Does
DeepTeam est un outil de red-teaming LLM de Confident AI (les créateurs de DeepEval). Il génère automatiquement des attaques et mesure les vulnérabilités avec des métriques standardisées. Intégré nativement avec DeepEval pour une évaluation complète.

## Key Features
- **Attaques automatisées**: Prompt injection, jailbreak, toxicité
- **Métriques standardisées**: Scores de vulnérabilité
- **DeepEval integration**: Pipeline eval + security
- **Apache 2.0**: Licence permissive

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 3 | Beta, nouveau |
| **Security** | 4 | Apache 2.0 |
| **Scalability** | 3 | Python, API |
| **Support/Community** | 2 | 1.4k stars, nouveau |
| **Documentation** | 3 | Docs en développement |
| **Integration Ease** | 4 | Intégré DeepEval |

## Use Cases
1. **Red-teaming** — Tester les vulnérabilités des LLMs
2. **Security CI/CD** — Tests de sécurité automatisés

## Getting Started
```python
from deepteam import red_team
results = red_team(model=my_model, attacks=["prompt_injection", "jailbreak"])
```

## Strengths
- Intégré avec DeepEval
- Apache 2.0
- Métriques standardisées

## Limitations
- Relativement nouveau
- Communauté petite
- Moins d'attaques que Promptfoo/Garak

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Promptfoo | Plus mature, plus populaire |
| Garak | Plus d'attaques, NVIDIA |

## References
- https://github.com/confident-ai/deepteam
