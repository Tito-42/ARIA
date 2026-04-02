# Metaflow

> Framework ML par Netflix — Python-first, orienté data science, prouvé sur 3000+ projets internes.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 10 - Data Science & MLOps / ML Framework |
| **URL** | https://metaflow.org |
| **GitHub** | https://github.com/Netflix/metaflow |
| **Stars** | ~10,000 |
| **License** | Apache 2.0 |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Metaflow est un framework ML développé par Netflix et open-sourcé, utilisé en interne sur plus de 3000 projets. Il permet aux data scientists d'écrire des pipelines ML en Python pur, sans se soucier de l'infrastructure, du scaling, ou du versioning.

Metaflow gère automatiquement le snapshot des données, le versioning du code, le scaling cloud (AWS/Azure), et les dépendances. Il est conçu pour que le code de prototypage local devienne du code de production sans modification.

## Key Features
- **Python-first**: Décorateur `@step` sur des méthodes Python
- **Auto-versioning**: Chaque run est versionné automatiquement
- **Cloud scaling**: `@batch` / `@kubernetes` pour scaler
- **Data management**: Snapshot automatique des données entre steps
- **Résumé client**: API client pour explorer les résultats passés
- **Multi-cloud**: AWS Step Functions, Azure, Kubernetes

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | Netflix-prouvé, 3000+ projets internes |
| **Security** | 4 | Self-hosted, Apache 2.0, data dans votre infra |
| **Scalability** | 4 | Cloud-native, AWS Batch/K8s/Azure |
| **Support/Community** | 3 | 10k stars, Netflix backing, Slack actif |
| **Documentation** | 5 | Docs excellentes, tutoriels progressifs |
| **Integration Ease** | 5 | Python pur, DX exceptionnelle |

## Use Cases
1. **ML R&D to production** — Même code du notebook à la production
2. **Data science workflows** — Pipelines avec auto-versioning et data management
3. **Cloud scaling** — Scaler du local vers AWS/Azure sans refactoring

## Getting Started
```python
from metaflow import FlowSpec, step

class TrainFlow(FlowSpec):
    @step
    def start(self):
        self.data = [1, 2, 3]
        self.next(self.train)
    
    @step
    def train(self):
        self.model = sum(self.data)
        self.next(self.end)
    
    @step
    def end(self):
        print(f"Model: {self.model}")

if __name__ == "__main__":
    TrainFlow()
```
```bash
python train_flow.py run
```

## Architecture / How It Works
Metaflow utilise un datastore (S3/Azure Blob) pour persister les données entre steps et un metadata service pour le versioning. Chaque step est un snapshot complet (code + données). Le décorateur `@batch` ou `@kubernetes` permet d'exécuter un step sur le cloud sans changer le code. Le client Metaflow permet d'explorer et requêter les runs passés.

## Strengths
- DX exceptionnelle, conçue par et pour les data scientists
- Netflix-prouvé à grande échelle
- Auto-versioning de tout (code + données + environnement)
- Transition local→cloud transparente

## Limitations
- Historiquement AWS-centric (Azure support plus récent)
- Moins d'intégrations que Airflow
- Pas d'UI native riche (Metaflow UI existe mais basique)

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Prefect | Orchestration générale, pas ML-specific |
| Dagster | Asset-centric, UI riche |
| ZenML | ML + LLM + Agents, stack flexible |
| Apache Airflow | Standard industrie, plus généraliste |

## References
- https://docs.metaflow.org
- https://github.com/Netflix/metaflow
- https://outerbounds.com (société derrière Metaflow)

## Notes
Metaflow est un excellent choix pour les équipes data science qui veulent le minimum de friction entre le prototypage et la production. Le backing Netflix garantit la pérennité et la qualité.
