# WhisperX

> Whisper + word-level timestamps + speaker diarization + VAD — pipeline complet audio→texte aligné.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 09 - Voice & Audio / Speech-to-Text |
| **URL** | https://github.com/m-bain/whisperX |
| **GitHub** | https://github.com/m-bain/whisperX |
| **Stars** | ~21,000 |
| **License** | BSD-2 |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
WhisperX étend Whisper avec l'alignement word-level timestamps (via wav2vec2), la speaker diarization (identification des locuteurs), et le Voice Activity Detection. C'est le pipeline le plus complet pour obtenir une transcription structurée avec qui dit quoi et quand.

## Key Features
- **Word-level timestamps**: Alignement précis via wav2vec2/MMS
- **Speaker diarization**: Identification des locuteurs (pyannote)
- **VAD**: Silero VAD pour filtrage du silence
- **Batch processing**: Traitement par lot optimisé
- **Faster-Whisper backend**: Utilise CTranslate2

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Production, pipeline complet |
| **Security** | 4 | BSD-2, self-hosted |
| **Scalability** | 3 | GPU requis, dépendances multiples |
| **Support/Community** | 4 | 21k stars |
| **Documentation** | 3 | README complet |
| **Integration Ease** | 3 | Dépendances multiples (pyannote token HF) |

## Use Cases
1. **Meeting transcription** — Transcrire des réunions avec identification des locuteurs
2. **Podcast processing** — Transcriptions structurées de podcasts
3. **Subtitle generation** — Sous-titres avec timestamps mot-par-mot

## Getting Started
```python
import whisperx
model = whisperx.load_model("large-v3", device="cuda")
audio = whisperx.load_audio("meeting.mp3")
result = model.transcribe(audio, batch_size=16)
# Alignment
model_a, metadata = whisperx.load_align_model(language_code=result["language"])
result = whisperx.align(result["segments"], model_a, metadata, audio)
# Diarization
diarize_model = whisperx.DiarizationPipeline(use_auth_token="HF_TOKEN")
diarize_segments = diarize_model(audio)
result = whisperx.assign_word_speakers(diarize_segments, result)
```

## Architecture / How It Works
Pipeline séquentiel : (1) Faster-Whisper pour la transcription, (2) wav2vec2/MMS pour l'alignement phonétique, (3) pyannote pour la diarization, (4) Silero VAD pour le filtrage. Les résultats sont fusionnés pour produire une transcription avec timestamps et locuteurs.

## Strengths
- Pipeline STT le plus complet
- Word-level timestamps précis
- Speaker diarization
- Batch processing

## Limitations
- Setup complexe (pyannote nécessite token HF)
- Dépendances multiples
- Plus lent que Faster-Whisper seul

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Faster-Whisper | Plus rapide, pas de diarization |
| AssemblyAI | API commerciale, pipeline complet |

## References
- https://github.com/m-bain/whisperX

## Notes
WhisperX est le choix pour les transcriptions avec diarization. Pour la transcription simple, Faster-Whisper suffit et est plus rapide.
