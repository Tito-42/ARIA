# bitsandbytes

> Bibliothèque de quantization pour LLMs — INT8, INT4, NF4 pour réduire l'empreinte mémoire.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 18 - AI Infrastructure / Quantization |
| **URL** | https://github.com/bitsandbytes-foundation/bitsandbytes |
| **GitHub** | https://github.com/bitsandbytes-foundation/bitsandbytes |
| **Stars** | ~14,000+ |
| **License** | MIT |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
bitsandbytes permet de charger et fine-tuner des LLMs en quantization 8-bit et 4-bit (NF4) directement dans PyTorch. C'est le backend de quantization par défaut de HuggingFace Transformers pour QLoRA et le chargement de modèles en mémoire réduite.

## Key Features
- **INT8 inference**: Chargement de modèles en 8-bit
- **NF4 quantization**: 4-bit pour QLoRA
- **HuggingFace intégré**: `load_in_4bit=True`
- **Optimizer 8-bit**: Adam 8-bit pour réduire la mémoire de training
- **MIT licence**: Aucune restriction

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Standard pour quantization HF |
| **Security** | 5 | MIT |
| **Scalability** | 3 | Single-GPU principalement |
| **Support/Community** | 4 | 14k+ stars |
| **Documentation** | 3 | README, HF docs |
| **Integration Ease** | 5 | 1 paramètre dans HF Transformers |

## Use Cases
1. **Réduction mémoire** — Charger des gros modèles sur des GPU plus petits
2. **QLoRA** — Fine-tuning en 4-bit quantization
3. **Inference économique** — Inférence à moindre coût mémoire

## Getting Started
```python
from transformers import AutoModelForCausalLM
model = AutoModelForCausalLM.from_pretrained("meta-llama/Llama-3-8B", load_in_4bit=True)
```

## Strengths
- Standard pour quantization dans HuggingFace
- 1 ligne de code pour activer
- MIT licence
- QLoRA support

## Limitations
- NVIDIA principalement
- Perte de qualité avec forte quantization
- Inference plus lente que FP16

## Alternatives
| Tool | Key Difference |
|------|---------------|
| GPTQ | Quantization post-training, plus précise |
| AWQ | Activation-aware, meilleure qualité |
| GGUF/llama.cpp | Multi-hardware, format standardisé |

## References
- https://github.com/bitsandbytes-foundation/bitsandbytes
