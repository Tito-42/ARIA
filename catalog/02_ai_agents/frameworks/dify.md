# Dify

> Production-ready platform for agentic workflow development with visual canvas, RAG, and comprehensive model management.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 02 - AI Agents |
| **URL** | https://dify.ai |
| **GitHub** | https://github.com/langgenius/dify |
| **Stars** | 135,000 |
| **License** | Dify Open Source License (Apache 2.0 based, with additional conditions) |
| **Pricing** | Free (self-hosted) / Dify Cloud (paid tiers) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Dify is a production-ready platform for building agentic workflows that combines AI workflow construction, RAG pipelines, agent capabilities, model management, and observability in a single platform. It provides a visual canvas for building and testing AI workflows, a Prompt IDE, comprehensive model support (hundreds of LLMs from dozens of providers), and Backend-as-a-Service APIs.

Dify occupies the "low-code/no-code AI platform" space, enabling both developers and non-developers to build sophisticated AI applications. It supports LLM Function Calling and ReAct-based agents with 50+ built-in tools, plus RAG pipelines with document ingestion for PDFs, PPTs, and other formats.

## Key Features
- **Visual workflow canvas**: Drag-and-drop AI workflow builder
- **Prompt IDE**: Interface for crafting and comparing prompts across models
- **RAG pipeline**: Document ingestion, chunking, and retrieval
- **Agent capabilities**: Function Calling and ReAct agents with 50+ tools
- **Model management**: Hundreds of LLMs from dozens of providers
- **LLMOps**: Monitoring, analysis, and continuous improvement
- **Backend-as-a-Service**: APIs for integration into business logic
- **Self-hosted**: Full self-hosted deployment option

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | 135K stars; widely deployed; comprehensive platform |
| **Security** | 4 | Self-hosted option; data residency control |
| **Scalability** | 4 | Cloud and self-hosted scaling options |
| **Support/Community** | 5 | 135K stars; massive community; active development |
| **Documentation** | 4 | Good docs; active community |
| **Integration Ease** | 5 | Visual builder; API access; Docker deployment |

## Use Cases
1. **Enterprise AI platform** - Organization-wide AI application builder
2. **RAG applications** - Document Q&A and knowledge management
3. **Workflow automation** - Visual AI workflow construction
4. **Chatbot development** - Customer-facing conversational AI

## Getting Started
```bash
docker compose up -d
```

## Strengths
- Comprehensive all-in-one platform
- Visual builder makes AI accessible to non-developers
- Self-hosted option for data sovereignty
- Massive community adoption (135K stars)
- Backend-as-a-Service for easy integration

## Limitations
- Custom license has additional conditions beyond Apache 2.0
- Less flexibility than code-first frameworks for complex agent logic
- Visual builder can be limiting for advanced use cases
- Performance overhead from platform abstraction layer

## References
- https://dify.ai
- https://docs.dify.ai
- https://github.com/langgenius/dify

## Notes
Dify is best understood as an AI application platform rather than a pure agent framework. It competes more with Flowise, n8n, and enterprise AI platforms than with LangChain or CrewAI. For teams wanting a visual, all-in-one platform with self-hosting capability, Dify is the top choice. For teams wanting code-first agent development, look at LangGraph, CrewAI, or PydanticAI instead.
