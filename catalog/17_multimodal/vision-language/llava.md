# LLaVA / LLaVA-NeXT

> The foundational open-source vision-language model combining CLIP visual encoder with a large language model via an instruction-tuned connector.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 17 - multimodal / vision-language |
| **URL** | https://llava-vl.github.io/ |
| **GitHub** | https://github.com/haotian-liu/LLaVA |
| **Stars** | 24 600 |
| **License** | Apache 2.0 |
| **Pricing** | Free / Open Source |
| **Last Verified** | 2026-04-02 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
LLaVA (Large Language and Vision Assistant) is the reference open-source Vision-Language Model (VLM) that established the pattern for connecting a frozen visual encoder (CLIP ViT-L/14) to a large language model (Vicuna/Llama) via a trained linear projection layer. By performing visual instruction tuning, LLaVA enables the LLM to understand and answer questions about images in natural language.

The LLaVA-NeXT series (January–May 2024) significantly extended the original work by adding: support for newer LLMs (Llama-3, Qwen-1.5, Mistral), 4x higher image resolution via dynamic high-resolution strategy, zero-shot video understanding, and improved reasoning. LLaVA-NeXT also introduces video interleaved inference, allowing simultaneous reasoning over images and video frames.

LLaVA serves as the base architecture for numerous downstream projects including Video-LLaVA, LLaMA-VID, Mantis, and others. Its clean codebase, LoRA/4-bit/8-bit training support, and extensive documentation have made it the de facto reference for VLM research and deployment.

## Key Features
- Visual instruction tuning paradigm (image + text → instruction-following)
- CLIP ViT-L/14 visual encoder (frozen) + MLP connector + LLM
- LLaVA-NeXT: dynamic high-resolution (up to 4x native resolution tiles)
- LLaVA-NeXT: multi-LLM support (Llama-3, Qwen-1.5, Mistral, Gemma)
- LLaVA-NeXT: zero-shot video understanding
- LoRA, 4-bit and 8-bit quantized training/inference
- Multi-turn conversation with images
- Visual question answering, image captioning, OCR
- Inference with vLLM for production serving
- SGLang integration for optimized batch inference

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Widely deployed, vLLM/SGLang serving support; superseded by newer models on benchmarks |
| **Security** | 4 | Local deployment, Apache 2.0; model weights have specific licenses per base LLM |
| **Scalability** | 4 | vLLM/SGLang integration enables high-throughput serving |
| **Support/Community** | 5 | 24K stars, very active community, base for many follow-up works |
| **Documentation** | 5 | Excellent README, training guides, inference examples, model zoo |
| **Integration Ease** | 4 | HuggingFace Transformers compatible, easy inference setup |

## Use Cases
1. **Visual QA systems** - Answer natural language questions about images in enterprise applications (product images, document screenshots, dashboards)
2. **Image captioning pipelines** - Generate descriptive captions for image assets at scale
3. **Multimodal chatbots** - Build conversational interfaces that understand images alongside text
4. **Document screenshot understanding** - Interpret screenshots of UIs, forms, charts without OCR preprocessing
5. **Research baseline** - Reference implementation for VLM research and benchmarking

## Getting Started
```bash
# Install
pip install llava

# Inference with LLaVA-NeXT
from llava.model.builder import load_pretrained_model
from llava.mm_utils import get_model_name_from_path

model_path = "lmms-lab/llava-onevision-qwen2-7b-ov"
tokenizer, model, image_processor, context_len = load_pretrained_model(
    model_path=model_path,
    model_base=None,
    model_name=get_model_name_from_path(model_path)
)

# Via HuggingFace Transformers
from transformers import LlavaNextProcessor, LlavaNextForConditionalGeneration
processor = LlavaNextProcessor.from_pretrained("llava-hf/llava-v1.6-mistral-7b-hf")
model = LlavaNextForConditionalGeneration.from_pretrained("llava-hf/llava-v1.6-mistral-7b-hf")
```

## Architecture / How It Works
LLaVA uses a three-component architecture: (1) a frozen CLIP ViT visual encoder that converts image patches into visual feature vectors; (2) a lightweight MLP projection layer (two linear layers with GELU activation in LLaVA 1.5) that maps visual features into the LLM's embedding space; (3) a pre-trained LLM (Vicuna, Llama-3, etc.) that processes the combined visual and text tokens. During training, only the connector and LLM weights are updated, keeping the visual encoder frozen. LLaVA-NeXT adds a dynamic high-resolution strategy that tiles large images into sub-images processed independently.

## Strengths
- Clean, well-documented codebase that is easy to modify for research
- Apache 2.0 license (code); base for a large ecosystem of follow-on work
- Excellent LoRA/quantization support for resource-constrained deployments
- Strong HuggingFace Transformers integration
- Multiple model sizes available (7B to 34B)
- Active maintenance with regular model releases

## Limitations
- Benchmark performance superseded by InternVL, Qwen-VL, and other newer models
- Base LLM licenses may restrict commercial use (e.g., Llama models require Meta license)
- No native audio modality
- High-resolution processing is memory-intensive
- Video understanding is zero-shot only, not specifically trained

## Alternatives
| Tool | Key Difference |
|------|---------------|
| InternVL3.5 | Higher benchmark scores; larger model family (1B-241B) |
| Qwen2.5-VL / Qwen3-VL | Better multilingual and document/OCR performance |
| DeepSeek-VL2 | More efficient MoE architecture for similar performance |
| Florence-2 | Smaller (0.2-0.8B), task-specific prompt-based, not instruction-tuned |

## References
- https://llava-vl.github.io/
- https://github.com/haotian-liu/LLaVA
- https://arxiv.org/abs/2304.08485 (LLaVA original paper)
- https://arxiv.org/abs/2310.03744 (LLaVA-1.5 improved baselines)
- https://llava-vl.github.io/blog/2024-01-30-llava-next/ (LLaVA-NeXT)

## Notes
LLaVA remains the canonical reference for VLM architecture education and research. For new production deployments, consider InternVL or Qwen-VL for better benchmark performance. LLaVA's true value in 2026 is as the foundational architecture that shaped the VLM field and as a well-maintained, easy-to-understand baseline.
