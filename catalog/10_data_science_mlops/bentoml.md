# BentoML

> Framework pour packager et déployer des modèles ML/LLM en production avec monitoring intégré.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 10 - Data Science & MLOps / Model Serving |
| **URL** | https://bentoml.com |
| **GitHub** | https://github.com/bentoml/BentoML |
| **Stars** | ~8,600 |
| **License** | Apache 2.0 |
| **Pricing** | Free (OSS) / BentoCloud (Paid SaaS) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
BentoML est un framework Python pour packager, déployer et monitorer des modèles ML/LLM. Il résout le problème du passage du notebook à la production en offrant un format de packaging standardisé ("Bento"), un serving performant, et un déploiement multi-cloud.

Le framework supporte tous les frameworks ML (PyTorch, TensorFlow, scikit-learn, XGBoost) et s'étend aux LLMs. BentoCloud offre un déploiement managé pour les équipes qui ne veulent pas gérer l'infrastructure.

## Key Features
- **Bento packaging**: Format standardisé pour modèles + code + dépendances
- **Multi-framework**: PyTorch, TensorFlow, scikit-learn, XGBoost, LLMs
- **Adaptive batching**: Optimisation automatique du batching
- **BentoCloud**: Déploiement cloud managé
- **Monitoring**: Métriques et observabilité intégrées
- **GPU support**: Allocation GPU configurable

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Production-ready, utilisé en enterprise |
| **Security** | 4 | Self-hosted ou BentoCloud, Apache 2.0 |
| **Scalability** | 4 | Auto-scaling via BentoCloud, Kubernetes support |
| **Support/Community** | 3 | 8.6k stars, communauté active, support commercial |
| **Documentation** | 4 | Docs complètes, tutoriels nombreux |
| **Integration Ease** | 4 | Python-first, décorateurs simples |

## Use Cases
1. **ML model serving** — Déployer des modèles scikit-learn/PyTorch en production
2. **LLM deployment** — Packager et servir des LLMs avec monitoring
3. **Multi-model pipelines** — Composer des services avec plusieurs modèles

## Getting Started
```python
import bentoml

@bentoml.service
class MyService:
    def __init__(self):
        self.model = bentoml.pytorch.load_model("my_model:latest")
    
    @bentoml.api
    def predict(self, input_data: dict) -> dict:
        return self.model(input_data)
```
```bash
bentoml serve MyService:latest
bentoml build
bentoml push my_service:latest  # vers BentoCloud
```

## Architecture / How It Works
BentoML utilise des décorateurs Python pour définir des services ML. Le build créé un "Bento" (archive contenant modèle, code, dépendances, Dockerfile). Le runtime BentoML gère le serving HTTP/gRPC, l'adaptive batching, et le monitoring. BentoCloud ajoute l'orchestration Kubernetes et l'auto-scaling.

## Strengths
- Packaging standardisé simplifiant le déploiement
- Python-first, DX agréable
- Multi-framework polyvalent
- BentoCloud pour managed deployment

## Limitations
- Écosystème plus petit que MLflow
- BentoCloud payant pour les features avancées
- Moins spécialisé LLM que vLLM/SGLang

## Alternatives
| Tool | Key Difference |
|------|---------------|
| MLflow | Plus complet (tracking + registry + serving), standard industrie |
| Triton | Multi-framework enterprise NVIDIA, plus performant |
| vLLM | Spécialisé LLM, meilleur throughput |
| Seldon Core | Kubernetes-natif, A/B testing |

## References
- https://docs.bentoml.com
- https://github.com/bentoml/BentoML
- https://bentoml.com/cloud

## Notes
BentoML est un bon choix pour les équipes qui ont besoin d'un framework de packaging et déploiement polyvalent. Pour du LLM-only, vLLM est plus performant. Pour du tracking complet, MLflow est plus complet.
