# Vosk

> Kit de reconnaissance vocale offline — 20+ langues, mobile et edge, Raspberry Pi compatible.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 09 - Voice & Audio / Speech-to-Text |
| **URL** | https://alphacephei.com/vosk |
| **GitHub** | https://github.com/alphacep/vosk-api |
| **Stars** | ~14,500 |
| **License** | Apache 2.0 |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Maintained |
| **Maturity** | Production |

## What It Does
Vosk est un kit de reconnaissance vocale offline, optimisé pour les appareils embarqués et mobile. Il fonctionne sur Raspberry Pi, Android, iOS, et supporte 20+ langues avec des modèles compacts. Idéal pour les cas nécessitant de l'ASR offline sans connexion internet.

## Key Features
- **Offline**: Aucune connexion internet requise
- **20+ langues**: Modèles multilingues compacts
- **Edge**: Raspberry Pi, Android, iOS, embedded
- **Streaming**: Transcription en temps réel
- **Multi-binding**: Python, Java, C#, JavaScript, Go
- **Speaker identification**: Identification de locuteurs

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Production, edge-optimized |
| **Security** | 5 | Apache 2.0, offline, local |
| **Scalability** | 3 | CPU, modèles légers |
| **Support/Community** | 3 | 14.5k stars |
| **Documentation** | 3 | Docs correctes |
| **Integration Ease** | 4 | Multi-binding, API simple |

## Use Cases
1. **Offline ASR** — Transcription sans internet
2. **IoT/Edge** — Reconnaissance vocale sur Raspberry Pi, embarqué
3. **Mobile** — ASR offline Android/iOS

## Getting Started
```python
from vosk import Model, KaldiRecognizer
import wave

model = Model("vosk-model-en-us-0.22")
wf = wave.open("audio.wav", "rb")
rec = KaldiRecognizer(model, wf.getframerate())
while True:
    data = wf.readframes(4000)
    if len(data) == 0: break
    rec.AcceptWaveform(data)
print(rec.FinalResult())
```

## Architecture / How It Works
Vosk utilise Kaldi/Vosk-engine comme backend ASR avec des modèles acoustiques compacts (Nnet3/Chain). Les modèles sont optimisés pour le CPU avec des vocabulaires réduits pour la vitesse.

## Strengths
- Offline complet, zero internet
- Edge/mobile optimisé
- Apache 2.0
- Multi-binding

## Limitations
- Qualité inférieure à Whisper
- Modèles plus anciens (pas de transformers)
- Communauté plus petite

## Alternatives
| Tool | Key Difference |
|------|---------------|
| whisper.cpp | Qualité Whisper sur CPU |
| Sherpa-ONNX | ONNX optimisé, plus moderne |

## References
- https://alphacephei.com/vosk
- https://github.com/alphacep/vosk-api

## Notes
Vosk reste pertinent pour l'ASR offline sur hardware limité. Pour la meilleure qualité offline, whisper.cpp avec un modèle small est souvent préférable.
