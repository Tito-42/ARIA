# Marvin

> Extraction structurée et classification via LLMs — approche fonctionnelle avec décorateurs Python.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 08 - NLP & Text / Structured Extraction |
| **URL** | https://askmarvin.ai |
| **GitHub** | https://github.com/prefecthq/marvin |
| **Stars** | ~6,100 |
| **License** | Apache 2.0 |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Marvin utilise des LLMs pour des tâches NLP via une API Python élégante basée sur des décorateurs. `@marvin.fn` transforme une fonction Python en fonction alimentée par un LLM, `marvin.extract()` extrait des entités, `marvin.classify()` classifie du texte. La v3.0 ajoute le support des agents.

## Key Features
- **@marvin.fn**: Fonctions Python alimentées par LLM
- **extract()**: Extraction d'entités typées
- **classify()**: Classification avec labels arbitraires
- **cast()**: Conversion de données entre types
- **Agents v3.0**: Support d'agents conversationnels
- **Pydantic**: Types Pydantic natifs

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 3 | Production-ready, Prefect backed |
| **Security** | 4 | Apache 2.0 |
| **Scalability** | 3 | Via API LLM |
| **Support/Community** | 3 | 6.1k stars, Prefect backing |
| **Documentation** | 4 | Docs claires |
| **Integration Ease** | 5 | API élégante, décorateurs intuitifs |

## Use Cases
1. **Quick extraction** — Extraire des données avec une seule ligne
2. **Classification** — Classifier du texte sans modèle custom
3. **Data transformation** — Convertir des données entre formats

## Getting Started
```python
import marvin

result = marvin.extract("I moved to NYC from LA last year", target=str, instructions="cities")
# ["NYC", "LA"]

sentiment = marvin.classify("This product is amazing!", labels=["positive", "negative", "neutral"])
# "positive"
```

## Architecture / How It Works
Marvin wrappe les appels LLM (principalement OpenAI) avec des prompts optimisés pour chaque tâche (extraction, classification, casting). Les décorateurs @marvin.fn convertissent les docstrings en prompts.

## Strengths
- API la plus élégante pour NLP via LLM
- Décorateurs intuitifs
- Apache 2.0
- Prefect backing (orchestration)

## Limitations
- Dépend principalement d'OpenAI
- Coût API LLM
- Moins de contrôle que Instructor

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Instructor | Plus de contrôle, multi-provider, validation |
| Outlines | Token-level, modèles locaux |

## References
- https://askmarvin.ai
- https://github.com/prefecthq/marvin

## Notes
Marvin v3.0 avec agents. L'API la plus élégante pour des tâches NLP simples via LLM. Pour plus de contrôle et de validation, Instructor est préférable.
