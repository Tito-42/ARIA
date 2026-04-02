# InternVL / InternVL3.5

> OpenGVLab's open-source vision-language model series achieving state-of-the-art performance on multimodal benchmarks, available from 1B to 241B parameters (MoE).

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 17 - multimodal / vision-language |
| **URL** | https://github.com/OpenGVLab/InternVL |
| **GitHub** | https://github.com/OpenGVLab/InternVL |
| **Stars** | 9 900 |
| **License** | MIT (code) / Model-specific license per variant |
| **Pricing** | Free / Open Weights |
| **Last Verified** | 2026-04-02 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
InternVL is a family of open-source vision-language models developed by OpenGVLab (Shanghai AI Lab), designed as a genuine open-source alternative to GPT-4V and GPT-4o. The series spans from compact 1B models to the massive InternVL3.5 flagship at 241B parameters (MoE architecture with 28B active parameters per forward pass).

InternVL2.5-78B was the first open-source model to surpass 70% on the MMMU benchmark, previously a proprietary-model-only threshold. The architecture uses a strong InternViT visual encoder paired with InternLM or Llama LLM backends, with dynamic high-resolution processing. The series consistently ranks at or near the top of open-source multimodal leaderboards across MMMU, MMStar, MathVista, DocVQA, ChartQA, and video understanding benchmarks.

InternVL3.5-241B-A28B (2025) represents the current state-of-the-art in open-source VLMs, narrowing the gap with closed-source models to near-zero on many benchmarks.

## Key Features
- Full model size range: 1B, 2B, 4B, 8B, 14B, 26B, 38B, 76B, 241B (MoE)
- State-of-the-art on MMMU, MMStar, MathVista, DocVQA, ChartQA
- Dynamic high-resolution: images split into up to 40 tiles at 448x448 each
- Video understanding with temporal encoding
- Multi-image multi-turn conversations
- Tool use and function calling support
- HuggingFace Transformers and vLLM compatible
- MIT code license (model weights have variant-specific licenses)
- Active training code with LoRA/QLoRA fine-tuning support
- Strong performance on math, science, and reasoning benchmarks

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | Widely deployed, vLLM support, multiple size options for different cost profiles |
| **Security** | 4 | MIT code; local deployment; model weight licenses vary by size |
| **Scalability** | 5 | MoE architecture for flagship; vLLM support; multiple sizes for cost optimization |
| **Support/Community** | 4 | Shanghai AI Lab backing, active GitHub issues, HuggingFace community |
| **Documentation** | 4 | Good technical docs, model cards, training guides |
| **Integration Ease** | 4 | HuggingFace Transformers compatible; vLLM deployment well-documented |

## Use Cases
1. **High-accuracy visual QA** - Enterprise applications requiring best-in-class accuracy on complex visual reasoning (medical imaging analysis, scientific figure interpretation)
2. **Math and science document understanding** - Strong performance on mathematical proofs, scientific charts, and technical diagrams
3. **Document intelligence at scale** - DocVQA and ChartQA SOTA makes it excellent for extracting data from business documents
4. **Video content analysis** - Understanding and Q&A over video content
5. **Research and academic benchmarking** - Reference model for measuring VLM progress

## Getting Started
```bash
pip install transformers accelerate einops timm

import torch
from transformers import AutoTokenizer, AutoModel

model = AutoModel.from_pretrained(
    "OpenGVLab/InternVL2_5-8B",
    torch_dtype=torch.bfloat16,
    low_cpu_mem_usage=True,
    trust_remote_code=True
).eval().cuda()

tokenizer = AutoTokenizer.from_pretrained(
    "OpenGVLab/InternVL2_5-8B",
    trust_remote_code=True
)

# Image loading and inference
from PIL import Image
import torchvision.transforms as T

pixel_values = load_image("path/to/image.jpg").cuda()
response = model.chat(tokenizer, pixel_values, "Describe this image.", {})
print(response)
```

## Architecture / How It Works
InternVL uses a dual-encoder architecture: InternViT (a large-scale vision transformer pre-trained at 300M-6B parameters) processes images, while an LLM (InternLM2, Llama-3, or Mistral) handles language. A Multi-Layer Perceptron (MLP) projector converts visual tokens to language embedding space. The dynamic high-resolution strategy splits images into tiles for fine-grained detail preservation. The MoE variant (InternVL3.5-241B) uses a Mixture-of-Experts LLM backbone, activating only 28B out of 241B parameters per token for efficiency.

## Strengths
- Highest open-source benchmark scores across most multimodal tasks
- MoE architecture delivers frontier performance at manageable compute cost
- Wide size range enables easy scaling from edge (1B) to datacenter (241B)
- MIT code license with active fine-tuning support
- Consistent leaderboard leadership since InternVL2.5

## Limitations
- Model weight licenses vary by size and may restrict commercial use for larger variants
- Requires `trust_remote_code=True` which some security-conscious enterprises disallow
- Larger models require substantial GPU resources
- Less established ecosystem tooling than LLaVA
- Chinese-first development team can mean slower English community support

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Qwen-VL | Stronger document/OCR/multilingual; Qwen License; comparable performance |
| LLaVA-NeXT | Apache 2.0; broader ecosystem; lower benchmark scores |
| DeepSeek-VL2 | More efficient MoE at small sizes; MIT code license |
| Florence-2 | Much smaller; task-specific; lower accuracy on complex tasks |

## References
- https://github.com/OpenGVLab/InternVL
- https://internvl.readthedocs.io/
- https://arxiv.org/abs/2312.14238 (InternVL original)
- https://arxiv.org/abs/2412.05271 (InternVL2.5)
- https://huggingface.co/OpenGVLab/InternVL2_5-78B

## Notes
InternVL is the top recommendation when benchmark performance is the primary criterion. The 8B variant offers an excellent performance-to-cost ratio and fits on a single A100 80GB GPU. For production deployments, verify the specific model weight license for the size you choose, as larger models may have more restrictive terms.
