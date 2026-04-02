# LangChain

> The agent engineering platform for building LLM-powered applications with composable components and 100+ integrations.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 02 - AI Agents |
| **URL** | https://docs.langchain.com |
| **GitHub** | https://github.com/langchain-ai/langchain |
| **Stars** | 132,000 |
| **License** | MIT |
| **Pricing** | Free (OSS) / LangSmith paid tiers for observability |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
LangChain is the dominant agent engineering platform for building LLM-powered applications. It provides a modular, component-based architecture that lets developers chain together interoperable building blocks -- model calls, tools, retrievers, memory, and output parsers -- to construct complex AI workflows. It acts as the glue layer between LLMs and the rest of the software stack.

The framework supports real-time data augmentation (connecting LLMs to APIs, PDFs, SQL, docs), model interoperability (swap providers without rebuilding), rapid prototyping, and production deployment. LangChain is model-agnostic and integrates with virtually every major LLM provider.

LangChain now positions itself primarily as the foundation for its agent orchestration ecosystem: **LangGraph** handles stateful agent workflows, **Deep Agents** manages complex task planning with sub-agents, and **LangSmith** provides observability, evaluation, and debugging.

## Key Features
- Model-agnostic: supports OpenAI, Anthropic, Google, local models, and 100+ providers
- Composable chain/pipeline architecture with modular components
- Extensive document loaders, text splitters, and retrieval integrations
- Built-in memory systems (conversation buffer, summary, entity, vector-backed)
- Tool and function calling abstractions
- Streaming support and async execution
- LangSmith integration for tracing, evaluation, and monitoring
- Deep integration with LangGraph for stateful agent orchestration
- Massive ecosystem: community packages, templates, and LangChain Hub

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | Used in production by thousands of companies; mature release cycle |
| **Security** | 4 | Enterprise deployments supported; LangSmith offers data residency |
| **Scalability** | 4 | Async support, streaming; scales well with LangGraph for complex flows |
| **Support/Community** | 5 | Largest community in the LLM tooling space; active forum, Discord |
| **Documentation** | 5 | Comprehensive docs, tutorials, LangChain Academy courses |
| **Integration Ease** | 5 | `pip install langchain`; modular -- use only what you need |

## Use Cases
1. **RAG applications** - Connect LLMs to enterprise data sources with retrieval pipelines
2. **Conversational agents** - Build chatbots with memory, tool access, and multi-step reasoning
3. **Data extraction** - Structured output extraction from documents using LLM chains
4. **Multi-agent orchestration** - Via LangGraph, build complex agent teams and workflows

## Getting Started
```bash
pip install langchain
# or with specific integrations
pip install langchain-openai langchain-anthropic
```

## Architecture / How It Works
LangChain follows a layered architecture:
- **langchain-core**: Base abstractions (Runnables, messages, prompts, output parsers)
- **langchain**: Chains, agents, and retrieval strategies
- **langchain-community / partner packages**: Provider-specific integrations
- **LangGraph**: Stateful graph-based agent orchestration (separate package)
- **LangSmith**: SaaS observability and evaluation platform

Components are composable via the LCEL (LangChain Expression Language) pipe syntax, enabling declarative chain construction.

## Strengths
- Largest ecosystem and community in the LLM application space
- Extremely flexible and modular -- works for simple chains and complex agents
- First-mover advantage with extensive documentation and examples
- Strong enterprise adoption and proven production track record
- Rapid release cycle keeping pace with LLM provider changes

## Limitations
- Complexity and abstraction overhead can be confusing for beginners
- Frequent API changes have historically caused breaking changes (stabilizing with v1.x)
- Performance overhead from abstraction layers vs. direct API calls
- "Framework lock-in" criticism -- deep LangChain usage can be hard to migrate away from
- LangSmith (observability) is a paid product for full features

## Alternatives
| Tool | Key Difference |
|------|---------------|
| LlamaIndex | More data/RAG focused vs. LangChain's broader agent focus |
| Haystack | More opinionated pipeline architecture, strong NLP roots |
| PydanticAI | Type-safe, Pydantic-native, lighter weight |
| CrewAI | Focused on multi-agent role-based collaboration |

## References
- https://docs.langchain.com
- https://python.langchain.com/docs/get_started/introduction
- https://github.com/langchain-ai/langchain
- https://smith.langchain.com (LangSmith)
- https://academy.langchain.com (LangChain Academy)

## Notes
LangChain has evolved significantly from its early "chain everything" approach into a more focused agent engineering platform. The ecosystem split (LangChain core + LangGraph + LangSmith) reflects maturity. For new projects in 2026, the recommended path is to use LangGraph for agent orchestration with LangChain components as building blocks, rather than using legacy LangChain agents.
