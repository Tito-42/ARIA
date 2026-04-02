# LitGPT

> Framework Lightning AI pour pretrain, fine-tune et déployer des LLMs avec 20+ architectures supportées

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 06_finetuning_training |
| **URL** | https://github.com/Lightning-AI/litgpt |
| **GitHub** | https://github.com/Lightning-AI/litgpt |
| **Stars** | 13,300 |
| **License** | Apache 2.0 |
| **Pricing** | Free / Open Source |
| **Last Verified** | 2026-04-01 |
| **Status** | Maintained |
| **Maturity** | Production |

## What It Does
LitGPT est un framework de Lightning AI permettant de pré-entraîner, fine-tuner et déployer des LLMs de manière simple et lisible. Contrairement à d'autres frameworks qui utilisent des bibliothèques externes complexes, LitGPT implémente les architectures de modèles directement en code PyTorch pur via Lightning, ce qui rend le code extrêmement lisible et hackable.

Le projet supporte plus de 20 architectures LLM incluant LLaMA, Mistral, Gemma, Phi, Falcon et d'autres, avec une implémentation cohérente et bien documentée pour chacune. Il inclut des méthodes de fine-tuning comme LoRA, QLoRA, adapter et full fine-tuning.

LitGPT est particulièrement adapté au prototypage et à la recherche où la lisibilité du code compte plus que la performance maximale. Son intégration dans l'écosystème Lightning facilite le scaling vers des clusters multi-GPU.

## Key Features
- **20+ architectures** : LLaMA 3, Mistral, Gemma, Phi, Falcon, CodeLlama, etc.
- **LoRA / QLoRA** : fine-tuning PEFT intégré
- **Full fine-tuning** : support entraînement complet des poids
- **Pre-training** : capacité d'entraîner des modèles from scratch
- **Lightning Fabric** : scaling multi-GPU/multi-nœud via Lightning
- **Code clair** : implémentations ~1000 lignes par modèle, lisibles
- **Quantization** : support GPTQ et bitsandbytes
- **Chat interface** : interface interactive pour tester les modèles
- **Déploiement** : export et serving intégrés

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 3 | Utilisable en production, mais moins battle-tested que LLaMA-Factory |
| **Security** | 3 | Projet open source, pas d'audit formel, mais code lisible et vérifiable |
| **Scalability** | 3 | Lightning Fabric pour multi-GPU, mais pas optimisé pour très large échelle |
| **Support/Community** | 3 | Communauté Lightning AI, mais moins actif récemment (dernier commit jan 2025) |
| **Documentation** | 4 | Documentation claire, tutoriels bien écrits |
| **Integration Ease** | 4 | API simple et cohérente, bien intégré Lightning ecosystem |

## Use Cases
1. **Prototypage rapide** : tester rapidement une idée de fine-tuning sur un nouveau modèle
2. **Recherche LLM** : comprendre les détails d'implémentation via code clair et lisible
3. **Pre-training from scratch** : entraîner un petit LLM custom sur données propriétaires
4. **Éducation** : apprendre le fonctionnement des LLMs via du code propre
5. **Fine-tuning Lightning** : utiliser l'écosystème Lightning pour training organisationnel

## Getting Started
```bash
# Installation
pip install litgpt

# Télécharger un modèle
litgpt download meta-llama/Llama-3.2-3B-Instruct

# Fine-tuning LoRA
litgpt finetune_lora meta-llama/Llama-3.2-3B-Instruct \
    --data Alpaca \
    --out_dir out/lora

# Chat avec le modèle
litgpt chat meta-llama/Llama-3.2-3B-Instruct

# Pre-training from scratch
litgpt pretrain --config config.yaml
```

## Architecture / How It Works
```
LitGPT Architecture
├── Model Implementations (PyTorch pur)
│   ├── llama.py        →  Famille LLaMA 1/2/3
│   ├── mistral.py      →  Famille Mistral
│   ├── gemma.py        →  Famille Gemma
│   └── ...             →  20+ architectures
├── Training Scripts
│   ├── pretrain.py     →  Pre-training from scratch
│   ├── finetune_lora.py →  LoRA fine-tuning
│   └── finetune_full.py →  Full fine-tuning
├── Lightning Fabric     →  Multi-GPU scaling transparent
└── Utils
    ├── download.py     →  Téléchargement depuis HF Hub
    └── chat.py         →  Interface interactive
```

## Strengths
- Code extrêmement lisible et bien structuré, idéal pour l'apprentissage
- Intégration naturelle avec l'écosystème Lightning AI
- Support large d'architectures avec implémentations cohérentes
- API simple et intuitive pour les opérations courantes
- Bon pour le prototypage avant de passer à des frameworks plus lourds

## Limitations
- Moins actif récemment (dernier commit majeur janvier 2025)
- Communauté plus petite que LLaMA-Factory ou Axolotl
- Moins de features avancées (GRPO, RLHF moins développés)
- Moins optimisé en performance pure que Unsloth

## Alternatives
| Tool | Key Difference |
|------|---------------|
| LLaMA-Factory | Plus d'algorithmes, interface web, communauté plus large |
| Axolotl | Plus de configurations, plus actif, YAML-driven |
| Unsloth | Beaucoup plus rapide, meilleur pour GPU consommateur |
| torchtune | PyTorch officiel, recettes similaires mais plus récent |

## References
- [GitHub Repository](https://github.com/Lightning-AI/litgpt)
- [Documentation](https://lightning.ai/docs/litgpt/stable/)
- [Lightning AI](https://lightning.ai)
- [Tutoriels](https://github.com/Lightning-AI/litgpt/tree/main/tutorials)

## Notes
- Développement moins actif depuis janvier 2025, à surveiller
- Excellent point d'entrée pédagogique avant d'utiliser des frameworks plus complexes
- Lightning Fabric (le core) est maintenu activement même si LitGPT l'est moins
- La lisibilité du code est intentionnelle et documentée : idéal pour comprendre les LLMs
