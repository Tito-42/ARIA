# MCP Python SDK

> Official Anthropic Python SDK for building MCP servers and clients

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 03 - MCP |
| **URL** | https://github.com/modelcontextprotocol/python-sdk |
| **GitHub** | https://github.com/modelcontextprotocol/python-sdk |
| **Stars** | 22,500 |
| **License** | MIT |
| **Pricing** | Free / Open Source |
| **Last Verified** | 2026-04-02 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
The MCP Python SDK is the official Python library for building servers and clients that implement the Model Context Protocol. Published and maintained by Anthropic under the `modelcontextprotocol` GitHub organization, it is the authoritative implementation for the Python ecosystem.

The SDK provides two levels of abstraction: a high-level API via the integrated FastMCP framework (accessible as `from mcp.server.fastmcp import FastMCP`) and a lower-level API for developers who need full control over the MCP lifecycle, session management, and transport negotiation. It supports all three MCP transports: stdio (for local integrations like Claude Desktop), Server-Sent Events (SSE, being deprecated), and the newer Streamable HTTP transport.

The SDK also includes a full MCP client implementation, enabling Python code to programmatically connect to and use any MCP server — useful for testing, orchestration, and building MCP-aware agent frameworks.

## Key Features
- Full MCP server implementation (tools, resources, prompts, sampling, roots)
- Full MCP client implementation for connecting to any MCP server
- High-level FastMCP API via `mcp.server.fastmcp`
- Transport support: stdio, SSE, Streamable HTTP
- Async-native design using Python `asyncio`
- Type-safe with Pydantic models for all MCP protocol messages
- `mcp dev` CLI command for running and debugging servers
- Integration with Claude Desktop via stdio transport

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | Official Anthropic SDK, actively maintained, used in production at scale |
| **Security** | 4 | Follows MCP security guidelines; supports OAuth 2.1 for remote servers |
| **Scalability** | 4 | Async architecture; Streamable HTTP transport enables stateless deployments |
| **Support/Community** | 5 | Official Anthropic support, 22.5k stars, large community |
| **Documentation** | 5 | Full docs at modelcontextprotocol.io, comprehensive API reference |
| **Integration Ease** | 5 | `pip install mcp`; FastMCP high-level API minimizes boilerplate |

## Use Cases
1. Building production MCP servers in Python to expose internal tools to AI assistants
2. Implementing MCP clients to connect agent frameworks to the MCP ecosystem
3. Low-level MCP server implementation when FastMCP's abstractions are insufficient
4. Testing and validating MCP server compliance with the protocol specification
5. Building Python-based MCP proxies, gateways, or middleware

## Getting Started
```bash
pip install mcp
# or with optional CLI tools
pip install "mcp[cli]"
```

```python
# High-level (FastMCP)
from mcp.server.fastmcp import FastMCP

mcp = FastMCP("My Server")

@mcp.tool()
def hello(name: str) -> str:
    """Greet someone."""
    return f"Hello, {name}!"

mcp.run()
```

```bash
# Run with the MCP CLI
mcp dev server.py
mcp install server.py  # installs into Claude Desktop
```

## Architecture / How It Works
The SDK implements the full JSON-RPC 2.0 based MCP protocol. At the transport layer, it handles framing and encoding for stdio (newline-delimited JSON), SSE, and Streamable HTTP. Above the transport, the `Server` class manages the MCP session lifecycle including capability negotiation, request routing, and response serialization. The FastMCP layer wraps this with a decorator-driven interface. On the client side, the `ClientSession` class handles connecting to servers, capability discovery, and invoking tools/resources/prompts.

## Strengths
- Official implementation — guaranteed protocol compliance
- Two-level API (high-level FastMCP + low-level) covers all use cases
- Complete: covers server, client, all transports, and all protocol features
- Well-tested with the official MCP Inspector
- Active release cadence following the MCP spec evolution

## Limitations
- Python only (TypeScript SDK for JS/TS environments)
- SSE transport being deprecated; migration to Streamable HTTP required for new projects
- Low-level API requires understanding of the full MCP protocol lifecycle
- No built-in auth middleware (OAuth 2.1 support exists but requires configuration)

## Alternatives
| Tool | Key Difference |
|------|---------------|
| MCP TypeScript SDK | Official SDK for Node.js/TypeScript; parity in features |
| FastMCP (standalone) | Superset of the SDK's FastMCP with additional experimental features |
| mcp-framework (npm) | Community TypeScript framework similar to FastMCP |

## References
- [GitHub Repository](https://github.com/modelcontextprotocol/python-sdk)
- [MCP Python SDK on PyPI](https://pypi.org/project/mcp/)
- [MCP Official Documentation](https://modelcontextprotocol.io/docs)
- [MCP Protocol Specification](https://spec.modelcontextprotocol.io)

## Notes
The `mcp` package on PyPI is the official distribution. The SDK is versioned alongside the MCP specification. As of March 2026, the SDK is at version 1.x with Streamable HTTP as the recommended transport for remote servers. The `mcp install` CLI command automates the registration of servers in Claude Desktop's configuration file.
