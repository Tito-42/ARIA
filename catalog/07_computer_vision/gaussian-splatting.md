# 3D Gaussian Splatting

> Rendu 3D temps réel par gaussian splatting — reconstruction photo-réaliste de scènes 3D. Licence non-commerciale.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 07 - Computer Vision / 3D Vision |
| **URL** | https://repo-sam.inria.fr/fungraph/3d-gaussian-splatting/ |
| **GitHub** | https://github.com/graphdeco-inria/gaussian-splatting |
| **Stars** | ~21,200 |
| **License** | Non-Commercial Research |
| **Pricing** | Free (Non-Commercial Research Only) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Research |

## What It Does
3D Gaussian Splatting est une technique révolutionnaire de reconstruction et rendu 3D en temps réel. À partir de photos d'une scène, il reconstruit une représentation 3D sous forme de gaussiennes 3D qui peuvent être rendues en temps réel à 100+ FPS, avec une qualité photo-réaliste supérieure aux NeRF.

C'est la percée la plus significative en rendu 3D depuis les NeRF, avec un training plus rapide et un rendu beaucoup plus efficace.

## Key Features
- **Rendu temps réel**: 100+ FPS rendering
- **Photo-réaliste**: Qualité supérieure aux NeRF
- **Training rapide**: Minutes vs heures pour les NeRF
- **Explicit representation**: Gaussiennes 3D manipulables
- **Multi-échelle**: Détails fins et larges scènes
- **Compact**: Représentation plus légère que les grilles volumiques

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 3 | Technique mature mais recherche |
| **Security** | 1 | **Licence NON-COMMERCIALE** — bloquant pour enterprise |
| **Scalability** | 3 | GPU requis pour training et rendering |
| **Support/Community** | 4 | 21.2k stars, communauté recherche active |
| **Documentation** | 3 | Paper + README |
| **Integration Ease** | 2 | Setup C++/CUDA complexe |

## Use Cases
1. **Virtual tours** — Reconstruction 3D de lieux réels (si licence OK)
2. **Recherche** — Reconstruction 3D, rendu neuronal
3. **Digital twins** — Jumeau numérique de scènes réelles

## Getting Started
```bash
git clone https://github.com/graphdeco-inria/gaussian-splatting --recursive
# Préparer les images COLMAP
python train.py -s /path/to/scene
# Visualiser
./SIBR_viewers/bin/SIBR_gaussianViewer_app -m /path/to/output
```

## Architecture / How It Works
La scène est représentée par des millions de gaussiennes 3D, chacune définie par position, covariance, opacité et harmoniques sphériques (couleur). Le training optimise ces paramètres pour reproduire les vues d'entraînement. Le rendu utilise un rasterizer GPU différentiable qui "splatte" les gaussiennes projetées sur l'écran.

## Strengths
- Révolutionnaire : rendu temps réel photo-réaliste
- Training beaucoup plus rapide que NeRF
- Qualité supérieure aux NeRF
- Représentation explicite et manipulable

## Limitations
- **Licence non-commerciale** — bloquant pour enterprise
- Setup C++/CUDA complexe
- Taille mémoire importante pour grandes scènes
- Pas de vues dynamiques natives

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Nerfstudio | **Apache 2.0**, inclut 3DGS, recommandé pour enterprise |
| Instant-NGP | NVIDIA, NeRF rapide, aussi non-commercial |
| Luma AI | API commerciale de 3DGS |

## References
- https://github.com/graphdeco-inria/gaussian-splatting
- https://arxiv.org/abs/2308.14737
- https://repo-sam.inria.fr/fungraph/3d-gaussian-splatting/

## Notes
**ALERTE LICENCE: Non-commerciale.** Pour un usage enterprise de 3D Gaussian Splatting, utiliser **Nerfstudio** (Apache 2.0) qui inclut une implémentation compatible. La technique est révolutionnaire mais la licence de l'implémentation originale est bloquante.
