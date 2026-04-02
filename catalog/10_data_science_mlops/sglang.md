# SGLang

> Moteur d'inférence LLM avec RadixAttention et prefix caching avancé, challenger de vLLM.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 10 - Data Science & MLOps / LLM Inference |
| **URL** | https://sgl-project.github.io |
| **GitHub** | https://github.com/sgl-project/sglang |
| **Stars** | ~25,300 |
| **License** | Apache 2.0 |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
SGLang est un moteur d'inférence LLM qui introduit RadixAttention, une innovation dans la gestion du KV cache par structure de données radix tree. Cela permet un prefix caching extrêmement efficace, surpassant vLLM dans les scénarios où de nombreuses requêtes partagent des préfixes communs (system prompts, few-shot examples).

Le projet a connu une croissance explosive, déployé sur plus de 400k+ GPUs, et se positionne comme le principal challenger de vLLM pour le serving LLM en production.

## Key Features
- **RadixAttention**: Gestion KV cache par radix tree, prefix caching ultra-efficace
- **Structured generation**: JSON schema, regex constraints natifs
- **Multi-modal**: Support des modèles vision-language
- **API OpenAI-compatible**: Drop-in replacement
- **Data parallelism + Tensor parallelism**: Scaling flexible
- **Speculative decoding**: Support Eagle, Medusa

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Production-ready, 400k+ GPUs déployés |
| **Security** | 4 | Self-hosted, Apache 2.0 |
| **Scalability** | 5 | Data + tensor parallelism, 400k+ GPUs prouvés |
| **Support/Community** | 4 | 25k stars, croissance rapide, maintenu activement |
| **Documentation** | 3 | Docs en amélioration, moins mature que vLLM |
| **Integration Ease** | 4 | API OpenAI-compatible |

## Use Cases
1. **Serving avec prefix caching** — Idéal quand de nombreuses requêtes partagent des préfixes (chatbots, agents)
2. **Structured output** — Génération JSON/structured contrôlée nativement
3. **Alternative haute performance** — Quand vLLM n'est pas optimal pour le use case

## Getting Started
```bash
pip install sglang[all]

# Lancer un serveur
python -m sglang.launch_server --model meta-llama/Llama-3-8B-Instruct --port 8000

# Requête API
curl http://localhost:8000/v1/chat/completions \
  -d '{"model": "meta-llama/Llama-3-8B-Instruct", "messages": [{"role": "user", "content": "Hello"}]}'
```

## Architecture / How It Works
SGLang utilise un radix tree pour indexer et réutiliser les segments de KV cache. Quand plusieurs requêtes partagent un préfixe commun, le KV cache de ce préfixe n'est calculé qu'une fois et partagé. Le frontend SGLang permet aussi de programmer des pipelines LLM complexes (fork, join, select) de façon native.

## Strengths
- RadixAttention surpasse vLLM pour le prefix caching
- Structured generation native et performante
- Croissance et adoption très rapides
- Support multi-modal

## Limitations
- Écosystème et documentation moins matures que vLLM
- Communauté plus petite (mais en forte croissance)
- Moins de recul en production enterprise

## Alternatives
| Tool | Key Difference |
|------|---------------|
| vLLM | Plus mature, PagedAttention, écosystème plus large |
| TGI | HuggingFace natif, en maintenance |
| Ollama | Plus simple, usage local |

## References
- https://sgl-project.github.io
- https://github.com/sgl-project/sglang
- https://arxiv.org/abs/2312.07104

## Notes
SGLang est le challenger le plus sérieux de vLLM en 2026. À surveiller de près pour les cas d'usage avec beaucoup de prefix sharing. Certains benchmarks montrent SGLang devant vLLM sur des workloads spécifiques.
