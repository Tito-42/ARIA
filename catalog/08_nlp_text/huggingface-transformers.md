# Hugging Face Transformers

> Framework central pour NLP/NLU/NLG — 500k+ modèles, pipelines prêts à l'emploi, écosystème dominant.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 08 - NLP & Text / Framework |
| **URL** | https://huggingface.co/docs/transformers |
| **GitHub** | https://github.com/huggingface/transformers |
| **Stars** | ~159,000 |
| **License** | Apache 2.0 |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Enterprise |

## What It Does
HuggingFace Transformers est le framework standard pour le NLP et le machine learning. Il fournit des APIs unifiées pour charger, fine-tuner et déployer plus de 500k modèles depuis le Hub, avec des pipelines prêts à l'emploi pour la classification, NER, résumé, traduction, Q&A, et génération de texte.

## Key Features
- **500k+ modèles**: Accès au Hub HuggingFace
- **Pipelines**: API haut niveau pour les tâches courantes
- **Multi-framework**: PyTorch, TensorFlow, JAX
- **Auto classes**: Chargement automatique du bon modèle
- **Fine-tuning**: Trainer API pour l'entraînement
- **Quantization**: bitsandbytes, GPTQ, AWQ

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | Standard industrie |
| **Security** | 5 | Apache 2.0, self-hosted |
| **Scalability** | 5 | Multi-GPU, distributed training |
| **Support/Community** | 5 | 159k stars, communauté massive |
| **Documentation** | 5 | Docs exemplaires |
| **Integration Ease** | 5 | Pipeline en 2 lignes |

## Use Cases
1. **NLP tasks** — Classification, NER, résumé, traduction via pipelines
2. **Fine-tuning** — Adapter des modèles à des domaines spécifiques
3. **LLM inference** — Charger et utiliser des LLMs

## Getting Started
```python
from transformers import pipeline
classifier = pipeline("sentiment-analysis")
result = classifier("I love this product!")
# [{'label': 'POSITIVE', 'score': 0.9998}]
```

## Architecture / How It Works
Transformers fournit des Auto classes qui détectent automatiquement l'architecture du modèle. Les pipelines assemblent tokenizer + modèle + post-processing. Le Hub stocke les poids et configs. Le Trainer gère le training loop avec logging, evaluation et checkpointing.

## Strengths
- Écosystème dominant, 500k+ modèles
- Pipeline en 2 lignes de code
- Docs exemplaires
- Multi-framework

## Limitations
- Overhead mémoire pour des tâches simples
- Dépendances lourdes
- Peut être overkill pour du NLP classique

## Alternatives
| Tool | Key Difference |
|------|---------------|
| spaCy | Plus rapide, production-first, NLP classique |
| Flair | NER spécialisé, stacked embeddings |
| NLTK | NLP classique, enseignement |

## References
- https://huggingface.co/docs/transformers
- https://github.com/huggingface/transformers

## Notes
HF Transformers est le framework par défaut pour tout projet NLP/ML. Pour du NLP production-optimized, spaCy est complémentaire. Les deux s'utilisent souvent ensemble.
