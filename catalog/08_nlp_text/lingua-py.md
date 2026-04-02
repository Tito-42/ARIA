# Lingua-py

> Détection de langue précise, surtout pour textes courts — alternative moderne à LangDetect, 75 langues.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 08 - NLP & Text / Language Detection |
| **URL** | https://github.com/pemistahl/lingua-py |
| **GitHub** | https://github.com/pemistahl/lingua-py |
| **Stars** | ~1,700 |
| **License** | Apache 2.0 |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Stable |
| **Maturity** | Production |

## What It Does
Lingua-py est une bibliothèque de détection de langue conçue pour la précision, en particulier sur les textes courts. Contrairement à LangDetect et FastText, Lingua utilise une approche multi-modèle (unigrams, bigrams, trigrams, quadrigrams, quintgrams) et est déterministe.

## Key Features
- **75 langues**: Bonne couverture
- **Textes courts**: Optimisée pour les textes courts (1 mot possible)
- **Déterministe**: Résultats reproductibles
- **Multi-modèle**: 5 niveaux de n-grams
- **Confidence scores**: Scores par langue
- **Filtre de langues**: Restreindre les langues candidates

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Stable, production-ready |
| **Security** | 4 | Apache 2.0, local |
| **Scalability** | 3 | Plus lent que FastText/LangDetect |
| **Support/Community** | 2 | 1.7k stars |
| **Documentation** | 4 | README complet |
| **Integration Ease** | 4 | API simple |

## Use Cases
1. **Détection précise** — Détecter la langue de textes courts (tweets, messages)
2. **Pipeline multilingue** — Router du contenu par langue

## Getting Started
```python
from lingua import Language, LanguageDetectorBuilder
detector = LanguageDetectorBuilder.from_all_languages().build()
language = detector.detect_language_of("Bonjour")
print(language)  # Language.FRENCH

confidences = detector.compute_language_confidence_values("Hello")
```

## Architecture / How It Works
Lingua utilise des modèles de n-grams à 5 niveaux (1 à 5 caractères). Pour chaque texte, elle calcule des probabilités sur chaque niveau et les agrège. L'approche multi-niveau rend la détection plus robuste, surtout pour les textes courts.

## Strengths
- Meilleure précision sur textes courts
- Déterministe
- Apache 2.0
- 75 langues

## Limitations
- Plus lent que FastText/LangDetect
- Utilisation mémoire plus élevée
- Communauté petite

## Alternatives
| Tool | Key Difference |
|------|---------------|
| LangDetect | Plus rapide mais non-déterministe |
| FastText lid.176 | Ultra-rapide, 176 langues, archivé |
| CLD3 | Google, C++ natif |

## References
- https://github.com/pemistahl/lingua-py

## Notes
Lingua-py v2.2.0. Le meilleur choix pour la détection de langue quand la précision sur textes courts est critique. Pour le volume pur, FastText lid.176 reste plus rapide.
