# FastMCP

> High-level Python framework for building MCP servers and clients with minimal boilerplate

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 03 - MCP |
| **URL** | https://github.com/jlowin/fastmcp |
| **GitHub** | https://github.com/jlowin/fastmcp |
| **Stars** | 24,200 |
| **License** | Apache-2.0 |
| **Pricing** | Free / Open Source |
| **Last Verified** | 2026-04-02 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
FastMCP is a high-level Python framework that dramatically simplifies the creation of MCP (Model Context Protocol) servers and clients. A single `@mcp.tool()` decorator applied to a Python function is sufficient to expose it as an MCP-compatible tool — no manual protocol plumbing required.

FastMCP has become the de facto standard for writing MCP servers in Python, powering an estimated 70% of all Python-based MCP servers. It is downloaded approximately 1 million times per day and has been integrated directly into the official MCP Python SDK as its high-level API layer.

Version 3.2.0 (released March 30, 2026) introduced further improvements, confirming the project's rapid iteration pace. Its design philosophy prioritizes developer ergonomics: Python type hints drive schema generation, docstrings become tool descriptions, and standard Python patterns work seamlessly.

## Key Features
- `@mcp.tool()` decorator to expose any Python function as an MCP tool
- `@mcp.resource()` and `@mcp.prompt()` decorators for resources and prompts
- Automatic JSON schema generation from Python type annotations
- Support for stdio, SSE, and Streamable HTTP transports
- Built-in FastMCP client for testing and programmatic server calls
- Integrated into the official `mcp` Python SDK (importable as `from mcp.server.fastmcp import FastMCP`)
- Context injection for logging, progress reporting, and resource access
- Composable servers via `mcp.mount()` for modular architectures

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | 1M+ daily downloads, v3.2.0, powers ~70% of Python MCP servers |
| **Security** | 3 | Security model delegated to transport layer; no built-in auth beyond what MCP provides |
| **Scalability** | 4 | Async-native; stateless tool functions scale horizontally; server composition via mount |
| **Support/Community** | 5 | 24.2k stars, integrated into official SDK, very active maintainer |
| **Documentation** | 5 | Comprehensive docs at gofastmcp.com, examples, tutorials |
| **Integration Ease** | 5 | Single decorator pattern; pip install; works with any Python function |

## Use Cases
1. Building a custom MCP server to expose internal APIs or databases to Claude/Copilot agents
2. Rapid prototyping of tool-augmented LLM workflows in Python
3. Wrapping existing Python libraries (pandas, SQLAlchemy, etc.) as MCP tools for AI assistants
4. Creating multi-tool MCP servers combining data retrieval, computation, and side effects
5. Composing multiple specialized MCP servers into a unified server via `mcp.mount()`

## Getting Started
```bash
pip install fastmcp

# or with uv (recommended)
uv add fastmcp
```

```python
from fastmcp import FastMCP

mcp = FastMCP("My Server")

@mcp.tool()
def add(a: int, b: int) -> int:
    """Add two numbers."""
    return a + b

if __name__ == "__main__":
    mcp.run()
```

## Architecture / How It Works
FastMCP acts as a decorator-driven abstraction over the lower-level MCP Python SDK. When a function is decorated with `@mcp.tool()`, FastMCP inspects its signature and docstring to generate the corresponding MCP `Tool` object with a JSON Schema. At runtime, incoming MCP `tools/call` requests are dispatched to the appropriate Python function, with arguments deserialized and validated automatically. The server can run over stdio (for Claude Desktop), SSE, or Streamable HTTP transports.

## Strengths
- Extremely low barrier to entry: one decorator, one `mcp.run()` call
- Pythonic API that leverages type hints and docstrings natively
- First-class async support
- Official integration: maintained as part of the `modelcontextprotocol/python-sdk`
- Massive community adoption (1M+ daily downloads)

## Limitations
- Python only (for TypeScript, use the official TypeScript SDK directly)
- Complex tool schemas (deeply nested types) may require extra annotation work
- No built-in authentication or authorization — must be handled at the transport/infrastructure level
- SSE transport scheduled for deprecation in favor of Streamable HTTP

## Alternatives
| Tool | Key Difference |
|------|---------------|
| MCP Python SDK (low-level) | More control, more boilerplate; FastMCP is built on top of this |
| MCP TypeScript SDK | Official SDK for Node.js/TypeScript ecosystem |
| mcp-framework (npm) | TypeScript alternative with similar decorator approach |

## References
- [FastMCP Documentation](https://gofastmcp.com)
- [GitHub Repository](https://github.com/jlowin/fastmcp)
- [MCP Python SDK (includes FastMCP)](https://github.com/modelcontextprotocol/python-sdk)
- [MCP Official Documentation](https://modelcontextprotocol.io/docs)

## Notes
FastMCP was originally a standalone project by Jeremiah Lowin before being adopted into the official MCP Python SDK. The standalone `jlowin/fastmcp` repo continues to be the primary development location. When installing via `pip install mcp`, FastMCP is available at `mcp.server.fastmcp`. The standalone package may include more experimental features ahead of the SDK integration.
