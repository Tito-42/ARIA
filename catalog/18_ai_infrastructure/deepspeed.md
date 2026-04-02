# DeepSpeed (Microsoft)

> Bibliothèque d'optimisation pour training et inference distribués — ZeRO, DeepSpeed-Inference, MoE.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 18 - AI Infrastructure / Distributed Training |
| **URL** | https://www.deepspeed.ai |
| **GitHub** | https://github.com/microsoft/DeepSpeed |
| **Stars** | ~36,000+ |
| **License** | Apache 2.0 |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Enterprise |

## What It Does
DeepSpeed est la bibliothèque de Microsoft pour le training et l'inference distribués. L'innovation ZeRO (Zero Redundancy Optimizer) permet d'entraîner des modèles 10x plus grands sur le même hardware en partitionnant les états de l'optimizer, les gradients et les paramètres entre les GPUs.

## Key Features
- **ZeRO Stage 1-3**: Partitionnement progressif mémoire
- **ZeRO-Offload**: Offload CPU/NVMe pour gros modèles
- **DeepSpeed-Inference**: Inference optimisée
- **MoE support**: Training de Mixture of Experts
- **DeepSpeed-Chat**: Pipeline RLHF
- **HuggingFace intégré**: Accelerate, Trainer

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | Enterprise, Microsoft |
| **Security** | 5 | Apache 2.0, Microsoft |
| **Scalability** | 5 | Multi-GPU, multi-node, ZeRO |
| **Support/Community** | 5 | 36k+ stars, Microsoft |
| **Documentation** | 4 | Docs complètes |
| **Integration Ease** | 4 | HuggingFace Accelerate, Trainer |

## Use Cases
1. **LLM training** — Entraîner des LLMs avec ZeRO
2. **Distributed training** — Multi-GPU/multi-node
3. **Memory optimization** — Entraîner des modèles trop gros pour un seul GPU

## Getting Started
```python
# Avec HuggingFace Accelerate
accelerate launch --use_deepspeed train.py
# Ou dans le Trainer
trainer = Trainer(model=model, args=TrainingArguments(deepspeed="ds_config.json"))
```

## Strengths
- ZeRO = innovation majeure du distributed training
- Microsoft enterprise backing
- Apache 2.0
- HuggingFace intégré

## Limitations
- Configuration ZeRO peut être complexe
- Debugging distribué difficile
- NVIDIA-focused principalement

## Alternatives
| Tool | Key Difference |
|------|---------------|
| FSDP (PyTorch) | Built-in PyTorch, plus simple |
| Megatron-LM | NVIDIA, model parallelism |
| Colossal-AI | Alternative chinoise |

## References
- https://www.deepspeed.ai
- https://github.com/microsoft/DeepSpeed
