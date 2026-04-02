# OpenVINO (Intel)

> Toolkit d'optimisation et déploiement de modèles IA par Intel — CPU, GPU Intel, VPU.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 18 - AI Infrastructure / Intel Inference |
| **URL** | https://docs.openvino.ai |
| **GitHub** | https://github.com/openvinotoolkit/openvino |
| **Stars** | ~8,000+ |
| **License** | Apache 2.0 |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Enterprise |

## What It Does
OpenVINO est le toolkit Intel pour optimiser et déployer des modèles IA sur hardware Intel (CPU, GPU intégré, VPU). Il convertit des modèles PyTorch/TensorFlow/ONNX en format OpenVINO optimisé avec quantization et graph optimization.

## Key Features
- **Multi-hardware Intel**: CPU, GPU intégré, VPU, NPU
- **Quantization**: INT8, INT4 post-training
- **Graph optimization**: Fusion de layers automatique
- **PyTorch/ONNX import**: Conversion depuis PyTorch et ONNX
- **LLM support**: Optimisations spécifiques LLM
- **Apache 2.0**: Licence permissive

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | Enterprise Intel |
| **Security** | 5 | Apache 2.0, Intel backing |
| **Scalability** | 4 | Optimisé pour scale Intel |
| **Support/Community** | 4 | Intel backing, 8k+ stars |
| **Documentation** | 4 | Docs Intel complètes |
| **Integration Ease** | 4 | HuggingFace Optimum integration |

## Use Cases
1. **Intel deployment** — Déployer des modèles sur hardware Intel
2. **Edge AI** — Inférence optimisée sur Intel NUC, edge servers
3. **CPU inference** — Alternative aux GPU pour certains workloads

## Getting Started
```python
from optimum.intel import OVModelForCausalLM
model = OVModelForCausalLM.from_pretrained("model_id", export=True)
```

## Strengths
- Performance optimale sur Intel
- Enterprise Intel backing
- Apache 2.0
- HuggingFace Optimum integration

## Limitations
- Intel-specific (pas pour NVIDIA/AMD)
- Performance inférieure aux GPU NVIDIA pour LLM serving
- Compilation/conversion nécessaire

## Alternatives
| Tool | Key Difference |
|------|---------------|
| ONNX Runtime | Multi-hardware, Microsoft |
| TensorRT-LLM | NVIDIA-optimisé |
| llama.cpp | Multi-hardware, plus simple |

## References
- https://docs.openvino.ai
- https://github.com/openvinotoolkit/openvino
