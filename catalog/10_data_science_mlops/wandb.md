# Weights & Biases (W&B)

> Plateforme d'experiment tracking et MLOps premium avec la meilleure UI du marché et Weave pour GenAI observabilité.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 10 - Data Science & MLOps / Experiment Tracking |
| **URL** | https://wandb.ai |
| **GitHub** | https://github.com/wandb/wandb |
| **Stars** | ~10,900 |
| **License** | MIT |
| **Pricing** | Free (personal) / Team ($50/user/mo) / Enterprise (custom) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Enterprise |

## What It Does
Weights & Biases est la plateforme de référence pour l'experiment tracking avec la meilleure interface utilisateur du marché. Au-delà du tracking classique (métriques, hyperparamètres, artefacts), W&B a lancé Weave, une plateforme d'observabilité spécifiquement conçue pour les applications GenAI/LLM.

W&B sert de hub centralisé pour les équipes ML/AI avec des fonctionnalités collaboratives (rapports, discussions), des Sweeps pour l'optimisation d'hyperparamètres, et des intégrations avec tous les frameworks majeurs.

## Key Features
- **Experiment tracking**: UI la plus complète et intuitive du marché
- **Weave**: Observabilité GenAI — tracing LLM, évaluation, monitoring
- **Sweeps**: Optimisation d'hyperparamètres automatisée
- **Artifacts**: Versioning de datasets et modèles
- **Reports**: Rapports collaboratifs intégrés
- **Model Registry**: Lifecycle management

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | Enterprise-grade, utilisé par les plus grandes entreprises |
| **Security** | 4 | SaaS ou self-hosted, SOC 2, SSO |
| **Scalability** | 5 | Cloud-native, conçu pour la scale |
| **Support/Community** | 5 | Support enterprise, communauté active, 10.9k stars |
| **Documentation** | 5 | Docs excellentes, tutoriels vidéo, cours |
| **Integration Ease** | 5 | 5 lignes de code pour intégrer |

## Use Cases
1. **Experiment tracking équipe** — Collaboration ML avec UI premium
2. **GenAI observability** — Tracer et évaluer les applications LLM avec Weave
3. **Hyperparameter optimization** — Sweeps automatisés

## Getting Started
```python
import wandb

wandb.init(project="my-project")
wandb.log({"loss": 0.5, "accuracy": 0.9})

# Weave pour GenAI
import weave
weave.init("my-llm-app")
```

## Architecture / How It Works
W&B utilise un agent léger (SDK Python) qui envoie les métriques au backend cloud (ou self-hosted). L'UI web affiche les dashboards, comparaisons et rapports. Weave instrumente les appels LLM et fournit un pipeline d'évaluation end-to-end.

## Strengths
- Meilleure UI d'experiment tracking du marché
- Weave pour GenAI est très complète
- Collaboration équipe native
- Sweeps pour hyperparameter tuning

## Limitations
- SaaS payant pour les équipes ($50/user/mois)
- Vendor lock-in possible (migration coûteuse)
- Self-hosted moins mainstream que la version cloud

## Alternatives
| Tool | Key Difference |
|------|---------------|
| MLflow | Open-source gratuit, standard industrie, moins beau UI |
| ClearML | Open-source, all-in-one, self-hosted |
| Neptune.ai | Focus collaboration, pricing différent |

## References
- https://docs.wandb.ai
- https://github.com/wandb/wandb
- https://weave-docs.wandb.ai

## Notes
W&B est le choix premium pour les équipes qui valorisent l'UI et la collaboration. MLflow est l'alternative gratuite. Weave positionne W&B comme leader sur l'observabilité GenAI. Évaluer le coût par rapport à MLflow self-hosted pour les grandes équipes.
