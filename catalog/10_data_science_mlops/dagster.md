# Dagster

> Orchestrateur asset-centric pour data pipelines — software-defined assets avec UI excellente.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 10 - Data Science & MLOps / Pipeline Orchestration |
| **URL** | https://dagster.io |
| **GitHub** | https://github.com/dagster-io/dagster |
| **Stars** | ~15,200 |
| **License** | Apache 2.0 |
| **Pricing** | Free (OSS) / Dagster Cloud (Paid) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Dagster est un orchestrateur data qui introduit le paradigme "asset-centric" : au lieu de définir des tâches (comme Airflow), on définit des assets (tables, fichiers, modèles) et leurs dépendances. Dagster orchestre automatiquement la matérialisation de ces assets.

Cette approche résout des problèmes classiques d'Airflow : pas de notion de données, pas de lineage natif, pas de type-safety. Dagster fournit un data lineage automatique, une UI de qualité, et une DX Python-first avec type-checking.

## Key Features
- **Software-defined assets**: Assets comme citoyens de première classe
- **Data lineage**: Lineage automatique basé sur les dépendances d'assets
- **Type system**: Types d'entrée/sortie vérifiés
- **Partitions**: Gestion native du partitioning temporel/catégoriel
- **Sensors & Schedules**: Event-driven et time-based triggers
- **UI Dagit**: Interface web moderne et intuitive

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Production, adopté par des entreprises majeures |
| **Security** | 4 | Self-hosted ou Dagster Cloud, Apache 2.0 |
| **Scalability** | 4 | Kubernetes executor, multi-code-locations |
| **Support/Community** | 4 | 15.2k stars, Slack actif, support commercial |
| **Documentation** | 5 | Docs excellentes, tutoriels interactifs |
| **Integration Ease** | 4 | Python-first mais paradigme nouveau à apprendre |

## Use Cases
1. **Data platform** — Orchestration asset-centric avec lineage automatique
2. **ML pipelines** — Orchestrer training avec partitions et type-safety
3. **Modern data stack** — Remplacer Airflow avec une approche plus moderne

## Getting Started
```python
from dagster import asset, Definitions

@asset
def raw_data():
    return [1, 2, 3, 4, 5]

@asset
def processed_data(raw_data):
    return [x * 2 for x in raw_data]

defs = Definitions(assets=[raw_data, processed_data])
```
```bash
pip install dagster dagster-webserver
dagster dev  # Lance l'UI sur localhost:3000
```

## Architecture / How It Works
Dagster utilise un graphe d'assets pour déterminer l'ordre de matérialisation. Le Dagster Daemon gère le scheduling et les sensors. Les assets sont matérialisés par des executors (local, multi-process, Kubernetes). L'UI Dagit affiche le lineage, les runs, et l'état des assets en temps réel.

## Strengths
- Paradigme asset-centric innovant et puissant
- Data lineage automatique
- UI Dagit excellente
- Type-safety et testing natifs

## Limitations
- Paradigme différent = courbe d'apprentissage
- Moins d'intégrations qu'Airflow
- Migration depuis Airflow non triviale

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Apache Airflow | Standard industrie, task-centric, 500+ intégrations |
| Prefect | Python-first, task-centric, plus simple |
| dbt | Asset-centric pour SQL, complémentaire |

## References
- https://docs.dagster.io
- https://github.com/dagster-io/dagster

## Notes
Dagster v1.12.21 courante. Excellent choix pour les nouvelles data platforms. L'approche asset-centric est un changement de paradigme qui demande un investissement initial mais améliore significativement la maintenabilité.
