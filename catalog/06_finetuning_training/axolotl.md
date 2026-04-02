# Axolotl

> Outil de fine-tuning LLM streamliné via configuration YAML, supportant LoRA, QLoRA, FSDP, DeepSpeed, GRPO et DPO

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 06_finetuning_training |
| **URL** | https://github.com/axolotl-ai-cloud/axolotl |
| **GitHub** | https://github.com/axolotl-ai-cloud/axolotl |
| **Stars** | 11,600 |
| **License** | Apache 2.0 |
| **Pricing** | Free / Open Source |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Axolotl est un framework de fine-tuning LLM centré sur la simplicité d'utilisation via configuration YAML. Là où LLaMA-Factory privilégie la richesse des fonctionnalités et l'interface web, Axolotl mise sur une approche "config-first" qui rend l'entraînement reproductible et versionnable via git. Toute la configuration d'un fine-tuning — modèle, dataset, méthode, hyperparamètres — est décrite dans un seul fichier YAML.

Le projet est géré par axolotl-ai-cloud, une organisation communautaire qui s'est développée autour de l'outil. Il supporte une large gamme de méthodes : LoRA, QLoRA, FSDP, DeepSpeed intégré pour le multi-GPU, et les algorithmes modernes GRPO et DPO. Il est maintenu activement avec des commits en mars 2026.

Axolotl est particulièrement populaire dans la communauté open source pour son équilibre entre simplicité et puissance. Il est souvent utilisé comme alternative plus accessible à LLaMA-Factory pour les développeurs qui préfèrent tout contrôler via des fichiers de configuration.

## Key Features
- **Config YAML complète** : tout le fine-tuning décrit dans un fichier YAML versionnable
- **LoRA / QLoRA** : PEFT intégré avec bitsandbytes
- **FSDP** : Fully Sharded Data Parallel natif
- **DeepSpeed intégré** : ZeRO stage 1/2/3 via configuration
- **DPO** : Direct Preference Optimization
- **GRPO** : Group Relative Policy Optimization (post-DeepSeek-R1)
- **Flash Attention** : support Flash Attention 2
- **Packing de séquences** : efficacité maximale du training via packing
- **Multi-datasets** : combiner plusieurs datasets dans une config
- **Weights & Biases** : intégration tracking expériences

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Actif mars 2026, largement utilisé en production |
| **Security** | 3 | Projet communautaire open source, pas d'audit formel |
| **Scalability** | 4 | FSDP + DeepSpeed pour multi-GPU, bien testé |
| **Support/Community** | 4 | Communauté open source forte, Discord actif |
| **Documentation** | 3 | Documentation suffisante mais peut manquer de profondeur sur certains cas |
| **Integration Ease** | 4 | Config YAML simple, Docker disponible, examples nombreux |

## Use Cases
1. **Fine-tuning reproductible** : versionner la config YAML dans git pour des expériences reproductibles
2. **Pipeline SFT → DPO** : enchaîner fine-tuning supervisé puis alignment DPO avec deux configs YAML
3. **GRPO reasoning** : entraîner des modèles de raisonnement avec GRPO
4. **Multi-GPU simple** : activer DeepSpeed/FSDP via une ligne dans la config YAML
5. **Experimentation rapide** : modifier rapidement hyperparamètres via YAML et relancer

## Getting Started
```bash
# Via Docker (recommandé)
docker run --gpus all -v $(pwd):/workspace axolotlai/axolotl:main-latest

# Ou pip
pip install axolotl

# Config minimale (config.yaml)
base_model: meta-llama/Llama-3-8B
model_type: LlamaForCausalLM
tokenizer_type: AutoTokenizer

load_in_4bit: true
adapter: lora
lora_r: 16
lora_alpha: 32

datasets:
  - path: tatsu-lab/alpaca
    type: alpaca

val_set_size: 0.05
output_dir: ./outputs/lora-out
learning_rate: 0.0002
num_epochs: 3

# Lancement
axolotl train config.yaml
```

## Architecture / How It Works
```
Axolotl Architecture
├── Config Layer (YAML)
│   ├── Model config        →  Base model, adapter type
│   ├── Dataset config      →  Sources, format, mix
│   ├── Training config     →  LR, epochs, batch size
│   └── Optimization        →  DeepSpeed/FSDP, flash attn
├── Preprocessing Pipeline
│   ├── Tokenization        →  Formats multiples (alpaca, chatml...)
│   └── Sequence packing    →  Efficacité maximale du training
├── Training Engine
│   ├── HF Trainer          →  Entraînement standard
│   └── TRL Integration     →  DPO, GRPO via TRL
└── Backends
    ├── LoRA / QLoRA (PEFT)
    ├── FSDP (PyTorch native)
    └── DeepSpeed ZeRO 1/2/3
```

## Strengths
- Configuration YAML complète et versionneable — idéal pour la reproductibilité
- Bon équilibre simplicité/puissance par rapport à LLaMA-Factory
- Communauté open source forte et active
- Support de nombreux formats de datasets (alpaca, sharegpt, chatml, etc.)
- Bien maintenu avec intégration rapide des nouvelles techniques

## Limitations
- Documentation peut manquer de profondeur sur des cas edge complexes
- Moins de features que LLaMA-Factory (pas d'interface web, moins d'algorithmes)
- Communauté légèrement plus petite que LLaMA-Factory ou TRL

## Alternatives
| Tool | Key Difference |
|------|---------------|
| LLaMA-Factory | Plus de features, interface web, plus grande communauté |
| Unsloth | Beaucoup plus rapide, mais moins de configurations |
| TRL | Bibliothèque algo-centric, plus bas niveau |
| Ludwig | YAML également mais plus généraliste (pas seulement LLMs) |

## References
- [GitHub Repository](https://github.com/axolotl-ai-cloud/axolotl)
- [Documentation](https://axolotl-ai-cloud.github.io/axolotl/)
- [Exemples de configs](https://github.com/axolotl-ai-cloud/axolotl/tree/main/examples)
- [Discord communauté](https://discord.gg/HhrNrHJPRb)

## Notes
- Actif en mars 2026, développement continu
- Particulièrement populaire pour les fine-tunings custom sur datasets propriétaires
- Config YAML peut être passée en argument CLI ou montée via Docker volume
- Organisation github axolotl-ai-cloud (non axolotl-org) depuis 2024
