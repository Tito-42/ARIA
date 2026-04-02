# Agno (formerly Phidata)

> Runtime platform for building and deploying agentic software systems at scale with FastAPI runtime and AgentOS control plane.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 02 - AI Agents |
| **URL** | https://agno.com |
| **GitHub** | https://github.com/agno-agi/agno |
| **Stars** | 39,100 |
| **License** | Apache 2.0 |
| **Pricing** | Free (OSS) / AgentOS (paid) for monitoring and management |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Agno (formerly Phidata) is a runtime platform for building and deploying agentic software systems at scale. It provides a framework layer for building agents with memory, knowledge bases, guardrails, and 100+ integrations, plus a stateless FastAPI runtime for production deployment and an AgentOS control plane UI for monitoring and management.

The platform distinguishes itself with its focus on production deployment: agents are built as stateful units but deployed as stateless, horizontally scalable FastAPI services. This architecture enables per-user and per-session isolation, native tracing, approval workflows, and human-in-the-loop governance at scale.

## Key Features
- **Production runtime**: Stateless, horizontally scalable FastAPI deployment
- **AgentOS**: Control plane UI for testing, monitoring, and managing agents
- **100+ integrations**: Tools, models, and data sources
- **Memory and knowledge**: Built-in persistence and knowledge base support
- **Guardrails**: Safety checks and validation for agent outputs
- **MCP support**: Model Context Protocol tool integration
- **Per-user isolation**: Session and user-level state management
- **Approval workflows**: Human-in-the-loop governance
- **Native tracing**: Built-in observability and audit logs
- **50+ APIs**: Background execution and management APIs

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | Built for production; FastAPI runtime; 178 releases |
| **Security** | 4 | Per-user isolation; approval workflows; audit logs |
| **Scalability** | 5 | Horizontally scalable; stateless runtime |
| **Support/Community** | 4 | 39.1K stars; active development; 5,348 commits |
| **Documentation** | 4 | Good docs; quick-start examples |
| **Integration Ease** | 5 | ~20 lines to build a production agent |

## Use Cases
1. **Production agent deployment** - Scale agents as microservices
2. **Enterprise agent platforms** - Multi-tenant agent systems with governance
3. **Conversational AI** - Stateful chatbots with memory and knowledge
4. **Workflow automation** - Agents with tool access and approval gates

## Getting Started
```bash
pip install agno
```

## Strengths
- Production-first architecture with FastAPI runtime
- Horizontally scalable stateless deployment
- Comprehensive governance (approval workflows, audit logs)
- Simple API (~20 lines for a production agent)
- Active development with frequent releases (178 total)

## Limitations
- AgentOS (monitoring/management) is a paid product
- Less sophisticated orchestration than LangGraph
- Smaller ecosystem compared to LangChain
- Rebranding from Phidata may cause confusion
- Less community content/tutorials than older frameworks

## Alternatives
| Tool | Key Difference |
|------|---------------|
| LangGraph | More advanced orchestration; graph-based; LangSmith for observability |
| CrewAI | Role-based multi-agent; different paradigm |
| Semantic Kernel | Microsoft-backed; multi-language; Azure integration |
| Google ADK | Google-backed; Vertex AI deployment; A2A protocol |

## References
- https://agno.com
- https://github.com/agno-agi/agno
- https://docs.agno.com

## Notes
Agno's production-first approach is refreshing in a space dominated by prototyping-focused frameworks. The FastAPI runtime and horizontal scaling architecture make it particularly attractive for teams that need to deploy agents as production microservices. The rapid star growth (39K+) suggests strong product-market fit. Watch for the AgentOS platform to mature as the enterprise offering.
