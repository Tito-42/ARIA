# Parler-TTS (HuggingFace)

> TTS par HuggingFace avec contrôle par description textuelle du style vocal — Apache 2.0.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 09 - Voice & Audio / Text-to-Speech |
| **URL** | https://github.com/huggingface/parler-tts |
| **GitHub** | https://github.com/huggingface/parler-tts |
| **Stars** | ~5,600 |
| **License** | Apache 2.0 |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Beta |

## What It Does
Parler-TTS permet de contrôler le style de la voix synthétisée via une description textuelle ("a warm, deep male voice speaking slowly"). C'est un nouveau paradigme de contrôle TTS par prompt, développé par HuggingFace.

## Key Features
- **Contrôle par prompt**: "A female voice, warm and soft" → voix correspondante
- **Apache 2.0**: Licence permissive
- **HuggingFace**: Intégration native
- **Descriptif**: Pas besoin d'échantillon audio de référence

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 3 | Beta, en développement |
| **Security** | 5 | Apache 2.0 |
| **Scalability** | 3 | GPU requis |
| **Support/Community** | 3 | 5.6k stars, HuggingFace |
| **Documentation** | 3 | README + HF docs |
| **Integration Ease** | 4 | HuggingFace Transformers |

## Use Cases
1. **TTS personnalisable** — Décrire la voix souhaitée par texte
2. **Prototypage** — Tester des styles de voix sans échantillons audio

## Getting Started
```python
from parler_tts import ParlerTTSForConditionalGeneration
from transformers import AutoTokenizer
model = ParlerTTSForConditionalGeneration.from_pretrained("parler-tts/parler-tts-mini-v1")
tokenizer = AutoTokenizer.from_pretrained("parler-tts/parler-tts-mini-v1")
description = "A warm, friendly female voice speaking at a moderate pace"
input_ids = tokenizer(description, return_tensors="pt").input_ids
prompt_ids = tokenizer("Hello, how are you?", return_tensors="pt").input_ids
generation = model.generate(input_ids=input_ids, prompt_input_ids=prompt_ids)
```

## Strengths
- Paradigme innovant (contrôle par prompt textuel)
- Apache 2.0
- HuggingFace backing

## Limitations
- Encore en beta
- Qualité en amélioration
- GPU requis

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Kokoro TTS | Apache 2.0, léger, production |
| MeloTTS | MIT, multilingue, léger |
| StyleTTS2 | MIT, style diffusion |

## References
- https://github.com/huggingface/parler-tts
