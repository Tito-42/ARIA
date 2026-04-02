# ChatTTS

> TTS conversationnel optimisé pour le dialogue — prosodie naturelle, contrôle du style. Licence restrictive.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 09 - Voice & Audio / Text-to-Speech |
| **URL** | https://github.com/2noise/ChatTTS |
| **GitHub** | https://github.com/2noise/ChatTTS |
| **Stars** | ~39,000 |
| **License** | AGPL / CC-NC |
| **Pricing** | Free (Non-Commercial) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
ChatTTS est un modèle TTS spécifiquement optimisé pour le dialogue conversationnel. Il produit une prosodie naturelle avec des pauses, des hésitations et des variations de ton qui rendent la synthèse vocale remarquablement humaine.

## Key Features
- **Prosodie naturelle**: Pauses, hésitations, ton conversationnel
- **Contrôle fin**: Vitesse, émotion, style
- **Multi-speaker**: Voix variées
- **Qualité impressionnante**: Parmi les meilleurs TTS pour le dialogue

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 3 | Bon mais licence restrictive |
| **Security** | 2 | **AGPL + CC-NC** — très restrictif |
| **Scalability** | 3 | GPU recommandé |
| **Support/Community** | 4 | 39k stars |
| **Documentation** | 3 | README |
| **Integration Ease** | 3 | Python API |

## Use Cases
1. **Chatbots vocaux** — TTS naturel pour assistants conversationnels (si licence OK)
2. **Recherche** — Exploration de TTS conversationnel

## Getting Started
```python
import ChatTTS
chat = ChatTTS.Chat()
chat.load()
wavs = chat.infer(["Hello, how are you doing today?"])
```

## Strengths
- Prosodie conversationnelle la plus naturelle
- Contrôle fin du style
- 39k stars

## Limitations
- **AGPL + CC-NC** — bloquant pour commercial
- Documentation limitée
- Modèles lourds

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Parler-TTS | Apache 2.0, contrôle par prompt |
| Fish Speech | Haute qualité, licence restrictive aussi |
| Kokoro TTS | Apache 2.0, léger |

## References
- https://github.com/2noise/ChatTTS

## Notes
**ALERTE LICENCE: AGPL + CC-NC.** Excellente qualité conversationnelle mais bloquant pour usage commercial. Parler-TTS (Apache 2.0) est l'alternative licence-safe.
