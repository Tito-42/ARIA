# Giskard

> Testing et monitoring de modèles ML/LLM — scan automatique de vulnérabilités, biais, performance.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 16 - AI Security & Safety / Testing & Monitoring |
| **URL** | https://giskard.ai |
| **GitHub** | https://github.com/Giskard-AI/giskard |
| **Stars** | ~5,200 |
| **License** | Apache 2.0 |
| **Pricing** | Free (OSS) / Giskard Hub (Paid) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Giskard fournit un scan automatique de vulnérabilités pour les modèles ML et LLM. Il détecte les biais, les failles de performance, les vulnérabilités de sécurité, et génère des rapports détaillés. Compatible CI/CD pour l'intégration dans les pipelines.

## Key Features
- **Scan automatique**: Détection automatique de vulnérabilités
- **ML + LLM**: Support modèles classiques et LLMs
- **Rapports détaillés**: Rapports HTML exploitables
- **CI/CD**: Intégration dans les pipelines
- **Biais detection**: Détection de biais dans les modèles
- **Apache 2.0**: Licence permissive

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Production, enterprise |
| **Security** | 4 | Apache 2.0 |
| **Scalability** | 3 | Self-hosted ou SaaS |
| **Support/Community** | 3 | 5.2k stars |
| **Documentation** | 4 | Docs complètes |
| **Integration Ease** | 4 | Python, CI/CD |

## Use Cases
1. **Model auditing** — Auditer les modèles ML/LLM pour biais et vulnérabilités
2. **CI/CD quality gates** — Bloquer les déploiements si vulnérabilités détectées
3. **Compliance** — Documenter la sécurité pour la conformité

## Getting Started
```python
import giskard
model = giskard.Model(my_model, model_type="classification")
dataset = giskard.Dataset(df, target="label")
scan_results = giskard.scan(model, dataset)
scan_results.to_html("report.html")
```

## Strengths
- Scan automatique innovant
- ML + LLM
- Apache 2.0
- Rapports détaillés

## Limitations
- Communauté modérée
- Setup initial peut être complexe

## Alternatives
| Tool | Key Difference |
|------|---------------|
| DeepEval | Plus populaire, focus LLM, pytest |
| Promptfoo | Focus prompts, red-teaming |

## References
- https://docs.giskard.ai
- https://github.com/Giskard-AI/giskard
