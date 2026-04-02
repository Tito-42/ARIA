# Weaviate

> Base de donnees vectorielle AI-native open source avec vectorisation integree et RAG natif

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 05_rag_knowledge |
| **URL** | https://weaviate.io |
| **GitHub** | https://github.com/weaviate/weaviate |
| **Stars** | 15,900 |
| **License** | BSD 3-Clause |
| **Pricing** | Free (self-hosted), Weaviate Cloud: Sandbox gratuit, Standard (usage-based), Enterprise (custom) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Weaviate est une base de donnees vectorielle open source cloud-native qui stocke a la fois les objets et leurs vecteurs, permettant de combiner recherche vectorielle et filtrage par mots-cles dans une interface de requete unifiee. Ecrit en Go, Weaviate met l'accent sur la performance et la fiabilite.

La caracteristique distinctive de Weaviate est son approche "AI-native" : il integre directement des modeles de vectorisation (OpenAI, Cohere, HuggingFace, Google) et des capacites de generation (RAG, reranking) au sein meme de la base de donnees, eliminant le besoin de pipelines externes pour ces operations.

Weaviate supporte la recherche semantique a l'echelle du milliard de vecteurs avec des temps de reponse en millisecondes, et propose des fonctionnalites avancees comme le multi-tenancy, la replication et le RBAC.

## Key Features
- **Vectorisation integree** : modules vectorizer pour OpenAI, Cohere, HuggingFace, Google, etc.
- **RAG natif (generative search)** : generation de reponses directement depuis les resultats de recherche
- **Reranking integre** : re-classement des resultats via modeles de reranking
- **Hybrid search** : combinaison semantique (dense) + keyword (BM25)
- **Image search** : recherche par similarite d'images
- **Multi-tenancy** : isolation des donnees par tenant pour applications SaaS
- **Replication** : haute disponibilite via replication des donnees
- **RBAC** : controle d'acces base sur les roles
- **Vector compression** : quantization pour reduire l'utilisation memoire
- **Object TTL** : expiration automatique des donnees avec time-to-live configurable
- **GraphQL & REST APIs** : interfaces de requete flexibles

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | v1.36, deploiements production, mais communaute plus petite que Milvus/Qdrant |
| **Security** | 4 | RBAC, TLS, multi-tenancy, auth OIDC |
| **Scalability** | 4 | Milliards de vecteurs, replication, mais moins de sharding options que Milvus |
| **Support/Community** | 4 | 15.9K stars, Weaviate Inc. support commercial, Slack actif |
| **Documentation** | 5 | Documentation tres complete avec guides, recipes, academy |
| **Integration Ease** | 5 | Vectorisation integree simplifie enormement le pipeline |

## Use Cases
1. **RAG tout-en-un** : pipeline RAG complet sans services externes (vectorisation + recherche + generation)
2. **Applications SaaS multi-tenant** : isolation des donnees par client
3. **Recherche multimodale** : recherche combinant texte et images
4. **Q&A sur documentation** : chatbots documentaires avec generative search integre

## Getting Started
```bash
# Docker Compose
docker compose up -d  # voir docker-compose.yml sur le repo

# Python client
pip install weaviate-client

import weaviate
client = weaviate.connect_to_local()
collection = client.collections.create(
    "Article",
    vectorizer_config=weaviate.Configure.Vectorizer.text2vec_openai()
)
collection.data.insert({"title": "Mon article", "content": "Contenu..."})
results = collection.query.near_text("recherche semantique", limit=5)
```

## Architecture / How It Works
```
Client (Python/JS/Go/Java)
         ↓
    Weaviate Server (Go)
    ┌──────────────────────┐
    │  GraphQL / REST API  │
    │         ↓            │
    │  Module System       │
    │  ┌────────────────┐  │
    │  │ Vectorizers     │  │ → text2vec-openai, -cohere, -huggingface...
    │  │ Generators      │  │ → generative-openai, -cohere, -anthropic...
    │  │ Rerankers       │  │ → reranker-cohere, -transformers...
    │  └────────────────┘  │
    │         ↓            │
    │  Vector Index (HNSW) │ → Recherche ANN + quantization
    │  Inverted Index      │ → BM25 keyword search
    │  Object Store        │ → Donnees + metadonnees
    │         ↓            │
    │  Replication Layer   │ → Multi-node HA
    └──────────────────────┘
```

## Strengths
- Vectorisation integree eliminant la complexite du pipeline embedding
- RAG natif (generative search) unique dans le marche des vector DB
- Approche modulaire tres extensible
- Multi-tenancy robuste pour applications SaaS
- Excellent pour les equipes qui veulent un pipeline RAG avec moins de composants

## Limitations
- **Communaute plus petite** : 15.9K stars vs 43.5K (Milvus) ou 30K (Qdrant)
- **Dependance modules** : la vectorisation integree cree une dependance aux providers
- **GPU** : pas de GPU acceleration native pour l'indexation
- **Complexite modulaire** : la configuration des modules peut etre complexe
- **Performance brute** : benchmarks generalement derriere Qdrant et Milvus sur la recherche pure

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Qdrant | Plus performant en recherche pure, Rust, mais sans vectorisation integree |
| Milvus | Plus scalable, GPU support, mais sans RAG natif |
| Pinecone | Managed, inference integree recemment, mais proprietary |
| ChromaDB | Plus simple, mais sans modules de vectorisation/generation |

## References
- [Documentation officielle](https://weaviate.io/developers/weaviate)
- [GitHub](https://github.com/weaviate/weaviate)
- [Weaviate Cloud](https://console.weaviate.cloud)
- [Weaviate Academy](https://weaviate.io/developers/academy)
- [Recipes](https://github.com/weaviate/recipes)

## Notes
- v1.36.0 en production (mars 2026)
- L'approche "AI-native" avec vectorisation integree est un differenciateur cle pour les equipes qui veulent simplifier leur stack
- Object TTL est une feature unique utile pour les donnees ephemeres
- Weaviate Academy propose des cours gratuits pour apprendre la plateforme
