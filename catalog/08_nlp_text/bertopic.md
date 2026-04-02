# BERTopic

> Topic modeling avec transformers et c-TF-IDF — modélisation de thèmes state-of-the-art.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 08 - NLP & Text / Topic Modeling |
| **URL** | https://maartengr.github.io/BERTopic |
| **GitHub** | https://github.com/MaartenGr/BERTopic |
| **Stars** | ~7,500 |
| **License** | MIT |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Stable |
| **Maturity** | Production |

## What It Does
BERTopic est la solution state-of-the-art pour le topic modeling, utilisant des sentence embeddings (BERT/SentenceTransformers) combinés avec UMAP pour la réduction de dimension, HDBSCAN pour le clustering, et c-TF-IDF pour la représentation des topics. Il génère des topics cohérents et interprétables.

## Key Features
- **Embedding-based**: Sentence Transformers, OpenAI embeddings
- **c-TF-IDF**: Représentation de topics interprétable
- **Dynamic topics**: Topics évoluant dans le temps
- **Visualisations**: Plots intégrés (topics, hierarchies, bars)
- **Modulaire**: Chaque composant interchangeable
- **LLM labels**: Labeling de topics via LLMs

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Production, stable |
| **Security** | 5 | MIT, self-hosted |
| **Scalability** | 3 | Dépend de UMAP/HDBSCAN, memory-intensive |
| **Support/Community** | 4 | 7.5k stars |
| **Documentation** | 5 | Docs exemplaires, notebooks |
| **Integration Ease** | 4 | API scikit-learn-like |

## Use Cases
1. **Analyse de corpus** — Découvrir les thèmes dans de grands corpus de texte
2. **Customer feedback** — Catégoriser automatiquement les retours clients
3. **Content analysis** — Analyser les tendances dans les publications

## Getting Started
```python
from bertopic import BERTopic
topic_model = BERTopic()
topics, probs = topic_model.fit_transform(documents)
topic_model.get_topic_info()
topic_model.visualize_topics()
```

## Architecture / How It Works
Pipeline : (1) Documents → sentence embeddings (Sentence Transformers), (2) UMAP réduit la dimensionnalité, (3) HDBSCAN cluster les documents, (4) c-TF-IDF extrait les mots représentatifs par cluster.

## Strengths
- State-of-the-art topic modeling
- Visualisations intégrées
- MIT licence
- Docs exemplaires

## Limitations
- Dépendances lourdes (UMAP, HDBSCAN)
- Memory-intensive pour gros corpus
- Pas de streaming/online learning natif

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Gensim LDA | NLP classique, plus léger |
| Top2Vec | Alternative embedding-based |

## References
- https://maartengr.github.io/BERTopic
- https://github.com/MaartenGr/BERTopic

## Notes
BERTopic est le gold standard pour le topic modeling moderne. Pour de très gros corpus, considérer l'option mini-batch de UMAP ou un échantillonnage.
