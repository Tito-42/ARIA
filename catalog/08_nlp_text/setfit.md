# SetFit

> Few-shot text classification avec Sentence Transformers — fine-tune avec seulement 8-16 exemples par classe.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 08 - NLP & Text / Text Classification |
| **URL** | https://huggingface.co/docs/setfit |
| **GitHub** | https://github.com/huggingface/setfit |
| **Stars** | ~2,700 |
| **License** | Apache 2.0 |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Stable |
| **Maturity** | Production |

## What It Does
SetFit permet la classification de texte few-shot en fine-tunant un Sentence Transformer avec seulement 8-16 exemples par classe. Pas besoin de prompts complexes ni de LLM coûteux — le modèle résultant est compact et rapide à l'inférence.

## Key Features
- **Few-shot**: 8-16 exemples par classe suffisent
- **Pas de LLM**: Utilise des Sentence Transformers, pas de GPT
- **Rapide**: Training en minutes, inférence rapide
- **Multi-label**: Support multi-label classification
- **Compact**: Modèle résultant léger et déployable

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Stable, HuggingFace backed |
| **Security** | 5 | Apache 2.0, self-hosted, pas d'API |
| **Scalability** | 4 | Modèle compact, inférence rapide |
| **Support/Community** | 3 | 2.7k stars, HuggingFace |
| **Documentation** | 4 | Docs HuggingFace |
| **Integration Ease** | 5 | API scikit-learn-like |

## Use Cases
1. **Classification avec peu de données** — Classifier quand on a peu d'exemples annotés
2. **Prototypage rapide** — Tester une classification en minutes
3. **Edge deployment** — Modèle compact déployable partout

## Getting Started
```python
from setfit import SetFitModel, SetFitTrainer
from datasets import Dataset

train_dataset = Dataset.from_dict({"text": ["Great!", "Terrible!"], "label": [1, 0]})
model = SetFitModel.from_pretrained("sentence-transformers/all-MiniLM-L6-v2")
trainer = SetFitTrainer(model=model, train_dataset=train_dataset)
trainer.train()
preds = model.predict(["This is wonderful!"])
```

## Architecture / How It Works
SetFit utilise le contrastive learning : il génère des paires de phrases (positives/négatives) depuis les exemples few-shot, fine-tune un Sentence Transformer sur ces paires, puis entraîne un classifieur (logistic regression) sur les embeddings résultants.

## Strengths
- Classification avec très peu d'exemples
- Pas besoin de LLM (coût zéro)
- Training en minutes
- Modèle compact et rapide

## Limitations
- Limité à la classification (pas d'extraction)
- Qualité dépend des exemples choisis
- Moins flexible que les approches LLM

## Alternatives
| Tool | Key Difference |
|------|---------------|
| LLM zero-shot | Plus flexible, plus cher, plus lent |
| FastText | Plus rapide, besoin de plus d'exemples |
| spaCy textcat | Pipeline intégré, besoin de plus d'exemples |

## References
- https://huggingface.co/docs/setfit
- https://github.com/huggingface/setfit

## Notes
SetFit v1.1.3 (août 2025). Excellent quand on a peu de données annotées et qu'on veut éviter les coûts LLM.
