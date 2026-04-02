# n8n

> Open-source workflow automation platform with 400+ integrations, AI agent capabilities, and a visual node-based editor for building complex automation pipelines.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 11_automation_workflows |
| **URL** | https://n8n.io |
| **GitHub** | https://github.com/n8n-io/n8n |
| **Stars** | ~53,000 |
| **License** | Sustainable Use License (source-available) / Enterprise license |
| **Pricing** | Free (self-hosted) / Cloud Starter $24/mo / Pro $60/mo / Enterprise (custom) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
n8n is an open-source (source-available) workflow automation platform that enables users to connect different services and build complex automation pipelines through a visual, node-based editor. With 400+ integrations and a JavaScript/Python code execution environment, n8n bridges the gap between simple no-code automation (like Zapier) and custom-coded solutions.

Since 2024, n8n has heavily invested in AI capabilities, adding native AI agent nodes, LLM integration (OpenAI, Anthropic, Ollama), vector store connections, and RAG pipeline building. This has made n8n one of the most popular platforms for building AI-powered automation workflows. The "AI Agent" node allows creating autonomous agents that can use tools, access databases, and make decisions within n8n workflows.

## Key Features
- **Visual workflow editor**: Drag-and-drop node-based builder
- **400+ integrations**: Slack, GitHub, Google, Salesforce, databases, etc.
- **AI Agent node**: Built-in autonomous AI agent with tool use
- **LLM integration**: OpenAI, Anthropic, Google, Ollama, HuggingFace
- **RAG pipelines**: Vector store + retrieval nodes for RAG workflows
- **Code nodes**: Execute JavaScript or Python within workflows
- **Webhooks**: Trigger workflows from external events
- **Error handling**: Built-in error workflows and retry logic
- **Self-hostable**: Docker, npm, or n8n Cloud
- **Credentials management**: Secure storage for API keys and OAuth
- **Sub-workflows**: Modular workflow composition
- **Community nodes**: 900+ community-built integrations

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | Mature; used by enterprises globally |
| **Security** | 4 | Self-hostable; credential encryption; RBAC |
| **Scalability** | 4 | Queue mode for high volume; horizontal scaling |
| **Support/Community** | 5 | 53K stars; vibrant community; enterprise support |
| **Documentation** | 5 | Excellent docs; many tutorials |
| **Integration Ease** | 5 | Visual builder; 400+ connectors |

## Use Cases
1. **AI-powered automation** - LLM-driven workflows with decision-making
2. **Data pipeline orchestration** - ETL and data sync between services
3. **DevOps automation** - CI/CD triggers, deployment workflows, monitoring
4. **Customer support** - AI-powered ticket routing and response generation
5. **Document processing** - Extract, transform, and route documents with AI

## Getting Started
```bash
# Docker (fastest)
docker run -it --rm --name n8n -p 5678:5678 n8nio/n8n

# npm
npx n8n

# Access at http://localhost:5678
```

## Strengths
- Most popular open-source automation platform (53K stars)
- AI-native features (agent nodes, LLM, RAG, vector stores)
- Self-hostable for data sovereignty
- Code nodes for unlimited customization
- Massive integration library (400+ official, 900+ community)

## Limitations
- Sustainable Use License (not true open source -- restrictions on competing SaaS)
- UI can be overwhelming for simple automations
- Self-hosting requires maintenance
- Complex workflows can be hard to debug
- AI features still evolving (less polished than dedicated AI platforms)

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Activepieces | True open source (MIT); simpler UX |
| Zapier | SaaS-only; simpler; more expensive |
| Make.com | Visual; more polished UI; SaaS-only |
| Temporal | Code-first; durable execution; enterprise-grade |
| Windmill | Open source; script-first approach |

## References
- https://n8n.io
- https://github.com/n8n-io/n8n
- https://docs.n8n.io
