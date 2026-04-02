# spacy-llm

> Intégration LLMs dans les pipelines spaCy — NER, classification via prompts LLM dans le pipeline NLP.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 08 - NLP & Text / NLP + LLM |
| **URL** | https://github.com/explosion/spacy-llm |
| **GitHub** | https://github.com/explosion/spacy-llm |
| **Stars** | ~1,400 |
| **License** | MIT |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
spacy-llm intègre les LLMs directement dans les pipelines spaCy. Au lieu d'utiliser un modèle NER entraîné, on peut utiliser un LLM via prompt pour le NER, la classification ou d'autres tâches, tout en bénéficiant de l'écosystème spaCy (pipeline composable, Doc annotations).

C'est le bridge entre le NLP classique (spaCy) et les LLMs.

## Key Features
- **LLM dans spaCy**: Composant pipeline pour LLM
- **Multi-provider**: OpenAI, Anthropic, Cohere, HuggingFace, Ollama
- **Tâches**: NER, classification, sentiment, summarization
- **Few-shot**: Exemples dans le prompt
- **Cache**: Caching des réponses LLM
- **spaCy native**: Résultats dans le Doc spaCy

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 3 | Production mais coût LLM |
| **Security** | 4 | MIT, multi-provider |
| **Scalability** | 3 | Dépend du provider LLM |
| **Support/Community** | 3 | 1.4k stars, Explosion |
| **Documentation** | 4 | Docs spaCy |
| **Integration Ease** | 4 | Si spaCy déjà utilisé |

## Use Cases
1. **NER LLM-powered** — NER dans un pipeline spaCy via LLM
2. **Migration progressive** — Ajouter des LLMs à un pipeline spaCy existant
3. **Prototypage** — Tester des tâches NLP via LLM sans training

## Getting Started
```python
import spacy
nlp = spacy.blank("en")
nlp.add_pipe("llm_ner", config={
    "task": {"@llm_tasks": "spacy.NER.v3", "labels": ["PERSON", "ORG", "PRODUCT"]},
    "model": {"@llm_models": "spacy.GPT-4.v1"}
})
doc = nlp("Apple was founded by Steve Jobs.")
```

## Architecture / How It Works
spacy-llm ajoute un composant `llm` au pipeline spaCy. Ce composant formatte le texte en prompt, l'envoie au LLM, parse la réponse et annote le Doc spaCy. Le caching évite de re-appeler le LLM pour des textes déjà vus.

## Strengths
- Bridge NLP classique ↔ LLM
- Multi-provider
- MIT licence
- Cache intégré

## Limitations
- Coût API LLM en production
- Plus lent que les modèles NER classiques
- Communauté petite

## Alternatives
| Tool | Key Difference |
|------|---------------|
| GLiNER | Zero-shot NER sans LLM, plus rapide |
| Instructor | Extraction structurée multi-provider |
| spaCy classique | Plus rapide, pas de coût API |

## References
- https://github.com/explosion/spacy-llm
- https://spacy.io/usage/large-language-models

## Notes
spacy-llm v0.7.4 (mars 2026). Intéressant pour les équipes déjà sur spaCy qui veulent ajouter des capacités LLM. Pour du NER zero-shot sans coût API, GLiNER est une meilleure option.
