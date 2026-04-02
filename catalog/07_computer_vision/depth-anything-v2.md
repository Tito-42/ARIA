# Depth Anything V2

> Estimation de profondeur monoculaire state-of-the-art — multiple tailles, très précis.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 07 - Computer Vision / Depth Estimation |
| **URL** | https://depth-anything-v2.github.io |
| **GitHub** | https://github.com/DepthAnything/Depth-Anything-V2 |
| **Stars** | ~7,800 |
| **License** | Apache 2.0 (Small) / Restrictive (Large) |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Depth Anything V2 est le modèle de référence pour l'estimation de profondeur monoculaire (prédire la profondeur 3D à partir d'une seule image 2D). Il fournit des cartes de profondeur denses et précises, utiles pour la reconstruction 3D, la réalité augmentée, la robotique et l'édition d'images.

Quatre tailles de modèles sont disponibles (Small, Base, Large, Giant), permettant de choisir le bon compromis vitesse/précision.

## Key Features
- **Depth estimation monoculaire**: Carte de profondeur à partir d'une image
- **4 tailles**: Small (25M), Base (98M), Large (335M), Giant (1.3B)
- **State-of-the-art**: Meilleur benchmark sur NYUv2 et KITTI
- **Video depth**: Estimation temporellement cohérente
- **Metric depth**: Possibilité de prédire la profondeur absolue

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | SOTA, modèles production-ready |
| **Security** | 3 | Apache 2.0 (Small seulement), grands modèles restrictifs |
| **Scalability** | 4 | Small model rapide, GPU ou CPU |
| **Support/Community** | 3 | 7.8k stars |
| **Documentation** | 3 | README et paper |
| **Integration Ease** | 4 | HuggingFace Transformers integration |

## Use Cases
1. **Réalité augmentée** — Occlusion correcte des objets virtuels
2. **Robotique** — Navigation et obstacle avoidance
3. **3D reconstruction** — Entrée pour reconstruction 3D

## Getting Started
```python
from transformers import pipeline
depth_estimator = pipeline("depth-estimation", model="depth-anything/Depth-Anything-V2-Small-hf")
result = depth_estimator("image.jpg")
depth_map = result["depth"]
```

## Architecture / How It Works
Depth Anything V2 utilise un encodeur DINOv2 (Vision Transformer) pré-entraîné et un décodeur DPT. L'entraînement utilise un large dataset de pseudo-labels générés par des modèles enseignants, puis fine-tune sur des datasets annotés manuellement.

## Strengths
- State-of-the-art en depth estimation
- Apache 2.0 (modèle Small)
- Multiple tailles pour différents budgets
- HuggingFace integration

## Limitations
- Grands modèles sous licence restrictive
- Depth relative (pas absolue) par défaut
- GPU recommandé pour temps réel

## Alternatives
| Tool | Key Difference |
|------|---------------|
| MiDaS | Intel, plus ancien, moins précis |
| ZoeDepth | Metric depth, ZeroDepth |
| Marigold | Diffusion-based, qualité fine |

## References
- https://github.com/DepthAnything/Depth-Anything-V2
- https://arxiv.org/abs/2406.09414

## Notes
Depth Anything V2 Small (Apache 2.0) est le choix par défaut pour la production. Pour la meilleure qualité, le modèle Giant est supérieur mais sous licence restrictive.
