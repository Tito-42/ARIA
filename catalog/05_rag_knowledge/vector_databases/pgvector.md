# pgvector

> Extension PostgreSQL open source pour la recherche par similarite vectorielle

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 05_rag_knowledge |
| **URL** | https://github.com/pgvector/pgvector |
| **GitHub** | https://github.com/pgvector/pgvector |
| **Stars** | 20,600 |
| **License** | PostgreSQL License (permissive, similaire MIT/BSD) |
| **Pricing** | Free (open source), disponible sur tous les managed PostgreSQL (Supabase, Neon, AWS RDS, etc.) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
pgvector est une extension PostgreSQL qui ajoute le support des vecteurs et de la recherche par similarite directement dans PostgreSQL. Au lieu de deployer une base de donnees vectorielle separee, pgvector permet d'utiliser la meme base PostgreSQL pour stocker les donnees relationnelles et les embeddings vectoriels.

L'avantage principal est l'elimination d'une piece d'infrastructure supplementaire : les equipes qui utilisent deja PostgreSQL peuvent ajouter des capacites vectorielles sans changer de stack. pgvector supporte la recherche exacte et approximative (ANN), avec des index HNSW et IVFFlat.

Avec 20.6K stars GitHub, pgvector est devenu l'extension PostgreSQL la plus populaire pour l'IA et est supporte nativement par la plupart des fournisseurs de PostgreSQL managed (Supabase, Neon, AWS RDS, Azure, GCP Cloud SQL).

## Key Features
- **Types de vecteurs** : single-precision, half-precision, binary, sparse vectors
- **6 metriques de distance** : L2, inner product, cosine, L1, Hamming, Jaccard
- **Index HNSW** : requetes rapides, construction plus lente (recommande)
- **Index IVFFlat** : construction rapide, requetes moderees
- **Iterative index scans** : filtrage ameliore avec les index approximatifs
- **Jusqu'a 2,000 dimensions** : vecteurs standards (64,000 pour binaires)
- **ACID compliance** : transactions completes, point-in-time recovery
- **JOINs natifs** : jointures SQL entre vecteurs et donnees relationnelles
- **Compatible tout langage** : fonctionne via n'importe quel client PostgreSQL
- **Parallel builds** : construction d'index en parallele pour accelerer l'indexation

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | Extension mature, PostgreSQL battle-tested, 20.6K stars |
| **Security** | 5 | Herite de toute la security de PostgreSQL (SSL, RBAC, row-level security) |
| **Scalability** | 3 | Bon pour millions de vecteurs, limite pour milliards (pas de sharding natif) |
| **Support/Community** | 5 | Enorme communaute PostgreSQL, supporte par tous les cloud providers |
| **Documentation** | 4 | Bonne doc, mais plus technique que les vector DB dediees |
| **Integration Ease** | 5 | SQL standard, n'importe quel ORM/driver PostgreSQL fonctionne |

## Use Cases
1. **RAG avec stack PostgreSQL existant** : ajout de capacites vectorielles sans nouvelle infrastructure
2. **Applications full-stack** : donnees relationnelles + embeddings dans la meme DB
3. **Recherche hybride SQL + vectorielle** : combinaison de filtres SQL complexes avec recherche semantique
4. **Startups/PME** : solution simple qui croit avec l'application sans complexity operationnelle

## Getting Started
```sql
-- Installation de l'extension
CREATE EXTENSION vector;

-- Creation d'une table avec colonne vectorielle
CREATE TABLE items (
  id SERIAL PRIMARY KEY,
  content TEXT,
  embedding vector(384)
);

-- Insertion
INSERT INTO items (content, embedding) VALUES ('texte exemple', '[0.1, 0.2, ...]');

-- Recherche par cosine similarity
SELECT * FROM items
ORDER BY embedding <=> '[0.1, 0.2, ...]'
LIMIT 10;

-- Creation d'index HNSW
CREATE INDEX ON items USING hnsw (embedding vector_cosine_ops);
```

## Architecture / How It Works
```
Application (Python/Node/Java/...)
         ↓
    PostgreSQL Client (psycopg2, pg, etc.)
         ↓
    PostgreSQL Server
    ┌──────────────────────────┐
    │  SQL Parser / Planner    │
    │         ↓                │
    │  pgvector Extension      │
    │  ┌────────────────────┐  │
    │  │ Vector Type        │  │ → Stockage des vecteurs
    │  │ Distance Operators │  │ → <-> L2, <=> cosine, <#> IP
    │  │ HNSW Index         │  │ → ANN search rapide
    │  │ IVFFlat Index      │  │ → ANN search alternatif
    │  └────────────────────┘  │
    │         ↓                │
    │  PostgreSQL Storage      │ → MVCC, WAL, ACID
    └──────────────────────────┘
```

## Strengths
- Zero infrastructure supplementaire si PostgreSQL est deja utilise
- Transactions ACID et toutes les garanties PostgreSQL
- JOINs SQL entre vecteurs et donnees relationnelles (impossible avec les vector DB dediees)
- Row-level security et RBAC PostgreSQL pour security granulaire
- Supporte par tous les managed PostgreSQL (Supabase, Neon, RDS, etc.)
- SQL familier - pas de nouvelle API a apprendre

## Limitations
- **Performance a grande echelle** : moins performant que Qdrant/Milvus sur des milliards de vecteurs
- **Pas de sharding vectoriel distribue** : scalabilite limitee a un seul noeud PostgreSQL
- **Dimensions limitees** : max 2,000 dimensions pour vecteurs standards
- **Pas de sparse vectors natifs** : support limite pour hybrid search
- **Tuning complexe** : optimisation des index HNSW necessite expertise PostgreSQL
- **Pas de GPU acceleration** : indexation et recherche CPU uniquement

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Qdrant | Vector DB dediee, plus performante sur gros volumes, hybrid search |
| Milvus | Distribue, GPU, milliards de vecteurs, mais infra complexe |
| Pinecone | Managed, zero ops, mais proprietary |
| Supabase pgvector | pgvector managed avec UI et API REST |
| Neon pgvector | pgvector serverless avec branching |

## References
- [GitHub](https://github.com/pgvector/pgvector)
- [Documentation pgvector](https://github.com/pgvector/pgvector/blob/master/README.md)
- [Supabase Vector](https://supabase.com/vector)
- [pgvector sur AWS RDS](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_pgvector.html)

## Notes
- v0.8.2 est la derniere version (avril 2026)
- Le choix ideal quand PostgreSQL est deja dans le stack et que les volumes restent raisonnables (< dizaines de millions de vecteurs)
- Supabase et Neon ajoutent des couches d'API et d'UI par-dessus pgvector pour une experience plus moderne
- La limitation a 2,000 dimensions est suffisante pour la plupart des modeles d'embedding (OpenAI text-embedding-3-small: 1536 dim)
