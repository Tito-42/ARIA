# TokenCost

> Lightweight Python library for precise LLM cost calculation across 400+ models — integrate cost tracking into any application.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 12 - Enterprise Integration |
| **URL** | https://github.com/AgentOps-AI/tokencost |
| **GitHub** | https://github.com/AgentOps-AI/tokencost |
| **Stars** | 2 000 |
| **License** | MIT |
| **Pricing** | Open source free |
| **Last Verified** | 2026-04-02 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
TokenCost is a Python utility library from AgentOps that calculates the exact cost of LLM API calls before or after they are made. It supports 400+ models from OpenAI, Anthropic, Google, Cohere, Mistral, and others, using Tiktoken for OpenAI token counting and the Anthropic API for accurate Claude 3+ token counting.

The library provides three simple functions: `count_string_tokens()`, `calculate_prompt_cost()`, and `calculate_completion_cost()`. These can be called before sending a request (to estimate cost or gate on budget), during logging (to record actual cost), or in analytics pipelines (to aggregate cost by feature, user, or session).

TokenCost is intentionally minimal — it does one thing well and has no runtime dependencies beyond Tiktoken and Anthropic's tokenizer. It is designed to be embedded as a cost calculation utility in larger observability or billing systems rather than as a standalone platform.

## Key Features
- Precise token counting using model-native tokenizers (Tiktoken for OpenAI, Anthropic API for Claude 3+)
- 400+ models supported with up-to-date pricing
- Functions: `count_string_tokens()`, `calculate_prompt_cost()`, `calculate_completion_cost()`
- Pre-request cost estimation (gate expensive calls on budget)
- Post-request cost logging
- MIT license — zero restrictions
- Lightweight — minimal dependencies

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Simple utility; low risk; MIT; actively updated for new model pricing |
| **Security** | 5 | Pure computation — no external calls; MIT |
| **Scalability** | 5 | Stateless function — scales trivially |
| **Support/Community** | 3 | 2k stars; AgentOps-maintained; small but focused |
| **Documentation** | 3 | README-level docs; simple API |
| **Integration Ease** | 5 | 3 functions, pip install — minimal integration |

## Use Cases
1. Pre-request budget gating — check estimated cost before calling expensive models; reject if over threshold
2. Per-request cost logging — log exact cost of each LLM call for cost attribution
3. Cost analytics — aggregate costs by user, session, feature, or model for billing and reporting
4. Model comparison — compare costs across models before selecting for a use case
5. Observability integration — embed in custom logging pipelines when full platforms like Langfuse are too heavy

## Getting Started
```python
pip install tokencost

from tokencost import calculate_prompt_cost, calculate_completion_cost, count_string_tokens

# Token counting
token_count = count_string_tokens("Hello, what is the capital of France?", "gpt-4o")
print(f"Token count: {token_count}")  # e.g., 11

# Pre-request cost estimation
prompt_messages = [{"role": "user", "content": "What is the capital of France?"}]
prompt_cost = calculate_prompt_cost(prompt_messages, "gpt-4o")
print(f"Prompt cost: ${prompt_cost:.6f}")  # e.g., $0.000005

# Post-request cost logging
completion = "The capital of France is Paris."
completion_cost = calculate_completion_cost(completion, "gpt-4o")
print(f"Completion cost: ${completion_cost:.6f}")

total_cost = prompt_cost + completion_cost
print(f"Total cost: ${total_cost:.6f}")
```

## Architecture / How It Works
TokenCost is a pure Python library with no server component. It maintains a pricing database (a JSON file updated in the repository) containing cost-per-token for prompt and completion across 400+ models. Token counting uses Tiktoken for OpenAI models (the same tokenizer OpenAI uses) and the Anthropic Python SDK's tokenizer for Claude models. The three public functions load the pricing database and tokenizer on first call, then perform local computation with no network requests.

## Strengths
- Simplest possible API for cost calculation — three functions
- Accurate token counting using model-native tokenizers
- 400+ models with pricing kept up-to-date
- No runtime overhead — pure local computation
- MIT license; zero commercial restrictions
- Made by AgentOps team who built a full LLM observability platform — domain expertise validated

## Limitations
- Pricing database must be kept updated when providers change prices — check for stale pricing
- No visualization or dashboard — purely a calculation library
- Does not handle streaming cost calculation natively
- No multi-currency support

## Alternatives
| Tool | Key Difference |
|------|---------------|
| LiteLLM built-in cost tracking | Full platform with virtual keys and dashboard; more complex |
| Langfuse cost analytics | Full observability platform; cost is one of many features |
| AgentOps | Full agent observability platform by same team |
| Manual calculation | No dependency; but requires maintaining your own pricing table |

## References
- https://github.com/AgentOps-AI/tokencost
- https://github.com/AgentOps-AI/tokencost/blob/main/tokencost/model_prices.json

## Notes
TokenCost is the right tool when you want to add cost awareness to an application without adopting a full observability platform. It is commonly used as a utility within custom logging pipelines, budget enforcement middleware, or alongside AgentOps for agent cost tracking. Since pricing changes frequently, pin the version and test after upgrading to ensure pricing data is current. Consider using it alongside a fuller platform (Langfuse, Opik) for production observability rather than as a replacement.
