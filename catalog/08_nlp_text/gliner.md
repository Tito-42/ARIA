# GLiNER

> NER zero-shot/few-shot — extraction d'entités sans entraînement spécifique, labels arbitraires.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 08 - NLP & Text / Named Entity Recognition |
| **URL** | https://github.com/urchade/GLiNER |
| **GitHub** | https://github.com/urchade/GLiNER |
| **Stars** | ~3,000 |
| **License** | Apache 2.0 |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
GLiNER révolutionne le NER en permettant l'extraction d'entités nommées avec des labels arbitraires, sans entraînement spécifique. Contrairement aux modèles NER classiques limités aux catégories d'entraînement (PER, ORG, LOC), GLiNER accepte n'importe quel label textuel à l'inférence.

C'est un modèle léger (pas un LLM) qui fonctionne en temps réel, contrairement aux approches LLM-based pour le NER.

## Key Features
- **Zero-shot NER**: Labels arbitraires sans training
- **Léger**: Pas un LLM, modèle small encoder
- **Rapide**: Inférence temps réel
- **Multi-langues**: Support multilingue
- **Fine-tunable**: Adaptable à des domaines spécifiques
- **spaCy integration**: Via GLiNER-spaCy wrapper

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Production, rapide et léger |
| **Security** | 4 | Apache 2.0, self-hosted |
| **Scalability** | 4 | Léger, CPU possible |
| **Support/Community** | 3 | 3k stars, en croissance |
| **Documentation** | 3 | README et exemples |
| **Integration Ease** | 4 | API simple, spaCy wrapper |

## Use Cases
1. **NER flexible** — Extraire des entités avec des types personnalisés
2. **Prototypage** — Tester des schémas d'extraction sans training
3. **Domain-specific NER** — NER médical, juridique, technique sans dataset

## Getting Started
```python
from gliner import GLiNER
model = GLiNER.from_pretrained("urchade/gliner_medium-v2.1")

text = "The drug Aspirin was developed by Bayer in Germany."
labels = ["drug", "company", "country"]
entities = model.predict_entities(text, labels)
for entity in entities:
    print(entity["text"], entity["label"], entity["score"])
```

## Architecture / How It Works
GLiNER utilise un encodeur bidirectionnel qui encode conjointement le texte et les labels d'entités. Le modèle apprend à aligner les spans de texte avec les descriptions de labels via un mécanisme d'attention croisée, permettant la généralisation zero-shot.

## Strengths
- Zero-shot avec labels arbitraires — révolutionnaire
- Léger et rapide (pas un LLM)
- Apache 2.0
- Fine-tunable

## Limitations
- Moins précis que des modèles fine-tunés pour des domaines spécifiques
- Communauté encore petite
- Certains labels complexes nécessitent du fine-tuning

## Alternatives
| Tool | Key Difference |
|------|---------------|
| spaCy NER | Plus précis si fine-tuné, labels fixes |
| Flair NER | Stacked embeddings, labels fixes |
| LLM-based NER | Plus flexible mais plus lent et coûteux |

## References
- https://github.com/urchade/GLiNER
- https://arxiv.org/abs/2311.08526

## Notes
GLiNER v0.2.26 (mars 2026). Change fondamentalement l'approche du NER. Idéal pour le prototypage et les cas où les catégories d'entités varient. Fine-tuner pour la production en domaine spécifique.
