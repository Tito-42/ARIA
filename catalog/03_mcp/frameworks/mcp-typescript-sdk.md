# MCP TypeScript SDK

> Official TypeScript/JavaScript SDK for building MCP servers and clients across Node.js, Bun, and Deno

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 03 - MCP |
| **URL** | https://github.com/modelcontextprotocol/typescript-sdk |
| **GitHub** | https://github.com/modelcontextprotocol/typescript-sdk |
| **Stars** | 12,100 |
| **License** | Apache-2.0 |
| **Pricing** | Free / Open Source |
| **Last Verified** | 2026-04-02 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
The MCP TypeScript SDK is the official JavaScript and TypeScript implementation of the Model Context Protocol, maintained by Anthropic under the `modelcontextprotocol` organization. It enables developers to build MCP servers and clients in the Node.js ecosystem, with support for Bun and Deno runtimes as well.

Version 1.29.0 was released on March 30, 2026, reflecting a very active development pace. The SDK supports all current MCP transports (stdio, SSE, Streamable HTTP) and includes middleware integrations for popular Node.js web frameworks including Express and Hono. A v2 is reportedly in preparation, which is expected to introduce breaking changes for improved ergonomics.

Given that many enterprise backend services and tooling are built on Node.js, this SDK is the primary choice for integrating MCP into JavaScript-heavy stacks. The GitHub MCP server, Cloudflare MCP server, and many other high-profile MCP servers are built on this SDK.

## Key Features
- Full MCP server implementation (tools, resources, prompts, sampling)
- Full MCP client implementation
- Transport support: stdio, SSE, Streamable HTTP
- Express and Hono middleware for embedding MCP into existing HTTP servers
- TypeScript-first with full type safety and Zod schema validation
- Support for Node.js, Bun, and Deno runtimes
- OAuth 2.1 authorization support for remote servers
- Proxy utilities for building MCP gateways

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | Official Anthropic SDK, v1.29.0, used by GitHub/Cloudflare/Microsoft |
| **Security** | 4 | OAuth 2.1 support, follows MCP security guidelines |
| **Scalability** | 4 | Stateless Streamable HTTP transport; Express/Hono integration for horizontal scaling |
| **Support/Community** | 5 | Official support, 12.1k stars, large TypeScript community |
| **Documentation** | 4 | Good official docs; TypeScript types serve as inline documentation |
| **Integration Ease** | 4 | More boilerplate than Python FastMCP; v2 expected to improve this |

## Use Cases
1. Building MCP servers in Node.js to expose TypeScript/JavaScript services to AI agents
2. Embedding MCP endpoints into existing Express or Hono HTTP servers
3. Creating MCP clients in TypeScript to orchestrate multi-server AI workflows
4. Building MCP proxies and gateways for enterprise deployments
5. Developing MCP servers for Cloudflare Workers and other edge runtimes

## Getting Started
```bash
npm install @modelcontextprotocol/sdk
# or
pnpm add @modelcontextprotocol/sdk
```

```typescript
import { McpServer } from "@modelcontextprotocol/sdk/server/mcp.js";
import { StdioServerTransport } from "@modelcontextprotocol/sdk/server/stdio.js";
import { z } from "zod";

const server = new McpServer({ name: "My Server", version: "1.0.0" });

server.tool("add", { a: z.number(), b: z.number() }, async ({ a, b }) => ({
  content: [{ type: "text", text: String(a + b) }],
}));

const transport = new StdioServerTransport();
await server.connect(transport);
```

## Architecture / How It Works
The SDK implements the MCP JSON-RPC 2.0 protocol using TypeScript classes. The `McpServer` class handles protocol negotiation and request routing; transport classes (`StdioServerTransport`, `SSEServerTransport`, `StreamableHTTPServerTransport`) handle the I/O layer. For Express/Hono, adapter middleware classes wrap the HTTP transports. Tool schemas are defined with Zod and automatically converted to JSON Schema for the MCP protocol messages.

## Strengths
- Official implementation guarantees protocol compliance
- Strong TypeScript typing catches schema errors at compile time
- Zod integration provides runtime validation and schema generation
- Express/Hono middleware enables embedding MCP into existing services
- Multi-runtime support (Node.js, Bun, Deno) for flexibility

## Limitations
- More verbose than Python FastMCP for simple use cases
- v2 breaking changes anticipated — production projects should pin versions
- SSE transport being deprecated in favor of Streamable HTTP
- Less convenient high-level API compared to Python's FastMCP (no decorator magic)

## Alternatives
| Tool | Key Difference |
|------|---------------|
| MCP Python SDK | Official SDK for Python; includes FastMCP high-level API |
| mcp-framework (npm) | Community TypeScript framework with decorator-based API |
| Hono MCP middleware | Built on this SDK; specific to Hono framework |

## References
- [GitHub Repository](https://github.com/modelcontextprotocol/typescript-sdk)
- [NPM Package (@modelcontextprotocol/sdk)](https://www.npmjs.com/package/@modelcontextprotocol/sdk)
- [MCP Official Documentation](https://modelcontextprotocol.io/docs)
- [MCP Protocol Specification](https://spec.modelcontextprotocol.io)

## Notes
The package is published as `@modelcontextprotocol/sdk` on npm. License is listed as Apache-2.0 for new code with MIT for existing code. Watch for v2 release announcements as it may require migration work. Many popular MCP servers (GitHub, Cloudflare, Notion) are built on this SDK and serve as good reference implementations.
