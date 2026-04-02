# Outlines

> Génération structurée (JSON, regex, grammaire) à partir de LLMs — outputs garantis conformes au schema.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 08 - NLP & Text / Structured Generation |
| **URL** | https://dottxt-ai.github.io/outlines |
| **GitHub** | https://github.com/dottxt-ai/outlines |
| **Stars** | ~13,600 |
| **License** | Apache 2.0 |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Outlines garantit que les outputs des LLMs respectent un format spécifique (JSON schema, regex, grammaire context-free). Contrairement aux approches basées sur le prompting, Outlines contraint le sampling au niveau des tokens, rendant impossible un output invalide.

## Key Features
- **JSON schema**: Output conforme à un schema JSON/Pydantic
- **Regex constraints**: Output respectant un pattern regex
- **CFG grammaires**: Grammaires context-free pour structures complexes
- **Multi-backend**: Transformers, vLLM, llama.cpp, ExLlamaV2
- **Token-level**: Contrainte au niveau du sampling, pas du post-processing

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Production-ready |
| **Security** | 4 | Apache 2.0, self-hosted |
| **Scalability** | 4 | Compatible vLLM pour production |
| **Support/Community** | 4 | 13.6k stars |
| **Documentation** | 4 | Docs complètes |
| **Integration Ease** | 4 | API simple, multi-backend |

## Use Cases
1. **API structured output** — Garantir que les LLMs retournent du JSON valide
2. **Data extraction** — Extraction structurée depuis du texte
3. **Code generation** — Garantir une syntaxe valide

## Getting Started
```python
import outlines
model = outlines.models.transformers("microsoft/Phi-3-mini-4k-instruct")

schema = '{"type": "object", "properties": {"name": {"type": "string"}, "age": {"type": "integer"}}}'
generator = outlines.generate.json(model, schema)
result = generator("Extract: John is 30 years old")
# {"name": "John", "age": 30}
```

## Architecture / How It Works
Outlines pré-compile les contraintes (JSON schema, regex) en un automate fini. Pendant le sampling, seuls les tokens menant à un état valide de l'automate sont autorisés. Cela garantit structurellement que l'output est conforme.

## Strengths
- Garantie structurelle (pas de post-processing)
- Multi-backend
- Apache 2.0
- Grammaires CFG pour cas complexes

## Limitations
- Performance overhead (contrainte de sampling)
- Compilation initiale de l'automate peut être lente
- Nécessite un modèle local (pas d'API cloud)

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Instructor | API-based, Pydantic, multi-provider, plus simple |
| Guardrails AI | Validation post-generation, composable |
| SGLang | Structured generation intégrée dans le serving |

## References
- https://dottxt-ai.github.io/outlines
- https://github.com/dottxt-ai/outlines

## Notes
Outlines est le gold standard pour la structured generation au niveau tokens. Instructor est complémentaire pour les cas API-based. Outlines pour les modèles locaux, Instructor pour les API cloud.
