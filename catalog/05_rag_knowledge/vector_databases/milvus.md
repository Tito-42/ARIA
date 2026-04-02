# Milvus

> Base de donnees vectorielle cloud-native hautement scalable pour la recherche ANN

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 05_rag_knowledge |
| **URL** | https://milvus.io |
| **GitHub** | https://github.com/milvus-io/milvus |
| **Stars** | 43,500 |
| **License** | Apache-2.0 |
| **Pricing** | Free (self-hosted), Zilliz Cloud: Free tier, Standard ($0.056/CU/h), Enterprise (custom) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Enterprise |

## What It Does
Milvus est une base de donnees vectorielle cloud-native construite pour la recherche ANN (Approximate Nearest Neighbor) a grande echelle. Developpe par Zilliz et gradue du programme LF AI & Data Foundation, Milvus est la vector DB open source la plus populaire (43.5K stars GitHub).

Milvus se distingue par son architecture distribuee separant compute et storage, permettant un scaling horizontal independant des workloads lecture/ecriture. Il supporte des milliards de vecteurs avec des performances de requete en millisecondes, ce qui en fait le choix privilegie pour les deployments enterprise a grande echelle.

Le projet est accompagne de Zilliz Cloud, une version managed, et d'un ecosysteme riche d'outils (Attu pour la GUI, Birdwatcher pour le diagnostic).

## Key Features
- **Architecture distribuee** : separation compute/storage, scaling horizontal independant
- **Multi-index support** : HNSW, IVF, FLAT, SCANN, DiskANN avec quantization et memory mapping
- **GPU acceleration** : support NVIDIA CAGRA GPU indexing pour performances maximales
- **Multi-tenancy** : isolation au niveau database, collection, partition ou partition key
- **Hot/cold storage** : stockage en tiers pour optimiser couts vs performance
- **Full-text search natif** : BM25, sparse embeddings (SPLADE, BGE-M3)
- **Hybrid search** : combinaison dense + sparse dans une seule requete
- **Security** : authentification, TLS, RBAC (Role-Based Access Control)
- **Streaming ingestion** : ingestion de donnees en temps reel + batch
- **CDC (Change Data Capture)** : capture des changements pour synchronisation
- **MMap support** : memory-mapped files pour reduire l'empreinte memoire

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | 43.5K stars, LF AI Foundation graduated, milliers de deployments |
| **Security** | 5 | RBAC, TLS, auth, multi-tenancy, SOC 2 (Zilliz Cloud) |
| **Scalability** | 5 | Architecture distribuee, milliards de vecteurs, GPU support |
| **Support/Community** | 5 | LF AI Foundation, Zilliz commercial support, communaute massive |
| **Documentation** | 5 | Documentation tres complete, bootcamp, tutorials |
| **Integration Ease** | 4 | SDKs Python/Java/Go/Node, mais deployment plus complexe que Qdrant |

## Use Cases
1. **RAG enterprise a grande echelle** : recherche vectorielle sur des milliards de documents
2. **Recherche multimodale** : images, texte, audio dans un meme index
3. **Systemes de recommandation temps reel** : matching a faible latence sur gros volumes
4. **Drug discovery / genomics** : recherche de similarite sur des embeddings moleculaires

## Getting Started
```bash
# Docker Compose (standalone)
wget https://github.com/milvus-io/milvus/releases/download/v2.5.0/milvus-standalone-docker-compose.yml -O docker-compose.yml
docker compose up -d

# Milvus Lite (embedded, pour dev)
pip install pymilvus
from pymilvus import MilvusClient
client = MilvusClient("milvus_demo.db")  # mode local embedded
client.create_collection("demo", dimension=384)
client.insert("demo", data=[{"id": 1, "vector": [0.1, ...], "text": "example"}])
results = client.search("demo", data=[[0.1, ...]], limit=10)
```

## Architecture / How It Works
```
Client SDKs (Python/Java/Go/Node)
              ↓
         Access Layer
         (Proxy / Load Balancer)
              ↓
    ┌─────────┴──────────┐
    │   Coordinator       │ → Root, Query, Data, Index coordinators
    │   (Control plane)   │
    └─────────┬──────────┘
              ↓
    ┌─────────┴──────────┐
    │   Worker Nodes      │
    │  ┌─────┐ ┌───────┐ │
    │  │Query│ │Data   │ │ → Separation read/write
    │  │Node │ │Node   │ │
    │  └─────┘ └───────┘ │
    └─────────┬──────────┘
              ↓
    ┌─────────┴──────────┐
    │   Storage           │
    │  MinIO/S3 + etcd    │ → Object storage + metadata
    └────────────────────┘
```

## Strengths
- La vector DB open source la plus populaire et mature (43.5K stars)
- Architecture distribuee reellement scalable (milliards de vecteurs)
- GPU acceleration pour les workloads les plus exigeants
- Multi-tenancy et RBAC robustes pour enterprise
- Milvus Lite permet un developpement local leger
- Ecosysteme d'outils riche (Attu GUI, Birdwatcher, CDC)

## Limitations
- **Complexite de deployment** : architecture distribuee complexe (etcd, MinIO, coordinators)
- **Ressources** : consommation memoire/CPU significative en mode distribue
- **Courbe d'apprentissage** : plus complexe que Qdrant ou ChromaDB
- **Overhead pour petits projets** : surdimensionne pour des cas d'usage simples
- **Cold start** : temps de demarrage plus long que les alternatives monolithiques

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Qdrant | Plus simple, Rust, moins de setup, ideal pour medium scale |
| Pinecone | Managed, zero ops, mais proprietary |
| Weaviate | Vectorisation integree, plus simple, mais moins scalable |
| pgvector | Extension PG, minimal setup, mais pas concu pour milliards de vecteurs |
| LanceDB | Serverless/embedded, columnar, plus simple mais moins distribue |

## References
- [Documentation officielle](https://milvus.io/docs)
- [GitHub](https://github.com/milvus-io/milvus)
- [Zilliz Cloud](https://cloud.zilliz.com)
- [Milvus Bootcamp](https://github.com/milvus-io/bootcamp)
- [Attu GUI](https://github.com/zilliztech/attu)

## Notes
- Milvus Lite (mode embedded via pymilvus) est ideal pour le developpement et les tests
- Zilliz Cloud offre une version managed compatible API avec Milvus
- Le support GPU (NVIDIA CAGRA) est un differenciateur majeur pour les workloads intensifs
- Gradue du programme LF AI & Data Foundation, gage de gouvernance open source mature
