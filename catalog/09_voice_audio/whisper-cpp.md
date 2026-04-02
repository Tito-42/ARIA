# whisper.cpp

> Port C/C++ de Whisper par ggerganov — inférence CPU rapide, edge-compatible, multi-plateforme.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 09 - Voice & Audio / Speech-to-Text |
| **URL** | https://github.com/ggerganov/whisper.cpp |
| **GitHub** | https://github.com/ggerganov/whisper.cpp |
| **Stars** | ~48,000 |
| **License** | MIT |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
whisper.cpp est un port C/C++ de Whisper par ggerganov (créateur de llama.cpp). Il permet l'inférence Whisper sur CPU sans dépendance Python, avec support GGML/GGUF pour des modèles quantizés. Idéal pour l'edge computing et les appareils embarqués.

## Key Features
- **CPU optimisé**: Inférence rapide sans GPU
- **Multi-plateforme**: Windows, macOS, Linux, iOS, Android, WebAssembly
- **GGML/GGUF**: Modèles quantizés légers
- **Streaming**: Support temps réel
- **Zero dependencies**: Pas de Python, pas de PyTorch
- **Bindings**: Python, Go, Rust, Java, etc.

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | Production, edge-ready |
| **Security** | 5 | MIT, local, pas de dépendances |
| **Scalability** | 4 | CPU scaling, edge deployment |
| **Support/Community** | 5 | 48k stars, ggerganov |
| **Documentation** | 3 | README, exemples |
| **Integration Ease** | 4 | CLI + bindings multi-langages |

## Use Cases
1. **Edge ASR** — Transcription sur appareils embarqués
2. **Desktop apps** — Intégration dans des applications desktop
3. **Mobile** — Transcription offline iOS/Android

## Getting Started
```bash
git clone https://github.com/ggerganov/whisper.cpp
cd whisper.cpp && make
./main -m models/ggml-base.en.bin -f audio.wav
```

## Architecture / How It Works
whisper.cpp ré-implémente l'architecture Transformer de Whisper en C/C++ pur avec GGML, une bibliothèque tenseur optimisée pour CPU (SIMD, ARM NEON, AVX). Les modèles GGUF sont quantizés (Q4, Q5, Q8) pour réduire la mémoire.

## Strengths
- CPU ultra-rapide, pas de GPU nécessaire
- Zero dependencies
- Multi-plateforme (même WebAssembly)
- MIT licence

## Limitations
- Moins de features que le Whisper Python original
- Mise à jour en retard sur les derniers modèles Whisper
- Qualité légèrement inférieure aux modèles FP16

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Faster-Whisper | Python, CTranslate2, GPU optimisé |
| Sherpa-ONNX | ONNX runtime, multi-plateforme aussi |
| Vosk | Offline ASR, modèles plus anciens |

## References
- https://github.com/ggerganov/whisper.cpp

## Notes
whisper.cpp est le choix pour l'ASR edge/embedded. Pour les serveurs avec GPU, Faster-Whisper est plus performant.
