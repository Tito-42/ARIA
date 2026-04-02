# GPUStack

> Plateforme de gestion multi-GPU pour LLM serving — orchestration de clusters GPU hétérogènes.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 18 - AI Infrastructure / GPU Management |
| **URL** | https://gpustack.ai |
| **GitHub** | https://github.com/gpustack/gpustack |
| **Stars** | ~5,000+ |
| **License** | Apache 2.0 |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
GPUStack est une plateforme de gestion de clusters GPU hétérogènes pour le serving de LLMs. Elle orchestre des GPU de différents types (NVIDIA, AMD, Apple) sur différentes machines pour servir des modèles avec load balancing et auto-scheduling.

## Key Features
- **Multi-GPU**: Orchestration de clusters hétérogènes
- **Multi-backend**: llama.cpp, vLLM support
- **Auto-scheduling**: Placement intelligent des modèles
- **UI web**: Dashboard de gestion
- **API compatible OpenAI**: REST API standard
- **Apache 2.0**: Licence permissive

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 3 | Production, relativement nouveau |
| **Security** | 4 | Apache 2.0 |
| **Scalability** | 4 | Multi-GPU, multi-node |
| **Support/Community** | 3 | 5k+ stars |
| **Documentation** | 3 | Docs en amélioration |
| **Integration Ease** | 4 | API OpenAI-compatible |

## Use Cases
1. **GPU cluster management** — Gérer un cluster GPU hétérogène
2. **Multi-model serving** — Servir plusieurs modèles sur un cluster
3. **Resource optimization** — Utiliser au mieux les GPU disponibles

## Strengths
- Multi-GPU hétérogène
- UI web
- API OpenAI-compatible
- Apache 2.0

## Limitations
- Relativement nouveau
- Communauté en croissance
- Moins mature que des solutions comme Ray Serve

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Ray Serve | Plus mature, distribué |
| Kubernetes + vLLM | Plus standard mais plus complexe |

## References
- https://gpustack.ai
- https://github.com/gpustack/gpustack
