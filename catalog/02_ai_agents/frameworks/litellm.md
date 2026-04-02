# LiteLLM

> Unified Python SDK and AI Gateway for calling 100+ LLM APIs in OpenAI format with routing, fallbacks, and cost tracking.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 02 - AI Agents / 18 - AI Infrastructure |
| **URL** | https://litellm.ai |
| **GitHub** | https://github.com/BerriAI/litellm |
| **Stars** | 41,800 |
| **License** | MIT |
| **Pricing** | Free (OSS) / Enterprise (paid) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
LiteLLM provides a unified interface to 100+ LLM APIs in OpenAI-compatible format. It operates as both a Python SDK for direct integration and an AI Gateway (proxy server) for centralized LLM access management. With 8ms P95 latency at 1,000 RPS, it is production-grade infrastructure for any team using multiple LLM providers.

LiteLLM supports virtual keys for access control, multi-tenant cost tracking, retry/fallback logic across deployments, and integrations with observability platforms. It has become essential infrastructure in the agent ecosystem, used by frameworks like Smolagents for multi-provider support.

## Key Features
- **100+ LLM providers**: OpenAI, Anthropic, Bedrock, Azure, VertexAI, Cohere, and more
- **OpenAI-compatible format**: Drop-in replacement for OpenAI SDK calls
- **AI Gateway (Proxy)**: Centralized LLM access with virtual keys and rate limiting
- **Routing**: Retry/fallback logic across deployments with load balancing
- **Cost tracking**: Per-project and per-user cost monitoring
- **MCP Gateway**: Model Context Protocol support
- **A2A Agent Protocol**: Agent-to-Agent protocol support
- **8ms P95 latency**: Production-grade performance at 1,000 RPS

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | Battle-tested; 8ms P95; enterprise features |
| **Security** | 4 | Virtual keys; access control; audit logging |
| **Scalability** | 5 | Proxy architecture; load balancing; 1K+ RPS |
| **Support/Community** | 5 | 41.8K stars; active development |
| **Documentation** | 4 | Good docs; comprehensive provider list |
| **Integration Ease** | 5 | Drop-in replacement for OpenAI SDK |

## Use Cases
1. **LLM API gateway** - Centralized access management for all LLM providers
2. **Multi-provider agents** - Agents that can use any LLM provider transparently
3. **Cost optimization** - Route to cheapest provider; track costs per project
4. **Reliability** - Automatic fallback when a provider is down

## Getting Started
```bash
pip install litellm
```
```python
from litellm import completion
response = completion(model="anthropic/claude-sonnet-4-20250514", messages=[{"role": "user", "content": "Hello"}])
```

## Strengths
- Universal LLM interface; switch providers in one line
- Production-grade proxy with enterprise features
- Essential infrastructure for multi-model agent systems
- Drop-in OpenAI compatibility reduces migration effort

## Limitations
- Adds a layer between application and LLM provider
- Some provider-specific features may not be fully supported
- Proxy deployment adds operational complexity
- Enterprise features require paid license

## References
- https://litellm.ai
- https://github.com/BerriAI/litellm
- https://docs.litellm.ai

## Notes
LiteLLM has become essential infrastructure in the AI agent ecosystem, sitting at Layer 1 of the agent stack. For any production deployment using multiple LLM providers -- which is increasingly common for cost optimization, fallback, and capability routing -- LiteLLM is the standard solution. It pairs naturally with any agent framework.
