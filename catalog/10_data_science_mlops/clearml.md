# ClearML

> Suite MLOps all-in-one open-source — experiment tracking, orchestration, data management et serving.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 10 - Data Science & MLOps / MLOps Platform |
| **URL** | https://clear.ml |
| **GitHub** | https://github.com/allegroai/clearml |
| **Stars** | ~6,600 |
| **License** | Apache 2.0 |
| **Pricing** | Free (OSS) / ClearML Pro (Hosted) / Enterprise |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
ClearML est la suite MLOps all-in-one la plus complète en open-source. Elle regroupe en une seule plateforme l'experiment tracking, l'orchestration de pipelines, la gestion de données, le scheduling d'agents de calcul, et le model serving.

Contrairement à MLflow ou W&B qui se focalisent sur le tracking, ClearML couvre l'ensemble du lifecycle ML avec un self-hosted complet, ce qui en fait un choix populaire pour les organisations qui veulent tout contrôler on-premise.

## Key Features
- **Experiment tracking**: Auto-logging, comparaison, reproduction
- **Orchestration**: Pipelines, scheduling d'agents, queues
- **Data management**: Versioning de datasets, caching
- **ClearML Agent**: Workers distribués pour l'entraînement
- **Model serving**: Déploiement et serving intégrés
- **Hyper-Datasets**: Gestion avancée de datasets multi-modaux

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Production-ready, utilisé en enterprise |
| **Security** | 5 | Self-hosted complet, Apache 2.0, on-premise |
| **Scalability** | 4 | Agents distribués, Kubernetes support |
| **Support/Community** | 3 | 6.6k stars, communauté plus petite mais active |
| **Documentation** | 4 | Docs complètes, exemples nombreux |
| **Integration Ease** | 4 | Auto-logging réduit le code nécessaire |

## Use Cases
1. **MLOps on-premise** — Suite complète self-hosted pour organisations sécurisées
2. **Pipeline orchestration** — Orchestrer entraînement distribué avec agents
3. **All-in-one** — Remplacer plusieurs outils (MLflow + Airflow + DVC) par un seul

## Getting Started
```python
from clearml import Task

task = Task.init(project_name="my-project", task_name="my-experiment")
task.connect({"learning_rate": 0.01, "epochs": 10})

# Auto-logging PyTorch/TensorFlow/scikit-learn est automatique
```
```bash
# Lancer un agent worker
clearml-agent daemon --queue default
```

## Architecture / How It Works
ClearML Server (Elasticsearch + MongoDB + Redis + FileServer) stocke les expériences et artefacts. Les ClearML Agents sont des workers qui consomment des tâches depuis des queues. Le SDK Python instrumente automatiquement les frameworks ML pour le logging.

## Strengths
- Suite all-in-one la plus complète en open-source
- Self-hosted complet, idéal pour on-premise
- Auto-logging minimise le code de tracking
- Agent scheduling pour compute distribué

## Limitations
- Communauté plus petite que MLflow ou W&B
- UI moins polish que W&B
- Nécessite plus de maintenance que les solutions SaaS

## Alternatives
| Tool | Key Difference |
|------|---------------|
| MLflow | Plus populaire, standard industrie, moins complet en orchestration |
| W&B | Meilleure UI, SaaS, plus cher |
| Kubeflow | Full platform K8s, plus complexe |

## References
- https://clear.ml/docs
- https://github.com/allegroai/clearml

## Notes
ClearML est le meilleur choix pour les organisations qui veulent une suite MLOps complète self-hosted. Si l'UI est prioritaire, W&B est meilleur. Si le standard industrie est important, MLflow est plus adopté.
