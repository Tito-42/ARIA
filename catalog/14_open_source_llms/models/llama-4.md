# Llama 4 (Meta)

> Meta's latest open-weight multimodal language models with mixture-of-experts architecture

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 14 - Open Source LLMs |
| **URL** | https://www.llama.com/ |
| **GitHub** | https://github.com/meta-llama/llama-models |
| **Stars** | ~7.5k (llama-models repo) |
| **License** | Llama 4 Community License (commercial, free under 700M MAU) |
| **Pricing** | Free / Open Weights |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Llama 4 is Meta's fourth-generation family of open-weight large language models, released April 5, 2025. It introduces a **mixture-of-experts (MoE) architecture** with early fusion for native multimodality, supporting both text and image inputs. This represents a major architectural shift from the dense transformer models of Llama 3.x.

The MoE design allows Llama 4 models to have very large total parameter counts while keeping the activated parameters per token small, resulting in better performance with lower inference costs. The models are natively multimodal, trained from the ground up on text and images rather than having vision added as an afterthought.

## Model Variants

### Llama 4 Scout (17B-16E)
| Spec | Value |
|------|-------|
| **Activated Parameters** | 17B |
| **Total Parameters** | 109B |
| **Experts** | 16 |
| **Context Length** | 10M tokens |
| **Training Tokens** | ~40 trillion |
| **Languages** | 12 (Arabic, English, French, German, Hindi, Indonesian, Italian, Portuguese, Spanish, Tagalog, Thai, Vietnamese) |

### Llama 4 Maverick (17B-128E)
| Spec | Value |
|------|-------|
| **Activated Parameters** | 17B |
| **Total Parameters** | 400B |
| **Experts** | 128 |
| **Context Length** | 1M tokens |
| **Training Tokens** | ~22 trillion |
| **Languages** | 12 (same as Scout) |

## Key Benchmarks

### Llama 4 Scout (Instruct)
| Benchmark | Score |
|-----------|-------|
| MMLU Pro | 74.3% |
| GPQA Diamond | 57.2% |
| MMMU (Image Reasoning) | 73.4% |
| MathVista | 73.7% |
| ChartQA | 90.0% |
| DocVQA | 94.4% |
| LiveCodeBench | 32.8% |
| MGSM (Multilingual) | 90.6% |

### Llama 4 Maverick (Instruct)
| Benchmark | Score |
|-----------|-------|
| MMLU | 85.5% |
| MMLU Pro | 62.9% |
| GPQA Diamond | 69.8% |
| MMMU | 73.4% |
| MathVista | 73.7% |
| MATH | 61.2% |
| LiveCodeBench | 43.4% |
| MBPP (Code) | 77.6% |

## Key Features
- Native multimodality (text + image) via early fusion
- Mixture-of-Experts (MoE) architecture for efficient inference
- Extremely long context windows (10M for Scout, 1M for Maverick)
- Quantization support: BF16, Int4, FP8
- Safety integration: Llama Guard 3, Prompt Guard, Code Shield
- Enhanced system prompt steerability
- Supports up to 5 input images
- 200+ languages in pretraining, 12 primary supported

## Complete Llama Family History

| Model | Release | Sizes | Context |
|-------|---------|-------|---------|
| Llama 2 | Jul 2023 | 7B, 13B, 70B | 4K |
| Llama 3 | Apr 2024 | 8B, 70B | 8K |
| Llama 3.1 | Jul 2024 | 8B, 70B, 405B | 128K |
| Llama 3.2 | Sep 2024 | 1B, 3B (text); 11B, 90B (vision) | 128K |
| Llama 3.3 | Dec 2024 | 70B | 128K |
| Llama 4 | Apr 2025 | Scout (109B/17B), Maverick (400B/17B) | 10M / 1M |

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | Widely deployed, massive ecosystem |
| **Security** | 4 | Built-in safety tools, commercial license |
| **Scalability** | 5 | MoE enables efficient scaling |
| **Support/Community** | 5 | Hundreds of millions of downloads, vast ecosystem |
| **Documentation** | 5 | Comprehensive docs, cookbook, tutorials |
| **Integration Ease** | 5 | HuggingFace, Ollama, vLLM, all major frameworks |

## Use Cases
1. **Multimodal understanding** - Document analysis, image reasoning, visual QA
2. **Long-context applications** - Processing entire codebases, long documents
3. **Multilingual chat** - 12 natively supported languages
4. **Code generation** - Strong coding benchmarks
5. **Enterprise AI** - On-premise deployment with commercial license

## Getting Started
```bash
# Via Ollama
ollama run llama4-scout

# Via HuggingFace Transformers
pip install transformers>=4.51.0
```

```python
from transformers import AutoProcessor, Llama4ForConditionalGeneration
import torch

model_id = "meta-llama/Llama-4-Scout-17B-16E-Instruct"
processor = AutoProcessor.from_pretrained(model_id)
model = Llama4ForConditionalGeneration.from_pretrained(
    model_id, device_map="auto", torch_dtype=torch.bfloat16
)
```

## Strengths
- Best-in-class multimodal open model
- Extremely long context windows (10M tokens)
- Efficient MoE inference (only 17B activated per token)
- Massive ecosystem and community support
- Commercial-friendly license (under 700M MAU threshold)

## Limitations
- Requires significant GPU memory for full models (especially Maverick at 400B total)
- Knowledge cutoff August 2024
- Image understanding limited to 5 images per prompt
- Commercial license requires Meta attribution ("Built with Llama")

## Alternatives
| Tool | Key Difference |
|------|---------------|
| DeepSeek V3/R1 | Stronger reasoning, MIT license, 671B MoE |
| Qwen 3 | More model sizes (0.6B-235B), 100+ languages |
| Mistral/Mixtral | European alternative, strong multilingual |
| Gemma 3 | Lighter weight, good for edge deployment |

## References
- [Llama Models GitHub](https://github.com/meta-llama/llama-models)
- [Llama Documentation](https://www.llama.com/docs/overview)
- [Llama Cookbook](https://github.com/meta-llama/llama-cookbook)
- [HuggingFace - Llama 4 Scout](https://huggingface.co/meta-llama/Llama-4-Scout-17B-16E-Instruct)
- [HuggingFace - Llama 4 Maverick](https://huggingface.co/meta-llama/Llama-4-Maverick-17B-128E-Instruct)
