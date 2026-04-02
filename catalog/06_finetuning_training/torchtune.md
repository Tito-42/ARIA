# torchtune

> Bibliothèque PyTorch officielle pour fine-tuning de LLMs avec recettes simples et intégration native PyTorch

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 06_finetuning_training |
| **URL** | https://github.com/pytorch/torchtune |
| **GitHub** | https://github.com/pytorch/torchtune |
| **Stars** | 5,700 |
| **License** | BSD |
| **Pricing** | Free / Open Source |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Beta |

## What It Does
torchtune est la bibliothèque officielle de PyTorch pour le fine-tuning de LLMs. Développée par Meta/PyTorch, elle fournit des "recettes" (recipes) prêtes à l'emploi pour fine-tuner les modèles LLaMA, Mistral, Qwen et d'autres architectures populaires, en utilisant uniquement PyTorch natif sans dépendances lourdes.

L'approche distinctive de torchtune est sa philosophie "PyTorch pur" : pas d'abstractions supplémentaires, pas de framework training supplémentaire comme Lightning ou Accelerate. Le code est minimal, lisible et directement compréhensible par quiconque connaît PyTorch. Cela le rend idéal pour la recherche et pour les équipes qui veulent comprendre exactement ce qui se passe pendant le training.

Bien qu'encore en beta avec une communauté en croissance, torchtune bénéficie du backing officiel PyTorch/Meta, ce qui garantit sa pérennité et son alignement avec les évolutions de PyTorch.

## Key Features
- **Recettes PyTorch** : scripts de fine-tuning clairs et modifiables
- **LoRA / QLoRA** : implémentation PyTorch native sans PEFT
- **Full fine-tuning** : support complet des poids
- **FSDP2** : Fully Sharded Data Parallel v2 (PyTorch 2.x)
- **DPO** : Direct Preference Optimization
- **Quantization** : support torchao pour quantization
- **Flash Attention** : intégration native
- **20+ modèles** : LLaMA 3, Mistral, Qwen, Gemma, Phi, etc.
- **YAML config** : configuration via YAML pour les recettes

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 3 | Beta, backing PyTorch officiel, mais communauté encore petite |
| **Security** | 4 | Meta/PyTorch officiel, BSD license très permissive, code auditable |
| **Scalability** | 3 | FSDP2 pour multi-GPU, moins mature que DeepSpeed |
| **Support/Community** | 3 | Communauté en croissance, support PyTorch officiel |
| **Documentation** | 4 | Documentation PyTorch de qualité, tutoriels bien écrits |
| **Integration Ease** | 4 | PyTorch natif, pas de dépendances supplémentaires, recettes directes |

## Use Cases
1. **Fine-tuning PyTorch natif** : utiliser uniquement PyTorch sans frameworks supplémentaires
2. **Recherche LLM** : modifier les recettes pour expérimenter des architectures custom
3. **Formation équipes** : apprendre le fine-tuning LLM avec du code clair et lisible
4. **DPO alignment** : aligner un modèle avec des préférences via DPO
5. **Intégration stack PyTorch** : s'intégrer nativement avec torchao, torchserve, etc.

## Getting Started
```bash
# Installation
pip install torchtune

# Lister les recettes disponibles
tune ls

# Télécharger un modèle
tune download meta-llama/Llama-3.2-3B-Instruct \
    --output-dir /tmp/Llama-3.2-3B-Instruct

# LoRA fine-tuning sur 1 GPU
tune run lora_finetune_single_device \
    --config llama3_2/3B_lora_single_device

# Full fine-tuning multi-GPU (4 GPUs)
tune run --nproc_per_node 4 full_finetune_distributed \
    --config llama3_2/3B_full

# DPO alignment
tune run dpo_full_finetune_single_device \
    --config llama3/8B_dpo_single_device
```

## Architecture / How It Works
```
torchtune Architecture
├── Recipes (scripts d'entraînement)
│   ├── lora_finetune_single_device.py  →  LoRA 1 GPU
│   ├── lora_finetune_distributed.py    →  LoRA multi-GPU
│   ├── full_finetune_single_device.py  →  Full 1 GPU
│   ├── full_finetune_distributed.py    →  Full multi-GPU
│   └── dpo_full_finetune_*.py          →  DPO alignment
├── Models (PyTorch natif)
│   ├── llama3.py, mistral.py, ...      →  20+ architectures
│   └── LoRA wrappers                   →  Adaptation LoRA
├── Config Layer (YAML)
│   └── Per-model configs              →  Hyperparamètres
└── Backend
    ├── PyTorch FSDP2                  →  Multi-GPU
    └── torchao                        →  Quantization
```

## Strengths
- Backing officiel PyTorch/Meta garantit pérennité et alignement
- Code PyTorch pur, extrêmement lisible et modifiable
- Licence BSD très permissive (même pour usage commercial)
- Bonne documentation dans le style PyTorch
- Intégration native avec l'écosystème PyTorch (torchao, torchserve)

## Limitations
- Communauté encore en croissance, moins de ressources que LLaMA-Factory
- Moins de features que LLaMA-Factory (pas d'interface web, moins d'algorithmes)
- Beta : l'API peut encore évoluer
- GRPO non inclus (à vérifier), moins d'algorithmes RL que TRL

## Alternatives
| Tool | Key Difference |
|------|---------------|
| LLaMA-Factory | Interface web, plus d'algorithmes, communauté plus grande |
| Axolotl | Config YAML similaire mais plus de méthodes et plus actif |
| PEFT + Trainer | Écosystème HuggingFace, plus populaire |
| LitGPT | Similaire philosophie PyTorch, Lightning backend |

## References
- [GitHub Repository](https://github.com/pytorch/torchtune)
- [Documentation officielle](https://pytorch.org/torchtune/stable/)
- [Blog PyTorch](https://pytorch.org/blog/torchtune-fine-tune-llms/)
- [Tutoriels](https://pytorch.org/torchtune/stable/tutorials/index.html)

## Notes
- Projet actif avec backing PyTorch officiel, maturité croissante
- Licence BSD est la plus permissive de tous les outils listés
- Philosophie "batteries not included" : code simple, pas de magie cachée
- Idéal pour les équipes déjà dans l'écosystème PyTorch natif
