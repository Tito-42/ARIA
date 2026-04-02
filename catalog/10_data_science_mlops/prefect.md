# Prefect

> Orchestrateur de workflows Python-first — alternative moderne à Airflow avec une DX supérieure.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 10 - Data Science & MLOps / Pipeline Orchestration |
| **URL** | https://prefect.io |
| **GitHub** | https://github.com/PrefectHQ/prefect |
| **Stars** | ~22,000 |
| **License** | Apache 2.0 |
| **Pricing** | Free (OSS) / Prefect Cloud (Free tier + paid plans) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Prefect est un orchestrateur de workflows Python-first qui se positionne comme l'alternative moderne à Airflow. Il résout les frustrations courantes d'Airflow (setup complexe, DAGs verbeux) en offrant une API élégante basée sur des décorateurs Python simples.

Avec Prefect, n'importe quelle fonction Python peut devenir un flow orchestré en ajoutant un décorateur `@flow`. Le scheduling, le monitoring, les retries et les notifications sont gérés automatiquement.

## Key Features
- **Python-first**: Décorateurs `@flow` et `@task` sur des fonctions normales
- **Hybrid execution**: Code local + orchestration cloud
- **Dynamic workflows**: Pas besoin de DAG statique, flows dynamiques
- **Retries & caching**: Gestion automatique des erreurs et du cache
- **Prefect Cloud**: UI, scheduling, notifications, observabilité
- **Blocks**: Abstractions réutilisables pour connexions et configurations

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Production-ready, entreprises adoptantes |
| **Security** | 4 | Self-hosted ou Cloud, hybrid execution |
| **Scalability** | 4 | Workers distribués, Kubernetes support |
| **Support/Community** | 4 | 22k stars, Slack actif, support commercial |
| **Documentation** | 5 | Docs excellentes, tutoriels clairs |
| **Integration Ease** | 5 | Décorateur sur fonction existante = done |

## Use Cases
1. **ML pipelines modernes** — Orchestrer training, evaluation, deployment
2. **Data pipelines** — ETL/ELT avec une DX meilleure qu'Airflow
3. **Event-driven workflows** — Réagir à des événements en temps réel

## Getting Started
```python
from prefect import flow, task

@task
def extract():
    return [1, 2, 3]

@task
def transform(data):
    return [x * 2 for x in data]

@flow
def my_pipeline():
    data = extract()
    result = transform(data)
    print(result)

my_pipeline()
```

## Architecture / How It Works
Prefect sépare la définition des flows (code Python) de l'orchestration (Prefect Server/Cloud). Le code s'exécute sur vos workers (local, Docker, K8s), et Prefect Server gère le scheduling, le monitoring et les notifications. Le modèle hybride permet de garder les données en local tout en bénéficiant de l'orchestration cloud.

## Strengths
- DX supérieure à Airflow (Python natif, pas de DAG boilerplate)
- Dynamic workflows (pas de DAG statique)
- Démarrage en 5 minutes
- Model hybride local/cloud

## Limitations
- Moins d'intégrations qu'Airflow (500+)
- Écosystème moins mature pour les grandes entreprises
- Prefect Cloud nécessaire pour certaines features

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Apache Airflow | Standard industrie, 500+ intégrations, plus complexe |
| Dagster | Asset-centric, type-safety |
| Argo Workflows | Kubernetes-natif |

## References
- https://docs.prefect.io
- https://github.com/PrefectHQ/prefect

## Notes
Prefect v3.6.24 est la version courante. Excellent choix pour les nouvelles équipes qui veulent de l'orchestration sans la complexité d'Airflow. Airflow reste le choix pour les organisations qui ont besoin du maximum d'intégrations.
