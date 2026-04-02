# Unsloth

> Fine-tuning LLM 2x plus rapide avec 70% moins de VRAM grâce à des optimisations kernel custom

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 06_finetuning_training |
| **URL** | https://github.com/unslothai/unsloth |
| **GitHub** | https://github.com/unslothai/unsloth |
| **Stars** | 58,800 |
| **License** | Apache 2.0 (core) / AGPL-3.0 (certains modules) |
| **Pricing** | Free / Open Source (Unsloth Pro disponible) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Unsloth est une bibliothèque de fine-tuning spécialement conçue pour maximiser les performances sur GPU consommateur (RTX 3090, 4090, A100 etc.). Elle propose des optimisations kernel custom en Triton/CUDA qui réduisent la consommation mémoire de 70% tout en doublant la vitesse d'entraînement par rapport à une configuration HuggingFace standard.

La bibliothèque s'intègre nativement avec l'écosystème HuggingFace (transformers, PEFT, TRL, datasets) et supporte les algorithmes modernes : SFT, DPO, GRPO, KTO. Elle est particulièrement populaire pour fine-tuner des modèles sur des machines locales ou des GPU cloud modestes (T4, L4, A100 40GB).

Unsloth représente le standard de facto pour le fine-tuning efficace en mémoire en 2026, notamment sur du hardware consommateur. Ses notebooks Colab gratuits permettent à quiconque d'accéder à cette technologie sans investissement en infrastructure.

## Key Features
- **Vitesse 2x** : optimisations custom Triton/CUDA pour attention et backward pass
- **-70% VRAM** : quantization 4-bit et optimisations mémoire avancées
- **QLoRA optimisé** : implémentation custom surpassant bitsandbytes standard
- **Intégration native HF** : drop-in replacement pour transformers + PEFT + TRL
- **Multi-algorithmes** : SFT, DPO, GRPO, KTO, PPO
- **Modèles supportés** : LLaMA 3, Mistral, Qwen, Gemma, Phi, DeepSeek, et plus
- **Notebooks Colab** : exemples prêts à l'emploi pour chaque modèle majeur
- **GGUF export** : export direct pour Ollama/llama.cpp
- **Vision fine-tuning** : support multimodal (images + texte)

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Très utilisé en production, mais licence mixte à vérifier |
| **Security** | 3 | Outil local, pas de surface réseau, licence AGPL à valider pour usage commercial |
| **Scalability** | 3 | Optimisé GPU unique/paires, moins adapté aux clusters massifs que DeepSpeed |
| **Support/Community** | 5 | Communauté très active, Discord animé, réponses rapides des mainteneurs |
| **Documentation** | 4 | Notebooks excellents, wiki clair, mais doc API moins fournie |
| **Integration Ease** | 5 | Drop-in replacement HuggingFace, migration en 2 lignes de code |

## Use Cases
1. **Fine-tuning sur GPU consommateur** : adapter un LLM 7B-70B sur une seule RTX 4090 ou A100
2. **Fine-tuning Colab gratuit** : utiliser les notebooks Unsloth pour expérimenter sans coût
3. **GRPO / RL training** : entraîner des modèles de raisonnement style DeepSeek-R1 efficacement
4. **Production cost reduction** : réduire les coûts de fine-tuning cloud en utilisant moins de GPU
5. **Vision-language models** : fine-tuner des modèles multimodaux (LLaVA, Qwen-VL, etc.)

## Getting Started
```bash
# Installation (avec support CUDA)
pip install unsloth

# Installation avec extras
pip install "unsloth[colab-new]"  # Pour Google Colab
pip install "unsloth[cu121]"       # Pour CUDA 12.1

# Exemple minimal SFT
from unsloth import FastLanguageModel
model, tokenizer = FastLanguageModel.from_pretrained(
    model_name="unsloth/llama-3-8b-bnb-4bit",
    max_seq_length=2048,
    load_in_4bit=True,
)
model = FastLanguageModel.get_peft_model(model, r=16)
```

## Architecture / How It Works
```
Unsloth Architecture
├── Kernel Layer (Triton/CUDA)
│   ├── Flash Attention 2 custom    →  2x speedup attention
│   ├── Optimized backward pass     →  30% less compute
│   └── Custom QLoRA kernels        →  70% less VRAM
├── Model Layer
│   ├── FastLanguageModel           →  Drop-in pour AutoModelForCausalLM
│   └── FastVisionModel             →  Support multimodal
└── Training Layer (via TRL/HF)
    ├── SFTTrainer                  →  Supervised fine-tuning
    ├── DPOTrainer                  →  Direct Preference Optimization
    └── GRPOTrainer                 →  Group Relative Policy Optimization
```

## Strengths
- Performance inégalée sur GPU consommateur (2x vitesse, 70% moins VRAM)
- Intégration transparente avec l'écosystème HuggingFace existant
- Notebooks Colab prêts à l'emploi pour chaque modèle majeur
- Support rapide des nouvelles techniques (GRPO, vision, etc.)
- Communauté très active et mainteneurs réactifs

## Limitations
- Licence mixte : core Apache 2.0, mais certains modules avancés sous AGPL-3.0 (à vérifier pour usage commercial)
- Moins flexible pour architectures de modèles très custom
- Optimisé pour GPU unique ou paires, pas pour clusters multi-nœuds massifs
- Dépendant de kernels spécifiques (peut ne pas fonctionner sur toutes les architectures GPU)

## Alternatives
| Tool | Key Difference |
|------|---------------|
| LLaMA-Factory | Plus d'algorithmes et de modèles, mais plus lent |
| PEFT (HuggingFace) | Standard de facto mais sans les optimisations kernel |
| TRL | Bibliothèque algo-centric, complémentaire plutôt que concurrent |
| DeepSpeed | Pour clusters multi-GPU, pas optimisé GPU unique |

## References
- [GitHub Repository](https://github.com/unslothai/unsloth)
- [Documentation officielle](https://docs.unsloth.ai)
- [Notebooks Colab](https://github.com/unslothai/unsloth?tab=readme-ov-file#-finetune-for-free)
- [Discord communauté](https://discord.gg/unsloth)

## Notes
- Version Pro disponible avec features supplémentaires (multi-GPU optimisé, support commercial)
- La licence AGPL de certains modules doit être vérifiée avant déploiement commercial
- Benchmarks publiés sur le repo GitHub montrent les gains de performance mesurés
- Compatible avec Google Colab T4 gratuit pour des modèles jusqu'à 7B en 4-bit
