# OpenLLMetry

> OpenTelemetry-based observability for LLM applications — instrument once, send anywhere.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 12 - Enterprise Integration |
| **URL** | https://www.traceloop.com |
| **GitHub** | https://github.com/traceloop/openllmetry |
| **Stars** | 7 000 |
| **License** | Apache 2.0 |
| **Pricing** | Open source + Traceloop cloud (freemium) |
| **Last Verified** | 2026-04-02 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
OpenLLMetry brings LLM observability into the standard OpenTelemetry ecosystem. Rather than building a proprietary tracing protocol, it extends OTel with semantic conventions for generative AI — capturing prompts, completions, token counts, model names, and latency as standard OTel spans.

The project instruments 16+ LLM providers (OpenAI, Anthropic, Bedrock, Cohere, Gemini, etc.) and 7+ vector databases (Pinecone, Weaviate, Chroma, Qdrant, etc.) through auto-instrumentation decorators. Because it speaks native OpenTelemetry, traces can be routed to any of 24+ supported backends without vendor lock-in: Datadog, Honeycomb, Grafana Tempo, New Relic, Splunk, Jaeger, Zipkin, and more.

This "standards-first" approach is its defining enterprise advantage: organizations with existing observability stacks can add LLM visibility in two lines of code without adopting a new platform.

## Key Features
- OpenTelemetry-native: LLM traces as standard OTel spans
- Auto-instrumentation for 16+ LLM providers with no code changes
- Vector DB instrumentation: Pinecone, Weaviate, Chroma, Qdrant, Milvus, ChromaDB, Redis
- 24+ backend destinations: Datadog, Honeycomb, Grafana, New Relic, Splunk, Jaeger, Zipkin, and Traceloop Cloud
- Two-line setup: `traceloop.init()` + provider import
- Semantic conventions for GenAI (aligned with OTel GenAI SIG working group)
- No vendor lock-in on the observability backend

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Production-ready; less feature-rich than Langfuse but simpler |
| **Security** | 4 | Apache 2.0, no data leaves to proprietary platform; routes to existing enterprise backends |
| **Scalability** | 4 | Inherits OTel scalability; backend-dependent |
| **Support/Community** | 3 | 7k stars, active but smaller community than Langfuse |
| **Documentation** | 4 | Good integration guides per provider and backend |
| **Integration Ease** | 5 | 2 lines of code; works with existing OTel collector infrastructure |

## Use Cases
1. Enterprises with existing Datadog/Grafana/Splunk — add LLM observability to current dashboards without a new tool
2. Multi-provider LLM apps — unified tracing across OpenAI, Anthropic, Bedrock in one trace
3. RAG pipelines — correlated traces spanning vector DB queries and LLM completions
4. Compliance environments — keep trace data within existing enterprise security perimeter

## Getting Started
```bash
pip install traceloop-sdk

# In application startup
from traceloop.sdk import Traceloop
Traceloop.init(app_name="my-llm-app")

# That's it — all LLM calls are now automatically traced
# Configure backend via OTLP_ENDPOINT env var or Traceloop.init(exporter=...)
```

## Architecture / How It Works
OpenLLMetry patches LLM client libraries at import time using standard Python instrumentation hooks (similar to OpenTelemetry's own auto-instrumentation packages). Each LLM call becomes an OTel span with GenAI semantic attributes. The SDK exports via OTLP to any configured backend. For the Traceloop Cloud backend, a proprietary UI adds workflow visualization and regression testing on top of the standard traces.

## Strengths
- Zero new infrastructure if OTel collector already deployed
- Standards-based — future-proof as OTel GenAI conventions mature
- No vendor lock-in: switch backends without changing application code
- Apache 2.0 — fully enterprise-friendly license

## Limitations
- Less feature-rich than purpose-built platforms (no prompt management, no built-in eval)
- Relies on OTel semantic conventions still evolving (GenAI SIG in progress)
- Traceloop Cloud UI less polished than Langfuse or Opik
- Smaller community than top-tier alternatives

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Langfuse | Purpose-built LLM platform with prompt management and evals; more features |
| Opik | Full lifecycle platform with higher proven scale |
| OpenLIT | Also OTel-native but adds GPU monitoring and guardrails |
| Langtrace | Similar OTel approach; AGPL license on app (caution for enterprise) |

## References
- https://www.traceloop.com/docs
- https://github.com/traceloop/openllmetry
- https://opentelemetry.io/docs/specs/semconv/gen-ai/

## Notes
Best fit for enterprises that already have an observability stack (Datadog, Grafana) and want to add LLM visibility with minimal new tooling. If starting from scratch, Langfuse or Opik offer more complete platforms. Watch the OTel GenAI SIG progress — as conventions stabilize, OpenLLMetry's standards-first bet becomes stronger.
