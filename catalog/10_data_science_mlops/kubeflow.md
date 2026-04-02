# Kubeflow

> Plateforme ML complète sur Kubernetes — pipelines, notebooks, training distribué et serving.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 10 - Data Science & MLOps / ML Platform |
| **URL** | https://www.kubeflow.org |
| **GitHub** | https://github.com/kubeflow/kubeflow |
| **Stars** | ~15,500 |
| **License** | Apache 2.0 |
| **Pricing** | Free (OSS) / Managed: AWS, GCP, Azure offerings |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Enterprise |

## What It Does
Kubeflow est une plateforme ML end-to-end sur Kubernetes. Elle fournit tout le lifecycle ML : notebooks Jupyter, pipelines d'entraînement (basés sur Argo Workflows), training distribué (PyTorch, TensorFlow), hyperparameter tuning (Katib), et model serving (KServe).

Kubeflow est le choix standard pour les grandes organisations Kubernetes-first qui veulent une plateforme ML unifiée, à la place de multiples outils disparates.

## Key Features
- **Kubeflow Pipelines**: Orchestration ML sur K8s (basé sur Argo)
- **Kubeflow Notebooks**: Jupyter sur K8s avec GPU
- **Training Operators**: PyTorch, TensorFlow, MPI distribué
- **Katib**: Hyperparameter tuning automatisé
- **KServe**: Model serving avec auto-scaling
- **Multi-tenancy**: Isolation par namespace K8s

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Enterprise, utilisé par les grandes organisations |
| **Security** | 5 | K8s RBAC, multi-tenancy, network policies |
| **Scalability** | 5 | Kubernetes-natif, scaling illimité |
| **Support/Community** | 4 | 15.5k stars, Google backing, CNCF ecosystem |
| **Documentation** | 3 | Docs existantes mais parfois fragmentées |
| **Integration Ease** | 2 | Complexe à installer et opérer |

## Use Cases
1. **ML platform enterprise** — Plateforme ML centralisée pour l'organisation
2. **Training distribué** — PyTorch/TF distribué sur GPU clusters
3. **Model serving** — Déploiement avec auto-scaling via KServe

## Getting Started
```bash
# Installation via kustomize
kubectl apply -k "github.com/kubeflow/manifests//example?ref=v1.9"
```

## Architecture / How It Works
Kubeflow est un ensemble de composants déployés sur Kubernetes : un portail web central, Jupyter notebook servers, un pipeline engine (Argo), des training operators (CRDs K8s pour jobs distribués), Katib (controller hyperparameter tuning), et KServe (model serving avec InferenceService CRD).

## Strengths
- Plateforme ML complète end-to-end
- Kubernetes-natif, multi-tenant
- Training distribué natif
- Managed offerings sur tous les clouds

## Limitations
- Très complexe à installer et opérer
- Cycles de release lents (annuels)
- Courbe d'apprentissage abrupte
- Requires K8s expertise

## Alternatives
| Tool | Key Difference |
|------|---------------|
| MLflow + Airflow | Plus modulaire, plus simple séparément |
| ClearML | All-in-one plus simple, pas K8s required |
| SageMaker | AWS managed, pas open-source |

## References
- https://www.kubeflow.org/docs
- https://github.com/kubeflow/kubeflow

## Notes
Dernier release majeur mars 2025. Kubeflow reste le choix pour les organisations K8s-first qui veulent une plateforme unifiée. Pour des besoins plus ciblés, une combinaison MLflow + Airflow + vLLM est souvent plus pragmatique.
