# DeepSpeed

> Bibliothèque d'optimisation deep learning par Microsoft pour training distribué à grande échelle

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 06_finetuning_training |
| **URL** | https://www.deepspeed.ai |
| **GitHub** | https://github.com/microsoft/DeepSpeed |
| **Stars** | 42,000 |
| **License** | Apache 2.0 |
| **Pricing** | Free / Open Source |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Enterprise |

## What It Does
DeepSpeed est une bibliothèque d'optimisation deep learning développée par Microsoft Research. Elle est devenue le standard industrie pour l'entraînement distribué de modèles de grande taille. Son innovation principale est le système ZeRO (Zero Redundancy Optimizer) qui permet de distribuer états d'optimiseur, gradients et paramètres entre les GPU, réduisant considérablement l'empreinte mémoire par GPU.

DeepSpeed propose trois niveaux ZeRO : ZeRO-1 (partitionnement états optimiseur), ZeRO-2 (+ gradients), ZeRO-3 (+ paramètres). ZeRO-3 permet théoriquement de fine-tuner des modèles de taille arbitraire en partitionnant les paramètres sur tous les GPU disponibles. Il supporte aussi le pipeline parallelism, tensor parallelism et l'offloading CPU/NVMe.

Intégré nativement dans HuggingFace Trainer, LLaMA-Factory, Axolotl et la majorité des frameworks de fine-tuning, DeepSpeed est un composant infrastructure essentiel pour tout projet de fine-tuning LLM à grande échelle en contexte enterprise.

## Key Features
- **ZeRO Stage 1/2/3** : partitionnement progressif pour réduction mémoire
- **ZeRO-Infinity** : offloading CPU et NVMe pour modèles dépassant la VRAM totale
- **Pipeline Parallelism** : découpage du modèle en étapes de pipeline
- **Tensor Parallelism** : via intégration Megatron-LM
- **Mixed Precision** : FP16, BF16, FP8 support
- **Gradient Checkpointing** : échange temps/mémoire configurable
- **Communication optimization** : NCCL, MPI, allreduce optimisé
- **DeepSpeed-Chat** : pipeline RLHF complet intégré
- **Monitoring intégré** : métriques détaillées d'utilisation mémoire/compute

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | Standard industrie, déployé par Microsoft, Meta, AWS et autres |
| **Security** | 4 | Projet Microsoft, maintenu activement, pas de surface d'attaque réseau |
| **Scalability** | 5 | Conçu pour des clusters de milliers de GPU, ZeRO-Infinity sans limite théorique |
| **Support/Community** | 4 | Support Microsoft + communauté active, issues répondues |
| **Documentation** | 4 | Documentation complète sur deepspeed.ai, exemples nombreux |
| **Integration Ease** | 3 | Configuration JSON complexe, debugging distribué difficile, courbe d'apprentissage |

## Use Cases
1. **Fine-tuning modèles 70B+** : utiliser ZeRO-3 pour fine-tuner des modèles qui ne tiennent pas en mémoire sur un seul nœud
2. **Pre-training LLM** : entraîner des modèles from scratch sur des clusters GPU massifs
3. **RLHF à grande échelle** : via DeepSpeed-Chat pour le pipeline complet SFT + RM + RLHF
4. **Réduction coûts cloud** : maximiser l'utilisation GPU pour réduire le nombre de machines nécessaires
5. **Research reproductible** : configuration standardisée pour comparer des approches d'entraînement

## Getting Started
```bash
# Installation
pip install deepspeed

# Vérification installation
ds_report

# Lancement training avec config ZeRO-2
deepspeed train.py --deepspeed ds_config_zero2.json

# Config ZeRO-3 minimale (ds_config_zero3.json)
{
  "zero_optimization": {
    "stage": 3,
    "offload_optimizer": {"device": "cpu"},
    "offload_param": {"device": "cpu"}
  },
  "bf16": {"enabled": true},
  "train_batch_size": 32
}
```

## Architecture / How It Works
```
DeepSpeed Parallelism Stack
├── Data Parallelism (ZeRO)
│   ├── ZeRO Stage 1  →  Partitionne états optimiseur
│   ├── ZeRO Stage 2  →  + Partitionne gradients
│   ├── ZeRO Stage 3  →  + Partitionne paramètres
│   └── ZeRO-Infinity →  + Offload CPU/NVMe
├── Pipeline Parallelism →  Découpage modèle en micro-batches
├── Tensor Parallelism   →  Via Megatron-LM integration
└── Communication Layer
    ├── NCCL (GPU-GPU)
    ├── MPI (nœud-à-nœud)
    └── Infinity (RAM/NVMe)
```

## Strengths
- Standard industrie reconnu pour le training distribué
- ZeRO-3 permet de fine-tuner des modèles de taille arbitraire
- Très bien intégré dans les frameworks majeurs (HF Trainer, LLaMA-Factory, Axolotl)
- Support Microsoft garantit la pérennité du projet
- ZeRO-Infinity ouvre le fine-tuning à des machines sans GPU dédié via CPU offload

## Limitations
- Configuration JSON complexe, courbe d'apprentissage significative
- Debugging de problèmes distribués particulièrement difficile
- Peut introduire de la latence par rapport à un entraînement single-GPU bien optimisé
- Certaines fonctionnalités avancées (Tensor Parallelism) nécessitent Megatron-LM

## Alternatives
| Tool | Key Difference |
|------|---------------|
| FSDP (PyTorch) | Native PyTorch, plus simple mais moins de features que ZeRO-3 |
| Megatron-LM | Parallelism plus avancé, mais encore plus complexe |
| Accelerate (HF) | Abstraction de plus haut niveau, peut utiliser DeepSpeed en backend |
| torchtune | Plus simple mais pas conçu pour les très grandes échelles |

## References
- [Site officiel](https://www.deepspeed.ai)
- [GitHub Repository](https://github.com/microsoft/DeepSpeed)
- [Documentation ZeRO](https://www.deepspeed.ai/tutorials/zero/)
- [Paper ZeRO arXiv](https://arxiv.org/abs/1910.02054)
- [DeepSpeed-Chat](https://github.com/microsoft/DeepSpeed/tree/master/blogs/deepspeed-chat)

## Notes
- Intégration HuggingFace Trainer via argument `--deepspeed config.json`
- ZeRO-Offload permet de fine-tuner un modèle 10B sur un seul GPU avec CPU offloading
- Configuration recommandée pour débuter : ZeRO Stage 2 avec BF16
- Très utilisé en combinaison avec Axolotl ou LLaMA-Factory pour le fine-tuning enterprise
