# Evidently AI

> Monitoring de modèles ML et LLM — détection de drift, métriques de performance, rapports visuels.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 10 - Data Science & MLOps / Model Monitoring |
| **URL** | https://evidentlyai.com |
| **GitHub** | https://github.com/evidentlyai/evidently |
| **Stars** | ~7,400 |
| **License** | Apache 2.0 |
| **Pricing** | Free (OSS) / Evidently Cloud (Paid) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Evidently AI est une plateforme de monitoring pour les modèles ML et LLM en production. Elle détecte automatiquement le data drift, le concept drift, et la dégradation de performance des modèles. Depuis 2025, Evidently étend ses capacités au monitoring des applications LLM (qualité des réponses, hallucinations, toxicité).

Evidently génère des rapports visuels interactifs et peut s'intégrer dans les pipelines CI/CD pour bloquer les déploiements si la qualité se dégrade.

## Key Features
- **Data drift detection**: Détection statistique du changement de distribution
- **Model performance**: Suivi de métriques ML (accuracy, AUC, etc.)
- **LLM monitoring**: Qualité des réponses, toxicité, hallucinations
- **Rapports visuels**: HTML interactifs ou dashboard
- **Test suites**: Tests automatisés dans CI/CD
- **Real-time monitoring**: Dashboard temps réel

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Production, utilisé en enterprise |
| **Security** | 4 | Self-hosted, Apache 2.0 |
| **Scalability** | 3 | Bon pour volumes modérés, Evidently Cloud pour scale |
| **Support/Community** | 4 | 7.4k stars, communauté active |
| **Documentation** | 4 | Docs complètes, exemples Jupyter |
| **Integration Ease** | 4 | Python-first, rapports en 3 lignes |

## Use Cases
1. **ML monitoring** — Détecter la dégradation des modèles en production
2. **LLM quality** — Monitorer la qualité des réponses LLM
3. **CI/CD quality gates** — Bloquer les déploiements si drift détecté

## Getting Started
```python
from evidently.report import Report
from evidently.metric_preset import DataDriftPreset

report = Report(metrics=[DataDriftPreset()])
report.run(reference_data=train_df, current_data=prod_df)
report.save_html("drift_report.html")
```

## Architecture / How It Works
Evidently calcule des métriques statistiques (KS test, PSI, Wasserstein distance) entre les données de référence et les données courantes. Les rapports sont générés en HTML ou envoyés à un monitoring service. Le dashboard temps réel utilise une base de données pour stocker les métriques.

## Strengths
- ML + LLM monitoring dans un outil
- Rapports visuels interactifs
- Apache 2.0, self-hosted
- CI/CD integration native

## Limitations
- Features avancées payantes (Evidently Cloud)
- Scaling limité en self-hosted pour gros volumes
- LLM monitoring encore en maturation

## Alternatives
| Tool | Key Difference |
|------|---------------|
| W&B Weave | Focus GenAI, UI premium, payant |
| Great Expectations | Focus data quality en amont, pas monitoring |
| Arize AI | Monitoring ML commercial, plus complet |
| WhyLabs | Monitoring ML SaaS |

## References
- https://docs.evidentlyai.com
- https://github.com/evidentlyai/evidently

## Notes
Evidently v0.7.21 courante. Excellent complément à Great Expectations : GX valide en amont, Evidently monitore en production. L'extension au monitoring LLM en fait un outil de plus en plus pertinent.
