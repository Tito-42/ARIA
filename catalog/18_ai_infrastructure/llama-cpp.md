# llama.cpp

> Inférence LLM en C/C++ pur — référence pour l'exécution locale et edge, format GGUF, 101k stars.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 18 - AI Infrastructure / Local Inference |
| **URL** | https://github.com/ggml-org/llama.cpp |
| **GitHub** | https://github.com/ggml-org/llama.cpp |
| **Stars** | ~101,000 |
| **License** | MIT |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
llama.cpp est le projet de référence pour l'inférence LLM locale. Écrit en C/C++ pur sans dépendances, il fonctionne partout : CPU, GPU NVIDIA/AMD/Intel, Apple Silicon, mobile, Raspberry Pi. Le format GGUF qu'il a défini est devenu le standard de facto pour les modèles quantizés. C'est la base technique d'Ollama, LM Studio et Jan.ai.

## Key Features
- **C/C++ pur**: Zero dependencies
- **Format GGUF**: Standard industriel pour modèles quantizés
- **Quantization extrême**: Q1.5 à Q8 (1.5-bit à 8-bit)
- **Multi-hardware**: CPU (AVX/ARM/Metal), GPU (CUDA/ROCm/Vulkan)
- **Hybride CPU+GPU**: Offload partiel sur GPU
- **API server**: Serveur HTTP compatible OpenAI

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | Standard industrie, 101k stars |
| **Security** | 5 | MIT, local, offline |
| **Scalability** | 3 | Single-node, pas de serving distribué |
| **Support/Community** | 5 | 101k stars, commits quotidiens |
| **Documentation** | 3 | README, exemples |
| **Integration Ease** | 4 | CLI, bindings Python/Go/Rust |

## Use Cases
1. **LLM local** — Exécuter des LLMs sur laptop/desktop
2. **Edge AI** — LLMs sur Raspberry Pi, mobile, IoT
3. **Base technique** — Backend pour Ollama, LM Studio

## Getting Started
```bash
git clone https://github.com/ggml-org/llama.cpp && cd llama.cpp
cmake -B build && cmake --build build
./build/bin/llama-cli -m model.gguf -p "Hello" -n 128
# Server
./build/bin/llama-server -m model.gguf --port 8080
```

## Architecture / How It Works
llama.cpp implémente l'architecture Transformer en C/C++ avec GGML (tensor library). Les modèles GGUF sont quantizés à différents niveaux. L'inférence utilise des kernels optimisés par plateforme (Metal pour Apple, CUDA pour NVIDIA, AVX pour x86).

## Strengths
- 101k stars, le plus populaire
- Fonctionne partout (CPU, GPU, mobile, edge)
- Format GGUF = standard industriel
- MIT licence
- Zero dependencies

## Limitations
- Throughput inférieur à vLLM pour le serving haute charge
- Pas de multi-GPU distribué natif
- API moins élaborée que vLLM/SGLang

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Ollama | Wrapper de llama.cpp, plus simple |
| vLLM | Serving production, PagedAttention |
| ExLlamaV2 | Quantization GPTQ/EXL2 optimisée |

## References
- https://github.com/ggml-org/llama.cpp

## Notes
llama.cpp est le fondement de l'écosystème LLM local. Ollama le simplifie pour les utilisateurs finaux. Pour le serving production haute charge, vLLM est préférable.
