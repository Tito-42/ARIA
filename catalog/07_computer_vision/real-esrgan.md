# Real-ESRGAN

> Super-résolution d'images (upscaling) — restauration et amélioration de photos et vidéos.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 07 - Computer Vision / Image Enhancement |
| **URL** | https://github.com/xinntao/Real-ESRGAN |
| **GitHub** | https://github.com/xinntao/Real-ESRGAN |
| **Stars** | ~34,900 |
| **License** | BSD-3 |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Stable |
| **Maturity** | Production |

## What It Does
Real-ESRGAN est le modèle de référence pour la super-résolution d'images (upscaling). Il améliore la résolution des images de 2x à 4x tout en restaurant les détails et en supprimant le bruit et les artefacts de compression. Il fonctionne aussi sur les vidéos frame par frame.

## Key Features
- **Upscaling 2x-4x**: Augmentation de résolution avec restauration
- **Real-world**: Entraîné sur des dégradations réelles (pas juste bicubique)
- **Anime model**: Modèle spécialisé pour l'anime/illustration
- **Vidéo**: Processing frame par frame
- **Portable**: Exécutables standalone (Windows, macOS, Linux)
- **GPU consommateur**: Fonctionne sur les GPU grand public

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Stable, largement utilisé |
| **Security** | 5 | BSD-3, self-hosted |
| **Scalability** | 3 | Batch processing, GPU recommandé |
| **Support/Community** | 4 | 34.9k stars |
| **Documentation** | 3 | README et exemples |
| **Integration Ease** | 4 | CLI et Python API, exécutables portables |

## Use Cases
1. **Image upscaling** — Augmenter la résolution de photos
2. **Restauration** — Restaurer des images basse qualité
3. **Video enhancement** — Améliorer la qualité de vidéos anciennes

## Getting Started
```bash
pip install realesrgan
# CLI
python inference_realesrgan.py -n RealESRGAN_x4plus -i input.jpg -o output/
```
```python
from realesrgan import RealESRGANer
upsampler = RealESRGANer(scale=4, model_path="weights/RealESRGAN_x4plus.pth")
output, _ = upsampler.enhance(img, outscale=4)
```

## Architecture / How It Works
Real-ESRGAN utilise un réseau RRDB (Residual in Residual Dense Block) entraîné avec un discriminateur GAN. Le modèle est entraîné sur des paires d'images dégradées/haute résolution avec des dégradations réalistes (blur, noise, compression JPEG, resize). Le pipeline de dégradation de second ordre simule des artefacts du monde réel.

## Strengths
- Référence upscaling, 34.9k stars
- BSD-3 licence permissive
- Exécutables portables
- Fonctionne sur GPU consommateur

## Limitations
- Modèle figé (pas de fine-tuning facile)
- Pas de super-résolution sémantique
- Lent sur CPU

## Alternatives
| Tool | Key Difference |
|------|---------------|
| ESRGAN | Prédécesseur, moins performant |
| SwinIR | Transformer-based, meilleur sur benchmarks |
| Stable Diffusion upscale | Diffusion-based, plus créatif mais moins fidèle |

## References
- https://github.com/xinntao/Real-ESRGAN
- https://arxiv.org/abs/2107.10833

## Notes
Real-ESRGAN est la solution standard d'upscaling. BSD-3 licence = pas de restrictions. Intégré dans de nombreux outils (ComfyUI, A1111) comme module d'upscaling.
