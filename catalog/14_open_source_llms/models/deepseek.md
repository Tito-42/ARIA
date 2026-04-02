# DeepSeek V3 / R1

> Chinese open-source MoE models with state-of-the-art reasoning capabilities

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 14 - Open Source LLMs |
| **URL** | https://www.deepseek.com/ |
| **GitHub** | https://github.com/deepseek-ai/DeepSeek-V3 / https://github.com/deepseek-ai/DeepSeek-R1 |
| **Stars** | 102k (V3) / 92k (R1) |
| **License** | MIT (code), Model License Agreement (model weights) |
| **Pricing** | Free / Open Weights |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
DeepSeek is a family of large language models developed by the Chinese AI lab DeepSeek. The two flagship models are **DeepSeek-V3** (a general-purpose MoE model) and **DeepSeek-R1** (a reasoning-focused model trained with large-scale reinforcement learning). Both use a Mixture-of-Experts (MoE) architecture with 671B total parameters and 37B activated per token.

DeepSeek-R1 is particularly notable for pioneering the use of large-scale RL without supervised fine-tuning for developing reasoning capabilities, achieving performance comparable to OpenAI's o1 on math, code, and reasoning benchmarks. The models also come with a series of distilled versions for more accessible deployment.

## Model Variants

### DeepSeek-V3
| Spec | Value |
|------|-------|
| **Total Parameters** | 671B |
| **Activated Parameters** | 37B per token |
| **Context Length** | 128K tokens |
| **Architecture** | MoE with Multi-head Latent Attention (MLA) |
| **Training Data** | 14.8 trillion tokens |
| **Training Cost** | 2.664M H800 GPU hours (pre-training) |
| **Key Innovations** | Auxiliary-loss-free load balancing, Multi-Token Prediction (MTP), FP8 mixed precision training |

### DeepSeek-R1
| Spec | Value |
|------|-------|
| **Total Parameters** | 671B |
| **Activated Parameters** | 37B per token |
| **Context Length** | 128K tokens |
| **Base Model** | DeepSeek-V3-Base |
| **Training Method** | Large-scale RL without SFT |
| **Key Capabilities** | Self-verification, reflection, extended chain-of-thought |

### DeepSeek-R1 Distilled Models
| Model | Base | Parameters |
|-------|------|-----------|
| DeepSeek-R1-Distill-Qwen-1.5B | Qwen 2.5 | 1.5B |
| DeepSeek-R1-Distill-Qwen-7B | Qwen 2.5 | 7B |
| DeepSeek-R1-Distill-Llama-8B | Llama 3.1 | 8B |
| DeepSeek-R1-Distill-Qwen-14B | Qwen 2.5 | 14B |
| DeepSeek-R1-Distill-Qwen-32B | Qwen 2.5 | 32B |
| DeepSeek-R1-Distill-Llama-70B | Llama 3.3 | 70B |

## Key Benchmarks

### DeepSeek-V3 (Base Model)
| Benchmark | Score |
|-----------|-------|
| MMLU | 87.1% |
| HumanEval | 65.2% |
| GSM8K | 89.3% |
| MATH-500 | 90.2% |

### DeepSeek-R1
| Benchmark | Score |
|-----------|-------|
| AIME 2024 | 79.8% (pass@1) |
| MATH-500 | 97.3% |
| CNMO 2024 | 78.8% |
| Codeforces | 2029 rating |
| LiveCodeBench | 65.9% |
| MMLU | 90.8% |
| AlpacaEval 2.0 | 87.6% LC-winrate |

## Key Features
- State-of-the-art reasoning (R1 rivals OpenAI o1)
- MIT license for code (very permissive)
- Efficient MoE architecture (only 37B activated from 671B)
- FP8 mixed precision training framework
- Knowledge distillation to smaller models (1.5B-70B)
- Multi-Token Prediction (MTP) training objective
- Extended chain-of-thought reasoning
- No irrecoverable loss spikes during training

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | Widely deployed, multiple inference frameworks |
| **Security** | 3 | Chinese origin may raise compliance concerns |
| **Scalability** | 5 | MoE efficient at scale |
| **Support/Community** | 5 | 102k+ stars, massive adoption |
| **Documentation** | 4 | Good technical papers, growing docs |
| **Integration Ease** | 5 | SGLang, vLLM, TensorRT-LLM, LMDeploy |

## Deployment Support
- SGLang (recommended)
- LMDeploy
- TensorRT-LLM
- vLLM
- LightLLM
- AMD GPU support
- Huawei Ascend support

## Use Cases
1. **Complex reasoning** - Math, science, logic problems
2. **Code generation** - Competitive programming level
3. **Research** - Open architecture enables academic study
4. **Knowledge distillation** - Transfer capabilities to smaller models
5. **Cost-efficient deployment** - MoE reduces inference cost vs dense models

## Getting Started
```bash
# Via Ollama
ollama run deepseek-r1

# For distilled models
ollama run deepseek-r1:7b
ollama run deepseek-r1:32b
```

## Usage Recommendations
- Temperature: 0.5-0.7 (0.6 recommended for R1)
- Avoid system prompts with R1 (can degrade performance)
- Force reasoning with `<think>\n` prefix
- Run multiple times and average for accuracy-critical tasks

## Strengths
- Best open-source reasoning model (R1)
- Extremely cost-efficient training ($5.6M for V3)
- MIT license for code
- Distilled models maintain strong performance at small sizes
- R1-Distill-Qwen-32B outperforms OpenAI o1-mini on multiple benchmarks

## Limitations
- Full 671B model requires substantial GPU resources
- Chinese company may face geopolitical/regulatory concerns
- Model license (distinct from code MIT) has some restrictions
- R1 can produce very long chain-of-thought outputs (higher token costs)

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Llama 4 | Native multimodal, longer context (10M) |
| Qwen 3 | More size options, stronger multilingual |
| OpenAI o1/o3 | Closed source but similar reasoning approach |
| Gemma 3 | Much lighter weight, Google backing |

## References
- [DeepSeek-V3 Paper](https://arxiv.org/abs/2412.19437)
- [DeepSeek-R1 Paper](https://arxiv.org/abs/2501.12948)
- [DeepSeek-V3 GitHub](https://github.com/deepseek-ai/DeepSeek-V3)
- [DeepSeek-R1 GitHub](https://github.com/deepseek-ai/DeepSeek-R1)
- [HuggingFace - DeepSeek-R1](https://huggingface.co/deepseek-ai/DeepSeek-R1)
