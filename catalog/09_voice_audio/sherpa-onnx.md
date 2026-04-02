# Sherpa-ONNX

> Runtime ONNX pour ASR/TTS en temps réel — multi-plateforme, streaming, edge-ready.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 09 - Voice & Audio / Speech Infrastructure |
| **URL** | https://k2-fsa.github.io/sherpa/onnx |
| **GitHub** | https://github.com/k2-fsa/sherpa-onnx |
| **Stars** | ~11,300 |
| **License** | Apache 2.0 |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Sherpa-ONNX fournit un runtime ASR et TTS en temps réel basé sur ONNX Runtime. Multi-plateforme (mobile, desktop, embedded), il supporte le streaming et fonctionne sans GPU. C'est l'alternative la plus complète à Vosk pour l'ASR/TTS edge.

## Key Features
- **ASR + TTS**: Reconnaissance et synthèse vocale
- **Streaming**: Transcription en temps réel
- **Multi-plateforme**: iOS, Android, Windows, Linux, macOS, embedded
- **ONNX optimisé**: Modèles optimisés pour CPU
- **Multiple modèles**: Whisper, Zipformer, Paraformer, etc.
- **Apache 2.0**: Licence permissive

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Production, edge-ready |
| **Security** | 5 | Apache 2.0, local, offline |
| **Scalability** | 3 | CPU, edge-focused |
| **Support/Community** | 3 | 11.3k stars, actif |
| **Documentation** | 3 | Docs et exemples |
| **Integration Ease** | 4 | Multi-plateforme, bindings variés |

## Use Cases
1. **Edge ASR/TTS** — Reconnaissance et synthèse sur appareils embarqués
2. **Mobile apps** — ASR/TTS offline pour iOS/Android
3. **Streaming** — Transcription temps réel sur CPU

## Getting Started
```python
import sherpa_onnx
recognizer = sherpa_onnx.OnlineRecognizer.from_pretrained(
    model_type="whisper", whisper_encoder="encoder.onnx", whisper_decoder="decoder.onnx"
)
```

## Strengths
- ASR + TTS dans un runtime
- Multi-plateforme complet
- Apache 2.0
- Streaming natif

## Limitations
- Communauté plus petite
- Documentation parfois fragmentée
- Qualité dépend des modèles ONNX disponibles

## Alternatives
| Tool | Key Difference |
|------|---------------|
| whisper.cpp | Whisper spécialisé, GGML |
| Vosk | Plus ancien, Kaldi-based |

## References
- https://github.com/k2-fsa/sherpa-onnx
