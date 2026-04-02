# Qdrant

> Moteur de recherche vectorielle open source haute performance ecrit en Rust

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 05_rag_knowledge |
| **URL** | https://qdrant.tech |
| **GitHub** | https://github.com/qdrant/qdrant |
| **Stars** | 30,000 |
| **License** | Apache-2.0 |
| **Pricing** | Free (self-hosted), Cloud: Free tier (1GB), Standard (from $0.034/h), Enterprise (custom) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Qdrant (prononce "quadrant") est un moteur de recherche par similarite vectorielle et base de donnees vectorielle open source ecrit en Rust. Il fournit un service pret pour la production avec une API pratique pour stocker, rechercher et gerer des vecteurs avec des payloads (metadonnees) enrichis.

Qdrant est concu pour des charges de travail etendues de filtrage, ce qui le rend ideal pour les applications de recherche neuronale, de matching semantique et de RAG. L'implementation en Rust garantit des performances elevees, une faible consommation memoire et une fiabilite sous forte charge.

Avec 30K stars GitHub et un rythme de release soutenu (v1.17.1 en mars 2026), Qdrant est l'une des solutions vectorielles open source les plus populaires et les plus activement developpees du marche.

## Key Features
- **Hybrid search** : combine vecteurs denses et sparse pour une recherche keyword-aware complementant la recherche semantique
- **Payload filtering** : filtrage riche sur des donnees JSON attachees aux vecteurs (keywords, ranges numeriques, geo-localisation)
- **Vector quantization** : compression integree reduisant l'utilisation RAM jusqu'a 97% avec gestion precision/vitesse
- **Distributed scaling** : expansion horizontale via sharding et replication avec mises a jour zero-downtime
- **SIMD acceleration** : optimisation CPU avancee pour les calculs de distance
- **Async I/O** : utilisation de io_uring pour des I/O asynchrones performantes
- **Write-ahead logging** : WAL pour fiabilite et durabilite des donnees
- **Multi-vector support** : plusieurs vecteurs par point (ex: titre + contenu)
- **APIs REST & gRPC** : OpenAPI 3.0 pour REST, gRPC pour haute performance
- **Client SDKs** : Python, TypeScript, Rust, Go, Java, C#

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | v1.17+, utilise en production par des milliers d'entreprises |
| **Security** | 4 | API key auth, TLS, RBAC dans la version cloud |
| **Scalability** | 5 | Sharding distribue, replication, quantization pour milliards de vecteurs |
| **Support/Community** | 5 | 30K stars, Discord actif, support commercial disponible |
| **Documentation** | 5 | Documentation exhaustive, tutorials, exemples pratiques |
| **Integration Ease** | 5 | SDKs 6 langages, Docker ready, integrations LlamaIndex/LangChain/Haystack |

## Use Cases
1. **RAG enterprise** : backend vectoriel pour systemes de question-answering sur documents internes
2. **Recherche semantique** : moteur de recherche semantique sur corpus de textes, images ou code
3. **Recommandation** : systemes de recommandation en temps reel bases sur les embeddings
4. **Detection de similarite** : detection de duplicats, plagiat, ou contenus similaires

## Getting Started
```bash
# Docker (methode recommandee)
docker run -p 6333:6333 -p 6334:6334 qdrant/qdrant

# Python client
pip install qdrant-client

from qdrant_client import QdrantClient
client = QdrantClient("localhost", port=6333)
client.create_collection("my_collection", vectors_config={"size": 384, "distance": "Cosine"})
client.upsert("my_collection", points=[{"id": 1, "vector": [0.1, 0.2, ...], "payload": {"city": "Paris"}}])
results = client.query_points("my_collection", query=[0.1, 0.2, ...], limit=10)
```

## Architecture / How It Works
```
Client SDK (REST/gRPC)
        ↓
   Qdrant Engine (Rust)
   ┌─────────────────────┐
   │  API Layer           │
   │       ↓              │
   │  Query Planner       │ → Payload filtering + vector search
   │       ↓              │
   │  Index Manager       │ → HNSW graph index + quantization
   │       ↓              │
   │  Storage Layer       │ → WAL + on-disk/in-memory segments
   │       ↓              │
   │  Consensus (Raft)    │ → Distribution & replication
   └─────────────────────┘
```

## Strengths
- Performance excellente grace a Rust et SIMD
- Quantization avancee (scalar, product, binary) pour optimiser RAM
- Hybrid search (dense + sparse) natif
- Multi-vector par point tres utile pour RAG avance
- Self-hosted gratuit avec toutes les fonctionnalites
- Communaute tres active et releases frequentes

## Limitations
- Moins de fonctionnalites managed que Pinecone (mais Qdrant Cloud comble le gap)
- Pas de GPU acceleration native (contrairement a Milvus)
- Courbe d'apprentissage pour le tuning de performance en production
- Ecosysteme d'outils moins riche que Milvus (Attu, Birdwatcher, etc.)

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Pinecone | Fully managed, zero ops, mais proprietary et vendor lock-in |
| Milvus | Plus scalable (GPU), mais plus lourd et complexe |
| Weaviate | Vectorisation integree, GraphQL, mais Go (vs Rust) |
| ChromaDB | Plus simple, ideal prototypage, mais moins performant a l'echelle |
| pgvector | Dans PostgreSQL existant, mais performances moindres sur gros volumes |

## References
- [Documentation officielle](https://qdrant.tech/documentation/)
- [GitHub](https://github.com/qdrant/qdrant)
- [Qdrant Cloud](https://cloud.qdrant.io)
- [Tutorials](https://qdrant.tech/documentation/tutorials/)

## Notes
- v1.17.1 sortie le 27 mars 2026 - rythme de release tres soutenu
- Le mode hybrid search avec sparse vectors est un avantage competitif significatif
- Qdrant supporte les snapshots pour backup/restore et migration entre clusters
- Option fastembed integree pour generer des embeddings sans service externe
