# Stable Diffusion 3.5 / SDXL

> Modèles de génération d'images par Stability AI — écosystème mature, supercédé par FLUX en qualité.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 07 - Computer Vision / Image Generation |
| **URL** | https://stability.ai |
| **GitHub** | https://github.com/Stability-AI/generative-models |
| **Stars** | ~27,100 |
| **License** | MIT (SD 3.5) / CreativeML (SDXL) |
| **Pricing** | Free (Open Source) / Stability AI API (Paid) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active but superceded |
| **Maturity** | Production |

## What It Does
Stable Diffusion est la famille de modèles de génération d'images qui a lancé la révolution de l'image IA en 2022. SD 3.5 utilise l'architecture MM-DiT (Multimodal Diffusion Transformer), tandis que SDXL reste basé sur le UNet classique. L'écosystème de modèles communautaires (fine-tunés, LoRA, ControlNet) est le plus riche du marché.

En 2026, FLUX a supercédé Stable Diffusion en qualité pure, mais l'écosystème SD reste inégalé pour les modèles spécialisés et les workflows custom.

## Key Features
- **SDXL**: 1024x1024 natif, UNet architecture, écosystème massif
- **SD 3.5**: MM-DiT architecture, meilleur que SDXL
- **Fine-tuning accessible**: LoRA, DreamBooth, textual inversion
- **ControlNet**: Contrôle posé, profondeur, edges, etc.
- **Modèles communautaires**: Des milliers de modèles spécialisés sur CivitAI
- **Multi-outil**: ComfyUI, A1111, Diffusers, InvokeAI

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Mature, écosystème production |
| **Security** | 3 | Licences variées selon version, Stability AI instable |
| **Scalability** | 4 | Via Diffusers, APIs cloud |
| **Support/Community** | 5 | Communauté la plus large en image gen |
| **Documentation** | 4 | Docs HuggingFace, communauté |
| **Integration Ease** | 5 | Via HuggingFace Diffusers, trivial |

## Use Cases
1. **Modèles spécialisés** — Utiliser des LoRA/fine-tunes spécifiques (anime, photo, architecture)
2. **ControlNet workflows** — Génération contrôlée avec poses, edges, profondeur
3. **Fine-tuning custom** — Entraîner des modèles sur des styles/sujets spécifiques

## Getting Started
```python
from diffusers import StableDiffusionXLPipeline
import torch

pipe = StableDiffusionXLPipeline.from_pretrained(
    "stabilityai/stable-diffusion-xl-base-1.0", torch_dtype=torch.float16
)
pipe.to("cuda")
image = pipe("A beautiful sunset over mountains").images[0]
```

## Architecture / How It Works
SDXL utilise un UNet avec cross-attention pour le guidage textuel (CLIP + OpenCLIP). SD 3.5 utilise MM-DiT, un transformer qui traite conjointement les tokens texte et image. Les deux utilisent un VAE pour encoder/décoder l'espace latent.

## Strengths
- Écosystème de modèles communautaires le plus riche
- Fine-tuning accessible (LoRA en minutes)
- ControlNet mature
- Support universel dans tous les outils

## Limitations
- Qualité inférieure à FLUX en génération brute
- Stability AI instable financièrement
- Licences variées selon les versions

## Alternatives
| Tool | Key Difference |
|------|---------------|
| FLUX.1 | **Supérieur en qualité**, rectified flow, Apache 2.0 (schnell) |
| DALL-E 3 | API OpenAI, pas open-source |
| Midjourney | Qualité art, discord-only |

## References
- https://github.com/Stability-AI/generative-models
- https://huggingface.co/stabilityai

## Notes
L'écosystème SD reste pertinent pour les modèles spécialisés et le fine-tuning. Pour la génération brute, FLUX est supérieur. La situation financière de Stability AI est à surveiller pour la pérennité.
