# NeMo Guardrails (NVIDIA)

> Toolkit NVIDIA pour guardrails programmables sur applications LLM — Colang DSL pour définir les rails.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 16 - AI Security & Safety / Guardrails |
| **URL** | https://github.com/NVIDIA/NeMo-Guardrails |
| **GitHub** | https://github.com/NVIDIA/NeMo-Guardrails |
| **Stars** | ~5,900 |
| **License** | Apache 2.0 |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
NeMo Guardrails est un toolkit NVIDIA pour ajouter des guardrails programmables aux applications LLM. Il utilise Colang, un DSL spécifique, pour définir des rails conversationnels : topical rails (maintenir le sujet), safety rails (bloquer contenu dangereux), fact-checking rails, et more.

## Key Features
- **Colang DSL**: Langage dédié pour définir les rails
- **Topical rails**: Maintenir la conversation dans le sujet
- **Safety rails**: Bloquer contenu toxique/dangereux
- **Fact-checking**: Vérification des faits
- **Input/Output rails**: Protection bidirectionnelle
- **Multi-LLM**: Supporte plusieurs providers

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Production, NVIDIA-backed |
| **Security** | 5 | Apache 2.0, conçu pour la sécurité |
| **Scalability** | 4 | NVIDIA ecosystem |
| **Support/Community** | 4 | 5.9k stars, NVIDIA backing |
| **Documentation** | 4 | Docs NVIDIA complètes |
| **Integration Ease** | 3 | Courbe d'apprentissage Colang |

## Use Cases
1. **Enterprise safety** — Sécuriser les chatbots d'entreprise
2. **Content moderation** — Filtrer les réponses dangereuses
3. **Topic control** — Maintenir le chatbot dans son périmètre

## Getting Started
```python
from nemoguardrails import RailsConfig, LLMRails
config = RailsConfig.from_path("config/")
rails = LLMRails(config)
response = rails.generate(messages=[{"role": "user", "content": "How to hack a system?"}])
```

## Strengths
- Colang DSL puissant et expressif
- NVIDIA backing
- Apache 2.0
- Multi-type de rails

## Limitations
- Courbe d'apprentissage Colang
- Dépendance écosystème NVIDIA
- Overhead de latence

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Guardrails AI | Hub de validators, pas de DSL |
| LLM Guard | Scanners modulaires, plus simple |

## References
- https://github.com/NVIDIA/NeMo-Guardrails
- https://docs.nvidia.com/nemo/guardrails/
