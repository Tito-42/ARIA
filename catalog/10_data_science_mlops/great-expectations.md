# Great Expectations

> Framework de validation et documentation de données — tests de qualité automatisés pour data pipelines.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 10 - Data Science & MLOps / Data Quality |
| **URL** | https://greatexpectations.io |
| **GitHub** | https://github.com/great-expectations/great_expectations |
| **Stars** | ~11,300 |
| **License** | Apache 2.0 |
| **Pricing** | Free (OSS) / GX Cloud (Paid SaaS) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Great Expectations (GX) est le framework standard pour la validation de données dans les pipelines ML et data. Il permet de définir des "expectations" (assertions) sur les données (colonnes non nulles, valeurs dans une plage, distributions statistiques) et de les exécuter automatiquement dans les pipelines.

GX génère aussi de la documentation automatique (Data Docs) sous forme de pages HTML, créant un contrat de données vivant.

## Key Features
- **Expectations**: 300+ validations prédéfinies
- **Data Docs**: Documentation HTML auto-générée
- **Profiling**: Analyse automatique de datasets
- **Multi-source**: Pandas, Spark, SQL databases
- **CI/CD**: Intégration dans les pipelines CI/CD
- **Checkpoints**: Orchestration de validations

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Standard data quality, production |
| **Security** | 4 | Self-hosted, Apache 2.0 |
| **Scalability** | 4 | Spark support pour gros volumes |
| **Support/Community** | 4 | 11.3k stars, communauté active |
| **Documentation** | 4 | Docs complètes, tutoriels |
| **Integration Ease** | 3 | Configuration initiale verbose |

## Use Cases
1. **Data validation** — Valider les données d'entrée des modèles ML
2. **Data contracts** — Documenter et enforcer les contrats de données
3. **Pipeline quality gates** — Bloquer les pipelines si les données sont invalides

## Getting Started
```python
import great_expectations as gx

context = gx.get_context()
datasource = context.data_sources.add_pandas("my_ds")

# Définir des expectations
suite = context.suites.add(gx.ExpectationSuite(name="my_suite"))
suite.add_expectation(gx.expectations.ExpectColumnValuesToNotBeNull(column="id"))
suite.add_expectation(gx.expectations.ExpectColumnValuesToBeBetween(
    column="age", min_value=0, max_value=150
))
```

## Architecture / How It Works
GX fonctionne avec un Data Context (configuration), des Datasources (connexions aux données), des Expectation Suites (collections de validations), et des Checkpoints (exécution de suites contre des données). Les résultats sont rendus en Data Docs (HTML statique).

## Strengths
- Standard data quality en Python
- 300+ expectations prédéfinies
- Documentation auto-générée
- Multi-source (Pandas, Spark, SQL)

## Limitations
- Configuration initiale verbose et complexe
- API a changé entre versions (breaking changes)
- Pas de monitoring temps réel natif

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Evidently AI | Focus monitoring ML/LLM, drift detection |
| Pandera | Plus léger, pandas-focused, type annotations |
| dbt tests | SQL-based, intégré dans dbt |

## References
- https://docs.greatexpectations.io
- https://github.com/great-expectations/great_expectations

## Notes
GX v1.15.1 courante. Excellent pour la validation de données dans les pipelines ML. Se combine bien avec Evidently pour le monitoring post-déploiement.
