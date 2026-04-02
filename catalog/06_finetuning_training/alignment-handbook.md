# Alignment Handbook

> Recettes HuggingFace de référence pour aligner les LLMs via SFT, DPO et RLHF avec exemples reproductibles

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 06_finetuning_training |
| **URL** | https://github.com/huggingface/alignment-handbook |
| **GitHub** | https://github.com/huggingface/alignment-handbook |
| **Stars** | 5,500 |
| **License** | Apache 2.0 |
| **Pricing** | Free / Open Source |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
L'Alignment Handbook est un dépôt de recettes pratiques maintenu par l'équipe HuggingFace pour aligner les LLMs. Il fournit des configurations, scripts et datasets prêts à l'emploi pour reproduire et étendre les techniques d'alignment modernes : SFT (Supervised Fine-Tuning), DPO (Direct Preference Optimization) et RLHF.

Contrairement à TRL ou PEFT qui sont des bibliothèques génériques, l'Alignment Handbook est un ensemble de recettes concrètes et reproductibles. Il documente les choix de conception, les hyperparamètres optimaux et les bonnes pratiques que l'équipe HuggingFace a appris en alignant des modèles réels comme Zephyr, StarChat et d'autres modèles du Hub.

Le projet sert à la fois de ressource pédagogique (comprendre comment aligner un LLM en pratique) et de point de départ pour des projets d'alignment réels. Il est activement maintenu avec une mise à jour en juillet 2025.

## Key Features
- **Recettes SFT** : scripts complets pour fine-tuning supervisé avec configuration optimale
- **Recettes DPO** : alignment par préférence directe avec datasets et configs
- **Multi-GPU** : configurations DeepSpeed et FSDP pré-faites
- **Datasets de référence** : exemples avec UltraChat, HH-RLHF, etc.
- **Configurations validées** : hyperparamètres testés par l'équipe HF
- **Intégration TRL** : s'appuie sur TRL pour les trainers
- **Scripts d'évaluation** : comparaison avec MT-Bench, Alpaca Eval
- **Documentation pédagogique** : explications des choix de conception

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 3 | Plus orienté apprentissage que production clé en main |
| **Security** | 4 | HuggingFace officiel, Apache 2.0, code auditable |
| **Scalability** | 3 | Multi-GPU via DeepSpeed configs incluses, mais pas optimisé pour très grande échelle |
| **Support/Community** | 4 | Soutien HuggingFace, bonne documentation, issues suivies |
| **Documentation** | 5 | Excellente documentation pédagogique, explications détaillées |
| **Integration Ease** | 4 | S'appuie sur TRL + PEFT, facile si déjà familier HF |

## Use Cases
1. **Apprendre l'alignment LLM** : comprendre en pratique comment aligner un modèle via des recettes documentées
2. **Point de départ projet** : utiliser les configs comme base pour un projet d'alignment sur mesure
3. **Reproduire Zephyr/StarChat** : suivre exactement le pipeline HuggingFace pour des modèles de référence
4. **SFT + DPO pipeline** : implémenter un pipeline complet d'alignment en deux étapes
5. **Benchmarking alignment** : comparer différentes approches d'alignment sur des modèles identiques

## Getting Started
```bash
# Cloner le repo
git clone https://github.com/huggingface/alignment-handbook.git
cd alignment-handbook

# Installation
pip install -e ".[torch,metrics]"

# SFT fine-tuning (exemple Zephyr)
ACCELERATE_LOG_LEVEL=info accelerate launch \
    --config_file recipes/accelerate_configs/multi_gpu.yaml \
    scripts/run_sft.py \
    recipes/zephyr-7b-beta/sft/config_full.yaml

# DPO alignment
ACCELERATE_LOG_LEVEL=info accelerate launch \
    --config_file recipes/accelerate_configs/deepspeed_zero3.yaml \
    scripts/run_dpo.py \
    recipes/zephyr-7b-beta/dpo/config_full.yaml
```

## Architecture / How It Works
```
Alignment Handbook Structure
├── recipes/
│   ├── zephyr-7b-beta/
│   │   ├── sft/config_full.yaml    →  SFT complet
│   │   └── dpo/config_full.yaml    →  DPO alignment
│   ├── starchat2-15b/
│   ├── accelerate_configs/         →  Multi-GPU configs
│   └── ...
├── scripts/
│   ├── run_sft.py                  →  Script SFT (via TRL)
│   ├── run_dpo.py                  →  Script DPO (via TRL)
│   └── run_reward_modeling.py      →  Reward model
└── src/alignment/
    ├── data_utils.py               →  Préparation datasets
    └── model_utils.py              →  Utilitaires modèles

Sous-jacent: TRL Trainers + PEFT + HF Transformers
```

## Strengths
- Référence pédagogique de l'équipe HuggingFace, qualité assurée
- Recettes reproductibles : résultats vérifiables par la communauté
- Documentation claire expliquant les choix de conception
- Couvre SFT + DPO + Reward Modeling dans un seul dépôt
- Excellent point de départ pour adapter à ses propres datasets

## Limitations
- Plus orienté apprentissage/recherche que déploiement production clé en main
- Ne couvre pas GRPO ni les techniques RL les plus récentes
- Moins de modèles supportés que LLaMA-Factory
- Dépendance complète à l'écosystème HuggingFace

## Alternatives
| Tool | Key Difference |
|------|---------------|
| TRL | La bibliothèque sous-jacente, plus générique et flexible |
| LLaMA-Factory | Plus d'algorithmes, interface web, production-ready |
| Axolotl | Config YAML similaire, plus de méthodes de fine-tuning |
| VERL | Pour les cas GRPO/RL avancés non couverts ici |

## References
- [GitHub Repository](https://github.com/huggingface/alignment-handbook)
- [Blog HuggingFace Zephyr](https://huggingface.co/blog/zephyr)
- [Documentation TRL](https://huggingface.co/docs/trl/index)
- [HuggingFace Alignment Models](https://huggingface.co/collections/alignment-handbook)

## Notes
- Dernière mise à jour active : juillet 2025
- Utilisé pour entraîner Zephyr 7B Beta, StarChat2 15B et autres modèles HF populaires
- Les configs DeepSpeed incluses sont un bon point de départ pour du multi-GPU
- Complémentaire à TRL : le handbook donne le "quoi et pourquoi", TRL donne le "comment"
