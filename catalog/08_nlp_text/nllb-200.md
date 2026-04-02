# NLLB-200 (Meta)

> Modèle de traduction multilingue par Meta — 200 langues, incluant langues à faibles ressources.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 08 - NLP & Text / Translation |
| **URL** | https://ai.meta.com/research/no-language-left-behind |
| **GitHub** | https://huggingface.co/facebook/nllb-200-distilled-600M |
| **Stars** | ~912k téléchargements/mois (HuggingFace) |
| **License** | CC-BY-NC 4.0 |
| **Pricing** | Free (Non-Commercial) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
NLLB-200 (No Language Left Behind) est le modèle de traduction multilingue de Meta, couvrant 200 langues, y compris de nombreuses langues à faibles ressources souvent ignorées par les services commerciaux. Des versions distillées (600M, 1.3B paramètres) permettent un déploiement accessible.

## Key Features
- **200 langues**: La couverture la plus large disponible
- **Langues rares**: Support de langues à faibles ressources
- **Modèles distillés**: 600M et 1.3B paramètres
- **Qualité compétitive**: Performance proche des systèmes commerciaux
- **HuggingFace**: Intégration native Transformers

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Production, Meta backed |
| **Security** | 2 | **CC-BY-NC 4.0 — non-commercial** |
| **Scalability** | 4 | Modèles distillés légers |
| **Support/Community** | 4 | 912k téléchargements/mois |
| **Documentation** | 3 | Paper + HuggingFace docs |
| **Integration Ease** | 5 | Via HuggingFace Transformers |

## Use Cases
1. **Traduction multilingue** — Traduire entre 200 langues
2. **Langues rares** — Traduire des langues non couvertes par Google/DeepL
3. **Research** — Benchmarking de traduction multilingue

## Getting Started
```python
from transformers import AutoModelForSeq2SeqLM, AutoTokenizer

model = AutoModelForSeq2SeqLM.from_pretrained("facebook/nllb-200-distilled-600M")
tokenizer = AutoTokenizer.from_pretrained("facebook/nllb-200-distilled-600M")

inputs = tokenizer("Hello, how are you?", return_tensors="pt")
translated = model.generate(**inputs, forced_bos_token_id=tokenizer.convert_tokens_to_ids("fra_Latn"))
print(tokenizer.decode(translated[0], skip_special_tokens=True))
```

## Architecture / How It Works
NLLB-200 utilise une architecture encoder-decoder Transformer. Le modèle est entraîné sur des données parallèles couvrant 200 langues avec des techniques de filtrage de qualité (LASER embeddings). Les modèles distillés utilisent la knowledge distillation pour réduire la taille.

## Strengths
- 200 langues, la couverture la plus large
- Support de langues rares
- Modèles distillés légers
- Meta Research backing

## Limitations
- **CC-BY-NC 4.0 — non-commercial**, vérifier avec legal
- Qualité variable selon les paires de langues
- Pas aussi bon que Google/DeepL pour les langues majeures

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Google Translate API | Commercial, meilleure qualité langues majeures |
| DeepL API | Qualité premium, 30+ langues, commercial |
| Opus-MT | Helsinki, Apache 2.0, paires spécifiques |
| SeamlessM4T | Meta, multi-modal (texte + voix), non-commercial |

## References
- https://ai.meta.com/research/no-language-left-behind
- https://huggingface.co/facebook/nllb-200-distilled-600M
- https://arxiv.org/abs/2207.04672

## Notes
**ALERTE LICENCE: CC-BY-NC 4.0 — non-commercial.** Pour un usage commercial, utiliser Opus-MT (Apache 2.0) pour des paires spécifiques, ou les APIs Google/DeepL. NLLB reste unique pour les langues rares.
