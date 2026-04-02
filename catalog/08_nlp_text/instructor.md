# Instructor

> Extraction structurée via LLMs avec validation Pydantic — multi-provider, retry automatique.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 08 - NLP & Text / Structured Extraction |
| **URL** | https://python.useinstructor.com |
| **GitHub** | https://github.com/jxnl/instructor |
| **Stars** | ~12,700 |
| **License** | MIT |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Instructor est le standard de facto pour l'extraction structurée via LLMs. Il patche les clients API (OpenAI, Anthropic, Ollama, etc.) pour retourner des objets Pydantic validés au lieu de texte brut. En cas d'erreur de validation, Instructor retry automatiquement avec le message d'erreur.

## Key Features
- **Pydantic validation**: Output typé et validé
- **Multi-provider**: OpenAI, Anthropic, Ollama, Cohere, Mistral, etc.
- **Auto-retry**: Retry avec feedback de validation
- **Streaming**: Support streaming de structured data
- **Nested models**: Structures Pydantic complexes
- **Hooks**: Intercepter les étapes de validation

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | Standard de facto, production |
| **Security** | 5 | MIT, client-side |
| **Scalability** | 4 | Via les providers API |
| **Support/Community** | 4 | 12.7k stars |
| **Documentation** | 5 | Docs exemplaires, cookbooks |
| **Integration Ease** | 5 | 3 lignes pour commencer |

## Use Cases
1. **Data extraction** — Extraire des entités structurées depuis du texte
2. **API responses** — Garantir des réponses LLM typées
3. **Document parsing** — Parser des documents en structures Pydantic

## Getting Started
```python
import instructor
from openai import OpenAI
from pydantic import BaseModel

client = instructor.from_openai(OpenAI())

class User(BaseModel):
    name: str
    age: int

user = client.chat.completions.create(
    model="gpt-4o",
    response_model=User,
    messages=[{"role": "user", "content": "John is 30 years old"}]
)
print(user)  # User(name='John', age=30)
```

## Architecture / How It Works
Instructor patche le client API pour injecter le JSON schema Pydantic dans le prompt/function calling. La réponse est parsée en Pydantic model. Si la validation échoue, le message d'erreur est renvoyé au LLM pour correction (retry loop).

## Strengths
- Standard de facto, MIT
- Multi-provider (8+ LLM providers)
- Auto-retry intelligent
- Docs exemplaires

## Limitations
- Dépend des API LLM (coût)
- Pas de contrainte au niveau tokens (vs Outlines)
- Qualité dépend du LLM utilisé

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Outlines | Token-level constraints, modèles locaux |
| Marvin | Approche décorateurs, Prefect ecosystem |
| Guardrails AI | Validation post-generation composable |

## References
- https://python.useinstructor.com
- https://github.com/jxnl/instructor

## Notes
Instructor v1.14.5 (jan 2026). Le choix par défaut pour l'extraction structurée via API LLM. Outlines est complémentaire pour les modèles locaux.
