# Fish Speech

> TTS haute qualité avec voice cloning — multilingual, faible latence. Licence propriétaire.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 09 - Voice & Audio / Text-to-Speech |
| **URL** | https://speech.fish.audio |
| **GitHub** | https://github.com/fishaudio/fish-speech |
| **Stars** | ~29,000 |
| **License** | Proprietary |
| **Pricing** | Free (restrictions commerciales) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Fish Speech est un modèle TTS haute qualité avec voice cloning multilingue et faible latence. Il produit des voix naturelles et expressives, rivalisant avec les solutions commerciales comme ElevenLabs.

## Key Features
- **Haute qualité**: Voix naturelles, prosodie fine
- **Voice cloning**: Zero-shot avec échantillon court
- **Multilingue**: Support de nombreuses langues
- **Faible latence**: Optimisé pour le temps réel
- **API**: REST API pour intégration

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Production-ready |
| **Security** | 2 | **Licence propriétaire** — vérifier conditions |
| **Scalability** | 4 | API, GPU optimisé |
| **Support/Community** | 4 | 29k stars |
| **Documentation** | 3 | README et docs |
| **Integration Ease** | 4 | API et Python |

## Use Cases
1. **TTS haute qualité** — Synthèse vocale production (si licence OK)
2. **Voice cloning** — Cloner des voix pour personnalisation

## Getting Started
```bash
pip install fish-speech
fish-speech serve --model fish-speech-1.4
```

## Strengths
- Qualité audio excellente
- Voice cloning performant
- Faible latence

## Limitations
- **Licence propriétaire** — vérifier pour usage commercial
- Dépend de GPU

## Alternatives
| Tool | Key Difference |
|------|---------------|
| OpenVoice | MIT, voice cloning |
| Parler-TTS | Apache 2.0, HuggingFace |
| ElevenLabs | API commerciale, qualité premium |

## References
- https://github.com/fishaudio/fish-speech
