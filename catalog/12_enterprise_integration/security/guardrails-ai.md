# Guardrails AI

> Python framework for LLM input/output validation — enforce rules against toxicity, sensitive data, competitor mentions, and custom patterns via a validators marketplace.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 12 - Enterprise Integration |
| **URL** | https://guardrailsai.com |
| **GitHub** | https://github.com/guardrails-ai/guardrails |
| **Stars** | 6 600 |
| **License** | Apache 2.0 |
| **Pricing** | Open source + Guardrails Hub (validator marketplace) |
| **Last Verified** | 2026-04-02 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Guardrails AI is a Python framework that validates and enforces constraints on LLM inputs and outputs. It takes a "validators as code" approach: developers define which validators to apply (toxicity detection, PII detection, regex matching, competitor blocking, JSON schema validation, etc.), and the framework applies them to every LLM request and response in the pipeline.

The Guardrails Hub is a marketplace of pre-built validators contributed by the community and partners. As of 2026, the Hub includes 24+ guardrails across 6 categories (security, privacy, quality, legality, brand safety, format). This marketplace model means organizations can adopt proven validators rather than building detection models from scratch.

For deployment, Guardrails AI runs as both an embedded Python library and a standalone Flask REST server. The server mode enables integration with any application language, not just Python. The framework also provides the Guardrails Index — a benchmark measuring the effectiveness of each guardrail across 6 categories, enabling data-driven selection.

## Key Features
- Validators as code — define constraints programmatically or via RAIL markup
- Guardrails Hub: 24+ pre-built validators (toxicity, PII, secrets, competitors, regex, JSON schema)
- Automatic retry with reask: if output fails validation, reprompt LLM with correction instructions
- Flask REST server for language-agnostic deployment
- Streaming support with incremental validation
- Guardrails Index benchmark for measuring validator effectiveness
- Apache 2.0 license
- Compatible with any LLM provider

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | 6.6k stars; REST server for production deployment; used in enterprise apps |
| **Security** | 4 | Apache 2.0; self-hosted; no data to third parties (validators run locally) |
| **Scalability** | 3 | REST server mode scales horizontally; CPU-bound validators may bottleneck |
| **Support/Community** | 3 | 6.6k stars; community Hub; company support available |
| **Documentation** | 4 | Good docs; Hub has per-validator documentation |
| **Integration Ease** | 4 | Python SDK: 5-10 lines; REST server for other languages |

## Use Cases
1. Brand safety enforcement — block outputs mentioning competitor products or brands
2. Output format validation — ensure LLM returns valid JSON matching a schema (with auto-retry)
3. Regulatory compliance — detect and block PII, financial advice, or legally sensitive content
4. Content moderation — filter toxic, harmful, or inappropriate content in customer-facing apps
5. Secrets detection — prevent LLM from inadvertently echoing API keys or passwords from context

## Getting Started
```python
pip install guardrails-ai

# Install a validator from the Hub
guardrails hub install hub://guardrails/toxic_language

import guardrails as gd
from guardrails.hub import ToxicLanguage

# Create a guard
guard = gd.Guard().use(
    ToxicLanguage(threshold=0.5, on_fail="exception")
)

# Wrap LLM call
try:
    response = guard(
        openai.chat.completions.create,
        model="gpt-4o",
        messages=[{"role": "user", "content": user_input}]
    )
except Exception as e:
    print(f"Guard triggered: {e}")
```

```bash
# Run as standalone REST server
pip install "guardrails-ai[server]"
guardrails start --config config.py
# POST to http://localhost:8000/guards/{guard_id}/openai/v1/chat/completions
```

## Architecture / How It Works
Guardrails AI wraps the LLM call in a Guard object. Each Guard has a list of Input Validators (applied to the prompt before the LLM call) and Output Validators (applied to the completion). Validators are Python functions that return a `PassResult` or `FailResult`. On failure, the framework can raise an exception, return a default value, or issue a "reask" — appending correction instructions to the conversation and calling the LLM again. The RAIL markup language allows validators to be specified in YAML with error messages for reask prompts. The Flask server exposes an OpenAI-compatible API endpoint, so any client that can call OpenAI can route through Guardrails for validation.

## Strengths
- Hub marketplace reduces time to implement common validators
- Reask mechanism enables automatic error correction without manual intervention
- REST server enables non-Python applications to benefit from validation
- Guardrails Index provides empirical data for choosing validators
- Apache 2.0 — enterprise-friendly

## Limitations
- Reask adds latency and cost (additional LLM calls for correction)
- Hub validator quality varies — review each validator before trusting it
- More LLM-focused than Presidio for pure PII use cases
- Streaming validation adds complexity
- Some validators require third-party API calls (e.g., OpenAI moderation endpoint)

## Alternatives
| Tool | Key Difference |
|------|---------------|
| NeMo Guardrails (NVIDIA) | Dialog-level flow control (not just I/O validation); Colang language |
| LLM Guard | Security-focused; prompt injection; no marketplace model |
| Microsoft Presidio | Specialized for PII detection only; multi-modal (images, structured) |
| Langfuse + custom evals | Async monitoring rather than synchronous blocking |

## References
- https://docs.guardrailsai.com
- https://github.com/guardrails-ai/guardrails
- https://hub.guardrailsai.com

## Notes
Guardrails AI excels at synchronous output validation where the application needs to enforce structural or content constraints before returning a response to the user. The reask mechanism is particularly valuable for JSON output validation — if the LLM returns malformed JSON, Guardrails reprompts automatically. For PII specifically, Presidio is more specialized and accurate. For dialog flow control (ensuring the LLM stays on topic), NeMo Guardrails is more appropriate. Guardrails AI works best as one layer in a defense-in-depth security stack rather than as the sole protection mechanism.
