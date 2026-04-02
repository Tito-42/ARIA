# LiveKit Agents

> Framework pour voice agents en temps réel — WebRTC + pipeline STT→LLM→TTS, Apache 2.0.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 09 - Voice & Audio / Voice Agents |
| **URL** | https://agents.livekit.io |
| **GitHub** | https://github.com/livekit/agents |
| **Stars** | ~9,900 |
| **License** | Apache 2.0 |
| **Pricing** | Free (OSS) / LiveKit Cloud (Paid) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
LiveKit Agents est un framework pour construire des agents vocaux en temps réel. Il fournit un pipeline complet STT→LLM→TTS sur infrastructure WebRTC, avec support multi-provider (OpenAI, Deepgram, ElevenLabs, etc.). C'est le standard émergent pour les voice agents.

## Key Features
- **Pipeline voix complet**: STT → LLM → TTS en temps réel
- **WebRTC**: Infrastructure temps réel de grade production
- **Multi-provider**: OpenAI, Deepgram, ElevenLabs, Cartesia, etc.
- **Turn detection**: Détection de tours de parole
- **Function calling**: Les agents peuvent appeler des outils
- **LiveKit Cloud**: Déploiement managé

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | Production, WebRTC grade |
| **Security** | 4 | Apache 2.0, self-hosted possible |
| **Scalability** | 5 | WebRTC scale, LiveKit Cloud |
| **Support/Community** | 4 | 9.9k stars, très actif |
| **Documentation** | 4 | Docs complètes |
| **Integration Ease** | 4 | SDK Python, multi-provider |

## Use Cases
1. **Voice agents** — Construire des assistants vocaux IA temps réel
2. **Call centers** — Agents vocaux pour le support client
3. **Voice apps** — Applications vocales interactives

## Getting Started
```python
from livekit.agents import AutoSubscribe, JobContext, WorkerOptions, cli, llm
from livekit.agents.voice_assistant import VoiceAssistant
from livekit.plugins import openai, silero

async def entrypoint(ctx: JobContext):
    assistant = VoiceAssistant(
        vad=silero.VAD.load(),
        stt=openai.STT(),
        llm=openai.LLM(),
        tts=openai.TTS(),
    )
    assistant.start(ctx.room)

cli.run_app(WorkerOptions(entrypoint_fnc=entrypoint))
```

## Architecture / How It Works
LiveKit Agents utilise le serveur WebRTC LiveKit pour le transport audio temps réel. Le pipeline traite l'audio en streaming : VAD détecte la parole, STT transcrit, LLM génère une réponse, TTS synthétise la voix. Le turn detection gère les interruptions.

## Strengths
- Pipeline voix complet production-ready
- WebRTC temps réel
- Multi-provider flexible
- Apache 2.0

## Limitations
- Dépend de l'infrastructure LiveKit (ou self-hosted)
- Latence dépend des providers STT/LLM/TTS
- Coût des providers API

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Pipecat | Alternative open-source, Daily.co backed |
| Vocode | Open-source, voice agents aussi |
| Retell AI | API commerciale managed |

## References
- https://docs.livekit.io/agents
- https://github.com/livekit/agents
