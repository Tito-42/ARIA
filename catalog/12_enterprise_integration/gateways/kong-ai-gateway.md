# Kong AI Gateway

> Battle-tested enterprise API gateway (43k stars) with a complete AI layer — semantic caching, routing, observability, security, and MCP governance.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 12 - Enterprise Integration |
| **URL** | https://konghq.com/products/kong-ai-gateway |
| **GitHub** | https://github.com/Kong/kong |
| **Stars** | 43 100 |
| **License** | Apache 2.0 |
| **Pricing** | Open source + Kong Konnect (Enterprise SaaS) |
| **Last Verified** | 2026-04-02 |
| **Status** | Active |
| **Maturity** | Enterprise |

## What It Does
Kong AI Gateway is the generative AI layer built on top of Kong, the most widely deployed open source API gateway in enterprise. Rather than being a new tool, it extends Kong's battle-tested API management infrastructure with 60+ AI-specific capabilities — semantic caching, semantic routing, AI observability, prompt engineering, and security guardrails.

For enterprises already running Kong as their API gateway, adding AI capabilities is a configuration change rather than a new deployment. For new deployments, Kong brings a 15-year heritage of enterprise API management, 393+ contributors, and a broad plugin ecosystem. The AI gateway supports all major providers: OpenAI, Anthropic, Amazon Bedrock, Azure AI, Databricks, Mistral, and HuggingFace. Kong has also added MCP (Model Context Protocol) traffic governance capabilities for managing agentic AI workloads.

## Key Features
- 60+ AI features built as Kong plugins
- Semantic caching to reduce duplicate LLM API costs
- Semantic routing: route to different models based on query intent
- AI observability: token usage, cost, latency per request
- AI security: prompt injection detection, PII masking, content filtering
- Prompt templating and transformation
- Supports OpenAI, Anthropic, Bedrock, Azure AI, Databricks, Mistral, HuggingFace
- MCP traffic governance for agentic AI workloads
- Kubernetes native (Ingress Controller, Gateway API)
- Plugin ecosystem: 100+ plugins for rate limiting, auth, logging, transforms
- Apache 2.0 core; Kong Konnect for managed enterprise

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | Kong is deployed in hundreds of enterprises globally; 15+ year track record |
| **Security** | 5 | Enterprise security hardened; Kong Inc. professional support; plugin ecosystem for auth/mTLS/RBAC |
| **Scalability** | 5 | Battle-tested at massive scale; 43.1k stars; K8s native |
| **Support/Community** | 5 | Kong Inc. commercial support, 393+ contributors, massive ecosystem |
| **Documentation** | 5 | Extensive docs, tutorials, Kong Academy, enterprise support portal |
| **Integration Ease** | 4 | Straightforward for existing Kong users; some learning curve for new deployments |

## Use Cases
1. Enterprises with existing Kong API gateway — add AI capabilities as Kong plugins, zero new infrastructure
2. Centralized LLM governance — apply rate limits, authentication, and logging to all LLM traffic across teams
3. Semantic caching — cache LLM responses at the gateway level, reducing costs for repeated similar queries
4. Multi-model semantic routing — route healthcare queries to specialized models, general queries to cheaper models
5. MCP/agent traffic management — govern agentic AI workloads with the same controls as REST API traffic

## Getting Started
```yaml
# Kong declarative config (deck/kong.yaml)
# Add AI proxy plugin
plugins:
- name: ai-proxy
  config:
    route_type: llm/v1/chat
    auth:
      header_name: Authorization
      header_value: "Bearer ${OPENAI_API_KEY}"
    model:
      provider: openai
      name: gpt-4o
      options:
        max_tokens: 4096
```

```bash
# Start Kong with Docker
docker run -d --name kong \
  -e "KONG_DATABASE=off" \
  -e "KONG_DECLARATIVE_CONFIG=/kong/declarative/kong.yaml" \
  -p 8000:8000 -p 8001:8001 \
  kong/kong-gateway
```

## Architecture / How It Works
Kong Gateway is built on OpenResty (NGINX + Lua) and processes all API traffic through a plugin pipeline. Each Kong plugin is a Lua (or Go/Python via PDK) module that can inspect and modify requests and responses at defined phases (access, header_filter, body_filter, log). The AI plugins intercept LLM-bound requests, apply transformations (prompt templating, PII masking, injection detection), forward to the configured provider, and capture response metrics. Semantic caching uses vector embeddings stored in Redis to identify semantically equivalent cached responses. Kong can run as a standalone binary, Docker container, Kubernetes Ingress Controller, or with the managed Kong Konnect cloud.

## Strengths
- Proven at enterprise scale — hundreds of global deployments, 15+ year track record
- Natural extension for existing Kong deployments — AI features as additional plugins
- Most complete plugin ecosystem for API governance (auth, rate limiting, transforms, logging)
- Apache 2.0 with robust open source core
- MCP governance is a unique forward-looking feature for agentic architectures
- 393+ contributors ensures longevity

## Limitations
- Learning curve for teams not already familiar with Kong architecture
- AI features are newer additions — may be less battle-tested than core gateway capabilities
- Some advanced AI features require Kong Konnect (paid)
- Heavier footprint than purpose-built AI gateways like Portkey (122kb)
- Less focused on LLM-specific observability compared to dedicated tools like Langfuse

## Alternatives
| Tool | Key Difference |
|------|---------------|
| LiteLLM | Purpose-built LLM gateway; simpler; 41.9k stars; better SDK integration |
| Portkey | SOC2+HIPAA+GDPR+CCPA certs; 122kb footprint; ML-focused |
| Cloudflare AI Gateway | No self-host; requires Cloudflare ecosystem; edge-first |
| AWS API Gateway + Lambda | Managed cloud; AWS-only; no semantic features |

## References
- https://docs.konghq.com/gateway/latest/
- https://docs.konghq.com/hub/?search=ai
- https://github.com/Kong/kong
- https://konghq.com/products/kong-ai-gateway

## Notes
Kong AI Gateway is the strongest choice for enterprises that already use Kong for API management — the AI layer is a configuration addition with no new infrastructure. For greenfield AI gateway deployments without existing Kong usage, purpose-built alternatives like LiteLLM or Portkey offer simpler setups with comparable capabilities. The MCP traffic governance feature is unique and positions Kong well for the emerging agentic AI workload management use case.
