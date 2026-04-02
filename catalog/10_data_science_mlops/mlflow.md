# MLflow

> Plateforme MLOps open-source standard de l'industrie — experiment tracking, model registry, serving et GenAI tracing.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 10 - Data Science & MLOps / Experiment Tracking |
| **URL** | https://mlflow.org |
| **GitHub** | https://github.com/mlflow/mlflow |
| **Stars** | ~25,000 |
| **License** | Apache 2.0 |
| **Pricing** | Free (OSS) / Databricks Managed MLflow (Paid) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Enterprise |

## What It Does
MLflow est la plateforme MLOps standard de l'industrie, utilisée par plus de 60M de téléchargements par mois. Il résout le problème du suivi, de la reproductibilité et du déploiement des modèles ML en offrant un tracking d'expériences, un model registry, du model serving, et depuis 2025-2026, du GenAI tracing.

MLflow se repositionne comme une "AI engineering platform" couvrant à la fois le ML classique et les applications GenAI/LLM, avec des fonctionnalités de tracing pour les agents et les pipelines RAG.

## Key Features
- **Experiment tracking**: Logging de paramètres, métriques, artefacts
- **Model registry**: Versioning et lifecycle management des modèles
- **MLflow Serving**: Déploiement REST de modèles
- **GenAI tracing**: Observabilité pour LLM apps, RAG, agents
- **Multi-framework**: PyTorch, TensorFlow, scikit-learn, HuggingFace, LangChain
- **Recipes**: Templates pour pipelines ML standards

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | Standard industrie, 60M+ téléchargements/mois |
| **Security** | 4 | Self-hosted, Apache 2.0, Databricks managed |
| **Scalability** | 4 | Backend SQL/blob storage, scalable horizontalement |
| **Support/Community** | 5 | Communauté massive, Databricks backing, 25k stars |
| **Documentation** | 5 | Docs excellentes, tutoriels nombreux |
| **Integration Ease** | 5 | 2 lignes de code pour démarrer le tracking |

## Use Cases
1. **Experiment tracking** — Comparer des runs d'entraînement, hyperparamètres, métriques
2. **Model registry** — Versionner, approuver et déployer des modèles
3. **GenAI observability** — Tracer les appels LLM, RAG, agents

## Getting Started
```python
import mlflow

mlflow.set_experiment("my-experiment")

with mlflow.start_run():
    mlflow.log_param("learning_rate", 0.01)
    mlflow.log_metric("accuracy", 0.95)
    mlflow.sklearn.log_model(model, "model")
```
```bash
# UI
mlflow ui --port 5000

# Serving
mlflow models serve -m "models:/my-model/1" --port 1234
```

## Architecture / How It Works
MLflow utilise un tracking server (backend SQL + artifact store) pour stocker les expériences. Le model registry gère les versions et les stages (Staging, Production, Archived). Le serving charge les modèles depuis le registry et les expose via REST. Le GenAI tracing instrumente les appels LLM avec OpenTelemetry.

## Strengths
- Standard industrie incontestable
- 60M+ téléchargements mensuels
- Très simple à démarrer (2 lignes de code)
- Repositionnement GenAI réussi

## Limitations
- UI moins moderne que Weights & Biases
- Peut être lourd pour des cas simples
- Databricks managed version a des features exclusives

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Weights & Biases | Meilleure UI, Weave pour GenAI, mais SaaS payant |
| ClearML | All-in-one plus complet (orchestration incluse) |
| Neptune.ai | UI collaborative, focus experiment tracking |

## References
- https://mlflow.org/docs/latest/
- https://github.com/mlflow/mlflow
- https://mlflow.org/docs/latest/llms/tracing/

## Notes
MLflow est le choix par défaut pour le ML experiment tracking. Son repositionnement comme "AI engineering platform" avec le GenAI tracing en fait un choix pertinent aussi pour les projets LLM. Intégration Databricks managed pour les grandes entreprises.
