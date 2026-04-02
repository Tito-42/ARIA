# mcpo

> Dead-simple proxy that exposes any MCP server as a standard OpenAPI/REST HTTP endpoint

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 03 - MCP |
| **URL** | https://github.com/open-webui/mcpo |
| **GitHub** | https://github.com/open-webui/mcpo |
| **Stars** | 4,100 |
| **License** | MIT |
| **Pricing** | Free / Open Source |
| **Last Verified** | 2026-04-02 |
| **Status** | Active |
| **Maturity** | Beta |

## What It Does
mcpo (MCP-to-OpenAPI) is a lightweight proxy server that bridges the MCP ecosystem to the broader HTTP/REST world. It takes any MCP stdio server as input and exposes its tools as standard REST endpoints with auto-generated OpenAPI documentation, making MCP tools consumable by any HTTP client, language, or framework — without requiring MCP-specific client libraries.

Developed by the Open WebUI team (creators of the popular Open WebUI interface for local LLMs), mcpo was created to enable Open WebUI to consume MCP tools without needing a native MCP client. This "bridge" pattern is increasingly important as organizations want to leverage the growing MCP tool ecosystem without fully committing to MCP-native clients.

Version 0.0.20 was released on February 27, 2026, showing active maintenance. With 4,100 stars, it has established itself as the standard solution for MCP-to-HTTP bridging.

## Key Features
- Converts any MCP stdio server into a REST API with OpenAPI 3.0 specification
- Auto-generated Swagger/OpenAPI documentation at `/docs`
- Single command invocation: `uvx mcpo -- <your-mcp-server-command>`
- Configurable multi-server support via a JSON config file
- Bearer token authentication for the proxy endpoint
- Compatible with any MCP server regardless of implementation language
- Docker support for containerized deployments

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 3 | v0.0.20, beta maturity; functional but not hardened for high-traffic production |
| **Security** | 3 | Bearer token auth available; process-level isolation per server instance |
| **Scalability** | 3 | Each stdio server is a subprocess; horizontal scaling requires orchestration |
| **Support/Community** | 4 | 4.1k stars, active Open WebUI team, responsive to issues |
| **Documentation** | 4 | Good README, config examples; auto-generated OpenAPI docs are a bonus |
| **Integration Ease** | 5 | Single `uvx mcpo -- cmd` invocation; works with any HTTP client immediately |

## Use Cases
1. Using MCP tools from applications that only support HTTP/REST APIs (no native MCP client)
2. Integrating MCP servers into Open WebUI for a local LLM assistant with tools
3. Exposing MCP tools to legacy enterprise systems via standard REST
4. Quick prototyping: test an MCP server's tools with curl or Postman
5. Enabling non-Python/TypeScript environments (Go, Java, Ruby) to consume MCP tools

## Getting Started
```bash
# Single server (uvx for zero-install)
uvx mcpo -- uvx your-mcp-server

# Example: expose the filesystem MCP server as REST
uvx mcpo -- npx -y @modelcontextprotocol/server-filesystem /tmp

# The API is now available at http://localhost:8000
# OpenAPI docs at http://localhost:8000/docs

# With authentication
uvx mcpo --api-key mysecretkey -- npx -y @modelcontextprotocol/server-filesystem /tmp

# Multi-server config
uvx mcpo --config config.json
```

```json
{
  "mcpServers": {
    "filesystem": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-filesystem", "/tmp"]
    },
    "github": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-github"],
      "env": { "GITHUB_TOKEN": "..." }
    }
  }
}
```

## Architecture / How It Works
mcpo runs as a FastAPI application. On startup, it launches each configured MCP server as a subprocess via stdio transport and connects to it using the MCP Python SDK client. It then introspects the server's tool list and dynamically generates FastAPI route handlers for each tool, along with the corresponding OpenAPI schema. Incoming HTTP POST requests to a tool's endpoint are translated into MCP `tools/call` protocol messages, sent to the subprocess, and the response is returned as JSON over HTTP.

## Strengths
- Extremely low friction: one command to make any MCP server HTTP-accessible
- Auto-generated OpenAPI docs serve as live documentation
- Language-agnostic: any HTTP client can use it
- Multi-server support in a single proxy instance
- Maintained by the active Open WebUI team

## Limitations
- Beta maturity (v0.0.x) — API and behavior may change
- Subprocess-per-server model limits scalability under high concurrent load
- Stdio-only for the MCP side (does not proxy SSE or Streamable HTTP servers)
- No built-in session management for stateful MCP servers
- Adds network hop latency compared to native MCP clients

## Alternatives
| Tool | Key Difference |
|------|---------------|
| mcp-proxy | Transport bridge (stdio ↔ SSE/HTTP) rather than protocol translation |
| Supergateway | stdio → SSE/WebSocket bridge; keeps MCP protocol intact |
| Agentgateway | Enterprise-grade proxy with RBAC/OTel; more complex setup |
| Direct MCP SDK | Native MCP client; better performance but requires MCP-aware code |

## References
- [GitHub Repository](https://github.com/open-webui/mcpo)
- [PyPI Package](https://pypi.org/project/mcpo/)
- [Open WebUI Documentation on mcpo](https://docs.openwebui.com/openapi-connections/mcpo)

## Notes
mcpo is particularly useful in the Open WebUI ecosystem but is a general-purpose tool. The project's version number (0.0.x) understates its stability for typical use cases. The auto-generated OpenAPI spec approach means that tool descriptions from the MCP server become the API documentation — well-documented MCP servers produce better REST APIs.
