# Triton Inference Server

> Serveur d'inférence enterprise multi-framework par NVIDIA. Supporte PyTorch, TensorFlow, ONNX et TensorRT.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 10 - Data Science & MLOps / Model Serving |
| **URL** | https://developer.nvidia.com/triton-inference-server |
| **GitHub** | https://github.com/triton-inference-server/server |
| **Stars** | ~10,500 |
| **License** | BSD-3 |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Enterprise |

## What It Does
Triton Inference Server est la solution enterprise de NVIDIA pour le serving de modèles ML/DL en production. Il résout le problème du déploiement multi-framework en supportant simultanément PyTorch, TensorFlow, ONNX Runtime, TensorRT, et même des backends custom Python.

Triton excelle dans les scénarios enterprise avec model ensembles (chaîner preprocessing → modèle → postprocessing), dynamic batching, model versioning, et métriques Prometheus intégrées.

## Key Features
- **Multi-framework**: PyTorch, TensorFlow, ONNX, TensorRT, Python dans un serveur
- **Model ensemble**: Pipelines multi-modèles avec DAG
- **Dynamic batching**: Optimisation automatique du batching
- **Model versioning**: A/B testing et rollback natifs
- **Métriques Prometheus**: Monitoring production intégré
- **gRPC + HTTP**: Double protocole de serving

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | Enterprise-grade, utilisé par les plus grandes entreprises |
| **Security** | 5 | NVIDIA enterprise support, auditable, BSD licence |
| **Scalability** | 5 | Multi-GPU, Kubernetes, auto-scaling |
| **Support/Community** | 4 | Support NVIDIA enterprise, communauté active |
| **Documentation** | 4 | Documentation complète, exemples NVIDIA |
| **Integration Ease** | 3 | Configuration complexe, courbe d'apprentissage |

## Use Cases
1. **Multi-model serving** — Servir plusieurs modèles de frameworks différents sur un seul cluster
2. **Model ensembles** — Pipelines preprocessing → inference → postprocessing
3. **Production enterprise** — Déploiement avec SLA, monitoring, versioning

## Getting Started
```bash
# Docker
docker run --gpus all -p 8000:8000 -p 8001:8001 -p 8002:8002 \
  -v /path/to/models:/models \
  nvcr.io/nvidia/tritonserver:24.03-py3 \
  tritonserver --model-repository=/models
```

## Architecture / How It Works
Triton charge les modèles depuis un model repository structuré. Chaque modèle a une configuration (config.pbtxt) spécifiant le backend, les shapes d'entrée/sortie, et les paramètres de batching. Le scheduler central gère les requêtes, le dynamic batching, et l'allocation GPU. Les model ensembles permettent de composer des pipelines complexes.

## Strengths
- Seule solution enterprise multi-framework mature
- Model ensemble pour pipelines complexes
- Monitoring Prometheus natif
- Support NVIDIA enterprise

## Limitations
- Configuration complexe (config.pbtxt pour chaque modèle)
- Fortement NVIDIA-centric
- Overhead pour des cas simples (préférer vLLM pour du LLM-only)

## Alternatives
| Tool | Key Difference |
|------|---------------|
| vLLM | Spécialisé LLM, plus simple, meilleur throughput LLM |
| BentoML | Plus simple, Python-first, multi-cloud |
| Seldon Core | Kubernetes-natif, A/B testing |
| TorchServe | PyTorch-only, plus simple |

## References
- https://developer.nvidia.com/triton-inference-server
- https://github.com/triton-inference-server/server
- https://docs.nvidia.com/deeplearning/triton-inference-server/

## Notes
Triton est le choix pour l'enterprise multi-framework. Pour du LLM-only, préférer vLLM/SGLang qui sont plus optimisés. Version v2.67.0 (mars 2026) est la dernière stable.
