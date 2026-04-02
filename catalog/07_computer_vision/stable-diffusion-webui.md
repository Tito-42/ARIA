# Stable Diffusion WebUI (AUTOMATIC1111)

> Interface web de référence historique pour Stable Diffusion — 162k stars, écosystème d'extensions massif, legacy.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 07 - Computer Vision / Image Generation |
| **URL** | https://github.com/AUTOMATIC1111/stable-diffusion-webui |
| **GitHub** | https://github.com/AUTOMATIC1111/stable-diffusion-webui |
| **Stars** | ~162,000 |
| **License** | AGPL-3.0 |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Maintenance / Legacy |
| **Maturity** | Production |

## What It Does
AUTOMATIC1111's Stable Diffusion WebUI est l'interface web qui a démocratisé la génération d'images par IA. Avec 162k stars, c'est l'un des projets les plus populaires de GitHub. Elle fournit une UI Gradio complète pour Stable Diffusion avec extensions, LoRA, ControlNet, et img2img.

Bien que supercédé par ComfyUI pour les workflows avancés, A1111 reste très utilisé pour sa simplicité et son écosystème d'extensions mature.

## Key Features
- **UI simple**: Interface Gradio intuitive
- **Extensions massives**: Plus grand écosystème d'extensions
- **txt2img / img2img**: Génération et édition d'images
- **ControlNet**: Contrôle posé, profondeur, edges
- **LoRA support**: Fine-tuning léger
- **Inpainting/Outpainting**: Édition et extension d'images

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 3 | Fonctionnel mais legacy, maintenance mode |
| **Security** | 2 | AGPL-3.0 (très restrictif pour commercial) |
| **Scalability** | 2 | Single-user, pas conçu pour la production |
| **Support/Community** | 4 | 162k stars, mais développement ralenti |
| **Documentation** | 3 | Wiki communautaire |
| **Integration Ease** | 3 | API disponible, mais UI-first |

## Use Cases
1. **Génération simple** — Interface accessible pour la génération d'images
2. **Extensions legacy** — Certaines extensions n'existent que pour A1111

## Getting Started
```bash
git clone https://github.com/AUTOMATIC1111/stable-diffusion-webui
cd stable-diffusion-webui
./webui.sh  # Linux/Mac
```

## Architecture / How It Works
A1111 utilise Gradio pour l'UI, avec un backend PyTorch qui charge les modèles Stable Diffusion. Les extensions sont des plugins Python qui ajoutent des tabs, des scripts, et des post-processings.

## Strengths
- 162k stars, le plus populaire
- Le plus grand écosystème d'extensions
- Interface simple et accessible
- Communauté massive

## Limitations
- AGPL-3.0 (bloquant pour commercial)
- Legacy, supercédé par ComfyUI pour les workflows avancés
- Support FLUX limité comparé à ComfyUI
- Développement ralenti

## Alternatives
| Tool | Key Difference |
|------|---------------|
| ComfyUI | **Recommandé** — Node-based, plus flexible, FLUX natif |
| Fooocus | Simplifié, Midjourney-like UX |
| InvokeAI | Node-based, Apache 2.0 |

## References
- https://github.com/AUTOMATIC1111/stable-diffusion-webui

## Notes
A1111 est en mode legacy. Pour de nouveaux projets, ComfyUI est le standard. La migration est facilitée par le support des mêmes modèles. Licence AGPL-3.0 à considérer sérieusement.
