# Google Agent Development Kit (ADK)

> Google's open-source framework for creating, evaluating, and deploying AI agents with multi-agent support and A2A protocol.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 02 - AI Agents |
| **URL** | https://google.github.io/adk-python/ |
| **GitHub** | https://github.com/google/adk-python |
| **Stars** | 18,700 |
| **License** | Apache 2.0 |
| **Pricing** | Free (OSS); Vertex AI Agent Engine (paid) for managed deployment |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Google's Agent Development Kit (ADK) is a code-first Python framework for building, evaluating, and deploying AI agents. It supports both code-based agent definition (direct Python) and configuration-based definition (YAML/JSON), making it accessible to developers and non-developers alike.

ADK is optimized for Google's Gemini models but is model-agnostic, supporting other providers. A standout feature is native support for the **Agent2Agent (A2A) protocol**, enabling agents built with ADK to communicate with agents built on other frameworks across organizational boundaries. The framework supports hierarchical multi-agent composition, tool integration (pre-built, custom, OpenAPI, MCP), and flexible deployment to Cloud Run or Vertex AI Agent Engine.

## Key Features
- **Code-first development**: Define agent logic directly in Python
- **Configuration-based agents**: Build agents via YAML/JSON without coding
- **Multi-agent architecture**: Hierarchical composition of specialized agents
- **A2A protocol support**: Inter-agent communication across frameworks
- **Tool integration**: Pre-built tools, custom functions, OpenAPI specs, MCP tools
- **Human-in-the-loop**: Tool confirmation flows for controlled execution
- **Built-in dev UI**: Testing and debugging interface
- **Flexible deployment**: Cloud Run, Vertex AI Agent Engine, or self-hosted
- **Evaluation framework**: Built-in agent evaluation and benchmarking
- **Bi-weekly releases**: Regular update cadence (v1.28.0 as of March 2026)

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Google-backed; Vertex AI for managed production deployment |
| **Security** | 4 | Google Cloud security; human-in-the-loop controls |
| **Scalability** | 5 | Cloud Run and Vertex AI provide Google-scale infrastructure |
| **Support/Community** | 4 | Google-backed; 18.7K stars; growing rapidly |
| **Documentation** | 4 | Good docs; active development; example repository |
| **Integration Ease** | 4 | Simple for Gemini users; more setup for non-Google models |

## Use Cases
1. **Enterprise agent deployment** - Deploy agents on Google Cloud with managed infrastructure
2. **Multi-agent ecosystems** - Connect agents across teams and organizations via A2A
3. **Customer-facing agents** - Build and deploy conversational agents at scale
4. **Internal tools** - Automated workflows with human approval gates

## Getting Started
```bash
pip install google-adk
```

## Architecture / How It Works
```
Agent Definition (Python or Config)
  |-- Model (Gemini default, model-agnostic)
  |-- Tools (pre-built, custom, OpenAPI, MCP)
  |-- Sub-Agents (hierarchical composition)
  |
  Deployment --> Cloud Run | Vertex AI Agent Engine | Self-hosted
  |
  Communication --> A2A Protocol (inter-agent)
```

## Strengths
- Google-backed with enterprise-grade deployment options
- A2A protocol support is a strategic differentiator for multi-agent ecosystems
- Dual code/config approach serves both developers and low-code users
- Built-in evaluation framework for agent quality assurance
- Strong Gemini integration with model-agnostic flexibility
- Rapid release cadence (bi-weekly)

## Limitations
- Relatively new (2025 launch); still building ecosystem
- Best experience with Gemini; other model support is secondary
- Google Cloud dependency for production deployment options
- Smaller community than LangChain or CrewAI
- Less mature orchestration compared to LangGraph

## Alternatives
| Tool | Key Difference |
|------|---------------|
| LangGraph | More mature orchestration; provider-agnostic; larger ecosystem |
| Semantic Kernel | Microsoft-backed; .NET/Python/Java; Azure integration |
| OpenAI Agents SDK | Simpler; OpenAI-native; no deployment platform |
| CrewAI | Role-based multi-agent; more opinionated |

## References
- https://google.github.io/adk-python/
- https://github.com/google/adk-python
- https://cloud.google.com/vertex-ai/docs/agents

## Notes
Google ADK's support for the A2A protocol positions it uniquely for enterprise scenarios where agents from different teams, vendors, or organizations need to communicate. This "agent interoperability" angle is a strategic bet that could become increasingly important as agent ecosystems mature. Teams on Google Cloud should strongly consider ADK for its native integration with Vertex AI.
