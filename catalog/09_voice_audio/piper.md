# Piper

> TTS local rapide pour Raspberry Pi et home assistants — 30+ langues, ultra-léger.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 09 - Voice & Audio / Text-to-Speech |
| **URL** | https://github.com/rhasspy/piper |
| **GitHub** | https://github.com/rhasspy/piper |
| **Stars** | ~10,700 |
| **License** | MIT |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Transition |
| **Maturity** | Production |

## What It Does
Piper est un moteur TTS ultra-léger conçu pour le Raspberry Pi et les home assistants (Home Assistant). Il fonctionne entièrement en local, avec 30+ langues et des voix VITS de qualité correcte. Idéal pour l'IoT et la domotique.

## Key Features
- **Ultra-léger**: Raspberry Pi, embedded
- **30+ langues**: Large couverture linguistique
- **Offline**: Aucune connexion requise
- **VITS models**: Voix neuronales compactes
- **Home Assistant**: Intégration native
- **MIT licence**: Aucune restriction

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Production, edge |
| **Security** | 5 | MIT, offline, local |
| **Scalability** | 3 | Edge, pas de GPU |
| **Support/Community** | 3 | 10.7k stars |
| **Documentation** | 3 | README et wiki |
| **Integration Ease** | 4 | CLI simple, Home Assistant |

## Use Cases
1. **Home automation** — TTS pour Home Assistant et domotique
2. **IoT** — Synthèse vocale sur Raspberry Pi et embarqué
3. **Offline TTS** — TTS sans internet

## Getting Started
```bash
echo "Hello world" | piper --model en_US-amy-medium --output_file output.wav
```

## Strengths
- Ultra-léger (Raspberry Pi)
- MIT
- 30+ langues
- Home Assistant intégré

## Limitations
- Qualité inférieure aux gros modèles
- Voix moins naturelles que ChatTTS/F5-TTS
- Projet en transition (migration OHF-Voice)

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Kokoro TTS | Apache 2.0, meilleure qualité |
| MeloTTS | MIT, multilingue |
| Sherpa-ONNX | ASR+TTS, ONNX runtime |

## References
- https://github.com/rhasspy/piper
