# PEFT

> Bibliothèque HuggingFace pour le Parameter-Efficient Fine-Tuning (LoRA, QLoRA, AdaLoRA, IA3...)

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 06_finetuning_training |
| **URL** | https://huggingface.co/docs/peft/index |
| **GitHub** | https://github.com/huggingface/peft |
| **Stars** | 20,900 |
| **License** | Apache 2.0 |
| **Pricing** | Free / Open Source |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
PEFT (Parameter-Efficient Fine-Tuning) est la bibliothèque officielle de HuggingFace regroupant les méthodes d'ajustement fin qui ne modifient qu'une fraction des paramètres du modèle. Au lieu de fine-tuner tous les milliards de paramètres d'un LLM, PEFT entraîne seulement des adaptateurs légers (LoRA, prefixes, prompts appris...) ce qui réduit considérablement les besoins en mémoire et en calcul.

La méthode phare est LoRA (Low-Rank Adaptation) : plutôt que de modifier les matrices de poids du modèle, LoRA injecte deux petites matrices A et B dont le produit approxime la mise à jour souhaitée. QLoRA combine LoRA avec la quantification 4-bit pour rendre le fine-tuning encore plus accessible.

PEFT est le standard de facto pour le fine-tuning efficace dans l'écosystème HuggingFace. Il est utilisé comme brique de base par LLaMA-Factory, Axolotl, Unsloth, TRL et pratiquement tous les frameworks de fine-tuning modernes.

## Key Features
- **LoRA** : Low-Rank Adaptation, la méthode la plus populaire
- **QLoRA** : LoRA + quantification 4-bit (via bitsandbytes)
- **AdaLoRA** : allocation adaptative du rang selon l'importance des couches
- **DoRA** : Weight-Decomposed Low-Rank Adaptation (amélioration LoRA)
- **IA3** : méthode ultra-légère par mise à l'échelle d'activations
- **Prefix Tuning** : optimisation de prefixes de contexte
- **Prompt Tuning** : optimisation de soft prompts
- **P-Tuning** : variante de prompt tuning
- **Merging adapters** : fusion de plusieurs adaptateurs LoRA
- **GGUF/ONNX export** : export des adaptateurs pour déploiement

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | Standard de facto, v0.18.1, utilisé massivement en production |
| **Security** | 4 | Bibliothèque HuggingFace, maintenue activement, pas de surface réseau |
| **Scalability** | 4 | S'intègre avec DeepSpeed/FSDP pour multi-GPU, adaptateurs légers à partager |
| **Support/Community** | 5 | Soutien HuggingFace, communauté massive, documentation exemplaire |
| **Documentation** | 5 | Documentation HuggingFace de haute qualité, nombreux notebooks |
| **Integration Ease** | 5 | API simple, intégration native transformers, 2-3 lignes pour activer LoRA |

## Use Cases
1. **Fine-tuning LLM sur GPU modeste** : adapter un modèle 7B-70B sur une seule GPU avec QLoRA
2. **Multi-task learning** : créer plusieurs adaptateurs LoRA spécialisés pour différentes tâches sur le même modèle base
3. **Continual learning** : ajouter des adaptateurs pour de nouveaux domaines sans catastrophic forgetting
4. **Partage de modèles** : publier uniquement les poids LoRA (quelques MB) plutôt que le modèle entier (50+ GB)
5. **A/B testing de comportements** : switcher entre adaptateurs LoRA pour tester différents comportements

## Getting Started
```bash
# Installation
pip install peft

# LoRA en 3 lignes
from peft import get_peft_model, LoraConfig
config = LoraConfig(r=16, lora_alpha=32, target_modules=["q_proj", "v_proj"])
model = get_peft_model(model, config)

# QLoRA avec bitsandbytes
from transformers import BitsAndBytesConfig
bnb_config = BitsAndBytesConfig(load_in_4bit=True, bnb_4bit_compute_dtype="bfloat16")
model = AutoModelForCausalLM.from_pretrained("meta-llama/Llama-3-8B", quantization_config=bnb_config)
model = get_peft_model(model, LoraConfig(r=16))

# Sauvegarder l'adaptateur
model.save_pretrained("./my-lora-adapter")
```

## Architecture / How It Works
```
PEFT - LoRA Architecture
Base Model (frozen)           LoRA Adapter (trainable)
├── Attention Layer           ├── Matrix A (d × r)  où r << d
│   ├── Q weight (frozen)  +  ├── Matrix B (r × d)
│   ├── K weight (frozen)     └── ΔW = B × A (low-rank update)
│   └── V weight (frozen)
└── FFN Layers (frozen)

Paramètres entraînés : r × d × 2 au lieu de d × d
Exemple : r=16, d=4096 → 131K params vs 16.7M params (-99.2%)
```

## Strengths
- Standard de facto pour LoRA dans l'écosystème HuggingFace
- Réduction drastique des besoins en mémoire et calcul
- Adaptateurs portables : quelques MB au lieu de dizaines de GB
- API simple et bien documentée
- Intégration transparente avec transformers, TRL, Trainer

## Limitations
- Fortement couplé à l'écosystème HuggingFace transformers
- Performances légèrement inférieures au full fine-tuning dans certains cas
- Choix des `target_modules` et hyperparamètres (r, alpha) nécessite expérience
- Certaines méthodes (prefix tuning) moins efficaces que LoRA pour les LLMs

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Unsloth | Utilise PEFT mais avec kernels custom pour 2x speedup |
| LLaMA-Factory | Interface de plus haut niveau, utilise PEFT en interne |
| torchtune | Implémentation PyTorch native, alternative à transformers+PEFT |
| Adapters library | Plus de méthodes d'adaptation, moins populaire |

## References
- [Documentation officielle](https://huggingface.co/docs/peft/index)
- [GitHub Repository](https://github.com/huggingface/peft)
- [Paper LoRA](https://arxiv.org/abs/2106.09685)
- [Paper QLoRA](https://arxiv.org/abs/2305.14314)
- [HuggingFace Hub - adaptateurs LoRA](https://huggingface.co/models?other=lora)

## Notes
- Version actuelle : v0.18.1 (développement continu)
- Le Hub HuggingFace héberge des milliers d'adaptateurs LoRA prêts à l'emploi
- `LoraConfig` paramètres clés : `r` (rang), `lora_alpha` (scaling), `target_modules` (quelles matrices)
- DoRA (v0.9+) améliore LoRA en décomposant magnitude et direction des poids
