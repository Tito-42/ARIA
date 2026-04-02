# Cloudflare AI Gateway

> Managed AI gateway on Cloudflare's global edge network — observability, caching, rate limiting, and GDPR compliance with zero infrastructure.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 12 - Enterprise Integration |
| **URL** | https://developers.cloudflare.com/ai-gateway/ |
| **GitHub** | N/A (managed cloud service) |
| **Stars** | N/A |
| **License** | Proprietary (Cloudflare service) |
| **Pricing** | Free tier (100k neurons/day) + Workers paid plans |
| **Last Verified** | 2026-04-02 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Cloudflare AI Gateway is a managed proxy service that sits between applications and LLM providers, running on Cloudflare's global edge network (300+ locations). It provides observability, caching, rate limiting, and request logging without any infrastructure to manage — deployments to all regions happen automatically via Cloudflare's network.

The service supports OpenAI, Anthropic, HuggingFace, Replicate, and Cloudflare Workers AI as providers. Like other AI gateways, it normalizes provider APIs and captures request/response metadata for analytics. Caching can be semantic (vector-based) or exact-match, reducing redundant LLM API costs. Rate limiting applies per user, IP, or API key.

Its primary value proposition is zero infrastructure overhead for Cloudflare ecosystem users. Organizations already on Cloudflare Workers, Pages, or using Cloudflare for CDN/DNS can add AI gateway capabilities with a configuration change. For non-Cloudflare users, the lack of self-hosting and vendor lock-in are significant concerns.

## Key Features
- Managed service: no infrastructure to deploy or maintain
- Global edge deployment across 300+ Cloudflare locations
- Semantic caching and exact-match caching
- Request/response logging with configurable retention
- Rate limiting per user, IP, or API key
- Cost analytics per provider and model
- Supports: OpenAI, Anthropic, HuggingFace, Replicate, Workers AI
- GDPR compliance with EU data localization options
- Free tier: 100k neurons/day
- Integration with Cloudflare Workers for custom logic

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Cloudflare infrastructure is enterprise-grade and battle-tested |
| **Security** | 4 | GDPR compliant; data localization; Cloudflare enterprise security |
| **Scalability** | 5 | Cloudflare edge scales globally; no capacity planning required |
| **Support/Community** | 3 | Cloudflare enterprise support; no open source community |
| **Documentation** | 4 | Cloudflare docs quality; comprehensive API reference |
| **Integration Ease** | 5 | Single URL change; seamless for Cloudflare ecosystem users |

## Use Cases
1. Cloudflare Workers applications — add AI gateway with a URL change, no new infrastructure
2. European enterprise GDPR compliance — EU data localization with Cloudflare's edge routing
3. Edge-deployed AI applications — minimize latency via Cloudflare's 300+ global PoPs
4. Organizations without DevOps capacity — no servers to manage, scale automatically

## Getting Started
```javascript
// Change the base URL in your application
// From: https://api.openai.com/v1
// To:   https://gateway.ai.cloudflare.com/v1/{account_id}/{gateway_id}/openai

const response = await fetch(
  `https://gateway.ai.cloudflare.com/v1/${ACCOUNT_ID}/${GATEWAY_ID}/openai/chat/completions`,
  {
    method: 'POST',
    headers: {
      'Authorization': `Bearer ${OPENAI_API_KEY}`,
      'Content-Type': 'application/json',
    },
    body: JSON.stringify({
      model: 'gpt-4o',
      messages: [{ role: 'user', content: 'Hello' }]
    })
  }
)
```

## Architecture / How It Works
Cloudflare AI Gateway runs on Cloudflare's edge network as a Workers service. All requests are processed at the edge location closest to the client, forwarded to the LLM provider, and logged to Cloudflare's analytics pipeline. Caching uses Cloudflare's distributed cache (exact-match) or a vector similarity layer (semantic). Configuration is managed via the Cloudflare dashboard or API. There is no self-hosted option — the service is entirely managed by Cloudflare.

## Strengths
- Zero infrastructure to manage — fully handled by Cloudflare
- Global edge deployment reduces latency for geographically distributed applications
- Seamless integration for Cloudflare ecosystem users
- GDPR-compliant with EU data localization
- Generous free tier (100k neurons/day)

## Limitations
- No self-hosting option — hard dependency on Cloudflare
- Proprietary service — vendor lock-in concern
- Limited provider support vs. open source alternatives (OpenAI, Anthropic, HuggingFace, Replicate)
- Less feature-rich than LiteLLM or Portkey for complex routing/governance scenarios
- No HIPAA certification
- Not suitable for air-gapped or strict data sovereignty environments

## Alternatives
| Tool | Key Difference |
|------|---------------|
| LiteLLM | Open source; self-hostable; 100+ providers; more enterprise features |
| Portkey | SOC2+HIPAA+GDPR; self-hosted; MIT; 250+ providers |
| Kong AI Gateway | Self-hosted; Apache 2.0; enterprise API management heritage |
| Helicone | Open source; observability + gateway; self-hosted option |

## References
- https://developers.cloudflare.com/ai-gateway/
- https://blog.cloudflare.com/announcing-ai-gateway/
- https://developers.cloudflare.com/ai-gateway/tutorials/

## Notes
Cloudflare AI Gateway is appropriate only for organizations already in the Cloudflare ecosystem. The zero-infrastructure advantage is compelling for Cloudflare Workers deployments, but the proprietary nature and lack of self-hosting rule it out for organizations with strict data sovereignty or air-gap requirements. For enterprises requiring HIPAA compliance, Portkey is the only option. For general enterprise use without Cloudflare dependency, LiteLLM or Portkey are stronger choices.
