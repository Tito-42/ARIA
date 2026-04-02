# spaCy

> Bibliothèque NLP industrielle — NER, POS tagging, dependency parsing, pipelines optimisés pour la production.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 08 - NLP & Text / NLP Library |
| **URL** | https://spacy.io |
| **GitHub** | https://github.com/explosion/spaCy |
| **Stars** | ~33,400 |
| **License** | MIT |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
spaCy est la bibliothèque NLP de référence pour la production. Développée par Explosion, elle fournit des pipelines optimisés pour la tokenization, NER, POS tagging, dependency parsing, lemmatization et text classification. spaCy est conçue pour être rapide, efficace et intégrable dans des applications de production.

## Key Features
- **Pipelines composables**: Assembler des composants NLP
- **NER production**: Extraction d'entités rapide et précise
- **Multi-langues**: 25+ langues avec modèles pré-entraînés
- **Transformer integration**: spaCy-transformers pour BERT, RoBERTa
- **Custom components**: Pipeline extensible avec composants custom
- **Prodigy integration**: Annotation active learning

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | Conçu pour la production |
| **Security** | 5 | MIT, self-hosted |
| **Scalability** | 4 | Rapide, batch processing |
| **Support/Community** | 5 | 33.4k stars, Explosion support |
| **Documentation** | 5 | Docs parmi les meilleures du marché |
| **Integration Ease** | 5 | Pipeline en quelques lignes |

## Use Cases
1. **NER production** — Extraction d'entités à grande échelle
2. **Text preprocessing** — Tokenization, lemmatization, POS tagging
3. **Custom NLP pipeline** — Pipelines métier composables

## Getting Started
```python
import spacy
nlp = spacy.load("en_core_web_sm")
doc = nlp("Apple is looking at buying U.K. startup for $1 billion")
for ent in doc.ents:
    print(ent.text, ent.label_)
# Apple ORG, U.K. GPE, $1 billion MONEY
```

## Architecture / How It Works
spaCy utilise un pipeline séquentiel : Tokenizer → tagger → parser → NER → etc. Chaque composant est un callable qui annote le Doc. Les modèles utilisent des architectures CNN ou Transformer (via spacy-transformers) sous le capot.

## Strengths
- Le plus rapide pour le NLP production
- MIT licence
- Docs parmi les meilleures du marché
- Pipeline composable et extensible

## Limitations
- Moins flexible que HF pour modèles custom
- Moins de modèles pré-entraînés que HuggingFace
- Pas conçu pour la génération de texte

## Alternatives
| Tool | Key Difference |
|------|---------------|
| HF Transformers | Plus de modèles, plus flexible, plus lourd |
| Stanza | Stanford, 70+ langues, plus académique |
| Flair | NER spécialisé, stacked embeddings |

## References
- https://spacy.io
- https://github.com/explosion/spaCy

## Notes
spaCy v3.8.14 (mars 2026). Le duo spaCy + HuggingFace Transformers couvre 95% des besoins NLP. spaCy pour la production rapide, HF pour les modèles state-of-the-art.
