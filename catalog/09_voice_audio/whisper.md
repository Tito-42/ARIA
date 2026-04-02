# OpenAI Whisper

> Modèle ASR multilingue par OpenAI — transcription et traduction robustes, 100+ langues, MIT.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 09 - Voice & Audio / Speech-to-Text |
| **URL** | https://github.com/openai/whisper |
| **GitHub** | https://github.com/openai/whisper |
| **Stars** | ~97,000 |
| **License** | MIT |
| **Pricing** | Free (Open Source) / OpenAI API (Paid) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Whisper est le modèle de reconnaissance vocale (ASR) de référence par OpenAI. Il transcrit et traduit la parole dans 100+ langues avec une robustesse remarquable au bruit, aux accents et aux conditions audio dégradées. C'est le standard open-source pour la transcription audio.

## Key Features
- **100+ langues**: Couverture multilingue massive
- **Robuste au bruit**: Fonctionne bien en conditions dégradées
- **Translation**: Traduction audio → texte anglais
- **Multiple tailles**: tiny, base, small, medium, large, turbo
- **MIT licence**: Aucune restriction
- **Timestamps**: Word et segment level

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | Standard ASR, 97k stars |
| **Security** | 5 | MIT, self-hosted |
| **Scalability** | 3 | GPU requis pour temps réel, pas de streaming natif |
| **Support/Community** | 5 | 97k stars, OpenAI |
| **Documentation** | 4 | README + paper |
| **Integration Ease** | 5 | 3 lignes Python |

## Use Cases
1. **Transcription** — Transcrire des réunions, podcasts, vidéos
2. **Traduction** — Traduire de l'audio non-anglais en texte anglais
3. **Sous-titrage** — Générer des sous-titres avec timestamps

## Getting Started
```python
import whisper
model = whisper.load_model("turbo")
result = model.transcribe("audio.mp3")
print(result["text"])
```

## Architecture / How It Works
Whisper utilise une architecture encoder-decoder Transformer. L'encodeur traite un spectrogramme log-mel de 30 secondes, et le décodeur génère le texte token par token. Le modèle est entraîné sur 680k heures d'audio multilingue web-scraped.

## Strengths
- Standard ASR, qualité state-of-the-art
- 100+ langues
- MIT licence
- Robuste au bruit

## Limitations
- Lent en inférence (Python natif)
- GPU nécessaire pour temps réel
- Pas de streaming natif

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Faster-Whisper | 4x plus rapide, CTranslate2 |
| whisper.cpp | CPU optimisé, C/C++ |
| WhisperX | Timestamps word-level, diarization |
| Deepgram | API commerciale, temps réel |

## References
- https://github.com/openai/whisper
- https://arxiv.org/abs/2212.04356

## Notes
Whisper est le standard. Pour la production, utiliser Faster-Whisper (4x plus rapide) ou whisper.cpp (CPU/edge). WhisperX ajoute diarization et timestamps précis.
