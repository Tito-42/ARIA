# PyRIT (Microsoft)

> Python Risk Identification Toolkit — red-teaming automatisé pour systèmes d'IA générative, MIT.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 16 - AI Security & Safety / Red-teaming |
| **URL** | https://github.com/microsoft/PyRIT |
| **GitHub** | https://github.com/microsoft/PyRIT |
| **Stars** | ~3,600 |
| **License** | MIT |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
PyRIT est le framework de red-teaming de Microsoft pour les systèmes d'IA générative. Il fournit des orchestrateurs d'attaques sophistiqués qui utilisent des LLMs pour générer et adapter automatiquement les attaques, avec support multi-modalité (texte, images).

## Key Features
- **Orchestrateurs d'attaques**: LLM-driven, adaptatifs
- **Multi-modalité**: Texte et images
- **Microsoft-backed**: Recherche Microsoft
- **Scorers**: Évaluation automatique des résultats
- **Memory**: Historique des attaques et résultats
- **MIT licence**: Aucune restriction

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Production, Microsoft |
| **Security** | 5 | MIT, conçu pour la sécurité |
| **Scalability** | 3 | Python, API-based |
| **Support/Community** | 3 | 3.6k stars, Microsoft |
| **Documentation** | 4 | Docs Microsoft complètes |
| **Integration Ease** | 3 | API Python, Azure-oriented |

## Use Cases
1. **Red-teaming avancé** — Attaques LLM-driven adaptatives
2. **Multi-modal testing** — Tester texte et images
3. **Enterprise security** — Audit de sécurité des applications IA

## Getting Started
```python
from pyrit.orchestrator import PromptSendingOrchestrator
from pyrit.prompt_target import AzureOpenAITextChatTarget
target = AzureOpenAITextChatTarget()
orchestrator = PromptSendingOrchestrator(prompt_target=target)
await orchestrator.send_prompts_async(prompt_list=["test prompt"])
```

## Strengths
- Orchestrateurs sophistiqués
- Multi-modalité
- Microsoft backing
- MIT licence

## Limitations
- Orienté Azure/OpenAI
- Setup plus complexe
- Documentation parfois Azure-centric

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Promptfoo | Plus simple, UI, plus populaire |
| Garak | NVIDIA, plus de probes |

## References
- https://github.com/microsoft/PyRIT
