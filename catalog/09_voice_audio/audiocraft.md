# AudioCraft / MusicGen (Meta)

> Suite Meta pour génération audio — MusicGen (musique), AudioGen (effets sonores), EnCodec (codec neural).

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 09 - Voice & Audio / Audio Generation |
| **URL** | https://github.com/facebookresearch/audiocraft |
| **GitHub** | https://github.com/facebookresearch/audiocraft |
| **Stars** | ~23,000 |
| **License** | MIT (code) / CC-NC (modèles) |
| **Pricing** | Free (Non-Commercial pour modèles) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
AudioCraft est la suite Meta pour la génération audio, comprenant MusicGen (génération de musique), AudioGen (effets sonores), et EnCodec (codec audio neural). MusicGen permet de générer de la musique à partir de descriptions textuelles ou de mélodies de référence.

## Key Features
- **MusicGen**: Text-to-music, melody-conditioned generation
- **AudioGen**: Génération d'effets sonores par texte
- **EnCodec**: Codec audio neural haute qualité
- **Multiple tailles**: Small, medium, large
- **Melody conditioning**: Guider par une mélodie
- **HuggingFace**: Intégration native

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Production, Meta-backed |
| **Security** | 3 | Code MIT, **modèles CC-NC** |
| **Scalability** | 3 | GPU requis |
| **Support/Community** | 4 | 23k stars, Meta Research |
| **Documentation** | 3 | README + paper |
| **Integration Ease** | 4 | HuggingFace integration |

## Use Cases
1. **Génération musicale** — Créer de la musique à partir de descriptions
2. **Effets sonores** — Générer des sons d'ambiance
3. **Audio research** — Recherche en génération audio

## Getting Started
```python
from audiocraft.models import MusicGen
model = MusicGen.get_pretrained('facebook/musicgen-small')
model.set_generation_params(duration=8)
wav = model.generate(["happy upbeat electronic music"])
```

## Strengths
- State-of-the-art génération musicale
- Suite complète (musique + effets + codec)
- Meta-backed
- HuggingFace integration

## Limitations
- **Modèles CC-NC** — non-commercial
- GPU requis (lourd)
- Durée limitée (~30s par génération)

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Stable Audio Tools | Stability AI, MIT |
| Suno AI | Commercial, qualité premium |
| Udio | Commercial, concurrent Suno |

## References
- https://github.com/facebookresearch/audiocraft
- https://arxiv.org/abs/2306.05284
