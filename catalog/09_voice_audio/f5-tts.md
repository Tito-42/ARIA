# F5-TTS

> TTS flow-matching — haute qualité, zero-shot voice cloning. Licence modèles CC-NC.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 09 - Voice & Audio / Text-to-Speech |
| **URL** | https://github.com/SWivid/F5-TTS |
| **GitHub** | https://github.com/SWivid/F5-TTS |
| **Stars** | ~14,300 |
| **License** | MIT (code) / CC-NC (modèles) |
| **Pricing** | Free (Non-Commercial pour modèles) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
F5-TTS utilise le flow matching (comme FLUX pour les images) pour la synthèse vocale. Il produit des voix de très haute qualité avec voice cloning zero-shot, représentant l'état de l'art en TTS open-source.

## Key Features
- **Flow matching**: Architecture innovante pour TTS
- **Zero-shot voice cloning**: Clone avec échantillon court
- **Haute qualité**: Voix naturelles state-of-the-art
- **MIT code**: Code ouvert

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 3 | Bon mais modèles CC-NC |
| **Security** | 2 | **Modèles CC-NC** — non-commercial |
| **Scalability** | 3 | GPU requis |
| **Support/Community** | 3 | 14.3k stars |
| **Documentation** | 3 | README |
| **Integration Ease** | 3 | Python API |

## Use Cases
1. **TTS research** — Exploration du flow matching pour TTS
2. **Voice cloning** — Cloning haute qualité (non-commercial)

## Getting Started
```python
from f5_tts.api import F5TTS
model = F5TTS()
audio = model.infer(ref_file="reference.wav", ref_text="Hello", gen_text="How are you?")
```

## Strengths
- Qualité state-of-the-art
- Flow matching innovant
- Voice cloning zero-shot

## Limitations
- **Modèles CC-NC** — bloquant commercial
- GPU requis
- Relativement nouveau

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Parler-TTS | Apache 2.0, HuggingFace |
| Kokoro TTS | Apache 2.0, léger |
| OpenVoice | MIT, voice cloning |

## References
- https://github.com/SWivid/F5-TTS
