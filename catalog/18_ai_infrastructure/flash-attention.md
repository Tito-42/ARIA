# Flash Attention

> Algorithme d'attention IO-aware — 2-4x plus rapide, utilisé dans tout l'écosystème LLM. Tri Dao.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 18 - AI Infrastructure / Kernel Optimization |
| **URL** | https://github.com/Dao-AILab/flash-attention |
| **GitHub** | https://github.com/Dao-AILab/flash-attention |
| **Stars** | ~18,000+ |
| **License** | BSD-3 |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Flash Attention est l'algorithme d'attention le plus important depuis le Transformer original. Développé par Tri Dao, il réduit la complexité mémoire de O(N²) à O(N) et accélère l'attention de 2-4x grâce à une utilisation IO-aware du GPU (tiling, kernel fusion). Intégré dans PyTorch, vLLM, HuggingFace Transformers, et tout l'écosystème LLM.

## Key Features
- **IO-aware**: Optimise les accès mémoire GPU (SRAM vs HBM)
- **2-4x speedup**: Accélération significative de l'attention
- **O(N) memory**: Réduit la mémoire de quadratique à linéaire
- **Flash Attention 3**: Support Hopper (H100), FP8
- **Universellement adopté**: PyTorch, vLLM, HF Transformers

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | Standard, universellement utilisé |
| **Security** | 5 | BSD-3 |
| **Scalability** | 5 | Accélère tous les modèles Transformer |
| **Support/Community** | 5 | Tri Dao, 18k+ stars |
| **Documentation** | 3 | Paper + README |
| **Integration Ease** | 5 | Intégré dans PyTorch et HF |

## Use Cases
1. **Training accéléré** — Entraîner des LLMs plus vite
2. **Inference optimisée** — Réduire la latence d'inférence
3. **Long context** — Supporter des contextes plus longs (mémoire réduite)

## Getting Started
```python
# Automatiquement utilisé par PyTorch et HuggingFace Transformers
# Ou directement:
from flash_attn import flash_attn_func
output = flash_attn_func(q, k, v, causal=True)
```

## Architecture / How It Works
Flash Attention tile les matrices Q, K, V en blocs qui tiennent dans le SRAM GPU (rapide). L'algorithme calcule l'attention par blocs avec une correction online du softmax, évitant de matérialiser la matrice d'attention N×N complète en mémoire HBM (lente).

## Strengths
- Innovation fondamentale, universellement adoptée
- 2-4x speedup
- Mémoire O(N) au lieu de O(N²)
- BSD-3

## Limitations
- NVIDIA-focused (Ampere+)
- Pas de support AMD/Intel natif
- Kernels CUDA spécialisés

## Alternatives
| Tool | Key Difference |
|------|---------------|
| FlashInfer | Spécialisé serving, PagedAttention |
| xFormers | Meta, memory-efficient attention |

## References
- https://github.com/Dao-AILab/flash-attention
- https://arxiv.org/abs/2205.14135
- https://arxiv.org/abs/2307.08691 (Flash Attention 2)
