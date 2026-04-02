# TensorRT-LLM (NVIDIA)

> Moteur d'optimisation et serving LLM par NVIDIA — performance maximale sur GPU NVIDIA.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 18 - AI Infrastructure / Inference Optimization |
| **URL** | https://nvidia.github.io/TensorRT-LLM |
| **GitHub** | https://github.com/NVIDIA/TensorRT-LLM |
| **Stars** | ~12,000+ |
| **License** | Apache 2.0 |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Enterprise |

## What It Does
TensorRT-LLM est le moteur d'optimisation LLM de NVIDIA qui compile les modèles en engines TensorRT optimisés pour les GPU NVIDIA. Il atteint les meilleures performances absolues sur hardware NVIDIA (H100, A100, L40S) grâce à des optimisations de kernels spécifiques.

## Key Features
- **TensorRT compilation**: Optimisation maximale pour NVIDIA
- **FP8/INT4 quantization**: Quantization hardware-accelerated
- **Inflight batching**: Batching dynamique optimisé
- **Multi-GPU**: Tensor parallelism, pipeline parallelism
- **Triton integration**: Serving via Triton Inference Server
- **H100/B100 optimized**: Kernels dédiés latest gen

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | Enterprise NVIDIA, performance maximale |
| **Security** | 5 | Apache 2.0, NVIDIA enterprise |
| **Scalability** | 5 | Multi-GPU, multi-node |
| **Support/Community** | 4 | NVIDIA backing |
| **Documentation** | 3 | Docs NVIDIA |
| **Integration Ease** | 2 | Compilation complexe, NVIDIA-only |

## Use Cases
1. **Maximum throughput** — Quand la performance absolue est critique
2. **NVIDIA enterprise** — Déploiements sur hardware NVIDIA dédié
3. **Multi-GPU serving** — Serving distribué sur clusters GPU

## Getting Started
```python
# Build engine
from tensorrt_llm import LLM
llm = LLM(model="meta-llama/Llama-3-8B-Instruct")
output = llm.generate(["Hello, how are you?"])
```

## Strengths
- Performance absolue maximale sur NVIDIA
- Quantization hardware-accelerated
- NVIDIA enterprise support
- Apache 2.0

## Limitations
- **NVIDIA-only** — pas d'AMD/Intel/Apple
- Compilation complexe et longue
- Setup non trivial

## Alternatives
| Tool | Key Difference |
|------|---------------|
| vLLM | Plus simple, multi-hardware, performance proche |
| SGLang | Meilleur prefix caching |
| llama.cpp | Multi-hardware, local |

## References
- https://nvidia.github.io/TensorRT-LLM
- https://github.com/NVIDIA/TensorRT-LLM
