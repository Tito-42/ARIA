# LLM Guard (ProtectAI)

> Suite de scanners pour sécuriser inputs/outputs LLM — toxicité, PII, prompt injection, code malveillant.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 16 - AI Security & Safety / Input/Output Security |
| **URL** | https://llm-guard.com |
| **GitHub** | https://github.com/protectai/llm-guard |
| **Stars** | ~2,800 |
| **License** | MIT |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
LLM Guard fournit des scanners modulaires pour sécuriser les inputs et outputs des LLMs. Il détecte la toxicité, les PII, les tentatives de prompt injection, le code malveillant, et plus. Chaque scanner est indépendant et composable.

## Key Features
- **Input scanners**: Anonymize, ban topics, prompt injection, toxicity
- **Output scanners**: Bias, code, malicious URLs, relevance
- **Modulaire**: Chaque scanner est indépendant
- **MIT licence**: Aucune restriction
- **API REST**: Serveur inclus

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Production, modulaire |
| **Security** | 5 | MIT, conçu pour la sécurité |
| **Scalability** | 3 | API REST, self-hosted |
| **Support/Community** | 3 | 2.8k stars, ProtectAI |
| **Documentation** | 4 | Docs complètes |
| **Integration Ease** | 4 | Scanners composables |

## Use Cases
1. **LLM security** — Sécuriser les applications LLM en production
2. **PII protection** — Détecter et masquer les données personnelles
3. **Prompt injection defense** — Bloquer les injections

## Getting Started
```python
from llm_guard import scan_prompt, scan_output
from llm_guard.input_scanners import Anonymize, PromptInjection, Toxicity
from llm_guard.output_scanners import Deanonymize, NoRefusal

input_scanners = [Anonymize(), PromptInjection(), Toxicity()]
sanitized_prompt, results_valid, results_score = scan_prompt(input_scanners, prompt)
```

## Strengths
- Scanners modulaires input + output
- MIT licence
- API REST incluse
- ProtectAI backing

## Limitations
- Communauté plus petite
- Certains scanners moins précis que des modèles dédiés

## Alternatives
| Tool | Key Difference |
|------|---------------|
| NeMo Guardrails | NVIDIA, Colang DSL, plus architectural |
| Guardrails AI | Hub communautaire, validation output |
| Presidio | Focus PII, Microsoft |

## References
- https://llm-guard.com
- https://github.com/protectai/llm-guard
