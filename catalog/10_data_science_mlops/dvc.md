# DVC (Data Version Control)

> Versioning de données et pipelines ML, Git-native avec remote storage flexible.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 10 - Data Science & MLOps / Data & Pipeline Management |
| **URL** | https://dvc.org |
| **GitHub** | https://github.com/iterative/dvc |
| **Stars** | ~15,500 |
| **License** | Apache 2.0 |
| **Pricing** | Free (OSS) / Iterative Studio (Paid SaaS) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
DVC (Data Version Control) étend Git au versioning de données et de modèles ML. Il résout le problème du tracking de fichiers volumineux (datasets, modèles) en stockant les métadonnées dans Git et les données dans un remote storage (S3, GCS, Azure Blob, SSH, etc.).

DVC permet aussi de définir des pipelines ML reproductibles sous forme de DAGs, avec caching intelligent pour ne ré-exécuter que les steps qui ont changé.

## Key Features
- **Data versioning**: Git pour les données — diff, branch, merge
- **Remote storage**: S3, GCS, Azure, SSH, HDFS, et plus
- **Pipelines**: DAGs ML reproductibles avec caching
- **Experiments**: Comparaison d'expériences basée sur Git
- **Metrics tracking**: Métriques versionnées avec Git
- **CLI simple**: Commandes similaires à Git

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Production, utilisé en enterprise |
| **Security** | 4 | Données sur votre storage, pas de SaaS requis |
| **Scalability** | 3 | Dépend du remote storage, pas distribué nativement |
| **Support/Community** | 4 | 15.5k stars, Iterative backing, communauté active |
| **Documentation** | 5 | Docs excellentes, tutoriels interactifs |
| **Integration Ease** | 5 | Git-native, CLI intuitive |

## Use Cases
1. **Dataset versioning** — Tracker les versions de datasets avec Git
2. **ML reproducibility** — Pipelines reproductibles avec caching
3. **Model versioning** — Versionner les modèles avec les expériences

## Getting Started
```bash
pip install dvc
dvc init
dvc remote add -d myremote s3://my-bucket/dvc

# Tracker un dataset
dvc add data/dataset.csv
git add data/dataset.csv.dvc .gitignore
git commit -m "Add dataset v1"
dvc push
```

## Architecture / How It Works
DVC stocke des fichiers `.dvc` (pointeurs) dans Git et les données réelles dans un remote storage. Les pipelines sont définis dans `dvc.yaml` comme des stages avec inputs/outputs. Le DAG permet le caching : si les inputs n'ont pas changé, le stage est skipé. `dvc repro` reproduit le pipeline complet.

## Strengths
- Git-native, courbe d'apprentissage minimale
- Remote storage flexible (votre infra)
- Pipelines reproductibles avec caching intelligent
- CLI similaire à Git

## Limitations
- Limité pour l'orchestration complexe (pas un scheduler)
- Pas de UI native (Iterative Studio est payant)
- Mono-repo oriented

## Alternatives
| Tool | Key Difference |
|------|---------------|
| MLflow | Plus complet (tracking + serving), mais data versioning limité |
| Git LFS | Plus simple, mais pas de pipelines ML |
| Pachyderm | Data lineage + pipelines, plus complexe |
| lakeFS | Git-like pour data lakes, focus data engineering |

## References
- https://dvc.org/doc
- https://github.com/iterative/dvc

## Notes
DVC v3.67.1 (31/03/2026). Excellent choix pour ajouter du data versioning à un workflow Git existant. Se combine bien avec MLflow pour le tracking d'expériences.
