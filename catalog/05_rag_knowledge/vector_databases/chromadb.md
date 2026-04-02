# ChromaDB

> Base de donnees d'embeddings open source simple et developer-friendly pour applications IA

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 05_rag_knowledge |
| **URL** | https://www.trychroma.com |
| **GitHub** | https://github.com/chroma-core/chroma |
| **Stars** | 27,100 |
| **License** | Apache-2.0 |
| **Pricing** | Free (open source), Chroma Cloud: $5 credits gratuits, puis usage-based |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
ChromaDB est une base de donnees d'embeddings open source concue comme infrastructure de donnees pour les applications IA. Sa philosophie est la simplicite extreme : une API minimaliste a 4 fonctions qui gere automatiquement la tokenisation, l'embedding et l'indexation.

Chroma s'est positionne comme le choix par defaut pour les developpeurs qui debutent avec les vector databases et le RAG. Sa facilite d'utilisation et son integration transparente avec les frameworks LLM (LangChain, LlamaIndex) en font un outil ideal pour le prototypage rapide et les projets de taille moyenne.

Avec le lancement de Chroma Cloud, le projet a evolue d'une solution locale vers une offre hybride permettant un passage en production sans changer de code.

## Key Features
- **API ultra-simple** : 4 fonctions principales (add, query, update, delete)
- **Auto-embedding** : tokenisation et embedding automatiques a l'ingestion
- **Metadata filtering** : filtrage sur les metadonnees lors des requetes
- **Full-text search** : recherche plein texte en complement de la recherche vectorielle
- **Hybrid search** : combinaison vectorielle + plein texte
- **Multi-language SDKs** : Python, JavaScript/TypeScript, Go
- **Chroma Cloud** : service managed avec $5 de credits gratuits
- **Docker deployment** : client-serveur deployable via Docker
- **Embedded mode** : utilisation directe en memoire sans serveur
- **Document search** : requetes directement sur le texte des documents

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | v1.5.5 stable, Chroma Cloud pour production managed |
| **Security** | 3 | Auth basique, TLS via reverse proxy, moins mature que Qdrant/Milvus |
| **Scalability** | 3 | Bon pour millions de vecteurs, moins adapte aux milliards |
| **Support/Community** | 4 | 27K+ stars, communaute active, Discord |
| **Documentation** | 4 | Bonne documentation, guides de demarrage, cookbooks |
| **Integration Ease** | 5 | API la plus simple du marche, integrations LangChain/LlamaIndex natives |

## Use Cases
1. **Prototypage RAG** : mise en place rapide d'un pipeline RAG pour POC
2. **Applications IA locales** : mode embedded sans infrastructure serveur
3. **Chatbots documentaires** : recherche semantique sur un corpus de documents
4. **Projets academiques/recherche** : simplicite ideale pour experimentation

## Getting Started
```bash
pip install chromadb

import chromadb
client = chromadb.Client()  # mode embedded en memoire
collection = client.create_collection("my_docs")
collection.add(
    documents=["doc1 text", "doc2 text"],
    ids=["id1", "id2"],
    metadatas=[{"source": "wiki"}, {"source": "arxiv"}]
)
results = collection.query(query_texts=["search query"], n_results=5)
```

## Architecture / How It Works
```
Application
    ↓
Chroma Client (Python/JS/Go)
    ↓
┌─────────────────────────────┐
│  Mode Embedded (in-process) │   ou   Mode Client-Server (HTTP)
│  SQLite + HNSW local        │         │
└─────────────────────────────┘         ↓
                                  Chroma Server (Docker)
                                  ┌──────────────┐
                                  │ REST API      │
                                  │     ↓         │
                                  │ Embedding fn  │ → auto-embed si besoin
                                  │     ↓         │
                                  │ HNSW Index    │ → recherche ANN
                                  │ + SQLite      │ → metadata storage
                                  └──────────────┘
```

## Strengths
- API la plus simple de toutes les vector DB (courbe d'apprentissage quasi nulle)
- Mode embedded ideal pour prototypage et tests
- Auto-embedding elimine la complexite du pipeline
- Excellent pour les petits/moyens projets et le developpement local
- Bonne integration ecosysteme LLM

## Limitations
- **Scalabilite limitee** : pas concu pour des milliards de vecteurs
- **Performance** : moins performant que Qdrant ou Milvus sur de gros volumes
- **Features avancees** : pas de multi-vector, quantization limitee, pas de sharding distribue natif
- **Security** : moins de features security que les concurrents enterprise
- **Sparse vectors** : support hybrid search moins mature que Qdrant

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Qdrant | Plus performant, plus de features, meilleur pour production |
| LanceDB | Aussi embedded/serverless mais columnar format, plus performant |
| pgvector | Dans PostgreSQL existant, SQL familier |
| Pinecone | Fully managed, plus scalable, mais proprietary |
| Milvus | Tres scalable, GPU support, mais beaucoup plus complexe |

## References
- [Documentation officielle](https://docs.trychroma.com)
- [GitHub](https://github.com/chroma-core/chroma)
- [Chroma Cloud](https://www.trychroma.com/cloud)
- [Cookbook](https://cookbook.chromadb.dev/)

## Notes
- v1.5.5 sortie le 10 mars 2026
- Le mode embedded fait de Chroma un excellent choix pour les notebooks Jupyter et les POC
- Chroma Cloud lance avec $5 de credits gratuits, modele de pricing usage-based
- Migration du mode embedded vers client-server possible sans changement de code
