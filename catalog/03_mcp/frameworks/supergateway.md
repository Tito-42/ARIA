# Supergateway

> Run stdio MCP servers over SSE or WebSocket for remote access and multi-client scenarios

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 03 - MCP |
| **URL** | https://github.com/supercorp-ai/supergateway |
| **GitHub** | https://github.com/supercorp-ai/supergateway |
| **Stars** | 2,500 |
| **License** | MIT |
| **Pricing** | Free / Open Source |
| **Last Verified** | 2026-04-02 |
| **Status** | Active |
| **Maturity** | Beta |

## What It Does
Supergateway is a transport bridge that wraps MCP stdio servers and exposes them over Server-Sent Events (SSE) or WebSocket, enabling remote access and multi-client scenarios that are not possible with stdio alone. It is the complement to mcp-proxy, targeting a slightly different use case: adding WebSocket support and enabling the server to accept connections from multiple clients simultaneously.

Developed by Supercorp AI, Supergateway is particularly useful for sharing an MCP server across a team or exposing it as a remote endpoint accessible from cloud-based agents. The tool is deployed as an npm package and can wrap any stdio MCP server with a single command.

With 2,500 stars, it has found a solid user base among developers who need to make local MCP servers remotely accessible without writing custom transport code.

## Key Features
- Wraps any stdio MCP server to expose it over SSE or WebSocket
- Single command: `npx supergateway --stdio "your-mcp-server-command"`
- WebSocket transport support (differentiator vs mcp-proxy)
- Configurable port and endpoint path
- CORS support for web client access
- No modification to the underlying MCP server required
- Docker-compatible for containerized deployments

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 3 | Functional but last major commit December 2024; activity has slowed |
| **Security** | 2 | No built-in authentication; must add reverse proxy (nginx/Caddy) for auth |
| **Scalability** | 3 | Single server process; multiple clients share one stdio server instance |
| **Support/Community** | 3 | 2.5k stars; Supercorp AI team; reduced recent activity |
| **Documentation** | 3 | Adequate README; limited advanced configuration docs |
| **Integration Ease** | 5 | Single `npx` command; wraps any stdio server transparently |

## Use Cases
1. Sharing a local MCP server with remote team members via WebSocket
2. Enabling cloud-hosted AI agents to connect to an on-premises MCP server
3. Providing a web-accessible MCP endpoint for browser-based AI interfaces
4. Testing SSE/WebSocket transport behavior without building a native server
5. Bridging stdio-only MCP servers for use with clients that require SSE/HTTP

## Getting Started
```bash
# Expose a stdio server over SSE (port 8000)
npx supergateway --stdio "npx -y @modelcontextprotocol/server-filesystem /tmp"

# Expose over WebSocket
npx supergateway --stdio "npx -y @modelcontextprotocol/server-filesystem /tmp" --transport ws

# Custom port
npx supergateway --stdio "uvx my-mcp-server" --port 9000

# The SSE endpoint is at: http://localhost:8000/sse
# The WebSocket endpoint is at: ws://localhost:8000/ws
```

## Architecture / How It Works
Supergateway launches the specified stdio command as a child process and bidirectionally pipes its stdin/stdout to an HTTP server. For SSE mode, it runs an Express server with an SSE endpoint; incoming client connections receive a persistent event stream. For WebSocket mode, it uses a WebSocket server. All MCP JSON-RPC messages from the stdio process are forwarded to connected clients, and messages from clients are forwarded to the stdio process stdin.

## Strengths
- WebSocket support distinguishes it from mcp-proxy (SSE-only)
- Zero modification to wrapped servers
- MIT license, no restrictions
- Works with any language's MCP stdio implementation

## Limitations
- Reduced development activity since December 2024
- No built-in authentication or authorization
- Single stdio process means concurrent clients share state (potential race conditions with stateful servers)
- SSE transport may be deprecated in MCP spec in favor of Streamable HTTP
- Limited to stdio-to-SSE/WS direction only

## Alternatives
| Tool | Key Difference |
|------|---------------|
| mcp-proxy | Bidirectional (stdio↔SSE and SSE→stdio); more actively maintained |
| Agentgateway | Enterprise-grade with RBAC, OTel, A2A; Rust+Go; more complex |
| mcpo | Converts MCP to REST/OpenAPI instead of keeping MCP protocol |

## References
- [GitHub Repository](https://github.com/supercorp-ai/supergateway)
- [NPM Package](https://www.npmjs.com/package/supergateway)
- [Supercorp AI](https://supercorp.ai)

## Notes
For new projects, consider mcp-proxy as an alternative since it appears more actively maintained and also supports the reverse direction (connecting stdio clients to SSE servers). Supergateway's WebSocket support may be its key differentiator if WebSocket transport is specifically needed. Monitor the project's activity level before adopting for production use.
