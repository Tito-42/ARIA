# OpenRLHF

> Framework RLHF/GRPO haute performance via Ray, supportant les modèles 70B+ sur clusters multi-GPU

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 06_finetuning_training |
| **URL** | https://github.com/OpenRLHF/OpenRLHF |
| **GitHub** | https://github.com/OpenRLHF/OpenRLHF |
| **Stars** | 9,300 |
| **License** | Apache 2.0 |
| **Pricing** | Free / Open Source |
| **Last Verified** | 2026-04-01 |
| **Status** | Maintained |
| **Maturity** | Beta |

## What It Does
OpenRLHF est un framework open source dédié à l'entraînement par renforcement à partir de feedback humain (RLHF) pour les LLMs. Sa caractéristique principale est l'utilisation de Ray pour l'orchestration distribuée, permettant de scaler le training RLHF à des modèles de 70B+ paramètres sur des clusters multi-GPU.

Le framework implémente PPO, GRPO, DPO et d'autres algorithmes RL pour l'alignment de LLMs. Il a été l'un des premiers frameworks open source à proposer une implémentation complète et scalable de PPO pour les LLMs de grande taille, avant que TRL et VERL ne le rattrapent.

Cependant, l'activité du projet a ralenti depuis janvier 2025, ce qui soulève des questions sur sa maintenance à long terme. VERL et TRL sont maintenant des alternatives plus actives pour les use cases similaires.

## Key Features
- **Ray-based** : orchestration distribuée via Ray pour scaling
- **PPO production** : implémentation PPO complète pour LLMs 70B+
- **GRPO natif** : support Group Relative Policy Optimization
- **DPO / SFT** : algorithmes d'alignment complets
- **Reward Model training** : pipeline complet SFT → RM → RLHF
- **vLLM integration** : génération de rollouts accélérée
- **Multi-nœuds** : support clusters distribués
- **Modèles larges** : optimisé pour 13B, 34B, 70B+

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 3 | Utilisable en production, mais activité ralentie |
| **Security** | 3 | Projet communautaire, pas d'audit formel |
| **Scalability** | 4 | Ray permet un scaling multi-nœuds robuste |
| **Support/Community** | 2 | Moins actif depuis janvier 2025, communauté plus petite |
| **Documentation** | 3 | Documentation fonctionnelle, pas exhaustive |
| **Integration Ease** | 3 | Setup Ray peut être complexe, moins accessible que TRL |

## Use Cases
1. **RLHF modèles 70B+** : fine-tuner des modèles très larges via PPO sur cluster multi-GPU
2. **Pipeline RLHF complet** : SFT → Reward Model → PPO en une seule infrastructure
3. **GRPO scaling** : entraîner des modèles de raisonnement sur des clusters existants Ray
4. **Reproduction papiers** : reproduire les résultats d'articles RLHF académiques
5. **Infrastructure Ray existante** : capitaliser sur une infra Ray déjà déployée

## Getting Started
```bash
# Installation
pip install openrlhf

# Avec Ray
pip install openrlhf[vllm]

# Initialiser Ray cluster
ray start --head

# Training PPO distribué
ray job submit --working-dir . -- \
    python -m openrlhf.cli.train_ppo \
    --pretrain meta-llama/Llama-3-8B \
    --reward_pretrain reward-model \
    --save_path ./checkpoint \
    --micro_train_batch_size 2 \
    --micro_rollout_batch_size 8 \
    --rollout_n_mbs 4

# Training GRPO
python -m openrlhf.cli.train_grpo \
    --pretrain meta-llama/Llama-3-8B \
    --reward_fn custom_reward.py \
    --save_path ./grpo-checkpoint
```

## Architecture / How It Works
```
OpenRLHF Architecture (Ray-based)
┌────────────────────────────────────────┐
│  Ray Cluster Orchestrator              │
└─────┬──────────┬──────────┬───────────┘
      │          │          │
┌─────▼──┐  ┌───▼───┐  ┌───▼────────┐
│ Actor  │  │Critic │  │  Reference │
│ Model  │  │ Model │  │   Model    │
│(Policy)│  │       │  │  (frozen)  │
└────┬───┘  └───┬───┘  └────────────┘
     │          │
┌────▼──────────▼──────────────┐
│   Rollout Engine (vLLM)       │
│   Génération trajectoires     │
└──────────────────────────────┘
     │
┌────▼──────────────────────────┐
│   Reward Model / Function     │
│   Calcul des récompenses      │
└───────────────────────────────┘
```

## Strengths
- Architecture Ray mature pour le scaling multi-nœuds
- L'un des premiers frameworks complets pour RLHF LLMs à grande échelle
- Support des modèles très larges (70B+) via Ray distributed
- Implémentation PPO de référence bien validée

## Limitations
- Activité ralentie depuis janvier 2025, maintenance incertaine
- Setup Ray complexe comparé à TRL ou VERL
- Communauté plus petite et moins active que les alternatives récentes
- Risque d'obsolescence face à VERL et TRL qui sont plus actifs

## Alternatives
| Tool | Key Difference |
|------|---------------|
| VERL (ByteDance) | Plus actif, architecture hybride vLLM/DeepSpeed, meilleure perf |
| TRL (HuggingFace) | Plus simple, écosystème HF, v1.0.0 stable |
| LLaMA-Factory | Plus accessible, interface web, multi-algorithmes |
| NeMo-Aligner | NVIDIA-specific, enterprise-grade, mieux maintenu |

## References
- [GitHub Repository](https://github.com/OpenRLHF/OpenRLHF)
- [Documentation](https://openrlhf.readthedocs.io)
- [Paper OpenRLHF](https://arxiv.org/abs/2405.11143)

## Notes
- Activité réduite depuis janvier 2025 : à considérer avant adoption
- Pour de nouveaux projets RLHF/GRPO, VERL ou TRL sont à privilégier
- L'architecture Ray reste une approche solide si l'infra Ray existe déjà
- Peut rester pertinent pour reproduire des résultats de papiers qui l'utilisent
