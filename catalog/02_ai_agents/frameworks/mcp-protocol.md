# Model Context Protocol (MCP)

> Open protocol for standardizing how AI agents and LLM applications access tools, resources, and context from external services.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 02 - AI Agents |
| **URL** | https://modelcontextprotocol.io |
| **GitHub** | https://github.com/modelcontextprotocol/python-sdk |
| **Stars** | 22,400 (Python SDK) |
| **License** | MIT |
| **Pricing** | Free (open standard) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
The Model Context Protocol (MCP) is an open standard initiated by Anthropic for standardizing how AI applications provide context to LLMs. It defines a client-server architecture where MCP clients (AI applications, agents) connect to MCP servers (tool providers) through standard transports (stdio, SSE, Streamable HTTP).

MCP has become the de facto standard for agent tool integration, adopted by virtually every major agent framework (LangChain, CrewAI, OpenAI Agents SDK, Google ADK, Anthropic Agent SDK, PydanticAI, and more). It provides three main primitives: **Resources** (data exposure, like GET endpoints), **Tools** (functionality exposure, like POST endpoints), and **Prompts** (reusable prompt templates).

## Key Features
- **Tools**: Expose functionality for LLM actions with side effects
- **Resources**: Expose data for LLM context (read-only)
- **Prompts**: Reusable prompt templates and workflows
- **FastMCP**: High-level Python interface with decorators
- **Structured output**: Pydantic models, TypedDicts, dataclasses support
- **Multiple transports**: stdio, SSE, Streamable HTTP
- **Universal adoption**: Supported by all major agent frameworks

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | Industry standard; universal adoption |
| **Security** | 4 | Transport-level security; server isolation |
| **Scalability** | 5 | Protocol-level; scales independently |
| **Support/Community** | 5 | Anthropic-initiated; adopted by entire industry |
| **Documentation** | 5 | Comprehensive docs and SDKs |
| **Integration Ease** | 5 | Simple decorator-based server creation |

## Use Cases
1. **Agent tool integration** - Standardized way for agents to access external tools
2. **Data provision** - Providing context to LLMs from enterprise data sources
3. **Tool marketplaces** - Discoverable, reusable tool servers
4. **Cross-framework compatibility** - Same tools work across all agent frameworks

## Getting Started
```bash
pip install mcp
```

## Strengths
- Industry-standard protocol adopted by all major frameworks
- Simple server creation with FastMCP decorators
- Clean separation of concerns (tools vs. resources vs. prompts)
- Universal compatibility across agent frameworks

## Limitations
- Server management complexity with many MCP servers
- Performance overhead from protocol layer (IPC for stdio)
- Security model still maturing
- Ecosystem quality varies (many community servers)

## References
- https://modelcontextprotocol.io
- https://github.com/modelcontextprotocol
- https://github.com/modelcontextprotocol/python-sdk

## Notes
MCP has achieved remarkable adoption in under two years, becoming the universal standard for agent-tool communication. Every agent framework now supports MCP. For teams building tools that agents should access, MCP is the clear choice. Combined with A2A (for agent-to-agent communication), MCP forms the foundation of the emerging agent protocol stack.
