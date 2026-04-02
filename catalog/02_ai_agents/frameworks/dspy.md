# DSPy

> Framework for programming -- not prompting -- language models, with automatic prompt and weight optimization.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 02 - AI Agents |
| **URL** | https://dspy.ai |
| **GitHub** | https://github.com/stanfordnlp/dspy |
| **Stars** | 33,300 |
| **License** | MIT |
| **Pricing** | Free (OSS) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
DSPy is a framework from Stanford NLP that replaces manual prompt engineering with programmatic optimization. Instead of writing fragile prompts, developers define modular AI systems as Python code with declarative signatures, and DSPy's optimizers automatically find the best prompts and weights for the task.

DSPy supports building classifiers, RAG pipelines, and agent loops through composable modules. Its self-improving capabilities enable systems to get better over time through programmatic optimization rather than manual prompt tuning. This makes it particularly valuable for applications where prompt quality directly impacts business outcomes.

## Key Features
- **Programmatic optimization**: Automatic prompt and weight tuning
- **Declarative signatures**: Define inputs/outputs, not implementation details
- **Composable modules**: Build complex systems from simple building blocks
- **Self-improving**: Systems optimize themselves through training
- **Agent loops**: Support for ReAct-style agent patterns
- **Model-agnostic**: Works with any LLM provider

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | v3.1.3; used by 1,600+ projects |
| **Security** | 3 | Research-oriented; less enterprise tooling |
| **Scalability** | 4 | Optimization reduces token usage at scale |
| **Support/Community** | 4 | Stanford NLP backing; 33.3K stars; active Discord |
| **Documentation** | 4 | Good docs at dspy.ai; research papers |
| **Integration Ease** | 4 | `pip install dspy`; requires understanding of optimization paradigm |

## Use Cases
1. **Prompt optimization** - Automatically finding optimal prompts for any task
2. **RAG systems** - Self-optimizing retrieval-augmented generation
3. **Classification** - Building optimized classifiers with LLMs
4. **Agent systems** - Agent loops with optimized reasoning steps

## Getting Started
```bash
pip install dspy
```

## Strengths
- Unique paradigm: programming > prompting
- Automatic optimization reduces manual prompt engineering
- Strong academic foundation (Stanford NLP)
- Significant token cost savings through optimization
- Research papers provide theoretical grounding

## Limitations
- Steep learning curve for the optimization paradigm
- Requires training data or evaluation metrics for optimization
- Less intuitive than imperative agent frameworks
- Smaller community than LangChain or CrewAI
- Agent capabilities are secondary to optimization focus

## Alternatives
| Tool | Key Difference |
|------|---------------|
| LangChain | Imperative approach; more integrations; larger ecosystem |
| PydanticAI | Type-safe; simpler; no optimization |
| Haystack | Pipeline-based; more NLP/RAG focused |

## References
- https://dspy.ai
- https://github.com/stanfordnlp/dspy
- https://arxiv.org/abs/2310.03714 (DSPy paper)

## Notes
DSPy represents a fundamentally different philosophy: instead of hand-crafting prompts, let the system optimize them. This is powerful for production systems where small prompt improvements translate to significant quality gains. Consider DSPy when you have evaluation metrics and want to systematically improve your LLM pipeline's performance.
