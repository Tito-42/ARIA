# Together AI

> AI inference and fine-tuning cloud platform providing fast, affordable access to open-source models with an OpenAI-compatible API.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 18_ai_infrastructure |
| **URL** | https://www.together.ai |
| **GitHub** | https://github.com/togethercomputer |
| **Stars** | N/A (cloud platform; some OSS repos) |
| **License** | Proprietary (platform) |
| **Pricing** | Pay-per-token: Llama 3.1 70B ~$0.88/M tokens / Mixtral ~$0.60/M / Fine-tuning from $2/hr |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Together AI is a cloud platform focused on running and fine-tuning open-source AI models. It provides inference endpoints for 100+ open-source models (Llama, Mixtral, DBRX, Stable Diffusion, Code Llama, etc.) with an OpenAI-compatible API, making it a drop-in replacement for OpenAI's API while using open-source models.

Together AI differentiates through speed (custom inference engine), competitive pricing, and a wide model catalog. It's a leading choice for teams that want to use open-source models without managing GPU infrastructure. The platform also offers fine-tuning, embedding generation, and model hosting.

## Key Features
- **100+ open-source models**: Llama, Mixtral, DBRX, Stable Diffusion, etc.
- **OpenAI-compatible API**: Drop-in replacement for OpenAI endpoints
- **Fast inference**: Custom inference engine for low latency
- **Fine-tuning**: Fine-tune open-source models via API
- **Embedding generation**: Generate embeddings for RAG
- **Image generation**: Stable Diffusion, SDXL, Flux models
- **Function calling**: Tool use support for compatible models
- **JSON mode**: Structured output generation
- **Batch inference**: Cost-efficient batch processing
- **Custom model hosting**: Deploy your own models
- **Serverless and dedicated**: Shared or dedicated endpoints

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | Used by many companies in production |
| **Security** | 4 | SOC 2; enterprise features |
| **Scalability** | 5 | Auto-scaling inference; large GPU fleet |
| **Support/Community** | 4 | Enterprise support; active community |
| **Documentation** | 4 | Good API docs; model cards |
| **Integration Ease** | 5 | OpenAI-compatible; one-line switch |

## Use Cases
1. **Open-source model inference** - Production API for Llama, Mixtral, etc.
2. **OpenAI alternative** - Drop-in replacement with open-source models
3. **Model fine-tuning** - Fine-tune Llama and other models via API
4. **RAG pipelines** - Embedding generation + inference for RAG
5. **Image generation** - Stable Diffusion / Flux API endpoints

## Getting Started
```python
# Install
pip install together

# Use (OpenAI-compatible)
from together import Together
client = Together()
response = client.chat.completions.create(
    model="meta-llama/Llama-3.1-70B-Instruct-Turbo",
    messages=[{"role": "user", "content": "Hello!"}]
)
```

## Strengths
- OpenAI-compatible API (minimal migration effort)
- Wide model catalog (100+ open-source models)
- Competitive pricing for open-source model inference
- Fast inference engine
- Fine-tuning support

## Limitations
- Only open-source models (no Claude, GPT-4)
- Pricing varies significantly by model
- Less control than self-hosted (RunPod, Vast.ai)
- Rate limits on lower tiers
- Custom model hosting can be expensive

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Replicate | Broader model types; simpler; container-based |
| Fireworks AI | Similar; competitive on speed/price |
| Groq | Faster inference (LPU); fewer models |
| vLLM (self-hosted) | Open source; self-manage; no API costs |
| Anyscale | Ray-based; more infrastructure control |

## References
- https://www.together.ai
- https://docs.together.ai
