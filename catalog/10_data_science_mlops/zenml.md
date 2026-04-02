# ZenML

> Framework MLOps extensible pour ML, LLM et agents — avec MCP Server natif pour Claude.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 10 - Data Science & MLOps / MLOps Framework |
| **URL** | https://zenml.io |
| **GitHub** | https://github.com/zenml-io/zenml |
| **Stars** | ~5,300 |
| **License** | Apache 2.0 |
| **Pricing** | Free (OSS) / ZenML Pro (Paid SaaS) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
ZenML est un framework MLOps extensible qui se distingue par son support natif de ML classique, LLM pipelines et agents AI. Il résout le problème de la fragmentation des outils MLOps en offrant une abstraction unifiée au-dessus de différentes stacks (MLflow, Kubeflow, Airflow, etc.).

L'innovation majeure de ZenML est son MCP Server natif, permettant une intégration directe avec Claude et d'autres LLMs via le Model Context Protocol. C'est le premier framework MLOps à intégrer nativement MCP.

## Key Features
- **Stack flexible**: Brancher MLflow, Kubeflow, Airflow, SageMaker, etc.
- **MCP Server natif**: Intégration Claude via Model Context Protocol
- **ML + LLM + Agents**: Support unifié des trois paradigmes
- **Pipeline as code**: Python-first avec décorateurs
- **Artifact versioning**: Tracking automatique des artefacts
- **Dashboard**: UI web pour monitoring

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Production-ready, stack enterprise |
| **Security** | 4 | Self-hosted, Apache 2.0, stack isolée |
| **Scalability** | 4 | Via les stacks sous-jacentes (K8s, cloud) |
| **Support/Community** | 3 | 5.3k stars, communauté en croissance |
| **Documentation** | 4 | Docs complètes, exemples nombreux |
| **Integration Ease** | 4 | Abstraction unifiée, mais stack setup initial |

## Use Cases
1. **MLOps unifiée** — Un framework pour ML classique + LLM + agents
2. **Claude integration** — Utiliser MCP Server pour connecter Claude à vos pipelines
3. **Stack migration** — Changer de backend (MLflow→W&B) sans changer le code

## Getting Started
```python
from zenml import step, pipeline

@step
def load_data() -> dict:
    return {"data": [1, 2, 3]}

@step
def train_model(data: dict) -> str:
    return "trained_model"

@pipeline
def ml_pipeline():
    data = load_data()
    model = train_model(data)

ml_pipeline()
```
```bash
pip install zenml
zenml init
zenml up  # Lance le dashboard
```

## Architecture / How It Works
ZenML utilise une architecture à stacks : chaque composant (orchestrator, artifact store, experiment tracker, model deployer) est pluggable. Le code pipeline reste identique, seule la stack change. Le ZenML Server gère les métadonnées, et le MCP Server permet aux LLMs d'interagir avec les pipelines.

## Strengths
- Abstraction unifiée ML + LLM + Agents
- MCP Server natif (unique dans le marché)
- Stack pluggable = pas de vendor lock-in
- Python-first, DX propre

## Limitations
- Communauté plus petite que MLflow ou Airflow
- Ajout d'une couche d'abstraction (overhead conceptuel)
- Certaines intégrations de stack moins matures

## Alternatives
| Tool | Key Difference |
|------|---------------|
| MLflow | Standard industrie, plus populaire, pas de MCP |
| Metaflow | Netflix-backed, plus mature, pas de LLM support |
| ClearML | All-in-one, pas de stack pluggable |

## References
- https://docs.zenml.io
- https://github.com/zenml-io/zenml

## Notes
ZenML est unique avec son MCP Server natif pour Claude. C'est un choix innovant pour les équipes qui veulent unifier ML classique et LLM/agents sous un même framework. Le risque est la taille de la communauté comparée aux alternatives.
