# Feast

> Feature store open-source — online/offline serving avec support Qdrant pour vector features.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 10 - Data Science & MLOps / Feature Store |
| **URL** | https://feast.dev |
| **GitHub** | https://github.com/feast-dev/feast |
| **Stars** | ~6,900 |
| **License** | Apache 2.0 |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Feast est le feature store open-source standard. Il résout le problème du "feature serving" en ML : stocker, versionner et servir des features de façon cohérente entre l'entraînement (offline) et l'inférence (online). Les features sont calculées une fois et réutilisées partout.

Feast supporte maintenant les vector features via Qdrant, ce qui permet de l'utiliser aussi comme store d'embeddings pour des applications RAG et de recherche sémantique.

## Key Features
- **Online/Offline stores**: Serving temps réel et batch
- **Feature registry**: Découverte et documentation des features
- **Point-in-time joins**: Pas de data leakage dans le training
- **Vector features**: Support Qdrant pour embeddings
- **Multi-backend**: Redis, DynamoDB, PostgreSQL, BigQuery, etc.
- **Feature transforms**: On-demand et batch transforms

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Production, utilisé en enterprise |
| **Security** | 4 | Self-hosted, Apache 2.0 |
| **Scalability** | 4 | Dépend du backend (Redis, DynamoDB scalent) |
| **Support/Community** | 3 | 6.9k stars, communauté active |
| **Documentation** | 4 | Docs complètes, quickstart clair |
| **Integration Ease** | 3 | Setup du store non trivial |

## Use Cases
1. **ML feature serving** — Servir des features en temps réel pour l'inférence
2. **Feature reuse** — Partager des features entre équipes et modèles
3. **Vector serving** — Stocker et servir des embeddings via Qdrant

## Getting Started
```python
from feast import FeatureStore

store = FeatureStore(repo_path=".")

# Récupérer des features online
features = store.get_online_features(
    features=["user_features:age", "user_features:total_purchases"],
    entity_rows=[{"user_id": 123}]
).to_dict()
```
```bash
pip install feast
feast init my_feature_repo
cd my_feature_repo
feast apply
feast materialize-incremental $(date +%Y-%m-%dT%H:%M:%S)
```

## Architecture / How It Works
Feast utilise un registry (SQLite, S3, GCS) pour les métadonnées des features, un offline store (BigQuery, Redshift, fichiers Parquet) pour le training, et un online store (Redis, DynamoDB, PostgreSQL) pour le serving temps réel. `feast materialize` copie les features de l'offline vers l'online store.

## Strengths
- Standard feature store open-source
- Online + offline serving cohérent
- Support vector features (Qdrant)
- Multi-backend flexible

## Limitations
- Setup et maintenance du store non triviaux
- Écosystème plus restreint que les solutions cloud (Vertex Feature Store, SageMaker)
- Pas de feature computation engine intégré

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Vertex AI Feature Store | GCP managed, plus intégré |
| SageMaker Feature Store | AWS managed |
| Tecton | Commercial, real-time feature engineering |
| Hopsworks | Feature store + ML platform |

## References
- https://docs.feast.dev
- https://github.com/feast-dev/feast

## Notes
Feast est le choix open-source par défaut pour les feature stores. Le support Qdrant pour les vector features est un ajout significatif pour les use cases RAG/embeddings.
