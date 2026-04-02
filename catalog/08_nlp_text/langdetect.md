# LangDetect

> Détection de langue basée sur les profils n-gram de Google — simple et léger, 55 langues. Peu maintenu.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 08 - NLP & Text / Language Detection |
| **URL** | https://github.com/Mimino666/langdetect |
| **GitHub** | https://github.com/Mimino666/langdetect |
| **Stars** | ~1,900 |
| **License** | Apache 2.0 |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Low Maintenance |
| **Maturity** | Production (Legacy) |

## What It Does
LangDetect est un port Python de la bibliothèque Java language-detection de Google. Il détecte la langue d'un texte parmi 55 langues en utilisant des profils de n-grammes de caractères. Simple et léger, mais peu maintenu depuis 2021.

## Key Features
- **55 langues**: Couverture des langues principales
- **N-gram based**: Détection par profils statistiques
- **Léger**: Pas de dépendance GPU ni ML
- **Probabilités**: Score de confiance par langue

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 3 | Fonctionne mais peu maintenu |
| **Security** | 4 | Apache 2.0, local |
| **Scalability** | 4 | Très rapide, CPU only |
| **Support/Community** | 2 | 1.9k stars, peu maintenu |
| **Documentation** | 2 | README minimal |
| **Integration Ease** | 5 | 2 lignes de code |

## Use Cases
1. **Language detection simple** — Détecter la langue de textes courts
2. **Pipeline preprocessing** — Router des textes par langue

## Getting Started
```python
from langdetect import detect, detect_langs
print(detect("Bonjour, comment allez-vous ?"))  # fr
print(detect_langs("This is a test."))  # [en:0.9999]
```

## Strengths
- Ultra-simple, 2 lignes de code
- Léger, pas de ML
- Apache 2.0

## Limitations
- Non-déterministe par défaut (utiliser DetectorFactory.seed)
- Peu maintenu (2021)
- 55 langues seulement
- Mauvais sur textes courts

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Lingua-py | **Recommandé** — meilleur sur textes courts, 75 langues |
| FastText lid.176 | Plus rapide, 176 langues, archivé |

## References
- https://github.com/Mimino666/langdetect

## Notes
Pour de nouveaux projets, Lingua-py est préférable (75 langues, déterministe, meilleur sur textes courts). LangDetect reste fonctionnel pour les cas simples.
