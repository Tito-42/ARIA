# Megatron-LM

> Framework NVIDIA de training distribué pour modèles de langage à très grande échelle avec tensor/pipeline/sequence parallelism

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 06_finetuning_training |
| **URL** | https://github.com/NVIDIA/Megatron-LM |
| **GitHub** | https://github.com/NVIDIA/Megatron-LM |
| **Stars** | 15,900 |
| **License** | Apache 2.0 |
| **Pricing** | Free / Open Source |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Enterprise |

## What It Does
Megatron-LM est un framework de training distribué développé par NVIDIA Research, conçu spécifiquement pour entraîner des modèles de langage de très grande taille (10B à 1T+ paramètres). Il est la référence pour le pré-entraînement de LLMs à l'échelle des data centers et a été utilisé pour entraîner les modèles Megatron-Turing NLG, ainsi que comme backend pour de nombreux LLMs propriétaires.

Sa contribution principale est la combinaison orthogonale de trois formes de parallelism : tensor parallelism (découper les matrices sur plusieurs GPU), pipeline parallelism (découper les couches en étages), et sequence parallelism (découper les séquences). Cette combinaison "3D parallelism" permet de scaler le training de manière quasi-linéaire sur des milliers de GPU.

Megatron-LM sert également de backend bas niveau pour NVIDIA NeMo, ce qui le positionne au cœur de l'infrastructure d'entraînement NVIDIA. Version v0.16.1 (mars 2026).

## Key Features
- **Tensor Parallelism** : partition des matrices de poids sur N GPU
- **Pipeline Parallelism** : découpage du modèle en étages de pipeline
- **Sequence Parallelism** : partition des séquences pour activation memory
- **3D Parallelism** : combinaison orthogonale des trois méthodes
- **Flash Attention** : support Flash Attention 2/3 pour efficacité mémoire
- **Distributed optimizer** : gradient sharding entre GPU de données
- **Selective activation recomputation** : trade-off mémoire/compute configurable
- **ROPE / Grouped Query Attention** : support des innovations modernes d'architecture
- **Checkpointing distribué** : sauvegarde efficace de checkpoints à grande échelle
- **FP8 training** : support H100 FP8 pour efficacité maximale

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | Utilisé en production pour entraîner des modèles frontier, très stable |
| **Security** | 4 | NVIDIA officiel, déploiement on-premise typique, pas de surface réseau externe |
| **Scalability** | 5 | Conçu pour des milliers de GPU, référence scalabilité LLM training |
| **Support/Community** | 3 | Communauté de recherche, pas de support grand public facilement accessible |
| **Documentation** | 3 | Documentation technique suffisante mais orientée experts |
| **Integration Ease** | 2 | Très complexe, nécessite expertise distributed systems et NVIDIA |

## Use Cases
1. **Pre-training LLM from scratch** : entraîner un modèle 70B-1T sur un cluster NVIDIA multi-nœuds
2. **Fine-tuning de modèles géants** : adapter un modèle 100B+ sur des données spécialisées
3. **Research sur le scaling** : étudier les scaling laws et l'architecture de modèles à très grande échelle
4. **Infrastructure LLM propriétaire** : construire la pile d'entraînement interne d'une organisation
5. **Backend NeMo** : utilisé en interne par NVIDIA NeMo pour les workloads d'entraînement

## Getting Started
```bash
# Prérequis : cluster NVIDIA multi-GPU
# Cloner le repo
git clone https://github.com/NVIDIA/Megatron-LM.git
cd Megatron-LM

# Installation des dépendances
pip install -r requirements.txt

# Lancement d'un entraînement GPT distribué
# (exemple avec 8 GPU, tensor parallelism=2, pipeline=2)
torchrun \
    --nproc_per_node=8 \
    pretrain_gpt.py \
    --tensor-model-parallel-size 2 \
    --pipeline-model-parallel-size 2 \
    --num-layers 32 \
    --hidden-size 4096 \
    --num-attention-heads 32 \
    --seq-length 4096 \
    --train-iters 500000
```

## Architecture / How It Works
```
Megatron-LM 3D Parallelism
┌─────────────────────────────────────────────────────┐
│  Data Parallel Groups (copies complètes du modèle)  │
│                                                     │
│  ┌─────────────── Pipeline Stage 1 ──────────────┐  │
│  │  TP GPU 0  │  TP GPU 1  │  TP GPU 2  │ TP GPU3│  │
│  │  Couches   │  Couches   │  Couches   │ Couches│  │
│  │  0-7       │  0-7       │  0-7       │  0-7  │  │
│  └────────────────────────────────────────────────┘  │
│  ┌─────────────── Pipeline Stage 2 ──────────────┐  │
│  │  TP GPU 4  │  TP GPU 5  │  TP GPU 6  │ TP GPU7│  │
│  │  Couches   │  Couches   │  Couches   │ Couches│  │
│  │  8-15      │  8-15      │  8-15      │  8-15 │  │
│  └────────────────────────────────────────────────┘  │
└─────────────────────────────────────────────────────┘
TP = Tensor Parallelism (matrices découpées sur ces GPU)
PP = Pipeline Parallelism (couches différentes)
DP = Data Parallelism (batches différents)
```

## Strengths
- Référence absolue pour le training de modèles 100B+ paramètres
- 3D parallelism permet un scaling quasi-linéaire sur des milliers de GPU
- Optimisations NVIDIA de premier ordre (Flash Attention, FP8, kernels custom)
- Utilisé par NVIDIA, Microsoft, et d'autres leaders pour leurs modèles frontier
- Intégration native avec NeMo pour un pipeline complet

## Limitations
- Extrêmement complexe à configurer et déboguer
- Nécessite une infrastructure multi-GPU NVIDIA significative
- Pas adapté pour les utilisateurs individuels ou les petits projets
- Courbe d'apprentissage très raide, expertise distributed systems requise
- Documentation principalement orientée recherche/experts

## Alternatives
| Tool | Key Difference |
|------|---------------|
| DeepSpeed | Plus accessible, ZeRO parallelism, multi-framework |
| FSDP (PyTorch) | Native PyTorch, plus simple mais moins performant pour très gros modèles |
| ColossalAI | Alternative communautaire, plus accessible |
| NeMo | Surcouche Megatron-LM avec interface plus accessible |

## References
- [GitHub Repository](https://github.com/NVIDIA/Megatron-LM)
- [Paper Megatron-LM](https://arxiv.org/abs/1909.08053)
- [Paper Megatron-LM v2 (pipeline parallelism)](https://arxiv.org/abs/2104.04473)
- [Paper Sequence Parallelism](https://arxiv.org/abs/2205.05198)
- [Release v0.16.1](https://github.com/NVIDIA/Megatron-LM/releases)

## Notes
- Version v0.16.1 (mars 2026), développement continu
- Utilisé comme base pour Megatron-Turing NLG 530B (Microsoft + NVIDIA)
- À utiliser via NeMo si possible pour une interface plus accessible
- Le support FP8 sur H100 représente une avancée majeure pour l'efficacité énergétique
