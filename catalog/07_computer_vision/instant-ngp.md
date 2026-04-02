# Instant-NGP (NVIDIA)

> NeRF ultra-rapide par NVIDIA — training en secondes, multi-resolution hash encoding. Licence non-commerciale.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 07 - Computer Vision / 3D Vision |
| **URL** | https://nvlabs.github.io/instant-ngp/ |
| **GitHub** | https://github.com/NVlabs/instant-ngp |
| **Stars** | ~17,300 |
| **License** | NVIDIA Non-Commercial |
| **Pricing** | Free (Non-Commercial Only) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Research |

## What It Does
Instant-NGP accélère les Neural Radiance Fields (NeRF) de façon spectaculaire grâce au multi-resolution hash encoding. Le training d'une scène NeRF passe de heures à quelques secondes, et le rendering est quasi temps réel. C'est la contribution NVIDIA la plus influente en reconstruction 3D.

## Key Features
- **Training en secondes**: Multi-resolution hash encoding
- **Rendu quasi temps réel**: Optimisation GPU CUDA
- **Multi-tâches**: NeRF, SDF, image encoding, volume rendering
- **Hash encoding**: Innovation clé réutilisée partout
- **NVIDIA optimisé**: CUDA natif, performance maximale

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 3 | Performant mais recherche |
| **Security** | 1 | **NVIDIA Non-Commercial** — bloquant pour enterprise |
| **Scalability** | 3 | GPU NVIDIA requis |
| **Support/Community** | 4 | 17.3k stars, NVIDIA research |
| **Documentation** | 3 | Paper + README |
| **Integration Ease** | 2 | C++/CUDA, compilation complexe |

## Use Cases
1. **Recherche 3D** — Reconstruction et rendu de scènes 3D
2. **Prototypage** — Test rapide de reconstruction NeRF

## Getting Started
```bash
git clone --recursive https://github.com/NVlabs/instant-ngp
cmake . -B build
cmake --build build --config RelWithDebInfo
./build/testbed --scene data/nerf/fox
```

## Architecture / How It Works
Instant-NGP remplace l'encodage positionnel classique de NeRF par un multi-resolution hash encoding. Chaque niveau de résolution utilise une hash table de features apprenables. Cette approche permet au réseau d'être beaucoup plus petit (donc rapide) tout en capturant les détails fins.

## Strengths
- NeRF le plus rapide (training en secondes)
- Hash encoding réutilisé dans toute l'industrie
- Qualité de rendu élevée

## Limitations
- **Licence NVIDIA Non-Commercial** — bloquant pour enterprise
- GPU NVIDIA requis
- C++/CUDA, compilation complexe

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Nerfstudio | **Apache 2.0**, recommandé pour enterprise |
| 3D Gaussian Splatting | Plus rapide en rendu, aussi non-commercial |

## References
- https://github.com/NVlabs/instant-ngp
- https://arxiv.org/abs/2201.05989

## Notes
**ALERTE LICENCE: NVIDIA Non-Commercial.** L'innovation (hash encoding) est intégrée dans Nerfstudio (Apache 2.0). Pour l'enterprise, utiliser Nerfstudio qui intègre les mêmes concepts sous licence permissive.
