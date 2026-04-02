# DeepEval (Confident AI)

> Framework d'évaluation de LLMs — 14+ métriques (hallucination, faithfulness, toxicity, bias), pytest intégré.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 16 - AI Security & Safety / LLM Evaluation |
| **URL** | https://docs.confident-ai.com |
| **GitHub** | https://github.com/confident-ai/deepeval |
| **Stars** | ~14,400 |
| **License** | MIT |
| **Pricing** | Free (OSS) / Confident AI (Paid SaaS) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
DeepEval est le framework d'évaluation LLM le plus complet avec 14+ métriques : hallucination, faithfulness, answer relevancy, toxicity, bias, contextual recall/precision, et plus. Il s'intègre nativement avec pytest pour les tests automatisés dans CI/CD.

## Key Features
- **14+ métriques**: Hallucination, faithfulness, toxicity, bias, etc.
- **pytest integration**: Tests automatisés natifs
- **CI/CD friendly**: GitHub Actions, Jenkins, etc.
- **Benchmarks**: MMLU, HellaSwag, etc.
- **Confident AI**: Dashboard cloud pour le suivi
- **MIT licence**: Aucune restriction

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | Production, standard évaluation |
| **Security** | 5 | MIT, self-hosted possible |
| **Scalability** | 4 | CI/CD, batch evaluation |
| **Support/Community** | 5 | 14.4k stars, très actif |
| **Documentation** | 5 | Docs excellentes |
| **Integration Ease** | 5 | pytest native, 5 lignes |

## Use Cases
1. **LLM evaluation** — Évaluer la qualité des réponses LLM
2. **CI/CD testing** — Tests automatisés de qualité LLM
3. **Hallucination detection** — Détecter les hallucinations

## Getting Started
```python
from deepeval import assert_test
from deepeval.metrics import HallucinationMetric
from deepeval.test_case import LLMTestCase

test_case = LLMTestCase(
    input="What is the capital of France?",
    actual_output="Paris is the capital of France.",
    context=["Paris is the capital of France."]
)
metric = HallucinationMetric(threshold=0.5)
assert_test(test_case, [metric])
```

## Strengths
- Métriques les plus complètes
- pytest natif = CI/CD trivial
- MIT licence
- 14.4k stars, très actif

## Limitations
- Certaines features enterprise payantes
- Métriques LLM-judge dépendent d'API LLM

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Promptfoo | Focus testing prompts, red-teaming |
| Giskard | Focus vulnérabilités, scanning |
| RAGAS | Spécialisé RAG evaluation |

## References
- https://docs.confident-ai.com
- https://github.com/confident-ai/deepeval
