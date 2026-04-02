# Coqui TTS / XTTS

> Bibliothèque TTS avec XTTS v2 voice cloning zero-shot — archivé mais code toujours utilisable.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 09 - Voice & Audio / Text-to-Speech |
| **URL** | https://github.com/coqui-ai/TTS |
| **GitHub** | https://github.com/coqui-ai/TTS |
| **Stars** | ~45,000 |
| **License** | MPL 2.0 |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Archived |
| **Maturity** | Production (Legacy) |

## What It Does
Coqui TTS était la bibliothèque TTS open-source la plus populaire, avec XTTS v2 pour le voice cloning zero-shot multilingue. L'entreprise Coqui a fermé mais le code et les modèles restent disponibles et fonctionnels. XTTS v2 reste l'un des meilleurs modèles de voice cloning open-source.

## Key Features
- **XTTS v2**: Voice cloning zero-shot (6 secondes d'audio suffisent)
- **Multi-architectures**: Tacotron2, VITS, GlowTTS, XTTS
- **Multilingue**: 17+ langues (XTTS)
- **Voice cloning**: Cloner une voix avec un court échantillon
- **API simple**: Python API et CLI
- **Fine-tuning**: Entraînement sur voix custom

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 3 | Code fonctionnel mais archivé |
| **Security** | 3 | MPL 2.0, pas de maintenance |
| **Scalability** | 3 | GPU recommandé |
| **Support/Community** | 2 | **Archivé** — plus de support |
| **Documentation** | 3 | Docs existantes |
| **Integration Ease** | 4 | API Python simple |

## Use Cases
1. **Voice cloning** — Cloner une voix avec XTTS v2
2. **TTS multilingue** — Synthèse vocale en 17+ langues
3. **Legacy** — Projets existants utilisant Coqui TTS

## Getting Started
```python
from TTS.api import TTS
tts = TTS("tts_models/multilingual/multi-dataset/xtts_v2")
tts.tts_to_file(text="Hello world!", speaker_wav="reference.wav", language="en", file_path="output.wav")
```

## Strengths
- XTTS v2 = excellent voice cloning
- 45k stars, écosystème riche
- Multi-architectures
- Fine-tuning possible

## Limitations
- **Archivé** — Coqui a fermé
- Plus de maintenance ni de nouvelles features
- MPL 2.0 (obligations de partage de modifications)

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Fish Speech | Actif, haute qualité, licence restrictive |
| OpenVoice | Voice cloning MIT |
| Parler-TTS | HuggingFace, actif, Apache 2.0 |
| F5-TTS | Flow matching, actif |

## References
- https://github.com/coqui-ai/TTS

## Notes
**ARCHIVÉ.** Le code reste utilisable pour le voice cloning via XTTS v2. Pour de nouveaux projets, considérer Fish Speech, OpenVoice, ou Parler-TTS.
