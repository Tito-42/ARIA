# Label Studio

> Plateforme d'annotation de données multi-format open source avec ML-assisted labeling

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 06_finetuning_training |
| **URL** | https://labelstud.io |
| **GitHub** | https://github.com/HumanSignal/label-studio |
| **Stars** | 26,900 |
| **License** | Apache 2.0 |
| **Pricing** | Freemium - Community (gratuit) / Enterprise (payant) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Enterprise |

## What It Does
Label Studio est une plateforme d'annotation de données open source développée par HumanSignal. Elle permet d'annoter tous types de données — texte, images, audio, vidéo, séries temporelles — via une interface web unifiée. Elle est devenue un standard dans les équipes ML pour la création de datasets d'entraînement de haute qualité.

La plateforme se distingue par sa fonctionnalité de ML-assisted labeling : elle peut connecter des modèles ML existants pour pré-labeler automatiquement les données, réduisant drastiquement le temps d'annotation manuelle. Les annotateurs n'ont plus qu'à valider ou corriger les suggestions du modèle.

En 2026, Label Studio est particulièrement utilisé pour créer des datasets RLHF (préférences humaines), annoter des données pour fine-tuning de LLMs, et construire des pipelines d'amélioration continue des modèles en production.

## Key Features
- **Multi-format** : texte, images, audio, vidéo, séries temporelles, HTML, PDF
- **ML Backend** : connexion de modèles ML pour pre-labeling automatique
- **Templates de tâches** : 40+ templates préconfigurés (NER, classification, OCR, etc.)
- **Collaboration équipe** : gestion des rôles, assignation des tâches, révision qualité
- **Export multi-format** : JSON, CSV, COCO, YOLO, spaCy, CoNLL et autres
- **API REST** : intégration dans des pipelines ML automatisés
- **Inter-annotator agreement** : calcul automatique de l'accord entre annotateurs
- **Webhooks** : notifications sur événements (tâche complétée, annotation créée)
- **Intégration cloud** : S3, GCS, Azure Blob pour sources de données

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Largement déployé en production, version Enterprise avec SLA |
| **Security** | 4 | Auth LDAP/SSO (Enterprise), RBAC, déploiement on-premise possible |
| **Scalability** | 4 | Scale horizontalement, version Enterprise pour grands volumes |
| **Support/Community** | 4 | Communauté active, support Enterprise payant disponible |
| **Documentation** | 4 | Documentation bien structurée, nombreux tutoriels |
| **Integration Ease** | 4 | Interface web intuitive, API REST, SDK Python |

## Use Cases
1. **Création datasets NLP** : annoter des données texte pour NER, classification, QA, résumé
2. **Données RLHF** : collecte de préférences humaines pour alignment de LLMs
3. **Computer vision** : bounding boxes, segmentation, keypoints pour modèles vision
4. **Amélioration continue** : labeling des erreurs de modèles en production pour réentraînement
5. **OCR et document AI** : annotation de documents pour extraction d'informations structurées

## Getting Started
```bash
# Installation pip
pip install label-studio

# Lancement (interface web sur localhost:8080)
label-studio start

# Ou via Docker
docker run -it -p 8080:8080 heartexlabs/label-studio:latest

# Avec données persistantes
docker run -it -p 8080:8080 \
  -v $(pwd)/mydata:/label-studio/data \
  heartexlabs/label-studio:latest
```

## Architecture / How It Works
```
Label Studio Architecture
├── Frontend (React)
│   ├── Annotation UI      →  Interface d'annotation par type de tâche
│   ├── Project Dashboard  →  Gestion projets et progression
│   └── Quality Review     →  Révision et accord inter-annotateurs
├── Backend (Django/Python)
│   ├── REST API           →  Intégration externe
│   ├── ML Backend Client  →  Connexion aux modèles ML
│   └── Storage Connectors →  S3, GCS, Azure, local
└── ML Backends (externes)
    ├── Modèle ML          →  Pre-labeling automatique
    └── Active Learning    →  Sélection intelligente des données à annoter
```

## Strengths
- Interface intuitive supportant tous les types de données courants
- ML-assisted labeling réduit significativement le temps d'annotation
- Large écosystème de templates couvrant la majorité des use cases ML
- Déploiement on-premise pour les données sensibles
- API REST complète pour automatisation des pipelines

## Limitations
- Version Enterprise payante pour les fonctionnalités avancées (SSO, analytiques avancées)
- Peut être lourd et over-engineered pour des projets d'annotation simples
- ML Backend nécessite une infrastructure serveur dédiée pour les modèles
- Performance peut dégrader avec des datasets très volumineux (millions d'items)

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Argilla | Spécialisé LLM/RLHF, moins généraliste mais mieux intégré HuggingFace |
| Prodigy | Payant, excellent pour NLP, active learning très avancé |
| CVAT | Spécialisé vision par ordinateur, open source |
| Doccano | Très simple, texte uniquement, idéal pour petits projets |

## References
- [Site officiel](https://labelstud.io)
- [GitHub Repository](https://github.com/HumanSignal/label-studio)
- [Documentation](https://labelstud.io/guide/)
- [ML Backend examples](https://github.com/HumanSignal/label-studio-ml-backend)

## Notes
- Commit actif au 2026-04-01, développement très soutenu
- HumanSignal est la société commerciale derrière Label Studio
- Version Enterprise ajoute : SSO/LDAP, analytiques avancées, SLA support, audit logs
- Idéal pour les équipes qui ont besoin d'une solution on-premise pour données sensibles
