# Apache Airflow

> Standard de l'industrie pour l'orchestration de workflows data et ML — DAGs Python, 500+ intégrations.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 10 - Data Science & MLOps / Pipeline Orchestration |
| **URL** | https://airflow.apache.org |
| **GitHub** | https://github.com/apache/airflow |
| **Stars** | ~44,800 |
| **License** | Apache 2.0 |
| **Pricing** | Free (OSS) / Managed: Astronomer, GCP Composer, AWS MWAA |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Enterprise |

## What It Does
Apache Airflow est le standard de l'industrie pour l'orchestration de workflows data et ML. Développé initialement par Airbnb et maintenu par l'Apache Foundation, il permet de définir des pipelines (DAGs) en Python avec scheduling, monitoring, et plus de 500 intégrations (AWS, GCP, Azure, Spark, dbt, etc.).

Airflow est le choix par défaut pour les data teams et ML teams qui ont besoin d'orchestrer des pipelines complexes avec des dépendances, des retries, et du monitoring.

## Key Features
- **DAGs Python**: Définition de workflows en code Python
- **500+ providers**: Intégrations AWS, GCP, Azure, Spark, dbt, Kubernetes, etc.
- **Scheduler**: Cron-based + event-driven scheduling
- **UI web**: Monitoring, logs, retries, backfills
- **TaskFlow API**: API moderne et simplifiée (Airflow 2+)
- **Kubernetes Executor**: Exécution sur K8s natif

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | Standard industrie, Apache Foundation |
| **Security** | 5 | RBAC, connections chiffrées, audit trail |
| **Scalability** | 5 | Celery, Kubernetes, multi-tenant |
| **Support/Community** | 5 | 44.8k stars, Apache Foundation, massive community |
| **Documentation** | 5 | Docs exhaustives, écosystème de cours |
| **Integration Ease** | 3 | Setup initial non trivial, courbe d'apprentissage |

## Use Cases
1. **ETL/ELT pipelines** — Orchestrer l'ingestion et transformation de données
2. **ML training pipelines** — Scheduler des entraînements avec dépendances
3. **Data platform** — Hub central d'orchestration pour toutes les équipes data

## Getting Started
```python
from airflow.decorators import dag, task
from datetime import datetime

@dag(schedule="@daily", start_date=datetime(2026, 1, 1))
def ml_pipeline():
    @task
    def extract(): return {"data": "raw"}
    
    @task
    def transform(data): return {"data": "processed"}
    
    @task
    def train(data): return {"model": "trained"}
    
    train(transform(extract()))

ml_pipeline()
```

## Architecture / How It Works
Airflow se compose d'un Scheduler (planification des DAGs), d'un Web Server (UI), d'un Metadata DB (PostgreSQL/MySQL), et d'Executors (Local, Celery, Kubernetes). Le scheduler parse les DAGs Python, planifie les tâches, et les distribue aux workers via l'executor choisi.

## Strengths
- Standard industrie incontestable, 44.8k stars
- 500+ intégrations couvrant tout l'écosystème data
- Apache Foundation = pérennité garantie
- Managed services disponibles (Astronomer, GCP Composer, AWS MWAA)

## Limitations
- Setup initial complexe
- DAGs Python peuvent devenir verbeux pour des pipelines simples
- Pas spécifiquement conçu pour le ML (pas de data lineage natif)

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Prefect | Python-first, plus simple, meilleure DX |
| Dagster | Asset-centric, type-safety, UI moderne |
| Argo Workflows | Kubernetes-natif, containerisé |
| Metaflow | Netflix, orienté data science |

## References
- https://airflow.apache.org/docs/
- https://github.com/apache/airflow

## Notes
Airflow v3.1.8 est la version stable courante. C'est le choix par défaut pour l'orchestration data/ML en enterprise. Prefect et Dagster gagnent du terrain comme alternatives plus modernes pour les nouvelles équipes.
