# Seldon Core

> Plateforme de déploiement ML sur Kubernetes — model serving, A/B testing, canary deployments. Attention: licence BSL.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 10 - Data Science & MLOps / Model Serving |
| **URL** | https://seldon.io |
| **GitHub** | https://github.com/SeldonIO/seldon-core |
| **Stars** | ~4,700 |
| **License** | BSL (Business Source License) |
| **Pricing** | BSL (gratuit sous conditions) / Seldon Enterprise (Paid) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Enterprise |

## What It Does
Seldon Core est une plateforme de déploiement de modèles ML sur Kubernetes. Elle fournit des fonctionnalités avancées de production ML : A/B testing, canary deployments, multi-armed bandits, model explanations (SHAP/Alibi), et monitoring de drift.

Seldon est passé à une licence BSL (Business Source License), ce qui restreint l'usage commercial — vérifier les implications légales avant adoption.

## Key Features
- **Kubernetes-natif**: SeldonDeployment CRD
- **A/B testing**: Comparaison de modèles en production
- **Canary deployments**: Déploiement progressif
- **Multi-armed bandits**: Routing intelligent
- **Explainability**: Intégration Alibi pour SHAP/LIME
- **Drift detection**: Monitoring de drift intégré

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Enterprise-grade, ML serving avancé |
| **Security** | 4 | K8s RBAC, mais **vérifier licence BSL** |
| **Scalability** | 4 | Kubernetes-natif, auto-scaling |
| **Support/Community** | 3 | 4.7k stars, support commercial |
| **Documentation** | 3 | Docs correctes |
| **Integration Ease** | 3 | Nécessite K8s, CRDs |

## Use Cases
1. **A/B testing ML** — Comparer des modèles en production avec traffic splitting
2. **Progressive rollout** — Canary deployments de modèles ML
3. **ML serving avancé** — Serving avec explainability et drift detection

## Getting Started
```yaml
apiVersion: machinelearning.seldon.io/v1
kind: SeldonDeployment
metadata:
  name: my-model
spec:
  predictors:
  - graph:
      implementation: SKLEARN_SERVER
      modelUri: gs://my-bucket/model
      name: classifier
    name: default
    replicas: 1
```

## Architecture / How It Works
Seldon Core s'exécute comme un opérateur Kubernetes qui gère des SeldonDeployment CRDs. Chaque déploiement crée un graphe de composants (model, transformer, combiner, router) orchestrés en pods K8s. Le router gère le traffic splitting pour A/B testing et canary.

## Strengths
- Fonctionnalités de production ML les plus avancées
- A/B testing et canary natifs
- Explainability intégrée
- Drift detection

## Limitations
- **Licence BSL — pas véritablement open-source pour usage commercial**
- Nécessite Kubernetes
- Complexité de setup
- KServe (gratuit, CNCF) est une alternative pour le serving basique

## Alternatives
| Tool | Key Difference |
|------|---------------|
| KServe | CNCF, Apache 2.0, serving standard K8s |
| BentoML | Python-first, plus simple, Apache 2.0 |
| Triton | NVIDIA, multi-framework, BSD-3 |
| vLLM | LLM-specific, plus performant |

## References
- https://docs.seldon.io
- https://github.com/SeldonIO/seldon-core

## Notes
**ALERTE LICENCE: BSL (Business Source License).** Vérifier avec le service juridique avant usage commercial. Pour du model serving standard sans contraintes de licence, KServe (Apache 2.0) ou BentoML sont des alternatives sûres.
