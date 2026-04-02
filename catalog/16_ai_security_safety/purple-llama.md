# Purple Llama / LlamaGuard + PromptGuard (Meta)

> Suite Meta pour la sécurité LLM — LlamaGuard (content safety) et PromptGuard (prompt injection).

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 16 - AI Security & Safety / Content Safety |
| **URL** | https://github.com/meta-llama/PurpleLlama |
| **GitHub** | https://github.com/meta-llama/PurpleLlama |
| **Stars** | ~4,100 |
| **License** | MIT + Llama Community License |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Purple Llama est la suite de sécurité de Meta pour les LLMs. Elle inclut LlamaGuard (classifieur de sécurité de contenu), PromptGuard (détecteur de prompt injection), et CyberSecEval (benchmark de sécurité). LlamaGuard peut classifier les inputs et outputs selon des catégories de risque personnalisables.

## Key Features
- **LlamaGuard**: Classifieur de sécurité de contenu (violence, sexual, illegal, etc.)
- **PromptGuard**: Détection de prompt injection et jailbreak
- **CyberSecEval**: Benchmark de sécurité pour LLMs
- **Customizable**: Catégories de risque personnalisables
- **Meta-backed**: Recherche Meta AI

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Production, Meta-backed |
| **Security** | 4 | Conçu pour la sécurité, licence mixte |
| **Scalability** | 4 | Modèles optimisés |
| **Support/Community** | 4 | 4.1k stars, Meta backing |
| **Documentation** | 3 | README + papers |
| **Integration Ease** | 3 | HuggingFace, mais modèles lourds |

## Use Cases
1. **Content moderation** — Classifier le contenu dangereux dans les outputs LLM
2. **Prompt injection defense** — Détecter les tentatives de jailbreak
3. **Benchmarking** — Évaluer la sécurité des LLMs

## Getting Started
```python
from transformers import AutoModelForCausalLM, AutoTokenizer
model = AutoModelForCausalLM.from_pretrained("meta-llama/LlamaGuard-3-8B")
tokenizer = AutoTokenizer.from_pretrained("meta-llama/LlamaGuard-3-8B")
# Classify content safety
```

## Strengths
- Meta-backed, modèles performants
- LlamaGuard + PromptGuard couvrent input et output
- CyberSecEval benchmark inclus
- Catégories personnalisables

## Limitations
- Llama Community License pour certains composants
- Modèles lourds (8B paramètres)
- Nécessite GPU

## Alternatives
| Tool | Key Difference |
|------|---------------|
| LLM Guard | Plus léger, MIT, modulaire |
| NeMo Guardrails | NVIDIA, architectural |
| OpenAI Moderation | API cloud, plus simple |

## References
- https://github.com/meta-llama/PurpleLlama
- https://ai.meta.com/research/publications/purple-llama-cyberseceval/
