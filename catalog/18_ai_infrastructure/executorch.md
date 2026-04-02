# ExecuTorch (Meta)

> Framework de déploiement PyTorch pour edge/mobile — Meta, optimisé pour on-device AI.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 18 - AI Infrastructure / Edge Deployment |
| **URL** | https://pytorch.org/executorch |
| **GitHub** | https://github.com/pytorch/executorch |
| **Stars** | ~3,500+ |
| **License** | BSD-3 |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Beta |

## What It Does
ExecuTorch est le framework officiel de Meta/PyTorch pour déployer des modèles PyTorch sur des appareils edge (mobile, IoT, wearables). Il compile les modèles PyTorch en programmes optimisés pour l'exécution on-device avec support des accélérateurs hardware (CoreML, XNNPACK, Qualcomm QNN).

## Key Features
- **PyTorch export**: Export direct depuis PyTorch
- **Edge optimized**: Mobile, IoT, wearables
- **Delegates**: CoreML, XNNPACK, Qualcomm QNN
- **Llama support**: Déploiement de Llama sur mobile
- **BSD-3**: Licence permissive

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 3 | Beta, Meta-backed |
| **Security** | 5 | BSD-3, on-device |
| **Scalability** | 3 | Edge-focused |
| **Support/Community** | 3 | PyTorch/Meta backing |
| **Documentation** | 3 | Docs PyTorch |
| **Integration Ease** | 3 | PyTorch export pipeline |

## Use Cases
1. **Mobile AI** — Déployer des modèles PyTorch sur iOS/Android
2. **On-device LLM** — Llama sur smartphone
3. **IoT** — AI sur appareils connectés

## Strengths
- Officiel PyTorch/Meta
- Multi-delegate (CoreML, XNNPACK, QNN)
- Llama mobile support

## Limitations
- Beta, en développement
- Communauté en croissance
- Moins mature que ONNX Runtime Mobile

## Alternatives
| Tool | Key Difference |
|------|---------------|
| MLC LLM | Multi-plateforme, WebGPU |
| CoreML Tools | Apple-only, très optimisé |
| ONNX Runtime Mobile | Multi-plateforme, plus mature |

## References
- https://pytorch.org/executorch
- https://github.com/pytorch/executorch
