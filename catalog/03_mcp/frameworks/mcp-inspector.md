# MCP Inspector

> Official visual debugging and testing tool for MCP servers

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 03 - MCP |
| **URL** | https://github.com/modelcontextprotocol/inspector |
| **GitHub** | https://github.com/modelcontextprotocol/inspector |
| **Stars** | 9,300 |
| **License** | MIT |
| **Pricing** | Free / Open Source |
| **Last Verified** | 2026-04-02 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
MCP Inspector is the official interactive debugging and testing tool for Model Context Protocol servers. Maintained by Anthropic, it provides a React-based web UI backed by a Node.js proxy that can connect to any MCP server regardless of transport type, making it an essential companion for MCP development.

The tool allows developers to visually browse the tools, resources, and prompts exposed by a server, invoke them with custom arguments, and inspect the raw protocol messages being exchanged. This dramatically accelerates the development cycle for MCP server authors by eliminating the need to configure a full AI client just to test a server.

With 9,300 stars and ongoing updates through 2026, MCP Inspector is the standard testing harness in the MCP ecosystem, recommended in the official MCP documentation and used by virtually all MCP server developers.

## Key Features
- Visual web UI (React) for exploring server capabilities (tools, resources, prompts)
- Interactive tool invocation with form-based argument input
- Raw JSON-RPC message inspection for debugging protocol issues
- Support for all three MCP transports: stdio, SSE, Streamable HTTP
- `npx @modelcontextprotocol/inspector` for zero-install usage
- Connection to both local (stdio process launch) and remote (SSE/HTTP URL) servers
- Real-time log streaming from the connected server
- OAuth flow support for remote servers requiring authentication

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | Official tool, essential for dev/QA workflows |
| **Security** | 4 | Development tool; local proxy model is safe; OAuth for remote servers |
| **Scalability** | 3 | Developer tool, not designed for production-scale testing |
| **Support/Community** | 5 | Official Anthropic tool, 9.3k stars |
| **Documentation** | 5 | Integrated into official MCP quickstart and debugging guides |
| **Integration Ease** | 5 | Single `npx` command, no installation needed |

## Use Cases
1. Debugging a new MCP server during development by inspecting tool schemas and responses
2. Validating that a server correctly implements the MCP protocol before deployment
3. Exploring the capabilities of third-party MCP servers before integrating them
4. Testing edge cases in tool argument handling with custom JSON inputs
5. Demonstrating MCP server capabilities to stakeholders without a full AI client setup

## Getting Started
```bash
# Zero-install usage (recommended)
npx @modelcontextprotocol/inspector

# Connect to a specific server via stdio
npx @modelcontextprotocol/inspector node my-server.js

# Connect to a remote SSE server
npx @modelcontextprotocol/inspector --url http://localhost:3000/sse

# Or install globally
npm install -g @modelcontextprotocol/inspector
mcp-inspector
```

## Architecture / How It Works
MCP Inspector consists of two components: a Node.js proxy server and a React web application. The proxy server acts as an MCP client that connects to the target MCP server (via stdio by launching a subprocess, or via SSE/HTTP by connecting to a URL). The web UI connects to the proxy via WebSocket and displays the server's capabilities. When a user invokes a tool through the UI, the request flows: Web UI -> WebSocket -> Proxy -> MCP protocol -> Target server, with responses flowing back the same path.

## Strengths
- Zero-friction: one `npx` command to start debugging
- Transport-agnostic: works with stdio, SSE, and Streamable HTTP servers
- Visual tool schema display helps verify argument definitions
- Raw message view exposes actual JSON-RPC traffic for protocol debugging
- Official tool ensures compatibility with all MCP spec versions

## Limitations
- Developer tool only — not designed for automated testing or CI/CD pipelines
- No test recording or playback features
- Cannot simulate concurrent clients or load testing
- Web UI requires a browser; no terminal-only interface

## Alternatives
| Tool | Key Difference |
|------|---------------|
| MCP CLI (`mcp dev`) | Part of Python SDK; terminal-based, less visual |
| Custom test scripts | Using MCP Python/TS SDK clients for automated testing |
| Postman / Bruno | For HTTP-based MCP servers; not MCP-protocol-aware |

## References
- [GitHub Repository](https://github.com/modelcontextprotocol/inspector)
- [NPM Package](https://www.npmjs.com/package/@modelcontextprotocol/inspector)
- [MCP Debugging Guide](https://modelcontextprotocol.io/docs/tools/debugging)
- [MCP Official Documentation](https://modelcontextprotocol.io/docs)

## Notes
MCP Inspector is the first tool recommended in the official MCP debugging guide. It is particularly valuable when developing servers that will run in Claude Desktop (stdio transport), as Claude Desktop itself provides limited debugging feedback. The proxy architecture means Inspector can connect to servers written in any language, not just Python or TypeScript.
