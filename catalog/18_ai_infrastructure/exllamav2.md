# ExLlamaV2

> Moteur d'inférence LLM avec quantization EXL2 optimisée — haute performance sur GPU consommateur.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 18 - AI Infrastructure / Quantized Inference |
| **URL** | https://github.com/turboderp/exllamav2 |
| **GitHub** | https://github.com/turboderp/exllamav2 |
| **Stars** | ~5,800 |
| **License** | MIT |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
ExLlamaV2 est un moteur d'inférence LLM spécialisé dans l'exécution de modèles quantizés (GPTQ, EXL2) sur GPU consommateur. Le format EXL2 permet une quantization mixte (différents bits par layer) pour un meilleur ratio qualité/taille.

## Key Features
- **EXL2 format**: Quantization mixte par layer
- **GPTQ support**: Compatible modèles GPTQ
- **GPU consommateur**: Optimisé pour RTX 3090/4090
- **Rapide**: Parmi les plus rapides pour quantized inference
- **MIT licence**: Aucune restriction

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 3 | Bon mais niche |
| **Security** | 5 | MIT |
| **Scalability** | 2 | Single-GPU |
| **Support/Community** | 3 | 5.8k stars |
| **Documentation** | 2 | README |
| **Integration Ease** | 3 | Python API |

## Use Cases
1. **LLM sur GPU consommateur** — Exécuter des gros modèles sur RTX 3090/4090
2. **Quantization mixte** — Optimiser le ratio qualité/taille

## Strengths
- Performance excellente sur GPU consommateur
- EXL2 quantization mixte innovante
- MIT

## Limitations
- NVIDIA-only
- Single-GPU
- Niche vs vLLM/llama.cpp

## Alternatives
| Tool | Key Difference |
|------|---------------|
| llama.cpp | Multi-hardware, GGUF |
| vLLM | Serving production |

## References
- https://github.com/turboderp/exllamav2
