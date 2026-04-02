# Phoenix (Arize AI)

> Open source AI observability platform for experimentation, evaluation, and troubleshooting of LLM applications.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 12 - Enterprise Integration |
| **URL** | https://phoenix.arize.com |
| **GitHub** | https://github.com/arize-ai/phoenix |
| **Stars** | 9 100 |
| **License** | Open source (Elastic License 2.0 for some components) |
| **Pricing** | Open source self-hosted free + Arize Cloud (enterprise paid) |
| **Last Verified** | 2026-04-02 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Phoenix is Arize AI's open source observability platform for LLM and ML applications. It provides OpenTelemetry-based tracing for LLM pipelines, including chains, agents, retrieval steps, and individual completions. Traces are stored locally (or in a cloud backend) and visualized in an interactive UI that shows execution timelines, token counts, latency, and input/output content.

Beyond tracing, Phoenix includes a built-in evaluation framework with LLM-as-judge support, a dataset store for golden datasets and production samples, and a prompt playground for iterative prompt development. Its roots in Arize's ML observability platform mean it also handles traditional ML model monitoring use cases, making it suitable for organizations running both classical ML and GenAI workloads.

Deployment options range from a single `pip install` and local Python launch, to Jupyter notebook embedding, Docker, and Kubernetes. Arize Cloud provides a managed enterprise version with SLAs, SSO, and dedicated support.

## Key Features
- OpenTelemetry-based tracing for LLM apps (chains, agents, RAG)
- LLM-as-judge evaluations with configurable templates
- Dataset management for golden sets and production samples
- Prompt playground with multi-model comparison
- Supports OpenAI, Anthropic, Amazon Bedrock, Google Gemini, LlamaIndex, LangChain
- Local, Docker, and Kubernetes deployment options
- Seamless upgrade path to Arize Platform for enterprise ML + GenAI observability
- Integration with OpenTelemetry collector ecosystem

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Production-ready; Arize enterprise backing provides longevity |
| **Security** | 4 | Self-hosted option; Arize Cloud has enterprise security (SSO, RBAC) |
| **Scalability** | 4 | K8s deployment supported; Arize Cloud for large-scale enterprise |
| **Support/Community** | 4 | 9.1k stars; professional support via Arize enterprise |
| **Documentation** | 4 | Good docs; Arize has strong developer relations |
| **Integration Ease** | 4 | OTel-based; standard integrations with major frameworks |

## Use Cases
1. LLM application tracing — debug complex agent workflows with visual execution trees
2. RAG pipeline evaluation — measure faithfulness, relevancy, and context precision
3. Production monitoring — detect regressions in LLM output quality over time
4. Prompt experimentation — compare prompt variants across multiple models in playground
5. ML + GenAI unified monitoring — single platform for organizations transitioning from ML to GenAI

## Getting Started
```bash
pip install arize-phoenix

# Launch local server
python -m phoenix.server.main serve

# Instrument with OpenAI
pip install openinference-instrumentation-openai
from phoenix.otel import register
tracer_provider = register(project_name="my-llm-app")

from openinference.instrumentation.openai import OpenAIInstrumentor
OpenAIInstrumentor().instrument(tracer_provider=tracer_provider)
```

## Architecture / How It Works
Phoenix uses the OpenInference specification (Arize's open standard for AI observability, built on OTel) to capture traces. The server stores traces in a local SQLite database (or PostgreSQL for production deployments). The frontend is a React application that renders trace trees, evaluation results, and dataset management. The `openinference-instrumentation-*` packages provide auto-instrumentation for each supported LLM provider and framework. For Arize Cloud, traces are forwarded to Arize's managed backend via OTLP.

## Strengths
- Strong enterprise heritage through Arize (established ML observability company)
- Covers both classical ML and GenAI in one platform — valuable for transition organizations
- Clean upgrade path from free self-hosted to paid Arize enterprise
- OpenInference spec is publicly documented — avoids full proprietary lock-in

## Limitations
- License for some components is Elastic License 2.0 (not Apache/MIT) — review before commercial deployment
- Less mature community than Langfuse (9.1k vs 24.2k stars)
- OpenInference spec is Arize-specific (vs standard OTel GenAI SIG conventions)
- Enterprise features require Arize Cloud subscription

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Langfuse | Larger community, more complete lifecycle features, MIT core |
| Opik (Comet ML) | Higher proven scale (40M traces/day), broader framework support |
| W&B Weave | Better if already using W&B for ML experiment tracking |
| OpenLLMetry | Pure OTel standards, routes to existing backends |

## References
- https://docs.arize.com/phoenix
- https://github.com/arize-ai/phoenix
- https://github.com/Arize-ai/openinference

## Notes
Phoenix is the best choice when the organization already uses Arize Platform for classical ML monitoring. The upgrade path from Phoenix (free) to Arize Platform (enterprise) is seamless, and the unified view of ML + GenAI is unique. For greenfield GenAI-only projects, Langfuse or Opik may offer more value. Verify the Elastic License 2.0 terms with legal before deploying in commercial products.
