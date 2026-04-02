# Argo Workflows

> Moteur de workflows Kubernetes-natif — CNCF Graduated project pour pipelines containérisés.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 10 - Data Science & MLOps / Pipeline Orchestration |
| **URL** | https://argoproj.github.io/workflows |
| **GitHub** | https://github.com/argoproj/argo-workflows |
| **Stars** | ~16,600 |
| **License** | Apache 2.0 |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Argo Workflows est un moteur d'orchestration de workflows Kubernetes-natif, membre CNCF Graduated. Il permet de définir des pipelines ML et data comme des séquences de conteneurs orchestrés sur Kubernetes, avec support pour le parallélisme, les DAGs, les boucles et les conditions.

Argo est le choix standard pour les organisations Kubernetes-first qui veulent des pipelines entièrement containérisés et reproductibles.

## Key Features
- **Kubernetes-natif**: Chaque step = un pod K8s
- **CNCF Graduated**: Maturité et pérennité prouvées
- **DAG & Steps**: Orchestration par DAG ou séquence
- **Artifacts**: Passage d'artefacts entre steps via S3/GCS/Minio
- **Templates réutilisables**: WorkflowTemplates partagés
- **UI web**: Monitoring et visualisation des workflows

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | CNCF Graduated, enterprise-grade |
| **Security** | 5 | Kubernetes RBAC, service accounts, network policies |
| **Scalability** | 5 | Scalabilité native Kubernetes |
| **Support/Community** | 4 | 16.6k stars, CNCF, Intuit backing |
| **Documentation** | 4 | Docs CNCF complètes |
| **Integration Ease** | 3 | Nécessite Kubernetes, YAML verbose |

## Use Cases
1. **ML pipelines K8s** — Training distribué sur Kubernetes
2. **CI/CD ML** — Pipelines de build et déploiement de modèles
3. **Data processing** — ETL containérisé sur K8s

## Getting Started
```yaml
apiVersion: argoproj.io/v1alpha1
kind: Workflow
metadata:
  name: ml-pipeline
spec:
  entrypoint: train
  templates:
  - name: train
    container:
      image: my-ml-image:latest
      command: [python, train.py]
```
```bash
argo submit ml-pipeline.yaml
argo watch ml-pipeline
```

## Architecture / How It Works
Argo Workflows s'exécute comme un contrôleur Kubernetes qui crée et gère des pods pour chaque step du workflow. Les workflows sont définis en YAML (CRD Kubernetes) et orchestrés via le controller. Les artefacts sont stockés dans un object store (S3, GCS, Minio).

## Strengths
- Kubernetes-natif, isolation par conteneur
- CNCF Graduated = pérennité garantie
- Reproductibilité parfaite (conteneurs immuables)
- Scalabilité native K8s

## Limitations
- Nécessite un cluster Kubernetes
- YAML verbose pour des pipelines simples
- Pas de notion d'assets/data lineage natif

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Apache Airflow | Python-first, 500+ intégrations, pas K8s-natif |
| Prefect | Python-first, plus simple, pas K8s-required |
| Kubeflow Pipelines | ML-specific sur K8s, basé sur Argo |
| Tekton | CI/CD K8s-natif, focus build pipelines |

## References
- https://argoproj.github.io/workflows
- https://github.com/argoproj/argo-workflows

## Notes
Argo Workflows v4.0.3 est la version courante. Kubeflow Pipelines est construit sur Argo Workflows, ajoutant des abstractions ML-specific. Choisir Argo directement si le besoin va au-delà du ML.
