# Yi (01.AI)

> Bilingual (English/Chinese) open-source LLMs trained from scratch

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 14 - Open Source LLMs |
| **URL** | https://01.ai/ |
| **GitHub** | https://github.com/01-ai/Yi |
| **Stars** | ~7.8k |
| **License** | Yi Model License Agreement v2.1 (Community License) |
| **Pricing** | Free / Open Weights |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Yi is a family of large language models developed from scratch by 01.AI, founded by Kai-Fu Lee. The models are designed to be strong bilingual (English/Chinese) performers, trained on a 3 trillion token multilingual corpus. Yi models come in multiple sizes from 6B to 34B parameters, with extended context variants supporting up to 200K tokens.

The Yi-34B model was the first open-source model to rank at the top of the HuggingFace Open LLM Leaderboard, and Yi-34B-Chat ranked second on AlpacaEval (behind only GPT-4 Turbo). The family also includes vision models (Yi-VL) that rank at the top of MMMU and CMMU benchmarks.

## Model Variants

### Chat Models
| Model | Parameters | Notes |
|-------|-----------|-------|
| Yi-34B-Chat | 34B | Enterprise-grade |
| Yi-34B-Chat-4bits | 34B | AWQ quantized |
| Yi-34B-Chat-8bits | 34B | GPTQ quantized |
| Yi-6B-Chat | 6B | Personal/academic |
| Yi-6B-Chat-4bits | 6B | AWQ quantized |
| Yi-6B-Chat-8bits | 6B | GPTQ quantized |

### Base Models
| Model | Parameters | Context |
|-------|-----------|---------|
| Yi-34B | 34B | 4K |
| Yi-34B-200K | 34B | 200K |
| Yi-9B | 9B | 4K |
| Yi-9B-200K | 9B | 200K |
| Yi-6B | 6B | 4K |
| Yi-6B-200K | 6B | 200K |

### Vision Models
| Model | Parameters | Top Benchmark |
|-------|-----------|---------------|
| Yi-VL-34B | 34B | #1 MMMU and CMMU |
| Yi-VL-6B | 6B | Compact vision-language |

## Key Benchmarks
- Yi-34B-Chat: **#2 on AlpacaEval** (behind GPT-4 Turbo only)
- Yi-34B: **#1 among open-source on HuggingFace Open LLM Leaderboard** (at time of release)
- Yi-VL-34B: **#1 on MMMU and CMMU** (at time of release)
- Yi-9B outperforms Mistral-7B and Gemma-7B on similar benchmarks

## Key Features
- Bilingual English/Chinese from ground up (3T token corpus)
- Context windows up to 200K tokens
- Strong reasoning, comprehension, and code generation
- Quantized versions for consumer-grade GPUs (4-bit, 8-bit)
- Vision-language models (Yi-VL)
- Supports fine-tuning and custom deployment

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Proven but smaller ecosystem |
| **Security** | 3 | Chinese company, community license |
| **Scalability** | 3 | Max 34B, no MoE variants |
| **Support/Community** | 3 | 7.8k stars, active but smaller |
| **Documentation** | 3 | Good but less extensive than competitors |
| **Integration Ease** | 4 | HuggingFace, standard formats |

## Use Cases
1. **Bilingual applications** - English/Chinese services
2. **Long-context tasks** - 200K token variants for document processing
3. **Vision understanding** - Yi-VL for multimodal tasks
4. **Research** - Open weights enable academic study
5. **Consumer deployment** - Quantized variants for consumer GPUs

## Getting Started
```bash
# Via Ollama
ollama run yi:34b

# Via pip
pip install transformers
```

## Strengths
- Excellent English/Chinese bilingual performance
- Strong benchmark results for model sizes
- 200K context variants available
- Vision-language models included
- Quantized versions for accessibility

## Limitations
- Maximum 34B parameters (smaller than competitors)
- Less active development compared to Qwen/Llama
- Community license may restrict some commercial uses
- Fewer model variants than Qwen or Llama families
- Yi-1.5 and Yi-Lightning exist but less documented

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Qwen 3 | Wider size range, more languages, more active |
| DeepSeek | Stronger reasoning, MIT license |
| Llama 4 | Larger scale, multimodal MoE |
| Gemma 3 | Google backing, better for non-Chinese use |

## References
- [Yi GitHub Repository](https://github.com/01-ai/Yi)
- [Yi HuggingFace Models](https://huggingface.co/01-ai)
- [Yi Technical Report](https://arxiv.org/abs/2403.04652)
- [01.AI Website](https://01.ai/)
