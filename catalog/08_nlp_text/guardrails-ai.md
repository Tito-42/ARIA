# Guardrails AI

> Validation et structuration des outputs LLM — guards composables pour qualité, format, sécurité.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 08 - NLP & Text / LLM Output Validation |
| **URL** | https://guardrailsai.com |
| **GitHub** | https://github.com/guardrails-ai/guardrails |
| **Stars** | ~6,600 |
| **License** | Apache 2.0 |
| **Pricing** | Free (OSS) / Guardrails Hub (Free + Paid validators) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Guardrails AI fournit un framework de validation composable pour les outputs LLM. Les "guards" vérifient et corrigent les réponses LLM pour la qualité, le format, la sécurité et la conformité. Le Hub fournit des validators pré-construits (PII, toxicité, hallucination, etc.).

## Key Features
- **Guards composables**: Empiler des validateurs
- **Guardrails Hub**: 50+ validators pré-construits
- **Multi-provider**: OpenAI, Anthropic, Cohere, etc.
- **Structured output**: JSON schema enforcement
- **PII detection**: Validation de données personnelles
- **Toxicity check**: Filtre de contenu toxique

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Production, utilisé en enterprise |
| **Security** | 4 | Apache 2.0, validateurs de sécurité |
| **Scalability** | 3 | Client-side processing |
| **Support/Community** | 3 | 6.6k stars |
| **Documentation** | 4 | Docs complètes, Hub |
| **Integration Ease** | 4 | Décorateurs sur clients LLM |

## Use Cases
1. **Output validation** — Vérifier que les LLMs retournent des données valides
2. **Safety guardrails** — Filtrer toxicité, PII, hallucinations
3. **Structured output** — Enforcer des schémas JSON

## Getting Started
```python
from guardrails import Guard
from guardrails.hub import ToxicLanguage, DetectPII

guard = Guard().use_many(ToxicLanguage(), DetectPII())
result = guard(
    model="gpt-4o",
    messages=[{"role": "user", "content": "Summarize this document"}]
)
```

## Architecture / How It Works
Guardrails wrappe les appels LLM et applique une chaîne de validators sur la réponse. Si un validator échoue, la réponse peut être rejetée, corrigée, ou retentée. Le Hub centralise les validators communautaires.

## Strengths
- Framework de validation composable
- Hub de validators
- Multi-provider
- Apache 2.0

## Limitations
- Overlap avec Instructor pour structured output
- Latence ajoutée par les validations
- Certains validators Hub sont payants

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Instructor | Focus structured extraction, plus simple |
| Outlines | Token-level constraints, modèles locaux |
| NeMo Guardrails | NVIDIA, focus conversation safety |

## References
- https://docs.guardrailsai.com
- https://github.com/guardrails-ai/guardrails

## Notes
Guardrails AI v0.9.2 (mars 2026). Complémentaire avec Instructor : Guardrails pour la validation/safety, Instructor pour la structured extraction.
