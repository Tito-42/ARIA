# Atlassian MCP (mcp-atlassian)

> Community MCP server for Jira and Confluence — the most complete Atlassian integration for AI agents

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 03 - MCP |
| **URL** | https://github.com/sooperset/mcp-atlassian |
| **GitHub** | https://github.com/sooperset/mcp-atlassian |
| **Stars** | 4,800 |
| **License** | MIT |
| **Pricing** | Free / Open Source (requires Atlassian account) |
| **Last Verified** | 2026-04-02 |
| **Status** | Active |
| **Maturity** | Beta |

## What It Does
mcp-atlassian is the leading community MCP server for Atlassian products, providing comprehensive access to both Jira (issue tracking) and Confluence (wiki/documentation) through a single MCP server. With 72 tools and support for both Atlassian Cloud and Server/Data Center deployments, it is the most complete Atlassian integration available for AI assistants.

Given that Jira is the de facto standard for enterprise project management and issue tracking, and Confluence is the standard enterprise wiki platform, this server is highly relevant for enterprise AI workflows — enabling agents to query sprint status, create tickets, update issue workflows, and search documentation through natural language.

Version 0.21.0 was released on March 2, 2026, showing active maintenance. With 4,800 stars, it has earned community trust as the primary Atlassian MCP solution.

## Key Features
- **Jira tools (40+)**: Create, update, search, transition issues; manage sprints; JQL queries; attachments
- **Confluence tools (30+)**: Create, update, search pages; manage spaces; retrieve content
- Support for Atlassian Cloud and Server/Data Center (self-hosted)
- Authentication: API token (Cloud), Personal Access Token (Server/DC), OAuth 2.0 (Cloud)
- Read-only mode for safe, risk-free deployments
- Filtering: include/exclude specific Jira projects or Confluence spaces
- Resource support: access pages/issues as MCP resources (not just tools)
- Docker image for containerized deployment

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 3 | v0.21.0, community-maintained; functionally stable but not enterprise-SLA backed |
| **Security** | 4 | API token auth; read-only mode available; MIT license; supports Server/DC for air-gapped environments |
| **Scalability** | 3 | Stdio process; scales via multiple instances; limited concurrent client support |
| **Support/Community** | 4 | 4.8k stars, active issue tracker, community PRs |
| **Documentation** | 4 | Comprehensive README with auth setup, filtering, and Docker deployment |
| **Integration Ease** | 4 | `uvx mcp-atlassian` with env vars; well-documented configuration |

## Use Cases
1. Sprint planning assistance: query current sprint issues, summarize blockers, suggest priorities
2. Automated issue triage: create Jira tickets from bug reports, apply labels, assign to team members
3. Documentation search: query Confluence for runbooks, architecture docs, and procedures during incidents
4. Release notes generation: summarize completed issues from a sprint or release
5. Cross-tool workflow: link Jira issues to GitHub PRs and Confluence pages via AI orchestration
6. Standup preparation: pull yesterday's closed issues and in-progress tickets per team member

## Getting Started
```bash
# Install via uvx (recommended)
uvx mcp-atlassian

# Claude Desktop config (Atlassian Cloud):
{
  "mcpServers": {
    "atlassian": {
      "command": "uvx",
      "args": ["mcp-atlassian"],
      "env": {
        "JIRA_URL": "https://your-org.atlassian.net",
        "JIRA_USERNAME": "user@company.com",
        "JIRA_API_TOKEN": "your_api_token",
        "CONFLUENCE_URL": "https://your-org.atlassian.net/wiki",
        "CONFLUENCE_USERNAME": "user@company.com",
        "CONFLUENCE_API_TOKEN": "your_api_token"
      }
    }
  }
}

# Read-only mode (safer for production)
{
  "args": ["mcp-atlassian", "--read-only"]
}
```

## Architecture / How It Works
mcp-atlassian is a Python FastMCP server that wraps the Atlassian Python REST client library. It authenticates against the Jira and Confluence REST APIs using the provided credentials. Tool definitions are generated from the REST API surface, with JQL (Jira Query Language) exposed directly for advanced queries. The server maintains a single connection to each Atlassian instance and handles API pagination, rate limiting, and error normalization internally.

## Strengths
- Most complete Atlassian integration: 72 tools covering both Jira and Confluence
- Supports both Cloud and self-hosted (Server/Data Center) deployments
- Read-only mode is safe for production: prevents accidental writes
- MIT license with no usage restrictions
- Active community with frequent feature additions

## Limitations
- Community-maintained — no official Atlassian support
- v0.x versioning reflects pre-stability status; breaking changes possible
- API token authentication exposes credentials via environment variables
- Self-hosted Server/DC requires network access to the Atlassian instance
- Large numbers of Jira projects/issues may cause slow initial tool listing

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Linear MCP | Linear issue tracker (not Atlassian); cleaner API but less enterprise adoption |
| GitHub Issues MCP | GitHub Issues via github-mcp-server; Jira alternative for GitHub-centric teams |
| Notion MCP | Notion workspace management; knowledge base alternative to Confluence |

## References
- [GitHub Repository](https://github.com/sooperset/mcp-atlassian)
- [PyPI Package (mcp-atlassian)](https://pypi.org/project/mcp-atlassian/)
- [Atlassian REST API Documentation](https://developer.atlassian.com/cloud/jira/platform/rest/v3/)
- [Confluence REST API Documentation](https://developer.atlassian.com/cloud/confluence/rest/v2/)

## Notes
For enterprises running Atlassian Data Center (self-hosted), this server provides the same functionality as the cloud version — a key advantage over some alternatives that only support Atlassian Cloud. The server can be configured to expose only specific Jira projects or Confluence spaces, which is useful for large enterprises with many projects/spaces to reduce context noise for the AI.
