# Faster-Whisper

> Réimplémentation de Whisper avec CTranslate2 — 4x plus rapide, moins de mémoire, batched inference.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 09 - Voice & Audio / Speech-to-Text |
| **URL** | https://github.com/SYSTRAN/faster-whisper |
| **GitHub** | https://github.com/SYSTRAN/faster-whisper |
| **Stars** | ~22,000 |
| **License** | MIT |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Faster-Whisper est une réimplémentation de Whisper utilisant CTranslate2 (moteur d'inférence optimisé). Il offre une accélération 4x par rapport au Whisper original avec une utilisation mémoire réduite, tout en restant compatible avec les modèles Whisper. C'est le choix production pour le STT serveur.

## Key Features
- **4x plus rapide**: CTranslate2 backend optimisé
- **Moins de mémoire**: FP16, INT8 quantization
- **Batched inference**: Traitement par lot
- **Compatible Whisper**: Utilise les mêmes modèles
- **Word-level timestamps**: Timestamps par mot
- **VAD filtering**: Silero VAD intégré

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | Standard production serveur |
| **Security** | 5 | MIT, self-hosted |
| **Scalability** | 4 | Batched inference, GPU optimisé |
| **Support/Community** | 4 | 22k stars |
| **Documentation** | 4 | README complet |
| **Integration Ease** | 5 | Drop-in replacement de Whisper |

## Use Cases
1. **Transcription production** — Serveur de transcription haute performance
2. **Batch processing** — Transcrire de gros volumes d'audio
3. **Real-time STT** — Transcription quasi temps réel avec VAD

## Getting Started
```python
from faster_whisper import WhisperModel
model = WhisperModel("large-v3", device="cuda", compute_type="float16")
segments, info = model.transcribe("audio.mp3", beam_size=5)
for segment in segments:
    print(f"[{segment.start:.2f}s -> {segment.end:.2f}s] {segment.text}")
```

## Architecture / How It Works
Faster-Whisper convertit les modèles Whisper au format CTranslate2 qui optimise les opérations Transformer (fusion de layers, INT8 quantization, batching optimisé). Le VAD Silero permet de skip les segments silencieux.

## Strengths
- 4x plus rapide que Whisper original
- Drop-in replacement
- VAD intégré
- MIT licence

## Limitations
- Dépend de CTranslate2
- GPU NVIDIA principalement
- Légèrement en retard sur les dernières features Whisper

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Whisper | Original, plus de features |
| whisper.cpp | CPU optimisé, edge |
| WhisperX | Diarization, alignement word-level |

## References
- https://github.com/SYSTRAN/faster-whisper

## Notes
Faster-Whisper est le choix par défaut pour le STT serveur en production. Combine vitesse et compatibilité Whisper.
