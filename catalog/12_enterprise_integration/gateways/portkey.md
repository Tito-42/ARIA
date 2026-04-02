# Portkey Gateway

> Enterprise-grade AI gateway for 250+ LLMs — ultra-lightweight (122kb), SOC2+HIPAA+GDPR+CCPA certified, proven at 10B tokens/day.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 12 - Enterprise Integration |
| **URL** | https://portkey.ai |
| **GitHub** | https://github.com/Portkey-AI/gateway |
| **Stars** | 11 200 |
| **License** | MIT |
| **Pricing** | Open source + Portkey Cloud (freemium) |
| **Last Verified** | 2026-04-02 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Portkey Gateway is an enterprise-ready AI gateway that routes requests to 250+ LLMs with a minimal operational footprint (122kb binary). It acts as a unified proxy layer between applications and LLM providers, adding reliability, governance, and cost management without changing application code.

The gateway's enterprise differentiation lies in its compliance certifications: SOC2 Type II, HIPAA, GDPR, and CCPA — a combination rare in open source AI tooling. This makes it one of the few AI gateways appropriate for healthcare, financial services, and European enterprise deployments without additional compliance work.

Operationally, Portkey provides 40+ built-in guardrails, automatic retries with fallback providers, load balancing across multiple API keys, and RBAC for team-level access control. It has been validated at 10 billion tokens per day in production. Deployment options include Cloudflare Workers, Kubernetes, AWS, Azure, and GCP.

## Key Features
- Routes to 250+ LLMs across providers
- Ultra-lightweight: 122kb binary, minimal overhead
- 40+ built-in guardrails (PII detection, content moderation, custom rules)
- Automatic retry with fallback provider routing
- Load balancing across API keys and regions
- RBAC for team and project-level access control
- Compliance certifications: SOC2, HIPAA, GDPR, CCPA
- Semantic caching to reduce redundant API calls
- Request/response logging with configurable retention
- Deployable on Cloudflare Workers, K8s, AWS, Azure, GCP
- MIT license on core gateway

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | 10B tokens/day validated; enterprise-grade reliability features |
| **Security** | 5 | SOC2 + HIPAA + GDPR + CCPA — broadest enterprise certification set in open source |
| **Scalability** | 5 | 10B tokens/day proven; horizontal scaling on K8s and Cloudflare Workers |
| **Support/Community** | 4 | 11.2k stars; professional support via Portkey Cloud enterprise |
| **Documentation** | 4 | Comprehensive provider guides, API reference, deployment docs |
| **Integration Ease** | 5 | Change baseURL + add api-key header — OpenAI SDK compatible |

## Use Cases
1. Healthcare applications — HIPAA compliance requirement eliminates most other gateways
2. European enterprise — GDPR certification + data residency controls
3. Multi-provider reliability — automatic failover when primary provider is degraded
4. Multi-team cost governance — RBAC + per-team API keys with spend limits
5. High-volume production — load balance across multiple API keys to stay within rate limits

## Getting Started
```python
# Python - minimal change from OpenAI SDK
from openai import OpenAI
from portkey_ai import PORTKEY_GATEWAY_URL, createHeaders

client = OpenAI(
    api_key="your-openai-api-key",
    base_url=PORTKEY_GATEWAY_URL,
    default_headers=createHeaders(
        api_key="your-portkey-api-key",
        provider="openai"
    )
)

# Switch to Anthropic: change provider="anthropic" and api_key
```

```bash
# Self-hosted Docker
docker run -d --name portkey-gateway \
  -p 8787:8787 \
  portkeyai/gateway:latest
```

## Architecture / How It Works
Portkey Gateway is a lightweight proxy written for edge deployment. The core gateway handles request routing, provider normalization (translating OpenAI-format requests to provider-specific formats), and response normalization back to OpenAI format. Guardrails run as middleware in the request pipeline. Load balancing and fallback logic are configured via a JSON config or the Portkey Cloud dashboard. Semantic caching uses vector similarity to identify near-duplicate requests. For the cloud version, Portkey manages the infrastructure; for self-hosted, the 122kb binary runs in any container environment.

## Strengths
- Best enterprise compliance certifications in open source AI gateways (SOC2 + HIPAA + GDPR + CCPA)
- Proven at massive scale (10B tokens/day)
- Minimal footprint (122kb) — negligible infrastructure overhead
- OpenAI SDK compatible — near-zero migration effort
- MIT license on core gateway

## Limitations
- Advanced analytics and features require Portkey Cloud
- Smaller community than LiteLLM (11.2k vs 41.9k stars)
- Some enterprise features (SSO, custom guardrails, advanced RBAC) are cloud-only
- Observability dashboard less feature-rich than purpose-built tools like Langfuse

## Alternatives
| Tool | Key Difference |
|------|---------------|
| LiteLLM | 41.9k stars; more popular; MIT; less compliance certifications |
| Kong AI Gateway | Enterprise API gateway heritage; better for existing Kong deployments |
| Helicone | Combines observability + gateway; simpler; fewer compliance certs |
| Cloudflare AI Gateway | No self-host; requires Cloudflare ecosystem |

## References
- https://portkey.ai/docs
- https://github.com/Portkey-AI/gateway
- https://portkey.ai/blog

## Notes
Portkey is the top choice when HIPAA compliance is required — it is one of the only open source AI gateways with HIPAA certification. The combination of SOC2 + HIPAA + GDPR + CCPA is unmatched in the open source space as of April 2026. For non-regulated industries, LiteLLM's larger community and feature set may be preferable. The 122kb footprint is a genuine differentiator for edge deployments or resource-constrained environments.
