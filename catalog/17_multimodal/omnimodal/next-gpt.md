# NExT-GPT

> The first end-to-end any-to-any multimodal LLM that can perceive and generate arbitrary combinations of text, image, video, and audio in a single unified system.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 17 - multimodal / omnimodal |
| **URL** | https://next-gpt.github.io/ |
| **GitHub** | https://github.com/NExT-GPT/NExT-GPT |
| **Stars** | 3 600 |
| **License** | BSD-3-Clause |
| **Pricing** | Free / Open Source |
| **Last Verified** | 2026-04-02 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
NExT-GPT is the first open-source end-to-end multimodal LLM capable of perceiving inputs and generating outputs in any combination of text, images, video, and audio. Unlike most multimodal models that only accept multiple input types but only output text, NExT-GPT closes the loop: it can generate image, video, or audio responses in addition to text, making it a genuine any-to-any model.

The system connects an LLM (Vicuna) with encoders for each input modality (ImageBind for image, audio, video) and decoders for each output modality (Stable Diffusion for images, ZeroScope for video, AudioLDM for audio). A lightweight alignment mechanism connects the LLM to the decoders without fully fine-tuning them, keeping training efficient. The system was published as an oral paper at ICML 2024.

NExT-GPT serves as the canonical architecture reference for "any-to-any" multimodal systems and has inspired subsequent work on unified generation+understanding models.

## Key Features
- Any-to-any multimodal I/O: text, image, video, audio — both input and output
- End-to-end system with LLM backbone (Vicuna-7B)
- Input encoders: ImageBind (image, audio, video), CLIP
- Output decoders: Stable Diffusion (image), ZeroScope (video), AudioLDM (audio)
- Lightweight alignment via small projection layers + modality signal tokens
- ICML 2024 Oral paper
- BSD-3-Clause license
- Instruction-following for multimodal generation tasks
- Cross-modal content creation (describe an image and get audio/video response)

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 2 | Research prototype; generation quality limited by decoder models used |
| **Security** | 4 | BSD-3-Clause code; ImageBind CC BY-NC complicates commercial use |
| **Scalability** | 2 | Multiple decoder models in memory simultaneously is resource-intensive |
| **Support/Community** | 3 | 3.6K stars; ICML Oral validates quality; moderate community activity |
| **Documentation** | 4 | Good paper, GitHub README, demo available |
| **Integration Ease** | 2 | Complex multi-model setup; not designed for production API use |

## Use Cases
1. **Creative content generation** - Generate image, video, or audio responses from any input modality combination
2. **Multimodal content transformation** - Convert audio descriptions to images, images to audio descriptions, etc.
3. **Research reference architecture** - Study and extend the any-to-any multimodal paradigm
4. **Multimedia story generation** - Create multi-modal narratives from text prompts
5. **Prototyping omnimodal applications** - Test any-to-any workflows before building production-specialized systems

## Getting Started
```bash
git clone https://github.com/NExT-GPT/NExT-GPT
cd NExT-GPT
pip install -r requirements.txt

# Download pre-trained encoders and decoder adapters
bash scripts/download_pretrained_weights.sh

# Launch demo
python demo.py --base_model path/to/vicuna \
               --image_root_path ./data/images \
               --video_root_path ./data/videos \
               --audio_root_path ./data/audios

# Inference with Python
from model.nextgpt import NExTGPT
model = NExTGPT.from_pretrained("NExT-GPT/NExT-GPT-7B")
response = model.generate(
    text="Create an image of a sunset over the ocean",
    output_modality="image"
)
```

## Architecture / How It Works
NExT-GPT uses a modular any-to-any architecture:

**Input side**: Each input modality (image, video, audio) is encoded by ImageBind into embeddings. A small linear projection maps these to Vicuna-7B's embedding dimension. Text input passes through Vicuna's tokenizer directly.

**Processing**: Vicuna-7B processes the combined multimodal tokens. The LLM is instructed to output special "modality signal tokens" indicating which output modality to generate along with the textual content.

**Output side**: Detected modality signal tokens trigger the corresponding decoder — Stable Diffusion for images, ZeroScope for video, AudioLDM for audio. A small translation network maps LLM output embeddings to decoder conditioning embeddings. Text output goes through the standard LLM decode path.

The key innovation is that only the projection layers and signal token classifiers are trained, while all encoders, the LLM, and decoders remain frozen. This makes training data-efficient but limits output quality to the capability of the frozen decoders.

## Strengths
- First open-source end-to-end any-to-any system (historically significant)
- ICML 2024 Oral validates architectural innovation
- BSD-3-Clause license for code
- Elegant lightweight alignment strategy (frozen decoders, trained projectors only)
- Reference architecture for unified generation+understanding research

## Limitations
- Output quality limited by the frozen decoder models (not state-of-the-art for any individual modality)
- Very resource-intensive: requires multiple large models loaded simultaneously
- ImageBind CC BY-NC in the encoder pipeline complicates commercial use
- Vicuna backbone superseded by newer, more capable LLMs
- Not designed for production throughput or latency requirements
- Generation latency is high due to sequential encoder-LLM-decoder pipeline

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Janus-Pro | Cleaner unified comprehension+generation architecture; image only; production-ready |
| 4M (EPFL/Apple) | Foundation model approach to any-to-any; more principled training |
| ImageBind | Input encoding only; no generation; 6 modalities |
| CogVLM + SDXL | Separate specialized models; better quality per modality |

## References
- https://next-gpt.github.io/
- https://github.com/NExT-GPT/NExT-GPT
- https://arxiv.org/abs/2309.05519 (NExT-GPT ICML 2024 paper)
- https://huggingface.co/NExT-GPT/NExT-GPT-7B

## Notes
NExT-GPT is primarily important as an architectural reference and proof-of-concept for any-to-any multimodal systems. For production use cases, specialized models per modality typically deliver better quality. If a unified any-to-any model is needed, Janus-Pro offers a cleaner and more production-tested approach for image comprehension+generation, while NExT-GPT covers more modalities at the cost of lower individual quality.
