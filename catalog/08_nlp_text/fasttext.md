# FastText

> Classification de texte et word embeddings rapides par Meta — archivé depuis mars 2024 mais lid.176 encore utilisé.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 08 - NLP & Text / Text Classification |
| **URL** | https://fasttext.cc |
| **GitHub** | https://github.com/facebookresearch/fastText |
| **Stars** | ~26,500 |
| **License** | MIT |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Archived |
| **Maturity** | Production (Legacy) |

## What It Does
FastText est une bibliothèque de Meta pour la classification de texte et les word embeddings. Son modèle lid.176 pour la détection de langue reste largement utilisé. FastText est extrêmement rapide et léger, capable de classifier des millions de textes en secondes.

**Le projet est archivé depuis mars 2024.** Le code et les modèles restent disponibles mais ne sont plus maintenus.

## Key Features
- **Classification ultra-rapide**: Millions de textes en secondes
- **Word embeddings**: Sous-word embeddings
- **Language detection**: lid.176 pour 176 langues
- **Léger**: Fonctionne sur CPU sans GPU
- **Multi-langues**: Embeddings pré-entraînés en 157 langues

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 3 | Fonctionne mais archivé |
| **Security** | 4 | MIT, self-hosted |
| **Scalability** | 5 | Ultra-rapide, CPU only |
| **Support/Community** | 2 | **Archivé** — plus de maintenance |
| **Documentation** | 3 | Docs existantes |
| **Integration Ease** | 4 | pip install, API simple |

## Use Cases
1. **Language detection** — Détecter la langue d'un texte (lid.176)
2. **Text classification** — Classification rapide à grande échelle
3. **Word embeddings** — Embeddings pour des tâches simples

## Getting Started
```python
import fasttext
# Language detection
model = fasttext.load_model('lid.176.bin')
predictions = model.predict("Bonjour, comment allez-vous ?")
# (('__label__fr',), array([0.99]))
```

## Architecture / How It Works
FastText utilise un classifieur linéaire avec bag-of-words et n-grams de caractères. Les sous-word embeddings capturent la morphologie. L'optimisation en C++ et le hierarchical softmax permettent un training et une inférence extrêmement rapides.

## Strengths
- Ultra-rapide, CPU-only
- lid.176 pour détection de langue
- MIT licence
- Léger et déployable partout

## Limitations
- **Archivé depuis mars 2024** — plus de maintenance
- Pas de deep learning (classifieur linéaire)
- API Python wrapper autour de C++

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Lingua-py | Meilleur sur textes courts, maintenu |
| SetFit | Few-shot avec transformers |
| spaCy | NLP complet, maintenu |

## References
- https://fasttext.cc
- https://github.com/facebookresearch/fastText

## Notes
**ARCHIVÉ depuis mars 2024.** Le modèle lid.176 reste utile pour la détection de langue rapide. Pour de nouveaux projets, considérer Lingua-py ou des classifieurs basés sur transformers.
