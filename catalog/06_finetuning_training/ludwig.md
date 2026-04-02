# Ludwig

> Framework déclaratif YAML pour training ML/DL et fine-tuning LLM, par Linux Foundation AI

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 06_finetuning_training |
| **URL** | https://ludwig.ai |
| **GitHub** | https://github.com/ludwig-ai/ludwig |
| **Stars** | 11,700 |
| **License** | Apache 2.0 |
| **Pricing** | Free / Open Source |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Ludwig est un framework déclaratif de machine learning développé initialement par Uber AI Labs et maintenant hébergé par la Linux Foundation AI. Son approche distinctive est la configuration via fichiers YAML : l'utilisateur décrit ce qu'il veut faire (types de features, architecture, training) sans écrire de code Python, et Ludwig gère tous les détails d'implémentation.

Le framework supporte un large spectre de tâches ML : classification, régression, génération de texte, reconnaissance vocale, vision par ordinateur et fine-tuning de LLMs. Cette polyvalence multi-modal combinée à l'approche no-code/low-code le rend particulièrement attractif pour les équipes data science qui veulent se concentrer sur les données plutôt que sur le code.

Ludwig inclut également des capacités AutoML permettant de rechercher automatiquement la meilleure configuration d'hyperparamètres, et supporte le déploiement via TorchServe ou FastAPI.

## Key Features
- **Configuration YAML** : définir tout le pipeline ML sans code Python
- **Multi-modal** : texte, images, audio, séries temporelles, données tabulaires
- **Fine-tuning LLM** : adapter des LLMs HuggingFace via YAML
- **AutoML** : recherche d'hyperparamètres automatisée
- **Backends distribués** : Ray, Horovod, DDP pour multi-GPU
- **Exportation** : TorchServe, ONNX, CoreML
- **Visualisation** : courbes d'apprentissage, confusion matrices intégrées
- **Python API** : API Python disponible pour cas avancés
- **Benchmarking intégré** : comparaison de configurations automatisée

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 3 | Utilisé en production chez Uber, mais communauté modérée |
| **Security** | 3 | Projet Linux Foundation, Apache 2.0, pas d'audit formel |
| **Scalability** | 4 | Ray/Horovod pour multi-GPU, AutoML distribué |
| **Support/Community** | 3 | Communauté modérée, Linux Foundation backing |
| **Documentation** | 4 | Documentation claire, nombreux exemples YAML |
| **Integration Ease** | 5 | Approche YAML très accessible, courbe d'apprentissage minimale |

## Use Cases
1. **Fine-tuning LLM no-code** : adapter un LLM HuggingFace via configuration YAML sans Python
2. **Pipeline ML multi-modal** : construire un pipeline combinant texte + images + données tabulaires
3. **AutoML organisationnel** : chercher automatiquement la meilleure config pour un dataset donné
4. **Prototypage rapide** : tester rapidement de nombreuses architectures via YAML
5. **Équipes data science** : permettre à des non-ingénieurs ML de construire des pipelines

## Getting Started
```bash
# Installation
pip install ludwig

# Fine-tuning LLM avec YAML
cat > config.yaml << EOF
model_type: llm
base_model: meta-llama/Llama-3-8B-Instruct
adapter:
  type: lora
  r: 16
quantization:
  bits: 4
input_features:
  - name: prompt
    type: text
output_features:
  - name: completion
    type: text
trainer:
  epochs: 3
  learning_rate: 0.0001
EOF

ludwig train --config config.yaml --dataset my_data.csv

# Classification texte
ludwig experiment \
    --dataset data.csv \
    --config_str "{input_features: [{name: text, type: text}], output_features: [{name: label, type: category}]}"
```

## Architecture / How It Works
```
Ludwig Architecture
├── Config Layer (YAML)
│   ├── Model definition    →  Architecture, base model
│   ├── Features            →  Types input/output
│   ├── Trainer config      →  Hyperparamètres
│   └── Preprocessing       →  Transformations données
├── Core Engine
│   ├── ECD Model           →  Encoder-Combiner-Decoder
│   ├── LLM Model           →  Fine-tuning LLMs HuggingFace
│   └── GBM Model           →  Gradient Boosting (LightGBM)
├── Backends
│   ├── Local               →  Single GPU/CPU
│   ├── Ray                 →  Distributed ML
│   └── Horovod             →  Multi-GPU MPI
└── Serving
    ├── TorchServe          →  Production inference
    └── REST API            →  FastAPI auto-généré
```

## Strengths
- Approche YAML rend le ML accessible sans expertise code profonde
- Linux Foundation backing garantit la pérennité et la neutralité
- Vraiment multi-modal : gère texte, images, audio, tabulaire dans un seul framework
- AutoML intégré pour optimisation d'hyperparamètres
- API Python disponible quand la config YAML ne suffit pas

## Limitations
- Moins flexible que du code pur pour les cas très avancés
- Communauté plus modérée que LLaMA-Factory ou HuggingFace
- Overhead de la couche YAML pour des cas simples
- Fine-tuning LLM moins avancé que des outils spécialisés (LLaMA-Factory, Axolotl)

## Alternatives
| Tool | Key Difference |
|------|---------------|
| LLaMA-Factory | Spécialisé LLM, plus d'algorithmes, interface web |
| Axolotl | YAML également mais spécialisé fine-tuning LLM |
| AutoGluon | AutoML plus avancé, moins de contrôle |
| Keras | Framework haut-niveau mais en Python, pas YAML |

## References
- [Site officiel](https://ludwig.ai)
- [GitHub Repository](https://github.com/ludwig-ai/ludwig)
- [Documentation](https://ludwig.ai/latest/)
- [Linux Foundation AI](https://lfaidata.foundation/projects/ludwig/)

## Notes
- Origine Uber AI Labs, maintenant gouverné par Linux Foundation AI & Data
- Idéal pour les organisations qui veulent standardiser le ML via config-as-code
- La combinaison YAML + AutoML est unique dans l'espace fine-tuning LLM
