# mcp-proxy

> Transport bridge for MCP: expose stdio servers as SSE endpoints or connect stdio clients to remote SSE servers

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 03 - MCP |
| **URL** | https://github.com/sparfenyuk/mcp-proxy |
| **GitHub** | https://github.com/sparfenyuk/mcp-proxy |
| **Stars** | 2,400 |
| **License** | {TODO} - confirm in repo (open source) |
| **Pricing** | Free / Open Source |
| **Last Verified** | 2026-04-02 |
| **Status** | Active |
| **Maturity** | Beta |

## What It Does
mcp-proxy is a bidirectional transport bridge for the Model Context Protocol that solves a fundamental interoperability problem in the MCP ecosystem: many clients (like Claude Desktop) only support stdio transport, while many servers are designed to run as remote SSE or Streamable HTTP endpoints — and vice versa.

The proxy supports two operating modes: (1) exposing a stdio-based MCP server as an SSE HTTP endpoint, enabling remote clients to connect to locally-running servers; and (2) connecting a stdio-based MCP client to a remote SSE server, enabling clients that only speak stdio to consume remote services.

With 2,400 stars and an Alpine Docker image available (`v0.3.2-alpine`), mcp-proxy has become the standard solution for transport bridging in the MCP ecosystem. It is installable via PyPI using `uv tool install mcp-proxy` for zero-fuss deployment.

## Key Features
- **stdio → SSE**: Wrap any stdio MCP server to expose it as an HTTP SSE endpoint
- **SSE → stdio**: Connect any stdio MCP client to a remote SSE server
- Support for Streamable HTTP transport in addition to SSE
- Alpine Docker image for minimal containerized deployments
- Available via PyPI (`uv tool install mcp-proxy`)
- Configurable port and host binding
- Pass-through environment variable forwarding to wrapped servers

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 3 | v0.3.2, functional but pre-1.0; Docker image available |
| **Security** | 2 | No built-in auth; must add reverse proxy (nginx/Caddy/Traefik) for security |
| **Scalability** | 3 | Single process bridge; multiple instances needed for parallel sessions |
| **Support/Community** | 3 | 2.4k stars; community-maintained |
| **Documentation** | 3 | Good README covering both modes; limited advanced config docs |
| **Integration Ease** | 5 | `uv tool install mcp-proxy` + single command to run |

## Use Cases
1. Claude Desktop (stdio-only client) accessing a remote SSE-hosted MCP server
2. Making a locally-developed stdio MCP server accessible to remote web clients
3. Sharing a local MCP server across a development team via an SSE endpoint
4. Containerizing stdio MCP servers behind an SSE interface for orchestration
5. Testing remote server behavior from a local stdio client during development

## Getting Started
```bash
# Install via uv (recommended)
uv tool install mcp-proxy

# Mode 1: Expose stdio server as SSE endpoint
# This wraps "uvx my-mcp-server" and serves it at http://localhost:8080/sse
mcp-proxy --sse-port 8080 -- uvx my-mcp-server

# Mode 2: Connect stdio client to remote SSE server
# Claude Desktop config (proxy stdio → remote SSE):
{
  "mcpServers": {
    "remote-server": {
      "command": "mcp-proxy",
      "args": ["https://my-remote-server.example.com/sse"]
    }
  }
}

# Docker (Alpine image)
docker run -i --rm \
  -p 8080:8080 \
  sparfenyuk/mcp-proxy:v0.3.2-alpine \
  --sse-port 8080 -- uvx my-mcp-server
```

## Architecture / How It Works
mcp-proxy operates as a protocol relay. In stdio-to-SSE mode: it launches the stdio server as a subprocess, connects to it over stdin/stdout using the MCP Python SDK client, then starts an HTTP server with an SSE endpoint. Incoming SSE client connections receive all MCP protocol messages forwarded from the stdio server, and messages from SSE clients are forwarded to the stdio server's stdin. In SSE-to-stdio mode: it connects to the remote SSE server as an MCP client, then presents itself as a stdio MCP server to the local client — bidirectionally relaying all messages.

## Strengths
- Bidirectional: handles both stdio→SSE and SSE→stdio directions
- Alpine Docker image keeps container size minimal
- Simple single-command operation for both modes
- Solves a real and common problem in the MCP ecosystem
- PyPI distribution via `uv tool install` is frictionless

## Limitations
- No built-in authentication — must be secured with a reverse proxy
- Pre-1.0 versioning indicates potential breaking changes
- Single subprocess model limits concurrency
- SSE transport may be deprecated in MCP spec; Streamable HTTP is the future
- Limited configurability for advanced routing or load balancing

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Supergateway | Also stdio→SSE/WebSocket; adds WebSocket support; less active |
| Agentgateway | Enterprise-grade proxy with RBAC, OTel, A2A; Rust+Go; more complex |
| mcpo | Converts to REST/OpenAPI rather than keeping MCP protocol |

## References
- [GitHub Repository](https://github.com/sparfenyuk/mcp-proxy)
- [PyPI Package](https://pypi.org/project/mcp-proxy/)
- [Docker Hub Image](https://hub.docker.com/r/sparfenyuk/mcp-proxy)

## Notes
mcp-proxy fills a critical gap in the MCP transport ecosystem. For production deployments, always put a reverse proxy (nginx, Caddy, Traefik) in front of the SSE endpoint with TLS and authentication. The project's activity level appears healthy — monitor for continued updates as the MCP transport landscape evolves from SSE to Streamable HTTP.
