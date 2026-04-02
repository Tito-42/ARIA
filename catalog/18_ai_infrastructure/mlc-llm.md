# MLC LLM

> Déploiement LLM multi-plateforme via compilation ML — iOS, Android, WebGPU, GPU, CPU.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 18 - AI Infrastructure / Cross-Platform Inference |
| **URL** | https://llm.mlc.ai |
| **GitHub** | https://github.com/mlc-ai/mlc-llm |
| **Stars** | ~20,000+ |
| **License** | Apache 2.0 |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
MLC LLM utilise la compilation ML (Apache TVM) pour déployer des LLMs sur toute plateforme : iOS, Android, navigateur (WebGPU), GPU NVIDIA/AMD, Apple Metal, et CPU. Un seul modèle compilé fonctionne nativement sur chaque plateforme.

## Key Features
- **Multi-plateforme**: iOS, Android, WebGPU, GPU, CPU
- **Apache TVM**: Compilation ML optimisée par plateforme
- **WebGPU**: LLMs dans le navigateur
- **Quantization**: Support quantization pour mobile
- **Apache 2.0**: Licence permissive

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 3 | Production mais niche |
| **Security** | 4 | Apache 2.0, local |
| **Scalability** | 3 | Multi-plateforme |
| **Support/Community** | 3 | 20k+ stars |
| **Documentation** | 3 | Docs MLC |
| **Integration Ease** | 3 | Setup compilation |

## Use Cases
1. **Mobile AI** — LLMs sur iOS/Android
2. **Browser AI** — LLMs dans le navigateur via WebGPU
3. **Cross-platform** — Un modèle, toutes les plateformes

## Strengths
- Multi-plateforme le plus complet
- WebGPU support
- Apache 2.0

## Limitations
- Compilation complexe
- Communauté plus petite que llama.cpp
- Performance variable par plateforme

## Alternatives
| Tool | Key Difference |
|------|---------------|
| llama.cpp | Plus simple, plus populaire, C/C++ |
| ExecuTorch | Meta, edge focus |

## References
- https://llm.mlc.ai
- https://github.com/mlc-ai/mlc-llm
