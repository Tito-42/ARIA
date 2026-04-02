# VideoChat / VideoChat2

> Comprehensive open-source framework for video understanding with instruction tuning, featuring the MVBench evaluation benchmark for multimodal video models.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 17 - multimodal / video |
| **URL** | https://github.com/OpenGVLab/Ask-Anything |
| **GitHub** | https://github.com/OpenGVLab/Ask-Anything |
| **Stars** | 3 300 |
| **License** | MIT |
| **Pricing** | Free / Open Source |
| **Last Verified** | 2026-04-02 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
VideoChat and VideoChat2 are video understanding systems developed by OpenGVLab (the same lab behind InternVL). The repository ("Ask-Anything") covers the full evolution of their video LLM work. VideoChat2 focuses on video instruction tuning with an emphasis on temporal understanding, using a mixed dataset approach that covers spatial and temporal reasoning tasks.

A key contribution of this project is MVBench, a comprehensive evaluation benchmark for multimodal video understanding covering 20 distinct temporal reasoning tasks that static image models cannot solve. MVBench has become a standard for evaluating video LLM temporal understanding capabilities.

VideoChat2 was presented as a CVPR 2024 Highlight, validating its quality. The system uses UMT (Unified Masking Transformer) as the video encoder, connected to various LLMs (miniGPT4, StableLM, Vicuna, InternLM) via Q-Former adapters.

## Key Features
- Video instruction tuning with temporal understanding focus
- MVBench: comprehensive video evaluation benchmark (20 temporal tasks, 4000 QA pairs)
- UMT (Unified Masking Transformer) video encoder
- Multiple LLM backend support: miniGPT4, StableLM, Vicuna, InternLM
- CVPR 2024 Highlight paper
- MIT license
- Temporal task coverage: causal reasoning, counter-factual inference, scene transition, object interaction
- HuggingFace model hub integration

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 3 | CVPR Highlight validates quality; not as widely deployed as InternVL video |
| **Security** | 5 | MIT license; fully local |
| **Scalability** | 3 | Standard inference setup; no specific high-throughput optimizations |
| **Support/Community** | 4 | OpenGVLab (InternVL team) backing; 3.3K stars; active |
| **Documentation** | 4 | Good README, benchmark documentation, training guides |
| **Integration Ease** | 3 | Requires setup work; multiple LLM backend options add complexity |

## Use Cases
1. **Temporal video reasoning** - Applications requiring understanding of causality, scene transitions, and object interactions over time
2. **Video-based QA systems** - Answer complex questions about video content including temporal aspects
3. **VLM evaluation** - Use MVBench to benchmark and compare video LLM performance rigorously
4. **Video instruction following** - Generate structured responses from video content following natural language instructions
5. **Research on video temporal understanding** - Reference implementation for video-specific temporal reasoning

## Getting Started
```bash
git clone https://github.com/OpenGVLab/Ask-Anything
cd Ask-Anything/video_chat2
pip install -r requirements.txt

# Download model weights (see repo)
# python scripts/download_weights.py

# Run demo
python demo.py --model_path path/to/weights --video path/to/video.mp4

# Evaluate on MVBench
python eval/eval_mvbench.py --model_path path/to/weights
```

## Architecture / How It Works
VideoChat2 uses a UMT (Unified Masking Transformer) video encoder that processes video frames with temporal masking, enabling understanding of motion and temporal relationships. Video features are aggregated via a Q-Former adapted from BLIP-2, projecting into the LLM embedding space. The training data is a carefully curated mix covering spatial understanding, temporal understanding, and conversational data. The MVBench benchmark was designed to test 20 temporal reasoning abilities including action counting, scene transitions, and causal inference — tasks specifically not testable on static images.

## Strengths
- MVBench benchmark is now a community-standard evaluation tool for video LLMs
- CVPR 2024 Highlight validates research quality
- MIT license for both code and models
- Strong temporal reasoning focus that complements spatial VLM capabilities
- OpenGVLab backing (same team as InternVL)

## Limitations
- Not as actively maintained for production deployment as InternVL video
- Multiple LLM backend options create configuration complexity
- Lower benchmark performance than modern dedicated video LLMs (Qwen2.5-VL video)
- Older video encoder (UMT) compared to more recent architectures
- No audio understanding

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Video-LLaVA | Unified image+video; Apache 2.0; LanguageBind encoder |
| Qwen2.5-VL | SOTA video understanding; Qwen License; long video support |
| InternVL3.5 | Same lab; better overall benchmarks; supports video |
| LMMS-Eval | Evaluation framework covering many video benchmarks including MVBench |

## References
- https://github.com/OpenGVLab/Ask-Anything
- https://arxiv.org/abs/2311.17005 (VideoChat2 paper)
- https://arxiv.org/abs/2301.05226 (VideoChat original)
- https://huggingface.co/OpenGVLab/VideoChat2-7B

## Notes
VideoChat2's most lasting contribution may be MVBench rather than the model itself. When evaluating any video LLM, running MVBench provides the best coverage of temporal reasoning tasks. For production video understanding, newer models from the same lab (InternVL) or from Qwen offer better performance.
