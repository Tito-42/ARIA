# Video-LLaVA

> Vision-language model that learns unified representations for images and videos through pre-alignment before projection, enabling simultaneous reasoning over both modalities.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 17 - multimodal / video |
| **URL** | https://github.com/PKU-YuanGroup/Video-LLaVA |
| **GitHub** | https://github.com/PKU-YuanGroup/Video-LLaVA |
| **Stars** | 3 500 |
| **License** | Apache 2.0 |
| **Pricing** | Free / Open Source |
| **Last Verified** | 2026-04-02 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Video-LLaVA is an open-source VLM from Peking University that addresses a key challenge in unified image-video understanding: prior models either handle images or videos well, but not both simultaneously. Video-LLaVA solves this by learning unified visual representations through alignment before the LLM projection stage, rather than treating images and videos with completely separate encoders.

The core innovation is the pre-alignment step: a LanguageBind encoder is trained to align image and video features into a shared representation space before either is projected into the LLM. This allows the same LLM to reason over images and videos simultaneously without requiring image-video paired training data. The model uses Vicuna-7B or Vicuna-13B as the LLM backbone and was accepted at EMNLP 2024.

Video-LLaVA demonstrates that unified image-video understanding is achievable with a simpler training strategy than models that use entirely separate branches, and its Apache 2.0 license and clean codebase make it a popular starting point for video-aware VLM development.

## Key Features
- Unified image and video understanding in a single model
- Pre-alignment strategy using LanguageBind encoder for shared visual representations
- No image-video paired data required for training
- Vicuna 7B and 13B backbone variants
- Accepts interleaved image and video inputs in the same conversation
- Apache 2.0 license for both code and model weights
- EMNLP 2024 accepted paper
- HuggingFace model hub compatible
- Gradient checkpointing and LoRA fine-tuning support

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 3 | Solid research model with Apache 2.0; superseded for production by InternVL/Qwen-VL |
| **Security** | 5 | Apache 2.0 code and weights; fully local |
| **Scalability** | 3 | Standard transformer; no specific high-throughput serving optimizations documented |
| **Support/Community** | 3 | 3.5K stars; active but smaller community |
| **Documentation** | 4 | Good README, training guides, demo |
| **Integration Ease** | 4 | HuggingFace compatible; standard LLaVA inference pattern |

## Use Cases
1. **Video question answering** - Answer natural language questions about video clips in enterprise applications
2. **Mixed image-video understanding** - Applications that need to reason over both static images and video clips in the same session
3. **Video captioning** - Generate descriptions of video content for accessibility or cataloging
4. **Research baseline** - Reference implementation for unified image-video LLMs
5. **Fine-tuning starting point** - Apache 2.0 clean base for domain-specific video understanding models

## Getting Started
```bash
git clone https://github.com/PKU-YuanGroup/Video-LLaVA
cd Video-LLaVA
pip install -r requirements.txt

# Inference
python videollava/serve/cli.py \
    --model-path "LanguageBind/Video-LLaVA-7B" \
    --video-file "path/to/video.mp4" \
    --query "What is happening in this video?"

# Python API
from videollava.serve.inference import load_video_llava, run_inference
model, tokenizer, image_processor = load_video_llava("LanguageBind/Video-LLaVA-7B")
response = run_inference(model, tokenizer, image_processor, 
                          video="video.mp4", query="Describe the video")
```

## Architecture / How It Works
Video-LLaVA uses LanguageBind as the shared visual encoder for both images and videos. LanguageBind is a multi-modal contrastive model trained to align image, video, and other modalities to a common language-anchored space. This pre-aligned representation is then projected via a MLP into Vicuna's embedding space. The key insight is that by using a shared encoder that produces language-aligned embeddings for both images and video frames, the LLM can reason uniformly over both modalities without separate visual tokens for images vs. video.

## Strengths
- Clean approach to unified image-video understanding
- Apache 2.0 license on code and weights enables unrestricted commercial use
- Elegant pre-alignment architecture that inspired follow-on work
- Does not require image-video paired training data
- Well-documented codebase based on LLaVA architecture

## Limitations
- Performance ceiling lower than newer specialized models (InternVL, Qwen-VL)
- Vicuna-based backbone superseded by newer LLMs
- No support for very long videos (no long-context video strategy)
- Limited audio understanding (visual-only)
- Less actively maintained compared to flagship VLM series

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Video-LLaMA | Adds audio understanding; BSD-3 license |
| InternVL3.5 | Higher accuracy; broader capability; model-specific license |
| Qwen2.5-VL | Better video understanding; long video support; Qwen License |
| VideoChat2 | Instruction-tuned with MVBench; MIT license |

## References
- https://github.com/PKU-YuanGroup/Video-LLaVA
- https://arxiv.org/abs/2311.10122 (Video-LLaVA paper)
- https://huggingface.co/LanguageBind/Video-LLaVA-7B

## Notes
Video-LLaVA is most useful as a clean, Apache 2.0 baseline for video-aware VLM development or as a lightweight starting point for fine-tuning. For production deployments requiring state-of-the-art video understanding, prefer Qwen2.5-VL or InternVL which have dedicated video training at scale.
