# Langfuse

> Open source LLM engineering platform for monitoring, evaluating, and debugging AI applications.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 12 - Enterprise Integration |
| **URL** | https://langfuse.com |
| **GitHub** | https://github.com/langfuse/langfuse |
| **Stars** | 24 200 |
| **License** | MIT (except `ee/` folders - enterprise features) |
| **Pricing** | Freemium - Cloud free tier + self-hosted free |
| **Last Verified** | 2026-04-02 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Langfuse is the leading open source LLM observability platform. It provides end-to-end tracing of LLM applications — capturing every prompt, completion, tool call, and agent step as structured traces. Engineers use it to debug failures, identify cost hotspots, and understand latency distributions across their AI pipelines.

Beyond tracing, Langfuse covers the full LLM development lifecycle: prompt management with versioning and A/B testing, dataset curation from production traces, and evaluation using LLM-as-judge metrics. This makes it a single pane of glass from development through production monitoring.

Self-hosting is first-class: Docker Compose, Kubernetes with Helm charts, and Terraform modules for AWS, Azure, and GCP are all provided. The cloud version holds SOC 2 Type II certification.

## Key Features
- Distributed tracing for LLM calls, chains, agents, and tool use
- Prompt management with versioning, rollback, and A/B testing
- LLM-as-judge evaluations and human annotation workflows
- Dataset management for building evaluation and fine-tuning sets
- Cost and token analytics per trace, session, user, or project
- Self-hosted deployment: Docker, Kubernetes, Helm, Terraform (AWS/Azure/GCP)
- Integrations with 20+ frameworks: OpenAI, Anthropic, LangChain, LlamaIndex, LiteLLM, DSPy, and more
- OpenTelemetry-compatible ingestion endpoint
- SOC 2 Type II (cloud), GDPR compliant

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | Battle-tested at scale, used by thousands of production deployments |
| **Security** | 5 | SOC 2 Type II (cloud), self-hosted option for data sovereignty, GDPR |
| **Scalability** | 5 | Handles millions of traces; K8s Helm chart for horizontal scaling |
| **Support/Community** | 5 | 24.2k stars, active Discord, responsive maintainers |
| **Documentation** | 5 | Comprehensive docs, integration guides per framework, video tutorials |
| **Integration Ease** | 5 | 2-3 lines to instrument OpenAI/Anthropic; LangChain callback handler |

## Use Cases
1. Production monitoring of LLM apps — track costs, latency, and error rates per user or feature
2. Prompt engineering — version and A/B test prompts without redeployment
3. Dataset curation — tag and export production traces to build evaluation or fine-tuning datasets
4. Agent debugging — visualize multi-step agent execution trees to identify failure points
5. Evaluation pipelines — run automated LLM-as-judge scoring on sampled production outputs

## Getting Started
```bash
# Self-hosted with Docker Compose
git clone https://github.com/langfuse/langfuse
cd langfuse
docker compose up -d

# Python SDK
pip install langfuse

# Instrument OpenAI (2 lines)
from langfuse.openai import openai
# All subsequent openai.chat.completions.create() calls are automatically traced
```

## Architecture / How It Works
Langfuse uses an event-driven architecture: SDKs send trace events asynchronously to the Langfuse server (self-hosted or cloud). The server stores traces in PostgreSQL (structured metadata) and Clickhouse (analytics queries). A Next.js frontend provides the dashboard. The SDK wraps LLM client libraries via monkey-patching or explicit instrumentation. Traces are organized as a tree: root observation → child spans → LLM generation leaves.

## Strengths
- Most feature-complete open source LLM observability platform as of 2026
- Self-hosted deployment is genuinely easy and production-grade
- Covers the full lifecycle: dev tracing → prompt management → evaluation → production monitoring
- Strong framework integrations mean minimal instrumentation code
- Active development with frequent releases

## Limitations
- Enterprise features (SSO, advanced RBAC, dedicated support) require paid cloud or EE license
- `ee/` folder in repo has stricter licensing terms than core MIT
- Clickhouse adds operational complexity for self-hosted deployments
- No native GPU or infrastructure monitoring (use OpenLIT for that)

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Opik (Comet ML) | Proven at larger scale (40M traces/day), backed by Comet company |
| Phoenix (Arize) | Stronger ML observability heritage, backed by Arize enterprise platform |
| W&B Weave | Better if organization already uses W&B for ML experiment tracking |
| Helicone | Combines observability + gateway in one tool, simpler setup |

## References
- https://langfuse.com/docs
- https://github.com/langfuse/langfuse
- https://langfuse.com/blog/2024-04-introducing-langfuse-2-0

## Notes
Langfuse is the de facto choice for new projects needing open source LLM observability. The MIT license on the core (excluding `ee/` folders) makes it safe for commercial use. For European enterprises, the self-hosted option with GDPR compliance is a strong advantage. Pair with Promptfoo for pre-deployment evaluation and Langfuse for production monitoring.
