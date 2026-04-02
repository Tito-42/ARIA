# NLTK

> Natural Language Toolkit — bibliothèque NLP classique pour tokenization, stemming, parsing, corpora.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 08 - NLP & Text / NLP Library |
| **URL** | https://www.nltk.org |
| **GitHub** | https://github.com/nltk/nltk |
| **Stars** | ~14,600 |
| **License** | Apache 2.0 |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
NLTK (Natural Language Toolkit) est la bibliothèque NLP la plus ancienne et la plus complète en Python. Elle fournit des outils pour la tokenization, le stemming, le lemmatization, le parsing syntaxique, et inclut une collection de corpora et de modèles linguistiques. Idéale pour l'apprentissage et les tâches NLP classiques.

## Key Features
- **Tokenization**: Word et sentence tokenizers multiples
- **Stemming/Lemmatization**: Porter, Snowball, WordNet lemmatizer
- **Corpora**: 100+ corpus intégrés (Brown, Reuters, WordNet, etc.)
- **Parsing**: CFG, PCFG, dependency parsing
- **Classification**: Naive Bayes, MaxEnt
- **Educational**: Excellent pour apprendre le NLP

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 3 | Fonctionnel mais lent pour la production |
| **Security** | 4 | Apache 2.0, self-hosted |
| **Scalability** | 2 | Lent comparé à spaCy |
| **Support/Community** | 4 | 14.6k stars, standard académique |
| **Documentation** | 5 | Livre NLTK complet gratuit |
| **Integration Ease** | 4 | API simple, bien connue |

## Use Cases
1. **Enseignement** — Apprendre le NLP
2. **Prototypage** — Tester des idées NLP rapidement
3. **NLP classique** — Stemming, parsing, corpora analysis

## Getting Started
```python
import nltk
nltk.download('punkt_tab')
nltk.download('averaged_perceptron_tagger')
from nltk.tokenize import word_tokenize
tokens = word_tokenize("This is a sample sentence.")
```

## Architecture / How It Works
NLTK est une collection de modules Python indépendants. Les corpora et modèles sont téléchargés séparément via `nltk.download()`. Chaque module fournit des classes et fonctions pour une tâche NLP spécifique.

## Strengths
- La plus complète pour le NLP classique
- 100+ corpora intégrés
- Excellent livre d'apprentissage gratuit
- Standard académique

## Limitations
- Lent comparé à spaCy (pas optimisé pour la production)
- API vieillissante
- Pas de deep learning natif

## Alternatives
| Tool | Key Difference |
|------|---------------|
| spaCy | **Recommandé production** — rapide, moderne |
| Stanza | Stanford, multilingue, deep learning |
| HF Transformers | Deep learning, state-of-the-art |

## References
- https://www.nltk.org
- https://www.nltk.org/book/

## Notes
NLTK reste pertinent pour l'enseignement, le prototypage et les tâches NLP classiques (stemming, parsing). Pour la production, spaCy est le choix standard.
