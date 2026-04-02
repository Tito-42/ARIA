# Stanza (Stanford NLP)

> Bibliothèque NLP multilingue par Stanford — 70+ langues, tokenization, NER, POS, dependency parsing.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 08 - NLP & Text / NLP Library |
| **URL** | https://stanfordnlp.github.io/stanza |
| **GitHub** | https://github.com/stanfordnlp/stanza |
| **Stars** | ~7,800 |
| **License** | Apache 2.0 |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Stanza est la bibliothèque NLP officielle de Stanford, offrant la meilleure couverture multilingue avec 70+ langues. Elle fournit des pipelines pour la tokenization, MWT expansion, lemmatization, POS tagging, NER et dependency parsing, avec une qualité académique de référence.

## Key Features
- **70+ langues**: Couverture multilingue la plus large
- **Pipeline complet**: Tokenization → POS → NER → parsing
- **Qualité académique**: Modèles de référence Stanford
- **Universal Dependencies**: Format UD standard
- **CoreNLP interface**: Bridge vers Stanford CoreNLP (Java)
- **Apache 2.0**: Licence permissive

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Production, qualité académique |
| **Security** | 4 | Apache 2.0, self-hosted |
| **Scalability** | 3 | Plus lent que spaCy |
| **Support/Community** | 3 | 7.8k stars, Stanford backing |
| **Documentation** | 4 | Docs complètes |
| **Integration Ease** | 4 | API Python simple |

## Use Cases
1. **NLP multilingue** — Processing de textes en 70+ langues
2. **Analyse linguistique** — Parsing syntaxique de qualité académique
3. **Research** — Benchmarking NLP multilingue

## Getting Started
```python
import stanza
stanza.download('en')
nlp = stanza.Pipeline('en')
doc = nlp("Barack Obama was born in Hawaii.")
for ent in doc.ents:
    print(ent.text, ent.type)
```

## Architecture / How It Works
Stanza utilise des modèles BiLSTM et Transformer par langue, organisés en pipeline séquentiel. Les modèles sont conformes aux annotations Universal Dependencies pour une standardisation cross-linguale.

## Strengths
- Meilleure couverture multilingue (70+ langues)
- Qualité académique Stanford
- Apache 2.0
- Universal Dependencies standard

## Limitations
- Plus lent que spaCy
- API moins moderne
- Moins d'intégrations que spaCy ou HF

## Alternatives
| Tool | Key Difference |
|------|---------------|
| spaCy | Plus rapide, meilleur écosystème, 25+ langues |
| HF Transformers | Plus de modèles, plus flexible |
| NLTK | NLP classique, enseignement |

## References
- https://stanfordnlp.github.io/stanza
- https://github.com/stanfordnlp/stanza

## Notes
Stanza v1.11.1 (fév 2026). Le choix quand la couverture multilingue (70+ langues) est la priorité. Pour la performance en production, spaCy est plus rapide.
