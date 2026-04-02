# FLUX.1

> Modèle de génération d'images par Black Forest Labs — rectified flow transformers, standard 2025-2026.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 07 - Computer Vision / Image Generation |
| **URL** | https://blackforestlabs.ai |
| **GitHub** | https://github.com/black-forest-labs/flux |
| **Stars** | ~25,400 |
| **License** | Apache 2.0 (schnell) / Propriétaire (pro/dev) |
| **Pricing** | Free (schnell) / API payante (pro/dev) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
FLUX.1 est le modèle de génération d'images qui a remplacé Stable Diffusion comme standard en 2025-2026. Développé par Black Forest Labs (fondée par des ex-Stability AI), il utilise une architecture rectified flow transformer qui produit des images de meilleure qualité en moins de steps.

FLUX existe en trois variantes : schnell (rapide, Apache 2.0), dev (qualité élevée, non-commercial), et pro (API commerciale, qualité maximale).

## Key Features
- **Rectified flow**: Génération en moins de steps que la diffusion classique
- **Transformer architecture**: MM-DiT (Multimodal Diffusion Transformer)
- **3 variantes**: schnell (Apache 2.0), dev (research), pro (commercial API)
- **Text rendering**: Meilleur rendu de texte dans les images
- **Résolutions variées**: Support multi-résolution
- **ComfyUI/Diffusers**: Intégration avec les principaux outils

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Standard actuel de génération d'images |
| **Security** | 3 | schnell Apache 2.0, mais pro/dev licences restrictives |
| **Scalability** | 4 | API Black Forest Labs, ou self-hosted |
| **Support/Community** | 5 | 25.4k stars, communauté massive, ComfyUI ecosystem |
| **Documentation** | 3 | Docs basiques, communauté fournit les tutoriels |
| **Integration Ease** | 4 | Via HuggingFace Diffusers ou ComfyUI |

## Use Cases
1. **Génération d'images** — Créer des images à partir de descriptions textuelles
2. **Design et créatif** — Prototypage visuel, concept art
3. **Content generation** — Production de visuels pour marketing/médias

## Getting Started
```python
from diffusers import FluxPipeline
import torch

pipe = FluxPipeline.from_pretrained(
    "black-forest-labs/FLUX.1-schnell", torch_dtype=torch.bfloat16
)
pipe.to("cuda")

image = pipe("A cat sitting on a rainbow", num_inference_steps=4).images[0]
image.save("flux_output.png")
```

## Architecture / How It Works
FLUX utilise un Multimodal Diffusion Transformer (MM-DiT) avec rectified flow matching. Au lieu du processus de diffusion classique (bruit → image en many steps), le rectified flow apprend un chemin direct entre bruit et image, nécessitant moins de steps. L'encodeur texte utilise T5 et CLIP pour un guidage textuel précis.

## Strengths
- Qualité d'image supérieure à Stable Diffusion
- Moins de steps = génération plus rapide
- schnell est Apache 2.0
- Meilleur rendu de texte dans les images

## Limitations
- Modèle pro/dev à licences restrictives
- VRAM significatif (~12GB pour schnell)
- Moins de modèles fine-tunés communautaires que SD (mais en croissance)

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Stable Diffusion 3.5 | Legacy, plus de modèles communautaires |
| DALL-E 3 | API OpenAI, pas open-source |
| Midjourney | Qualité art, pas open-source |
| Ideogram | Bon pour texte, API commerciale |

## References
- https://blackforestlabs.ai
- https://github.com/black-forest-labs/flux
- https://huggingface.co/black-forest-labs/FLUX.1-schnell

## Notes
FLUX.1 est le nouveau standard pour la génération d'images open-source. schnell (Apache 2.0) pour la production, dev pour la R&D. La migration depuis Stable Diffusion est facilitée par le support natif dans Diffusers et ComfyUI.
