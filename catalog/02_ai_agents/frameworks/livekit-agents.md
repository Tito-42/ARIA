# LiveKit Agents

> Framework for building real-time voice AI agents with STT/LLM/TTS orchestration and telephony support.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 02 - AI Agents / 09 - Voice & Audio |
| **URL** | https://docs.livekit.io/agents/ |
| **GitHub** | https://github.com/livekit/agents |
| **Stars** | 9,900 |
| **License** | Apache 2.0 |
| **Pricing** | Free (OSS) / LiveKit Cloud (paid) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
LiveKit Agents is a framework for building real-time voice AI agents that run on servers. It provides an ecosystem for mixing and matching STT (speech-to-text), LLM, TTS (text-to-speech), and Realtime API components, with built-in task scheduling, telephony support, semantic turn detection, and MCP integration.

The framework is specifically designed for conversational voice agents that need to perceive, understand, and respond in real-time -- use cases like virtual receptionists, customer support, sales assistants, and interactive voice applications.

## Key Features
- **Voice pipeline**: STT + LLM + TTS orchestration
- **Realtime API**: Support for OpenAI Realtime and similar APIs
- **Telephony**: Phone-based agent interactions via LiveKit's telephony stack
- **Semantic turn detection**: Transformer-based understanding of when users finish speaking
- **MCP integration**: Native support for Model Context Protocol tools
- **Task scheduling**: Built-in dispatch APIs for connecting users to agents
- **Testing framework**: Native test integration with LLM judges
- **Multi-agent handoffs**: Support for transferring between voice agents

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | LiveKit is production-grade WebRTC infrastructure |
| **Security** | 4 | LiveKit Cloud; self-hosted option |
| **Scalability** | 5 | LiveKit's WebRTC infrastructure scales massively |
| **Support/Community** | 4 | 9.9K stars; active development; extensive examples |
| **Documentation** | 4 | Good docs; restaurant ordering demo; multi-agent examples |
| **Integration Ease** | 4 | pip install; requires understanding of voice pipeline |

## Use Cases
1. **Voice assistants** - Real-time conversational AI agents
2. **Call center automation** - Telephony-based customer service agents
3. **Interactive voice applications** - Voice-controlled application interfaces
4. **Multi-modal agents** - Agents that see (video) and hear (audio)

## Getting Started
```bash
pip install "livekit-agents[openai,silero,deepgram,cartesia,turn-detector]~=1.4"
```

## Strengths
- Best-in-class voice agent infrastructure
- LiveKit's proven WebRTC platform as foundation
- Semantic turn detection solves a hard problem
- MCP integration for tool access
- Telephony support for real-world deployment

## Limitations
- Voice-specific; not a general-purpose agent framework
- Requires understanding of audio/voice pipeline
- LiveKit Cloud recommended for production (cost)
- Smaller community than general agent frameworks

## References
- https://docs.livekit.io/agents/
- https://github.com/livekit/agents

## Notes
LiveKit Agents fills the voice agent niche that most general-purpose agent frameworks ignore. For any team building voice-based AI interactions, this is the go-to framework. It pairs well with general agent frameworks (LangGraph, CrewAI) for the reasoning layer while handling the voice-specific challenges (turn detection, latency, telephony).
