# Tiktoken

> Tokenizer BPE rapide par OpenAI — comptage de tokens et encoding/decoding pour GPT-3.5/4.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 08 - NLP & Text / Tokenization |
| **URL** | https://github.com/openai/tiktoken |
| **GitHub** | https://github.com/openai/tiktoken |
| **Stars** | ~17,800 |
| **License** | MIT |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Tiktoken est le tokenizer BPE officiel d'OpenAI, utilisé pour compter les tokens et encoder/décoder du texte pour les modèles GPT. Implémenté en Rust pour des performances maximales, il est 3-6x plus rapide que les alternatives Python pures.

## Key Features
- **Ultra-rapide**: Backend Rust, 3-6x plus rapide
- **Encodings OpenAI**: cl100k_base (GPT-4), o200k_base (GPT-4o)
- **Token counting**: Compter les tokens avant un appel API
- **Encode/Decode**: Tokenization bidirectionnelle
- **MIT licence**: Aucune restriction

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | Standard pour tokenization OpenAI |
| **Security** | 5 | MIT, local, pas d'API call |
| **Scalability** | 5 | Ultra-rapide, Rust backend |
| **Support/Community** | 4 | 17.8k stars, OpenAI |
| **Documentation** | 4 | README clair |
| **Integration Ease** | 5 | 2 lignes de code |

## Use Cases
1. **Token counting** — Estimer le coût avant un appel API OpenAI
2. **Prompt management** — Gérer la taille des prompts
3. **Text chunking** — Découper du texte par nombre de tokens

## Getting Started
```python
import tiktoken
enc = tiktoken.encoding_for_model("gpt-4o")
tokens = enc.encode("Hello, world!")
print(len(tokens))  # Nombre de tokens
text = enc.decode(tokens)
```

## Architecture / How It Works
Tiktoken implémente le Byte Pair Encoding (BPE) en Rust avec des bindings Python. Les encodings sont des vocabulaires de merge rules pré-calculés spécifiques à chaque famille de modèles OpenAI.

## Strengths
- Le plus rapide tokenizer BPE
- Standard pour l'écosystème OpenAI
- MIT licence
- Très simple d'utilisation

## Limitations
- Spécifique aux encodings OpenAI
- Pas un tokenizer universel
- Pas de support training custom BPE

## Alternatives
| Tool | Key Difference |
|------|---------------|
| HuggingFace Tokenizers | Multi-modèles, training custom, Rust aussi |
| SentencePiece | Google, training BPE/Unigram, C++ |

## References
- https://github.com/openai/tiktoken

## Notes
Tiktoken est indispensable pour tout projet utilisant l'API OpenAI. Pour d'autres modèles, HuggingFace Tokenizers est plus polyvalent.
