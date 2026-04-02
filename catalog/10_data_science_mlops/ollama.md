# Ollama

> Standard de facto pour exécuter des LLMs en local avec une interface simple et une API compatible OpenAI.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 10 - Data Science & MLOps / LLM Inference |
| **URL** | https://ollama.com |
| **GitHub** | https://github.com/ollama/ollama |
| **Stars** | ~167,000 |
| **License** | MIT |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Ollama est devenu le standard pour exécuter des LLMs en local sur macOS, Linux et Windows. Il résout le problème de la complexité de téléchargement, configuration et exécution de modèles de langage en offrant une expérience "one-liner" similaire à Docker pour les conteneurs.

L'outil gère automatiquement le téléchargement des modèles (Llama 3, Mistral, Gemma, Phi, etc.), la quantization, l'allocation GPU/CPU, et expose une API REST compatible OpenAI. Cela permet aux développeurs de prototyper et tester localement avant de déployer en production.

Ollama sert aussi de backend pour de nombreux outils (Open WebUI, Continue.dev, LangChain) grâce à son API standardisée.

## Key Features
- **One-liner setup**: `ollama run llama3` pour démarrer immédiatement
- **API compatible OpenAI**: Drop-in replacement pour les SDKs OpenAI
- **Multi-OS**: macOS, Linux, Windows natif
- **Gestion de modèles**: Pull, create, customize via Modelfile
- **Multi-modèles**: Llama 3, Mistral, Gemma, Phi, Qwen, DeepSeek, etc.
- **GPU auto-detection**: NVIDIA CUDA, Apple Metal, AMD ROCm

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 3 | Excellent pour dev/test, moins optimisé que vLLM pour production haute perf |
| **Security** | 4 | Local-first, pas d'envoi de données, MIT licence |
| **Scalability** | 2 | Single-node, pas de distributed serving natif |
| **Support/Community** | 5 | 167k stars, communauté massive, Discord très actif |
| **Documentation** | 4 | Docs claires, nombreux tutoriels communautaires |
| **Integration Ease** | 5 | API OpenAI-compatible, intégration triviale |

## Use Cases
1. **Développement local** — Prototyper des applications LLM sans dépendance cloud
2. **Privacy-first** — Exécuter des modèles sur données sensibles sans envoi externe
3. **Backend local** — Servir de backend pour Open WebUI, Continue.dev, IDE extensions

## Getting Started
```bash
# Installation (macOS/Linux)
curl -fsSL https://ollama.com/install.sh | sh

# Lancer un modèle
ollama run llama3

# API compatible OpenAI
curl http://localhost:11434/v1/chat/completions \
  -d '{"model": "llama3", "messages": [{"role": "user", "content": "Hello"}]}'
```

## Architecture / How It Works
Ollama wrappe llama.cpp avec une couche de gestion de modèles et une API HTTP. Les modèles sont stockés localement dans un registry (similaire à Docker). Le runtime détecte automatiquement le hardware disponible (GPU NVIDIA/AMD/Apple Silicon) et alloue les couches du modèle de façon optimale entre GPU et CPU.

## Strengths
- Ultra-simple à installer et utiliser
- Standard de facto pour LLM local (167k stars)
- API OpenAI-compatible = migration triviale
- Support hardware large (NVIDIA, AMD, Apple Silicon)

## Limitations
- Pas optimisé pour production haute performance (throughput inférieur à vLLM)
- Single-node uniquement, pas de scaling horizontal
- Pas de continuous batching avancé

## Alternatives
| Tool | Key Difference |
|------|---------------|
| vLLM | Production haute performance, PagedAttention, multi-GPU |
| SGLang | RadixAttention, prefix caching avancé |
| LM Studio | GUI desktop, moins orienté développeur |
| llama.cpp | Plus bas niveau, plus de contrôle, pas d'API intégrée |

## References
- https://ollama.com
- https://github.com/ollama/ollama
- https://ollama.com/library

## Notes
Ollama est le choix par défaut pour le développement local et le prototypage. Pour la production à haute charge, migrer vers vLLM ou SGLang. L'API OpenAI-compatible rend la migration transparente.
