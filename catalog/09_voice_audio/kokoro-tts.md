# Kokoro TTS

> TTS léger et rapide — optimisé edge et production, Apache 2.0.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 09 - Voice & Audio / Text-to-Speech |
| **URL** | https://github.com/kokoro-xtts/kokoro |
| **GitHub** | https://github.com/kokoro-xtts/kokoro |
| **Stars** | ~6,200 |
| **License** | Apache 2.0 |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Kokoro TTS est un modèle TTS léger et rapide, conçu pour les déploiements edge et production. Apache 2.0, il est l'un des rares TTS production-ready avec une licence permissive et une faible empreinte compute.

## Key Features
- **Léger**: Faible empreinte mémoire et compute
- **Rapide**: Inférence temps réel sur CPU
- **Apache 2.0**: Licence permissive
- **Production-ready**: Conçu pour le déploiement

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Production, Apache 2.0 |
| **Security** | 5 | Apache 2.0 |
| **Scalability** | 4 | Léger, CPU possible |
| **Support/Community** | 3 | 6.2k stars, en croissance |
| **Documentation** | 3 | README |
| **Integration Ease** | 4 | Simple à déployer |

## Use Cases
1. **Edge TTS** — Synthèse vocale sur appareils embarqués
2. **Production TTS** — TTS rapide avec licence Apache 2.0

## Getting Started
```python
import kokoro
model = kokoro.KokoroTTS()
audio = model.generate("Hello, how are you?")
```

## Strengths
- Apache 2.0
- Léger et rapide
- Edge-compatible

## Limitations
- Communauté en croissance
- Moins de voix que les gros modèles
- Qualité correcte mais pas state-of-the-art

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Piper | Edge aussi, MIT, home automation |
| MeloTTS | MIT, multilingue |
| Parler-TTS | Apache 2.0, contrôle par prompt |

## References
- https://github.com/kokoro-xtts/kokoro
