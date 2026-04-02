# LLaMA-Factory

> Framework unifié de fine-tuning supportant 100+ LLMs avec interface web intégrée

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 06_finetuning_training |
| **URL** | https://github.com/hiyouga/LLaMA-Factory |
| **GitHub** | https://github.com/hiyouga/LLaMA-Factory |
| **Stars** | 69,300 |
| **License** | Apache 2.0 |
| **Pricing** | Free / Open Source |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
LLaMA-Factory est un framework unifié de fine-tuning permettant d'entraîner et ajuster plus de 100 modèles de langage différents via une interface cohérente. Il prend en charge tous les algorithmes d'entraînement modernes : SFT (Supervised Fine-Tuning), RLHF, DPO, GRPO, PPO et KTO, ce qui en fait l'une des solutions les plus complètes du marché.

Le projet se distingue par son interface web intégrée appelée LLaMA Board, qui permet de configurer et lancer des entraînements sans écrire de code. Cette approche le rend accessible aussi bien aux chercheurs qu'aux praticiens ML moins expérimentés.

Avec près de 70K étoiles GitHub et des commits datant du 2026-04-01, LLaMA-Factory est l'un des projets open source les plus actifs dans le domaine du fine-tuning de LLMs. Sa communauté massive garantit un support solide, des corrections rapides et une adoption des nouvelles techniques (comme GRPO post-DeepSeek-R1).

## Key Features
- **100+ modèles supportés** : LLaMA, Mistral, Qwen, DeepSeek, Gemma, Falcon et bien d'autres
- **Multi-algorithmes** : SFT, RLHF, DPO, GRPO, PPO, KTO en un seul framework
- **LLaMA Board** : interface web intuitive pour configuration et monitoring
- **LoRA / QLoRA** : support natif des méthodes PEFT pour fine-tuning efficace en mémoire
- **DeepSpeed & FSDP** : intégration pour training distribué multi-GPU
- **Flash Attention** : support pour accélération kernel
- **Quantization** : support GPTQ, AWQ, GGUF
- **Export multi-format** : sauvegarde vers HuggingFace, GGUF, vLLM-ready
- **Datasets intégrés** : bibliothèque de datasets préconfigurés

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | Très actif, utilisé massivement en production, 69K+ stars |
| **Security** | 3 | Outil local, pas de surface d'attaque réseau, mais pas d'audit de sécurité formel |
| **Scalability** | 4 | Multi-GPU via DeepSpeed/FSDP, mais principalement orienté single-node |
| **Support/Community** | 5 | Communauté massive, issues répondues rapidement, documentation exhaustive |
| **Documentation** | 5 | Wiki complet, exemples nombreux, tutoriels détaillés |
| **Integration Ease** | 4 | Installation pip simple, interface web, compatible écosystème HuggingFace |

## Use Cases
1. **Fine-tuning sur données métier** : adapter un LLM open source à un domaine spécifique (finance, juridique, médical) via SFT
2. **Alignment RLHF/DPO** : aligner un modèle sur des préférences humaines avec DPO ou PPO
3. **Post-training RL** : entraîner un modèle à raisonner avec GRPO (style DeepSeek-R1)
4. **Prototypage rapide** : tester différents algorithmes et configurations via l'interface LLaMA Board
5. **Comparaison de méthodes** : évaluer SFT vs DPO vs GRPO sur le même modèle base

## Getting Started
```bash
# Installation
pip install llamafactory

# Lancement de l'interface web
llamafactory-cli webui

# Fine-tuning en ligne de commande
llamafactory-cli train examples/train_lora/llama3_lora_sft.yaml

# Inférence
llamafactory-cli chat examples/inference/llama3_lora_sft.yaml
```

## Architecture / How It Works
```
LLaMA-Factory
├── LLaMA Board (Web UI)  →  Configuration visuelle
├── CLI Interface         →  Automatisation / scripting
└── Core Engine
    ├── Model Hub         →  100+ architectures supportées
    ├── Trainer Hub       →  SFT / DPO / PPO / GRPO / KTO / RLHF
    ├── Data Pipeline     →  Templates, datasets, préprocessing
    ├── PEFT Module       →  LoRA, QLoRA, AdaLoRA, DoRA
    └── Export Module     →  HuggingFace / GGUF / vLLM
```

## Strengths
- Couverture d'algorithmes la plus large du marché (SFT, DPO, GRPO, PPO, KTO, RLHF)
- Interface web LLaMA Board pour une utilisation sans code
- Communauté massive et développement très actif
- Documentation exhaustive avec exemples pratiques
- Compatible avec la grande majorité des LLMs open source

## Limitations
- Peut être overwhelmant pour les débutants vu la quantité d'options
- Dépendances lourdes (nécessite PyTorch, transformers, etc.)
- Principalement orienté single-node, moins optimisé pour clusters multi-nœuds massifs

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Axolotl | Plus simple, config YAML, moins d'algorithmes |
| Unsloth | Beaucoup plus rapide (2x) mais moins d'algorithmes |
| TRL | Bibliothèque HuggingFace native, plus bas niveau |
| LitGPT | Plus simple mais moins complet |

## References
- [GitHub Repository](https://github.com/hiyouga/LLaMA-Factory)
- [Documentation Wiki](https://github.com/hiyouga/LLaMA-Factory/wiki)
- [Paper arXiv](https://arxiv.org/abs/2403.13372)
- [HuggingFace Models](https://huggingface.co/hiyouga)

## Notes
- Commit actif au 2026-04-01, développement extrêmement rapide
- Supporte GRPO depuis l'émergence de DeepSeek-R1, adoption très rapide des nouvelles techniques
- LLaMA Board permet de monitorer les métriques d'entraînement en temps réel
