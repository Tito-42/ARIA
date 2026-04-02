# Nerfstudio

> Framework modulaire pour NeRF et 3D Gaussian Splatting — seul framework Apache 2.0 pour la 3D vision.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 07 - Computer Vision / 3D Vision |
| **URL** | https://docs.nerf.studio |
| **GitHub** | https://github.com/nerfstudio-project/nerfstudio |
| **Stars** | ~11,400 |
| **License** | Apache 2.0 |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Nerfstudio est le seul framework Apache 2.0 complet pour la reconstruction 3D. Il fournit une plateforme modulaire supportant NeRF, 3D Gaussian Splatting, et d'autres méthodes de reconstruction 3D. C'est le choix recommandé pour l'enterprise car les implémentations originales (Instant-NGP, 3DGS) sont sous licences non-commerciales.

## Key Features
- **Multi-méthodes**: NeRF, Nerfacto, 3D Gaussian Splatting, Instant-NGP
- **Apache 2.0**: Seul framework 3D avec licence permissive
- **Modulaire**: Components interchangeables
- **Viewer web**: Visualisation interactive dans le navigateur
- **Pipeline complet**: Data processing → training → rendering → export
- **Well-documented**: Docs et tutoriels complets

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Production-ready, Apache 2.0 |
| **Security** | 5 | Apache 2.0 — **seul choix sûr pour enterprise** |
| **Scalability** | 3 | GPU requis, single-node |
| **Support/Community** | 4 | 11.4k stars, communauté active |
| **Documentation** | 5 | Docs excellentes, tutoriels progressifs |
| **Integration Ease** | 4 | CLI et Python API, bien structuré |

## Use Cases
1. **Reconstruction 3D commerciale** — Seule option Apache 2.0
2. **Digital twins** — Reconstruction de scènes réelles
3. **Virtual tours** — Captures 3D navigables

## Getting Started
```bash
pip install nerfstudio
# Traiter des images
ns-process-data images --data /path/to/images --output-dir /path/to/output
# Entraîner
ns-train nerfacto --data /path/to/output
# Visualiser
ns-viewer --load-config outputs/nerfacto/config.yml
```

## Architecture / How It Works
Nerfstudio utilise une architecture modulaire : DataManager (chargement des données), Model (NeRF/3DGS), Pipeline (training loop), et Viewer (visualisation web). Les modèles sont des composants interchangeables partageant la même interface.

## Strengths
- **Seul framework 3D Apache 2.0** — recommandé pour enterprise
- Multi-méthodes dans un framework unifié
- Viewer web interactif
- Documentation excellente

## Limitations
- Performance légèrement inférieure aux implémentations originales
- GPU requis
- Communauté plus petite que les projets de recherche

## Alternatives
| Tool | Key Difference |
|------|---------------|
| 3D Gaussian Splatting | Plus performant, mais **non-commercial** |
| Instant-NGP | Plus rapide, mais **NVIDIA non-commercial** |
| Luma AI | API commerciale, pas open-source |

## References
- https://docs.nerf.studio
- https://github.com/nerfstudio-project/nerfstudio

## Notes
**Nerfstudio est le SEUL choix recommandé pour l'enterprise en 3D vision.** Les alternatives (3DGS, Instant-NGP) ont des licences non-commerciales bloquantes. Nerfstudio intègre les mêmes techniques sous Apache 2.0.
