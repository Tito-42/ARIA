# TGI (Text Generation Inference)

> Serveur d'inférence LLM par HuggingFace — en mode maintenance depuis mars 2026, migrer vers vLLM/SGLang.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 10 - Data Science & MLOps / LLM Inference |
| **URL** | https://huggingface.co/docs/text-generation-inference |
| **GitHub** | https://github.com/huggingface/text-generation-inference |
| **Stars** | ~10,800 |
| **License** | Apache 2.0 |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Maintenance |
| **Maturity** | Production (Legacy) |

## What It Does
TGI était le serveur d'inférence LLM de référence par HuggingFace. Il fournit un serving optimisé avec continuous batching, tensor parallelism, et quantization. Depuis mars 2026, TGI est officiellement en mode maintenance — pas de nouvelles features, HuggingFace redirige vers vLLM et SGLang.

TGI reste fonctionnel pour les déploiements existants mais ne doit pas être choisi pour de nouveaux projets.

## Key Features
- **Continuous batching**: Optimisation du throughput
- **Tensor parallelism**: Multi-GPU support
- **Quantization**: GPTQ, AWQ, bitsandbytes
- **HuggingFace native**: Intégration directe avec le Hub
- **Watermarking**: Marquage des textes générés
- **Grammar-based generation**: Structured output via grammaires

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 3 | Fonctionne mais en maintenance, pas de nouvelles features |
| **Security** | 4 | Self-hosted, Apache 2.0 |
| **Scalability** | 3 | Multi-GPU mais optimisations en retard vs vLLM |
| **Support/Community** | 2 | **Mode maintenance** — support minimal |
| **Documentation** | 4 | Docs HuggingFace complètes |
| **Integration Ease** | 5 | Intégration HuggingFace Hub triviale |

## Use Cases
1. **Déploiements existants** — Maintenir des services TGI déjà en production
2. **Migration source** — Base de départ pour migrer vers vLLM/SGLang

## Getting Started
```bash
# Docker (méthode recommandée)
docker run --gpus all -p 8080:80 \
  ghcr.io/huggingface/text-generation-inference:latest \
  --model-id meta-llama/Llama-3-8B-Instruct
```

## Architecture / How It Works
TGI est écrit en Rust (serveur HTTP) avec un backend Python/PyTorch pour l'inférence. Il utilise FlashAttention et continuous batching pour optimiser le throughput. Les modèles sont chargés depuis le HuggingFace Hub.

## Strengths
- Intégration HuggingFace Hub native
- Simple à déployer via Docker
- Bonne documentation

## Limitations
- **En mode maintenance depuis mars 2026** — pas de nouvelles features
- Performance en retard vs vLLM et SGLang
- HuggingFace recommande de migrer

## Alternatives
| Tool | Key Difference |
|------|---------------|
| vLLM | **Recommandé** — Plus performant, activement développé |
| SGLang | **Recommandé** — RadixAttention, prefix caching |
| Ollama | Plus simple pour usage local |

## References
- https://huggingface.co/docs/text-generation-inference
- https://github.com/huggingface/text-generation-inference

## Notes
**ALERTE: En maintenance depuis mars 2026.** Ne pas utiliser pour de nouveaux projets. Migrer les déploiements existants vers vLLM ou SGLang. L'API est suffisamment similaire pour que la migration soit relativement simple.
