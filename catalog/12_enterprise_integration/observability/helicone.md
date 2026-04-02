# Helicone

> LLM observability and AI gateway combined — monitor costs, latency, and quality with a one-line integration.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 12 - Enterprise Integration |
| **URL** | https://helicone.ai |
| **GitHub** | https://github.com/Helicone/helicone |
| **Stars** | 5 400 |
| **License** | Apache 2.0 |
| **Pricing** | Freemium - 10k requests/month free; paid plans beyond |
| **Last Verified** | 2026-04-02 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Helicone is a dual-purpose platform that combines LLM observability with an AI gateway. On the observability side, it captures every LLM request and response to provide dashboards for cost tracking, latency analysis, error rates, and output quality metrics. On the gateway side, it proxies calls to 100+ models from 15+ providers, adding caching, rate limiting, and routing without changing application business logic.

The key enterprise appeal is the combination: rather than deploying a separate observability tool and a separate gateway, Helicone handles both through a single proxy endpoint. Setup requires changing one URL in the OpenAI client — Helicone intercepts the call, logs it, and forwards it to the actual provider.

Helicone is SOC 2 and GDPR compliant, with self-hosting available via Docker and Kubernetes for organizations requiring data sovereignty.

## Key Features
- One-line integration: change `baseURL` to Helicone's proxy endpoint
- Cost tracking with per-user, per-session, and per-feature breakdowns
- Latency and error rate monitoring with alerting
- Prompt management with versioning and deployment
- AI gateway for 100+ models across 15+ providers
- Semantic caching to reduce duplicate LLM call costs
- Rate limiting per user or API key
- SOC 2 Type II and GDPR compliance
- Self-hosting with Docker Compose and Kubernetes

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Production deployments confirmed; SOC 2 validates maturity |
| **Security** | 5 | SOC 2, GDPR, Apache 2.0, self-hosted option |
| **Scalability** | 4 | Proxy architecture scales horizontally; K8s deployment available |
| **Support/Community** | 3 | 5.4k stars; active but smaller community than leaders |
| **Documentation** | 4 | Clear integration guides, good dashboard documentation |
| **Integration Ease** | 5 | Single baseURL change — lowest friction of all LLM observability tools |

## Use Cases
1. Quick LLM cost visibility — instrument any OpenAI-compatible app in under 5 minutes
2. Multi-provider cost comparison — compare actual costs across GPT-4o, Claude, and Gemini for the same workload
3. User-level cost attribution — tag requests by user ID for SaaS cost allocation
4. Semantic caching — cache LLM responses for repeated or similar queries to cut API costs
5. European enterprise compliance — GDPR + self-hosted deployment for data residency requirements

## Getting Started
```python
# Python - change one line
from openai import OpenAI

client = OpenAI(
    api_key="your-openai-key",
    base_url="https://oai.helicone.ai/v1",
    default_headers={
        "Helicone-Auth": "Bearer your-helicone-key",
    }
)
# All subsequent calls are automatically monitored
```

```bash
# Self-hosted with Docker Compose
git clone https://github.com/Helicone/helicone
cd docker
docker compose up -d
```

## Architecture / How It Works
Helicone operates as a transparent HTTP proxy. Client requests are sent to Helicone's endpoint with the original provider credentials passed as headers. Helicone logs the request and response asynchronously (to minimize latency overhead), then forwards to the actual LLM provider. The logging pipeline writes to ClickHouse for analytics and PostgreSQL for metadata. The frontend dashboard is a Next.js application. For self-hosted deployments, all components run as Docker containers.

## Strengths
- Lowest integration friction of any LLM observability tool (one URL change)
- Combines observability + gateway = one less tool to deploy and maintain
- SOC 2 + GDPR = enterprise compliance out-of-the-box
- Apache 2.0 license with genuine self-hosted option
- Semantic caching provides measurable cost reduction

## Limitations
- Proxy architecture adds a network hop (marginal latency overhead)
- Less feature-rich eval/dataset management compared to Langfuse or Opik
- Smaller community than top-tier competitors
- Cloud tier pricing can escalate at high request volumes
- Does not cover agent-specific observability (use AgentOps for that)

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Langfuse | More complete lifecycle features (prompt mgmt, evals, datasets); larger community |
| LiteLLM | More powerful gateway with virtual keys and load balancing; no built-in observability UI |
| Portkey | More enterprise certifications (HIPAA); stronger gateway features |
| Opik | Better scale (40M traces/day); no gateway included |

## References
- https://docs.helicone.ai
- https://github.com/Helicone/helicone
- https://helicone.ai/blog

## Notes
Helicone is the fastest way to get LLM cost visibility into an existing application — the one-URL-change integration has no equal. For teams that need both a gateway and basic observability, it eliminates a tool from the stack. For deeper evaluation, prompt management, or agent debugging, complement with Langfuse. The SOC 2 + GDPR combination makes it one of the more compliance-ready open source options.
