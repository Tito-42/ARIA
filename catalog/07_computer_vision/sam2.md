# SAM 2 (Segment Anything Model 2)

> Modèle de segmentation universel par Meta/FAIR — images et vidéo, zero-shot, streaming memory.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 07 - Computer Vision / Segmentation |
| **URL** | https://sam2.metademolab.com |
| **GitHub** | https://github.com/facebookresearch/sam2 |
| **Stars** | ~18,800 |
| **License** | Apache 2.0 |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
SAM 2 est le successeur de Segment Anything Model par Meta/FAIR. Il étend la segmentation universelle aux images ET aux vidéos avec un modèle unifié. SAM 2 peut segmenter n'importe quel objet dans une image ou une vidéo à partir de prompts (points, boîtes, masques, texte via Grounding DINO).

L'innovation clé est la streaming memory architecture qui permet de propager les masques de segmentation à travers les frames vidéo de façon efficace, sans retraiter l'intégralité de la vidéo.

## Key Features
- **Segmentation universelle**: Images + vidéo dans un modèle
- **Multi-prompt**: Points, boîtes, masques, texte (via Grounding DINO)
- **Streaming memory**: Propagation efficace dans les vidéos
- **4 tailles**: Tiny, Small, Base+, Large
- **Zero-shot**: Pas d'entraînement spécifique nécessaire
- **SA-V dataset**: Entraîné sur le plus grand dataset de segmentation vidéo

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Production-ready, Meta-backed |
| **Security** | 4 | Apache 2.0, self-hosted |
| **Scalability** | 3 | GPU requis, tailles variées pour différents budgets |
| **Support/Community** | 5 | 18.8k stars, Meta/FAIR backing |
| **Documentation** | 4 | Docs Meta, notebooks, démo interactive |
| **Integration Ease** | 4 | API Python claire, HuggingFace integration |

## Use Cases
1. **Segmentation interactive** — Segmenter des objets en cliquant/dessinant
2. **Video object segmentation** — Suivre et segmenter des objets dans des vidéos
3. **Annotation assistée** — Accélérer le labeling de datasets

## Getting Started
```python
from sam2.build_sam import build_sam2
from sam2.sam2_image_predictor import SAM2ImagePredictor

model = build_sam2("sam2_hiera_l.yaml", "sam2_hiera_large.pt")
predictor = SAM2ImagePredictor(model)

predictor.set_image(image)
masks, scores, logits = predictor.predict(
    point_coords=[[500, 375]],
    point_labels=[1]
)
```

## Architecture / How It Works
SAM 2 utilise un image encoder (Hiera), un prompt encoder, un mask decoder, et une streaming memory (memory bank + memory attention). Pour les vidéos, les features des frames précédentes sont stockées dans le memory bank et utilisées via cross-attention pour propager les masques.

## Strengths
- Segmentation universelle la plus performante
- Images + vidéo dans un modèle unifié
- Apache 2.0
- Meta/FAIR backing

## Limitations
- GPU requis (pas de CPU inference efficace)
- Large model = VRAM significatif
- Pas de classification des segments

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Grounded-SAM | SAM + Grounding DINO pour segmentation par texte |
| Ultralytics YOLO | Segmentation d'instance temps réel, classes fixes |
| Florence-2 | Multi-tâche plus léger |

## References
- https://github.com/facebookresearch/sam2
- https://arxiv.org/abs/2408.00714
- https://sam2.metademolab.com

## Notes
SAM 2 est le standard de segmentation universelle en 2026. Pour la segmentation guidée par texte, le combiner avec Grounding DINO (Grounded-SAM). Pour la segmentation temps réel, YOLO reste plus rapide.
