# Argilla

> Plateforme de curation de données et feedback humain spécialisée LLMs pour annotation, évaluation et RLHF

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 06_finetuning_training |
| **URL** | https://argilla.io |
| **GitHub** | https://github.com/argilla-io/argilla |
| **Stars** | 4,900 |
| **License** | Apache 2.0 |
| **Pricing** | Free / Open Source (Argilla Cloud payant) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Argilla est une plateforme open source spécialisée dans la curation de données et la collecte de feedback humain pour les LLMs. Là où Label Studio est un outil d'annotation généraliste, Argilla est conçu spécifiquement pour les workflows LLM : évaluation de réponses, collecte de préférences RLHF, annotation d'instructions pour SFT, et critique de modèles.

La plateforme s'intègre nativement avec HuggingFace Datasets et Distilabel (l'outil HF de génération de données synthétiques), ce qui en fait un maillon naturel du pipeline HuggingFace pour créer et affiner des datasets d'entraînement. Les équipes peuvent collaborativement annoter, évaluer et exporter des datasets directement vers le Hub HuggingFace.

Argilla est particulièrement fort pour les use cases RLHF où plusieurs annotateurs doivent comparer des paires de réponses (préférence A vs B), pour l'évaluation qualitative des LLMs, et pour la construction de datasets d'instructions fine-tuning avec contrôle qualité.

## Key Features
- **Interface d'annotation LLM** : optimisée pour texte, instructions, réponses de modèles
- **Feedback Human** : collecte de préférences, évaluations, corrections
- **Intégration HF Datasets** : export direct vers Hub HuggingFace
- **Distilabel integration** : pipeline génération + annotation synthétique
- **Tasks LLM** : Rating, Ranking, Span labeling, Text classification, Q&A
- **Multi-annotateurs** : gestion des équipes, accord inter-annotateurs
- **REST API** : intégration dans des pipelines ML
- **SDK Python** : client Python pour automatisation
- **Argilla Cloud** : version SaaS hébergée disponible

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 3 | Utilisé en production, mais moins mature que Label Studio Enterprise |
| **Security** | 3 | Apache 2.0, déploiement on-premise possible, pas d'audit formel connu |
| **Scalability** | 3 | Scale modérément, Argilla Cloud pour éviter la gestion infra |
| **Support/Community** | 3 | Communauté active, Argilla Cloud avec support commercial |
| **Documentation** | 4 | Documentation claire et bien organisée, nombreux tutoriels |
| **Integration Ease** | 4 | SDK Python simple, intégration HF native, setup Docker facile |

## Use Cases
1. **Collecte préférences RLHF** : annoter des paires de réponses pour entraîner des reward models
2. **Curation dataset SFT** : valider et améliorer la qualité d'un dataset d'instructions
3. **Évaluation LLM qualitative** : faire évaluer les réponses par des experts humains
4. **Pipeline Distilabel** : générer des données synthétiques et les valider humainement
5. **Red-teaming collaboratif** : identifier les faiblesses d'un modèle en équipe

## Getting Started
```bash
# Via Docker (recommandé)
docker run -d --name argilla \
    -p 6900:6900 \
    argilla/argilla-quickstart:latest

# Ou pip
pip install argilla

# Connexion et création dataset
import argilla as rg

rg.init(api_url="http://localhost:6900", api_key="admin.apikey")

# Créer un dataset de feedback
dataset = rg.FeedbackDataset(
    fields=[rg.TextField(name="instruction"), rg.TextField(name="response")],
    questions=[rg.RatingQuestion(name="quality", values=[1, 2, 3, 4, 5])],
)
dataset.push_to_argilla(name="my-feedback-dataset")

# Export vers HuggingFace Hub
dataset.push_to_huggingface("my-org/my-dataset")
```

## Architecture / How It Works
```
Argilla Architecture
├── Frontend (Vue.js)
│   ├── Annotation UI     →  Interface optimisée LLM tasks
│   ├── Dataset Browser   →  Navigation et filtrage
│   └── Analytics         →  Métriques d'annotation
├── Backend (FastAPI + Elasticsearch)
│   ├── REST API          →  Intégration externe
│   ├── Python SDK        →  Client Python
│   └── Auth              →  Users, workspaces, roles
└── Integrations
    ├── HF Datasets        →  Import/Export Hub
    ├── Distilabel         →  Génération données synthétiques
    └── LLM Backends       →  Génération de réponses pour annotation
```

## Strengths
- Spécialisé pour les workflows LLM/RLHF, bien plus adapté que Label Studio pour ce use case
- Intégration native HuggingFace (Datasets Hub, Distilabel)
- Interface utilisateur pensée pour l'évaluation comparative de réponses LLM
- SDK Python simple pour automatisation des pipelines de données
- Actif en mars 2025, maintenu activement

## Limitations
- Moins généraliste que Label Studio (principalement texte/LLM, pas vision/audio)
- Communauté et écosystème plus petits que Label Studio
- Argilla Cloud nécessaire pour éviter la complexité de gestion infra
- Elasticsearch en backend peut être lourd pour petits projets

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Label Studio | Plus généraliste (images, audio, vidéo), plus grande communauté |
| Prodigy (spaCy) | Payant, excellent NLP, active learning avancé |
| Scale AI | Plateforme commerciale, annotation professionnelle outsourcée |
| LabelBox | Enterprise, multi-modal, fonctionnalités avancées payantes |

## References
- [Site officiel](https://argilla.io)
- [GitHub Repository](https://github.com/argilla-io/argilla)
- [Documentation](https://docs.argilla.io)
- [Distilabel](https://github.com/argilla-io/distilabel)
- [Argilla Cloud](https://argilla.io/argilla-cloud)

## Notes
- Maintenu activement jusqu'en mars 2025
- L'intégration Distilabel + Argilla forme un pipeline complet : génération synthétique + validation humaine
- Utilisé par l'équipe HuggingFace pour la création de datasets alignement
- Version 2.x a significativement amélioré l'API Python et l'interface utilisateur
