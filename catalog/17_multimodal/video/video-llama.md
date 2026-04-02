# Video-LLaMA

> Open-source multimodal LLM from DAMO Academy (Alibaba) that simultaneously understands video and audio, using dedicated visual and audio encoders connected to a Llama-2 backbone.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 17 - multimodal / video |
| **URL** | https://github.com/DAMO-NLP-SG/Video-LLaMA |
| **GitHub** | https://github.com/DAMO-NLP-SG/Video-LLaMA |
| **Stars** | 3 100 |
| **License** | BSD-3-Clause |
| **Pricing** | Free / Open Source |
| **Last Verified** | 2026-04-02 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Video-LLaMA is an open-source multimodal large language model developed by DAMO Academy (Alibaba Group) that extends LLM capabilities to jointly understand video and audio. Unlike most VLMs that focus solely on visual content, Video-LLaMA explicitly processes audio from video files alongside the visual frames, enabling richer and more accurate video comprehension.

The model uses two parallel processing branches: a Vision-Language branch that uses ViT-G/14 (from EVA-CLIP) and a BLIP-2 Q-Former to encode video frames, and an Audio-Language branch that uses ImageBind to encode audio segments. Both branches project into Llama-2-Chat's embedding space through dedicated Q-Former adapters. The model is available in 7B and 13B parameter sizes based on Llama-2-Chat, trained on WebVid-2.5M and AudioCaps.

Video-LLaMA was one of the first models to demonstrate coherent audio-visual-text reasoning, understanding what is being said (audio), what is happening (visual), and answering questions that require combining both.

## Key Features
- Dual-branch architecture: Vision-Language + Audio-Language
- Video frame encoding via ViT-G/14 + BLIP-2 Q-Former
- Audio encoding via ImageBind
- Llama-2-Chat backbone (7B and 13B)
- Trained on WebVid-2.5M (video) + AudioCaps (audio)
- Supports video files (multiple frames) and audio streams simultaneously
- Multi-turn conversation about audio-visual content
- BSD-3-Clause license

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 3 | Good research baseline; audio-visual integration is unique; superseded on pure video benchmarks |
| **Security** | 4 | BSD-3-Clause; local deployment; ImageBind audio encoder has CC BY-NC (check commercial use) |
| **Scalability** | 3 | Standard inference; no specialized serving optimizations |
| **Support/Community** | 3 | 3.1K stars; DAMO Academy backing; moderately active |
| **Documentation** | 3 | Good README, inference examples; limited deployment guides |
| **Integration Ease** | 3 | Requires setup of dual-branch pipeline; more complex than single-branch VLMs |

## Use Cases
1. **Audio-visual content analysis** - Understand video content by combining speech, ambient sound, and visuals simultaneously
2. **Meeting/lecture analysis** - Process recorded meetings where understanding speech + visual aids together matters
3. **Media monitoring** - Analyze video clips for content moderation using both visual and audio signals
4. **Research on audio-visual fusion** - Reference architecture for models combining visual and audio understanding
5. **Accessibility applications** - Generate comprehensive descriptions of video content including audio events

## Getting Started
```bash
git clone https://github.com/DAMO-NLP-SG/Video-LLaMA
cd Video-LLaMA
pip install -r requirements.txt

# Download pre-trained weights (see repo for latest links)
# python download_models.py

# Inference demo
python inference.py \
    --cfg-path eval_configs/video_llama_eval_withaudio.yaml \
    --model_type llama_v2 \
    --gpu_id 0 \
    --video_path path/to/video.mp4 \
    --query "Describe what you see and hear in this video"
```

## Architecture / How It Works
Video-LLaMA's architecture has two branches that feed into the same LLM:

**Vision-Language Branch**: Video frames are sampled and encoded by EVA ViT-G/14. A Video Q-Former (based on BLIP-2) with positional embeddings aggregates frame features into a fixed number of visual tokens. A linear projection maps these to Llama-2's embedding dimension.

**Audio-Language Branch**: Audio segments are encoded using ImageBind's audio encoder. An Audio Q-Former aggregates audio features into a fixed number of audio tokens. A linear projection maps to Llama-2's embedding dimension.

Both visual and audio token sequences are concatenated with the text instruction and fed to Llama-2-Chat for response generation. Training is done in two stages: first training the Q-Formers and projectors with the LLM frozen, then fine-tuning with instruction data.

## Strengths
- Unique combined video + audio understanding in a single open-source model
- ImageBind audio encoder provides strong audio understanding capability
- BSD-3-Clause license is permissive
- Well-documented dual-branch architecture, useful as a research template
- Llama-2-Chat backbone enables natural conversation style

## Limitations
- Llama-2 backbone is older; newer LLMs offer better language quality
- ImageBind (CC BY-NC 4.0) in the audio branch creates commercial license complications
- Meta Llama-2 license adds commercial use terms
- Lower benchmark performance than modern VLMs on pure video understanding
- No support for very long videos
- Complex dual-branch setup requires more configuration than simpler VLMs

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Video-LLaVA | Unified image+video; Apache 2.0; no audio branch |
| Qwen2.5-VL | Better video understanding; no dedicated audio branch |
| InternLM-XComposer2.5 | Omnimodal including audio+video; larger; Apache 2.0 |
| SALMONN | More focused on audio+video quality; Apache 2.0 |

## References
- https://github.com/DAMO-NLP-SG/Video-LLaMA
- https://arxiv.org/abs/2306.02858 (Video-LLaMA paper)
- https://huggingface.co/DAMO-NLP-SG/Video-LLaMA-2-7B-Finetuned

## Notes
Video-LLaMA is the canonical reference for combined audio-visual LLM understanding. In practice, the ImageBind audio encoder (CC BY-NC) complicates commercial deployment. For production video understanding without audio, Video-LLaVA or modern VLMs (Qwen-VL, InternVL) offer better performance. For omnimodal audio+video, SALMONN or InternLM-XComposer2.5 are more recent alternatives.
