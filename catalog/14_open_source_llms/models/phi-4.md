# Phi-4 (Microsoft)

> Microsoft's small language models with outsized STEM and reasoning performance

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 14 - Open Source LLMs |
| **URL** | https://azure.microsoft.com/en-us/products/phi |
| **GitHub** | N/A (models on HuggingFace) |
| **Stars** | N/A |
| **License** | MIT |
| **Pricing** | Free / Open Weights |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Phi-4 is Microsoft Research's family of small but powerful language models, built on the philosophy that high-quality synthetic data and curated training can produce models that punch far above their parameter weight class. Phi-4 (14B) achieves performance on STEM benchmarks that rivals or exceeds models many times its size, while Phi-4-multimodal-instruct (5.6B) extends capabilities to text, image, and audio understanding.

The Phi family demonstrates that careful data curation and training methodology matter more than raw scale. Phi-4's MATH benchmark score of 80.4% is remarkable for a 14B model, dramatically outperforming its predecessor Phi-3 (44.6%).

## Model Variants

### Phi-4 (Text)
| Spec | Value |
|------|-------|
| **Parameters** | 14B |
| **Architecture** | Dense decoder-only Transformer |
| **Context Length** | 16K tokens |
| **Training Data** | 9.8T tokens |
| **Training Hardware** | 1920 H100-80G GPUs, 21 days |
| **Release Date** | December 12, 2024 |
| **License** | MIT |

### Phi-4-Multimodal-Instruct
| Spec | Value |
|------|-------|
| **Parameters** | 5.6B |
| **Backbone** | Phi-4-Mini-Instruct |
| **Context Length** | 128K tokens |
| **Input Modalities** | Text, Image, Audio |
| **Output Modality** | Text |
| **Training Data** | 5T text tokens, 2.3M speech hours, 1.1T image-text tokens |
| **Training Hardware** | 512 A100-80G GPUs, 28 days |
| **License** | MIT |
| **Text Languages** | 23 languages |
| **Audio Languages** | 8 languages (EN, ZH, DE, FR, IT, JA, ES, PT) |

## Key Benchmarks

### Phi-4 (14B) - OpenAI SimpleEval
| Benchmark | Phi-4 | Phi-3 (14B) | Delta |
|-----------|-------|-------------|-------|
| MMLU | 84.8% | 77.9% | +6.9 |
| GPQA (Science) | 56.1% | 31.2% | +24.9 |
| MATH | 80.4% | 44.6% | +35.8 |
| MGSM | 80.6% | 53.5% | +27.1 |
| HumanEval (Code) | 82.6% | 67.8% | +14.8 |
| DROP (Reasoning) | 75.5% | 68.3% | +7.2 |

### Phi-4-Multimodal-Instruct (5.6B)

#### Vision Benchmarks
| Benchmark | Score |
|-----------|-------|
| MMMU | 55.1% |
| MMBench | 86.7% |
| ScienceQA Visual | 97.5% |
| MathVista | 62.4% |
| AI2D | 82.3% |
| DocVQA | 93.2% |
| TextVQA | 75.6% |

#### Speech Benchmarks
| Task | Performance |
|------|------------|
| OpenASR Leaderboard (WER) | 6.14% (#1) |
| Speech Recognition | Surpasses WhisperV3 |
| Speech Translation | Outperforms SeamlessM4T-v2-Large |
| Speech Summarization | Close to GPT-4o |

## Key Features
- MIT license (fully open for commercial use)
- Exceptional STEM performance for model size
- Multimodal variant handles text, images, and audio
- #1 on HuggingFace OpenASR Leaderboard (speech)
- 23 text languages, 8 audio languages
- Safety alignment via SFT + DPO + RLHF
- Red-teamed by Microsoft AIRT
- 740k+ monthly downloads on HuggingFace

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | Microsoft-backed, MIT license |
| **Security** | 5 | Red-teamed, safety-aligned |
| **Scalability** | 4 | Small models, easy to deploy |
| **Support/Community** | 4 | Microsoft support, Azure integration |
| **Documentation** | 4 | Good HuggingFace docs |
| **Integration Ease** | 5 | HuggingFace, Azure, ONNX |

## Use Cases
1. **Resource-constrained deployment** - 5.6B/14B models fit on single GPUs
2. **STEM applications** - Math, science, reasoning tasks
3. **Speech AI** - ASR, translation, summarization (multimodal variant)
4. **Document understanding** - DocVQA 93.2% on multimodal
5. **Mobile/edge AI** - Small enough for on-device deployment

## Getting Started
```bash
# Via Ollama
ollama run phi4

# Via pip
pip install transformers torch
```

```python
import transformers

pipeline = transformers.pipeline(
    "text-generation",
    model="microsoft/phi-4",
    model_kwargs={"torch_dtype": "auto"},
    device_map="auto",
)

messages = [
    {"role": "system", "content": "You are a helpful assistant."},
    {"role": "user", "content": "Explain quantum entanglement simply."},
]

outputs = pipeline(messages, max_new_tokens=128)
```

## Strengths
- Best-in-class performance for model size
- MIT license (most permissive)
- Trimodal capabilities (text + vision + audio) in 5.6B model
- Exceptional STEM/math benchmarks
- Easy to deploy on consumer hardware
- Strong safety alignment

## Limitations
- Primarily English-focused (non-English performance lower)
- 14B model limited to 16K context (short compared to competitors)
- May hallucinate factual information
- Code training primarily Python-focused
- Knowledge cutoff June 2024

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Gemma 3 | Google, similar size, stronger multilingual |
| Qwen 3 (4B/8B) | More model sizes, longer context |
| Llama 3.2 (3B) | Meta ecosystem, good for mobile |
| Mistral Nemo (12B) | European, similar size class |

## References
- [Phi-4 on HuggingFace](https://huggingface.co/microsoft/phi-4)
- [Phi-4 Multimodal on HuggingFace](https://huggingface.co/microsoft/Phi-4-multimodal-instruct)
- [Phi-4 Technical Report](https://arxiv.org/abs/2412.08905)
- [Azure AI Model Catalog](https://azure.microsoft.com/en-us/products/phi)
