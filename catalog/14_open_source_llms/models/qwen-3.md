# Qwen 3 (Alibaba Cloud)

> Alibaba's state-of-the-art multilingual LLM family with thinking/reasoning capabilities

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 14 - Open Source LLMs |
| **URL** | https://qwenlm.github.io/ |
| **GitHub** | https://github.com/QwenLM/Qwen2.5 (Qwen3 hosted here) |
| **Stars** | ~27k |
| **License** | Apache 2.0 (most models), Qwen License (some larger models) |
| **Pricing** | Free / Open Weights |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Qwen 3 is the third generation of large language models from Alibaba Cloud's Qwen team. It offers the widest range of model sizes among open-source LLM families, from 0.6B to 235B parameters, including both dense and Mixture-of-Experts (MoE) architectures. The series features innovative dual-mode capabilities: "thinking" mode for complex reasoning and "non-thinking" mode for efficient chat.

The Qwen3 family includes standard instruct models, thinking/reasoning models (similar to DeepSeek-R1 / OpenAI o1 approach), and comprehensive quantized variants in every major format (FP8, GPTQ, AWQ, GGUF, MLX). This makes Qwen3 one of the most versatile and accessible open model families available.

## Model Variants

### Dense Models
| Model | Parameters | Downloads |
|-------|-----------|-----------|
| Qwen3-0.6B | 0.6B | 13.6M |
| Qwen3-1.7B | 1.7B | 7M |
| Qwen3-4B | 4B | 7M |
| Qwen3-8B | 8B | 9.5M |
| Qwen3-14B | 14B | 2.9M |
| Qwen3-32B | 32B | 3.7M |

### MoE Models
| Model | Total / Active Params | Downloads |
|-------|----------------------|-----------|
| Qwen3-30B-A3B | 30B total / 3B active | 1.5M |
| Qwen3-235B-A22B | 235B total / 22B active | 600k |

### Thinking Models (2507 series - July 2025)
- Qwen3-235B-A22B-Thinking-2507
- Qwen3-30B-A3B-Thinking-2507
- Qwen3-4B-Thinking-2507
- (All also available in FP8)

### Instruct Models (2507 series)
- Qwen3-235B-A22B-Instruct-2507
- Qwen3-30B-A3B-Instruct-2507
- Qwen3-4B-Instruct-2507
- (All also available in FP8)

### Quantized Formats Available
- **FP8**: All 8 model sizes
- **GPTQ-Int4**: 235B-A22B, 30B-A3B
- **GPTQ-Int8**: 1.7B, 0.6B
- **AWQ**: 32B, 14B, 8B, 4B
- **GGUF**: All 8 model sizes
- **MLX**: All sizes in 4-bit, 6-bit, 8-bit, bf16

## Key Features
- **Dual mode**: Thinking (extended reasoning) and non-thinking (fast chat)
- **256K context** with extension to 1M tokens
- **100+ language support** with strong multilingual performance
- **State-of-the-art reasoning** among open-weight models
- Superior tool use and agent capabilities
- Comprehensive quantization support for all deployment scenarios
- Apple Silicon optimization via MLX variants

## Key Benchmarks
- State-of-the-art results among open-weight thinking models on reasoning tasks
- Leading performance in instruction following, logical reasoning, mathematics, science, and coding
- Top performance in complex agent-based tasks
- Significant improvements over Qwen2.5 across all benchmarks

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | Massive downloads, proven in production |
| **Security** | 3 | Chinese origin may raise compliance questions |
| **Scalability** | 5 | Models from 0.6B to 235B, MoE for efficiency |
| **Support/Community** | 5 | 27k stars, millions of downloads |
| **Documentation** | 4 | Good technical reports, growing ecosystem |
| **Integration Ease** | 5 | Every major format, all inference frameworks |

## Use Cases
1. **Multilingual applications** - 100+ languages natively
2. **Complex reasoning** - Thinking mode for math, logic, science
3. **Edge deployment** - 0.6B and 1.7B models for mobile/edge
4. **Agent/tool use** - Superior agent capabilities
5. **On-device AI** - MLX variants for Apple Silicon

## Getting Started
```bash
# Via Ollama
ollama run qwen3:32b
ollama run qwen3:8b

# Via pip
pip install transformers>=4.51.0
```

```python
from transformers import AutoModelForCausalLM, AutoTokenizer

model_name = "Qwen/Qwen3-8B"
model = AutoModelForCausalLM.from_pretrained(model_name, device_map="auto")
tokenizer = AutoTokenizer.from_pretrained(model_name)
```

## Strengths
- Widest range of model sizes in any open LLM family
- Best multilingual support (100+ languages)
- Dual thinking/non-thinking modes
- Every quantization format available
- Very strong performance-per-parameter ratio
- Apache 2.0 license for most models

## Limitations
- Largest models (235B) need significant compute
- Some larger models use Qwen License (not Apache 2.0)
- Newer than Llama ecosystem, slightly fewer integrations
- Chinese company may face regulatory considerations

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Llama 4 | Native multimodal, longer context, Meta ecosystem |
| DeepSeek R1 | Stronger pure reasoning, MIT license |
| Gemma 3 | Google backing, lighter weight |
| Mistral | European alternative, strong in French/European |

## References
- [Qwen3 GitHub Repository](https://github.com/QwenLM/Qwen2.5)
- [Qwen3 Technical Report](https://huggingface.co/papers/2505.09388)
- [Qwen3 HuggingFace Collection](https://huggingface.co/collections/Qwen/qwen3-67dd247413f0e2e4f653967f)
- [Qwen3 Demo Space](https://huggingface.co/spaces/Qwen/Qwen3-Demo)
