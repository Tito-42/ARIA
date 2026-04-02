# MeloTTS

> TTS multilingue haute qualité par MyShell — optimisé production, MIT, léger et rapide.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 09 - Voice & Audio / Text-to-Speech |
| **URL** | https://github.com/myshell-ai/MeloTTS |
| **GitHub** | https://github.com/myshell-ai/MeloTTS |
| **Stars** | ~7,300 |
| **License** | MIT |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Reduced |
| **Maturity** | Production |

## What It Does
MeloTTS est un modèle TTS multilingue léger par MyShell, optimisé pour la production. MIT licence, rapide et compact, il est idéal pour les déploiements nécessitant un TTS fiable sans modèles lourds.

## Key Features
- **Multilingue**: Anglais, chinois, japonais, coréen, français, espagnol
- **MIT licence**: Aucune restriction
- **Léger et rapide**: Optimisé pour la production
- **Qualité** : Bonne qualité pour un modèle léger

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Production, MIT, léger |
| **Security** | 5 | MIT |
| **Scalability** | 4 | Léger, rapide |
| **Support/Community** | 2 | 7.3k stars, activité réduite |
| **Documentation** | 3 | README |
| **Integration Ease** | 4 | pip install, API simple |

## Use Cases
1. **TTS production léger** — Synthèse vocale rapide avec licence MIT
2. **Multilingue** — TTS dans 6+ langues

## Getting Started
```python
from melo.api import TTS
model = TTS(language="EN")
model.tts_to_file("Hello world", model.hps.data.spk2id["EN-US"], "output.wav")
```

## Strengths
- MIT licence
- Léger et rapide
- Multilingue

## Limitations
- Activité réduite
- Qualité inférieure aux modèles lourds
- Moins de langues

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Kokoro TTS | Apache 2.0, aussi léger |
| Parler-TTS | Apache 2.0, contrôle par prompt |
| Piper | Edge-optimized, MIT |

## References
- https://github.com/myshell-ai/MeloTTS
