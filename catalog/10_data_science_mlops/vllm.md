# vLLM

> Moteur d'inférence LLM haute performance avec PagedAttention et continuous batching pour le serving en production.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 10 - Data Science & MLOps / LLM Inference |
| **URL** | https://docs.vllm.ai |
| **GitHub** | https://github.com/vllm-project/vllm |
| **Stars** | ~74,900 |
| **License** | Apache 2.0 |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
vLLM est le moteur d'inférence LLM standard pour la production. Il résout le problème du throughput et de la latence en servant des LLMs à grande échelle grâce à des innovations comme PagedAttention (gestion mémoire KV cache inspirée de la mémoire virtuelle OS), le continuous batching, et le tensor parallelism multi-GPU.

Utilisé par des entreprises majeures pour servir des modèles en production, vLLM supporte la majorité des architectures LLM (Llama, Mistral, Qwen, GPT-NeoX, etc.) et expose une API compatible OpenAI.

## Key Features
- **PagedAttention**: Gestion mémoire KV cache ultra-efficace, quasi-zéro gaspillage
- **Continuous batching**: Maximise le throughput en ajoutant des requêtes dynamiquement
- **Tensor parallelism**: Distribution multi-GPU automatique
- **API OpenAI-compatible**: Drop-in replacement pour les services OpenAI
- **Speculative decoding**: Accélération de la génération avec draft models
- **Quantization**: AWQ, GPTQ, FP8 support natif

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | Standard production, utilisé à grande échelle |
| **Security** | 4 | Self-hosted, Apache 2.0, audit possible |
| **Scalability** | 5 | Multi-GPU, tensor parallelism, pipeline parallelism |
| **Support/Community** | 5 | 75k stars, communauté massive, backing enterprise |
| **Documentation** | 4 | Docs complètes, exemples de déploiement |
| **Integration Ease** | 4 | API OpenAI-compatible, mais config initiale non triviale |

## Use Cases
1. **LLM serving production** — Servir des modèles à haute charge avec latence minimale
2. **Multi-modèle serving** — Héberger plusieurs modèles sur un cluster GPU
3. **Batch inference** — Traitement de gros volumes de requêtes offline

## Getting Started
```bash
pip install vllm

# Lancer un serveur
vllm serve meta-llama/Llama-3-8B-Instruct

# Requête API
curl http://localhost:8000/v1/chat/completions \
  -d '{"model": "meta-llama/Llama-3-8B-Instruct", "messages": [{"role": "user", "content": "Hello"}]}'
```

## Architecture / How It Works
vLLM utilise PagedAttention pour gérer le KV cache comme de la mémoire virtuelle paginée, éliminant la fragmentation mémoire. Le continuous batching permet d'ajouter de nouvelles requêtes dès qu'un slot se libère. Le scheduler central orchestre l'allocation GPU, la préemption et le batching pour maximiser le throughput.

## Strengths
- Throughput maximal parmi les moteurs d'inférence open-source
- PagedAttention élimine le gaspillage mémoire KV cache
- Support large des architectures LLM
- Standard de facto pour production

## Limitations
- Configuration complexe pour les déploiements multi-GPU
- Principalement NVIDIA-focused (support AMD/TPU en développement)
- Overhead pour des déploiements simples single-user

## Alternatives
| Tool | Key Difference |
|------|---------------|
| SGLang | RadixAttention, meilleur prefix caching |
| Ollama | Plus simple mais moins performant |
| TGI | HuggingFace natif mais en maintenance |
| Triton | Multi-framework, enterprise NVIDIA |

## References
- https://docs.vllm.ai
- https://github.com/vllm-project/vllm
- https://arxiv.org/abs/2309.06180

## Notes
vLLM v0.18.1 (mars 2026) est la version courante. C'est le choix par défaut pour tout serving LLM en production. SGLang émerge comme challenger sérieux, notamment pour les cas avec beaucoup de prefix caching.
