# Cloudflare MCP Server

> Official Cloudflare suite of 16 MCP servers for Workers, KV, R2, D1, security, and AI services

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 03 - MCP |
| **URL** | https://github.com/cloudflare/mcp-server-cloudflare |
| **GitHub** | https://github.com/cloudflare/mcp-server-cloudflare |
| **Stars** | 3,600 |
| **License** | Apache-2.0 |
| **Pricing** | Free / Open Source (Cloudflare service costs apply separately) |
| **Last Verified** | 2026-04-02 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
The Cloudflare MCP Server is the official collection of 16 specialized MCP servers published by Cloudflare, covering the full breadth of Cloudflare's platform — from serverless compute (Workers) and storage (KV, R2, D1) to security (CASB, Zero Trust), analytics (Radar), and AI services (AI Gateway, AutoRAG).

Released with high frequency (314 releases, with `@repo/mcp-common@0.20.4` on March 31, 2026), this suite demonstrates Cloudflare's strong commitment to MCP as an integration standard. It enables developers to deploy Workers, manage storage, configure security policies, and monitor traffic — all through natural language prompts in AI assistants.

The Cloudflare platform is particularly relevant to the MCP ecosystem because Cloudflare itself provides a managed MCP hosting infrastructure (via Cloudflare Workers), making this server both a tool for managing Cloudflare and a showcase of MCP-on-Cloudflare capabilities.

## Key Features
- **Workers**: Deploy, invoke, manage Cloudflare Workers scripts
- **KV**: Manage Workers KV namespaces and key-value pairs
- **R2**: Manage object storage buckets and objects
- **D1**: Manage SQLite-compatible D1 serverless databases
- **Observability**: Access Workers analytics and logs
- **CASB (Security)**: Cloud Access Security Broker configuration
- **Radar**: Global internet traffic analytics and threat data
- **AI Gateway**: Manage AI model routing and caching policies
- **AutoRAG**: Configure retrieval-augmented generation pipelines
- Individual server packages for focused deployments

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | Official Cloudflare, 314 releases, updated March 31 2026 |
| **Security** | 4 | Apache-2.0, Cloudflare API token scoping, CASB integration |
| **Scalability** | 5 | Cloudflare's global edge infrastructure; Workers-based hosting possible |
| **Support/Community** | 4 | Official Cloudflare support, active community, Cloudflare Discord |
| **Documentation** | 4 | Per-server READMEs, Cloudflare developer docs |
| **Integration Ease** | 4 | Per-server npm packages; requires Cloudflare API token |

## Use Cases
1. Deploying and updating Cloudflare Workers scripts via AI coding assistant
2. Managing R2 buckets and D1 database schemas during development
3. Monitoring KV namespaces and debugging caching issues
4. Querying Cloudflare Radar for threat intelligence and traffic insights
5. Configuring AI Gateway routing policies for multi-model LLM applications
6. Setting up AutoRAG pipelines for document-grounded AI assistants

## Getting Started
```bash
# Install a specific server (example: Workers)
npm install @cloudflare/mcp-server-cloudflare-workers

# Claude Desktop config:
{
  "mcpServers": {
    "cloudflare-workers": {
      "command": "npx",
      "args": ["@cloudflare/mcp-server-cloudflare-workers"],
      "env": {
        "CLOUDFLARE_API_TOKEN": "your_api_token",
        "CLOUDFLARE_ACCOUNT_ID": "your_account_id"
      }
    }
  }
}

# Or use the unified package
npx @cloudflare/mcp-server-cloudflare
```

## Architecture / How It Works
Each Cloudflare MCP server is a TypeScript package built on the official MCP TypeScript SDK. They communicate with the Cloudflare REST API using a Cloudflare API token for authentication. The mono-repo structure at `cloudflare/mcp-server-cloudflare` uses a shared `@repo/mcp-common` package for authentication handling, error normalization, and common utilities. Each sub-server is published independently to npm as `@cloudflare/mcp-server-cloudflare-*`.

## Strengths
- Official Cloudflare maintenance with 314 releases — extremely active
- Full platform coverage: compute, storage, security, analytics, AI
- Apache-2.0 license suitable for any enterprise use
- Fine-grained API token scoping aligns with least-privilege principles
- Cloudflare's edge infrastructure available as a hosting platform for MCP servers

## Limitations
- Requires a Cloudflare account and API token
- 16 servers to manage — no unified "all Cloudflare" meta-server
- Each server must be configured separately in Claude Desktop
- TypeScript/Node.js only — no Python equivalent
- Cloudflare API rate limits apply (vary by plan)

## Alternatives
| Tool | Key Difference |
|------|---------------|
| AWS MCP Servers | Amazon Web Services equivalent; stdio-only |
| Terraform MCP | Multi-cloud IaC; covers Cloudflare as a provider |
| Pulumi MCP | Multi-cloud IaC alternative with Cloudflare provider |

## References
- [GitHub Repository](https://github.com/cloudflare/mcp-server-cloudflare)
- [Cloudflare Developer Documentation](https://developers.cloudflare.com)
- [Cloudflare MCP Blog Post](https://blog.cloudflare.com/mcp)
- [NPM Packages](https://www.npmjs.com/search?q=%40cloudflare%2Fmcp-server)

## Notes
Cloudflare is both a consumer and enabler of MCP: the platform can host MCP servers on Workers (competing with or complementing AWS Lambda for serverless MCP deployments). The AI Gateway and AutoRAG servers are particularly relevant for organizations building production AI applications on Cloudflare's infrastructure. Watch for the Cloudflare Workers AI MCP server as the AI service offerings expand.
