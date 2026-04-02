# GitHub MCP Server

> Official GitHub MCP server for repository management, issues, PRs, and CI/CD via natural language

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 03 - MCP |
| **URL** | https://github.com/github/github-mcp-server |
| **GitHub** | https://github.com/github/github-mcp-server |
| **Stars** | 28,500 |
| **License** | MIT |
| **Pricing** | Free / Open Source (requires GitHub account/token) |
| **Last Verified** | 2026-04-02 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
The GitHub MCP Server is the official MCP server published by GitHub (Microsoft) that provides comprehensive access to the GitHub platform through the Model Context Protocol. It enables AI agents to manage repositories, create and triage issues, review and merge pull requests, analyze code security, and interact with GitHub Actions workflows — all through natural language.

With 28,500 stars, it is the second most popular MCP server after Playwright MCP. It is available in two deployment modes: a hosted remote version accessible at `api.githubcopilot.com/mcp/` (no local installation needed), and a self-hosted Docker image for enterprise environments. The hosted version integrates natively with GitHub Copilot, making it the tool of choice for AI-assisted development workflows.

This server replaces the original GitHub MCP server that was previously part of `modelcontextprotocol/servers` but was archived in favor of this official standalone implementation.

## Key Features
- Repository management: create, fork, clone, search repositories
- Issue management: create, update, comment, label, assign, close issues
- Pull request workflow: create, review, merge, request changes on PRs
- Code search across GitHub (semantic and keyword)
- GitHub Actions: trigger workflows, check run status
- Security alerts and code scanning results access
- Notifications management
- Hosted mode: `api.githubcopilot.com/mcp/` (no local setup)
- Docker image for self-hosted enterprise deployment

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | Official GitHub product, hosted endpoint, used in Copilot |
| **Security** | 4 | GitHub token scoping limits permissions; hosted version managed by GitHub |
| **Scalability** | 5 | Hosted remote endpoint scales with GitHub's infrastructure |
| **Support/Community** | 5 | Official GitHub support, 28.5k stars |
| **Documentation** | 5 | Comprehensive README, GitHub documentation, Copilot integration docs |
| **Integration Ease** | 5 | Hosted version: just add URL to MCP config; no local install |

## Use Cases
1. AI-assisted code review: agents analyze PRs, suggest improvements, approve/request changes
2. Automated issue triage: classify, label, assign issues based on content analysis
3. Release management: draft changelogs from merged PRs, create releases
4. Codebase exploration: search across repos, understand project structure
5. CI/CD monitoring: check workflow status, re-trigger failed runs via natural language
6. Security triage: review and prioritize security alerts across repositories

## Getting Started
```bash
# Option 1: Hosted endpoint (recommended - no local install)
# Add to claude_desktop_config.json:
{
  "mcpServers": {
    "github": {
      "url": "https://api.githubcopilot.com/mcp/",
      "authorization_token": "YOUR_GITHUB_TOKEN"
    }
  }
}

# Option 2: Local Docker
docker run -i --rm \
  -e GITHUB_PERSONAL_ACCESS_TOKEN=YOUR_TOKEN \
  ghcr.io/github/github-mcp-server

# Option 3: stdio via npx
GITHUB_PERSONAL_ACCESS_TOKEN=YOUR_TOKEN \
  npx @github/mcp-server
```

## Architecture / How It Works
The GitHub MCP Server wraps the GitHub REST and GraphQL APIs as MCP tools. Each tool corresponds to one or more GitHub API calls (e.g., `create_issue` → `POST /repos/{owner}/{repo}/issues`). The server handles authentication via a GitHub Personal Access Token or OAuth App token, with the token's scopes determining which tools are available. The hosted version at `api.githubcopilot.com/mcp/` uses Copilot's OAuth flow for authentication. For self-hosted deployments, the Docker image accepts the token as an environment variable.

## Strengths
- Hosted remote endpoint eliminates local installation and maintenance
- Native GitHub Copilot integration enables use directly in VS Code/Copilot Chat
- Comprehensive coverage of GitHub API surface
- Official GitHub support and maintenance
- Token scoping provides fine-grained permission control

## Limitations
- Requires a GitHub Personal Access Token with appropriate scopes
- Rate limits apply based on GitHub API tier (5,000 req/hr for standard)
- No support for GitHub Enterprise Server without custom self-hosted deployment
- Some enterprise GitHub features may require GitHub Enterprise Cloud plan
- Read-heavy operations safe; write operations (push, merge) require careful prompt guardrails

## Alternatives
| Tool | Key Difference |
|------|---------------|
| GitLab MCP (community) | For GitLab repositories; community-maintained |
| Linear MCP | Issue tracking alternative to GitHub Issues |
| Atlassian MCP | Jira + Confluence; enterprise issue tracking |

## References
- [GitHub Repository](https://github.com/github/github-mcp-server)
- [Hosted Endpoint Documentation](https://github.com/github/github-mcp-server#hosted)
- [GitHub REST API Documentation](https://docs.github.com/en/rest)
- [GitHub MCP in Copilot Chat](https://docs.github.com/en/copilot/using-github-copilot/using-github-copilot-in-your-ide/using-github-copilot-in-the-command-line)

## Notes
The hosted endpoint (`api.githubcopilot.com/mcp/`) is the simplest integration path for most users. The server replaced the archived GitHub server from `modelcontextprotocol/servers` — if you find references to the old server, use this one instead. Token scopes to request: `repo`, `read:org`, `read:user`, `gist`, `workflow` depending on desired capabilities.
