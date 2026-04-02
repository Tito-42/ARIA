# Grounded-SAM

> Pipeline combinant Grounding DINO + SAM — texte → détection → segmentation automatique, zero-shot.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 07 - Computer Vision / Segmentation |
| **URL** | https://github.com/IDEA-Research/Grounded-Segment-Anything |
| **GitHub** | https://github.com/IDEA-Research/Grounded-Segment-Anything |
| **Stars** | ~17,500 |
| **License** | Apache 2.0 |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Grounded-SAM combine Grounding DINO (détection par texte) et SAM/SAM 2 (segmentation universelle) en un pipeline unifié. On décrit les objets en texte, Grounding DINO les détecte, et SAM génère les masques de segmentation précis. Le tout sans entraînement spécifique.

C'est le pipeline le plus puissant pour la segmentation zero-shot guidée par texte.

## Key Features
- **Pipeline complet**: Texte → détection → segmentation
- **Zero-shot**: Aucun entraînement nécessaire
- **Multi-modèles**: Grounding DINO + SAM/SAM 2 + optionnel (Stable Diffusion, OSX)
- **Inpainting**: Combinaison avec Stable Diffusion pour l'édition d'images
- **Tracking vidéo**: Via SAM 2 pour la segmentation vidéo
- **Apache 2.0**: Utilisable commercialement

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 3 | Fonctionne bien mais pipeline lourd |
| **Security** | 4 | Apache 2.0, self-hosted |
| **Scalability** | 2 | Pipeline lourd, GPU puissant requis |
| **Support/Community** | 4 | 17.5k stars, communauté active |
| **Documentation** | 3 | Exemples et notebooks disponibles |
| **Integration Ease** | 3 | Pipeline multi-modèles à configurer |

## Use Cases
1. **Annotation automatique** — Pré-segmenter des images pour le labeling
2. **Image editing** — Sélectionner et remplacer des objets par texte
3. **Video segmentation** — Suivre et segmenter des objets dans des vidéos

## Getting Started
```python
# Grounded-SAM 2 pipeline
from grounded_sam2 import GroundedSAM2

pipeline = GroundedSAM2()
masks, boxes, labels = pipeline.predict(
    image="photo.jpg",
    text_prompt="person . dog"
)
```

## Architecture / How It Works
Le pipeline exécute séquentiellement : (1) Grounding DINO encode le texte et l'image pour produire des bounding boxes, (2) SAM/SAM 2 prend ces boxes comme prompts et génère des masques de segmentation précis. Pour la vidéo, SAM 2 propage les masques temporellement avec son streaming memory.

## Strengths
- Pipeline texte→segmentation le plus puissant
- Zero-shot, pas d'entraînement
- Apache 2.0
- Extension vidéo via SAM 2

## Limitations
- Pipeline lourd (2+ modèles en mémoire GPU)
- Latence élevée (non temps réel)
- Configuration multi-modèles complexe

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Florence-2 | Plus léger, multi-tâche, moins précis |
| YOLO + SAM | YOLO temps réel + SAM, mais pas open-set |

## References
- https://github.com/IDEA-Research/Grounded-Segment-Anything
- https://arxiv.org/abs/2401.14159

## Notes
Grounded-SAM est le gold standard pour la segmentation zero-shot. Pour la production haute performance, considérer des modèles fine-tunés spécialisés. Pour le prototypage et l'annotation, c'est imbattable.
