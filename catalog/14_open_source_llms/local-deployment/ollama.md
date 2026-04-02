# Ollama

> The simplest way to run open-source LLMs locally

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 14 - Open Source LLMs / Local Deployment |
| **URL** | https://ollama.com/ |
| **GitHub** | https://github.com/ollama/ollama |
| **Stars** | ~167k |
| **License** | MIT |
| **Pricing** | Free / Open Source |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Ollama is the most popular tool for running open-source LLMs locally. It provides a simple CLI and REST API to download, manage, and serve language models with a single command. With 167k GitHub stars, it has become the de facto standard for local LLM deployment, comparable to what Docker did for containers.

Ollama handles model downloading, quantization, GPU acceleration, and serving behind a clean API. It supports 200+ models including Llama 4, Gemma 3, Qwen 3, DeepSeek R1, Mistral, Phi-4, and many more. It runs on macOS, Windows, Linux, and Docker.

## Key Features
- One-command model execution (`ollama run llama4-scout`)
- REST API at `http://localhost:11434`
- OpenAI-compatible API endpoints
- Automatic GPU detection and acceleration
- Model library with 200+ community models
- Official Python and JavaScript SDKs
- Streaming response support
- Multi-model concurrent serving
- Docker container support
- Model Context Protocol (MCP) integration
- Claude Code, Codex, and other AI tool integrations

## Supported Models (Selection)
- Llama 4 (Scout, Maverick)
- Gemma 3 (1B, 4B, 12B, 27B)
- Qwen 3 (all sizes)
- DeepSeek R1 (all distilled variants)
- Mistral / Mixtral
- Phi-4
- GLM-5
- Kimi-K2.5
- MiniMax
- Command R
- Yi
- 200+ additional community models

## Installation

### macOS / Linux
```bash
curl -fsSL https://ollama.com/install.sh | sh
```

### Windows
```powershell
irm https://ollama.com/install.ps1 | iex
```

### Docker
```bash
docker run -d -v ollama:/root/.ollama -p 11434:11434 --name ollama ollama/ollama
```

## Usage
```bash
# Run a model
ollama run llama4-scout

# List available models
ollama list

# Pull a specific model
ollama pull qwen3:32b

# Serve API
ollama serve
```

### REST API
```bash
curl http://localhost:11434/api/chat -d '{
  "model": "llama4-scout",
  "messages": [{"role": "user", "content": "Hello!"}],
  "stream": false
}'
```

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Great for dev/staging, production with caveats |
| **Security** | 4 | Local-only by default, data stays on-premise |
| **Scalability** | 3 | Single-node, not designed for high-throughput serving |
| **Support/Community** | 5 | 167k stars, massive community |
| **Documentation** | 5 | Simple, clear documentation |
| **Integration Ease** | 5 | One command to start, OpenAI-compatible API |

## Use Cases
1. **Local development** - Test LLM features without API costs
2. **Privacy-sensitive applications** - All data stays local
3. **AI tool integration** - Backend for Claude Code, Cursor, etc.
4. **Prototyping** - Quick model evaluation and comparison
5. **Education** - Learn LLM interaction patterns

## Strengths
- Simplest possible setup (one command)
- Massive model library (200+ models)
- Cross-platform (macOS, Windows, Linux, Docker)
- OpenAI-compatible API
- Active development with rapid model support
- Free and open source (MIT)
- Excellent community and ecosystem

## Limitations
- Single-node only (no distributed serving)
- Not optimized for high-throughput production serving
- Less control over inference parameters than vLLM/TGI
- No built-in load balancing or autoscaling
- Model management can consume significant disk space

## Alternatives
| Tool | Key Difference |
|------|---------------|
| LM Studio | Desktop GUI, better for non-technical users |
| LocalAI | OpenAI + Anthropic API compatibility, multi-backend |
| Jan | ChatGPT-like UI, offline-first |
| GPT4All | Focus on CPU inference, educational |
| vLLM | High-throughput production serving |

## References
- [Ollama GitHub](https://github.com/ollama/ollama)
- [Ollama Model Library](https://ollama.com/library)
- [Ollama Python SDK](https://github.com/ollama/ollama-python)
- [Ollama JavaScript SDK](https://github.com/ollama/ollama-js)
- [Ollama API Documentation](https://github.com/ollama/ollama/blob/main/docs/api.md)
