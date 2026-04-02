# Gemma 3 (Google DeepMind)

> Google's lightweight open-weight multimodal model family for on-device and research use

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 14 - Open Source LLMs |
| **URL** | https://ai.google.dev/gemma/docs/core |
| **GitHub** | https://github.com/google-deepmind/gemma (JAX) / https://github.com/google/gemma.cpp (C++) |
| **Stars** | ~4.1k (JAX) / ~6.8k (C++) |
| **License** | Gemma License (permissive, allows commercial use) |
| **Pricing** | Free / Open Weights |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Gemma 3 is a family of lightweight, open-weight models from Google DeepMind, built with the same research and technology used to create the Gemini models. Gemma 3 introduces native multimodal capabilities (text + images), supports 140+ languages, and features a 128K token context window. The models are designed to be efficient enough to run on laptops, desktops, and cloud infrastructure.

The Gemma family also includes PaliGemma 2, a vision-language model variant optimized for image understanding tasks. The C++ implementation (gemma.cpp) enables CPU-only inference with SIMD optimization, making it suitable for edge deployment.

## Model Variants

### Gemma 3 (Text + Vision)
| Model | Parameters | Context | Notes |
|-------|-----------|---------|-------|
| Gemma 3 1B | 1B | 32K | Text-only, smallest |
| Gemma 3 4B | 4B | 128K | Text + Vision |
| Gemma 3 12B | 12B | 128K | Text + Vision |
| Gemma 3 27B | 27B | 128K | Text + Vision, flagship |

### Gemma 2 (Legacy)
| Model | Parameters | Context |
|-------|-----------|---------|
| Gemma 2 2B | 2B | 8K |
| Gemma 2 9B | 9B | 8K |
| Gemma 2 27B | 27B | 8K |

### PaliGemma 2
| Model | Parameters | Notes |
|-------|-----------|-------|
| PaliGemma 2 3B | 3B | Vision-language, 224px/448px/896px |

## Key Benchmarks (Gemma 3 27B-IT)

### Reasoning and Factuality
| Benchmark | Score |
|-----------|-------|
| HellaSwag (10-shot) | 85.6 |
| BoolQ (0-shot) | 82.4 |
| TriviaQA (5-shot) | 85.5 |
| ARC-c (25-shot) | 70.6 |
| BIG-Bench Hard (few-shot) | 77.7 |

### STEM and Code
| Benchmark | Score |
|-----------|-------|
| MMLU (5-shot) | 78.6 |
| MATH (4-shot) | 50.0 |
| GSM8K (8-shot) | 82.6 |
| MBPP (3-shot) | 65.6 |
| HumanEval (0-shot) | 48.8 |

### Multilingual
| Benchmark | Score |
|-----------|-------|
| MGSM | 74.3 |
| Global-MMLU-Lite | 75.7 |
| XQuAD | 76.8 |

### Multimodal (Vision)
| Benchmark | Score |
|-----------|-------|
| DocVQA | 85.6 |
| MMMU | 56.1 |
| TextVQA | 68.6 |
| AI2D | 79.0 |
| ChartQA | 76.3 |

## Key Features
- Multimodal: text + image processing (images encoded to 256 tokens each)
- 128K token context window
- 140+ language support
- Lightweight enough for laptops and desktops
- CPU-only inference via gemma.cpp with SIMD optimization
- TPU/GPU/CPU training and inference
- LoRA fine-tuning support
- Pre-trained and instruction-tuned variants
- PaliGemma 2 for specialized vision tasks
- Multi-turn conversation support

## Architecture Details
- Dense decoder-only transformer
- Training on 14 trillion tokens (27B model)
- BF16 precision
- Trained on TPUv4p, TPUv5p, TPUv5e
- JAX + ML Pathways software stack

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | Google-backed, well-tested |
| **Security** | 5 | Google's safety evaluation, CSAM filtering |
| **Scalability** | 4 | Max 27B, good for edge to cloud |
| **Support/Community** | 4 | Google support, Kaggle community |
| **Documentation** | 5 | Excellent docs, Colab notebooks, tutorials |
| **Integration Ease** | 5 | HuggingFace, Ollama, gemma.cpp, Keras |

## Use Cases
1. **On-device AI** - Small enough for laptops and edge devices
2. **Document analysis** - Multimodal vision for DocVQA, OCR
3. **Research** - Open weights enable academic study
4. **Multilingual chatbots** - 140+ languages
5. **Education** - Well-documented for learning LLM development

## Getting Started
```bash
# Via Ollama
ollama run gemma3:27b
ollama run gemma3:4b

# Via pip
pip install transformers>=4.50.0
```

```python
from transformers import pipeline
import torch

pipe = pipeline(
    "image-text-to-text",
    model="google/gemma-3-27b-it",
    device="cuda",
    torch_dtype=torch.bfloat16
)
```

## Strengths
- Excellent performance-per-parameter ratio
- Google backing and safety infrastructure
- CPU inference capability (gemma.cpp)
- Strong multimodal vision capabilities
- Very well documented with tutorials
- Permissive license for commercial use

## Limitations
- Maximum 27B parameters (smaller than competitors)
- Benchmarks lag behind DeepSeek R1 / Qwen3 on reasoning
- No MoE variants (less compute-efficient at scale)
- May struggle with sarcasm and figurative language
- English-only safety evaluation

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Phi-4 | Microsoft, 14B but strong STEM scores |
| Qwen 3 | Wider size range, stronger reasoning |
| Llama 4 | Larger scale, native MoE |
| Mistral Nemo | Similar size, European alternative |

## References
- [Gemma 3 Technical Report](https://goo.gle/Gemma3Report)
- [Google DeepMind Gemma JAX](https://github.com/google-deepmind/gemma)
- [gemma.cpp](https://github.com/google/gemma.cpp)
- [Gemma Model Page](https://ai.google.dev/gemma/docs/core)
- [HuggingFace - Gemma 3 27B IT](https://huggingface.co/google/gemma-3-27b-it)
