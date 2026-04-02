# Grafana MCP Server

> Official Grafana MCP server for dashboards, datasources, alerts, and incident management via AI

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 03 - MCP |
| **URL** | https://github.com/grafana/mcp-grafana |
| **GitHub** | https://github.com/grafana/mcp-grafana |
| **Stars** | 2,700 |
| **License** | {TODO} - check repo LICENSE file |
| **Pricing** | Free / Open Source (requires Grafana instance) |
| **Last Verified** | 2026-04-02 |
| **Status** | Active |
| **Maturity** | Beta |

## What It Does
The Grafana MCP Server is the official MCP integration published by Grafana Labs, enabling AI assistants to interact with Grafana's observability platform through natural language. It provides access to dashboards, datasources (Prometheus, Loki, ClickHouse, CloudWatch, and more), alerting, incident management, and the Grafana OnCall on-call scheduling system.

With 2,700 stars and 510 commits, it is one of the most active monitoring-focused MCP servers. It supports Grafana 9.0+ and is compatible with both Grafana Cloud and self-hosted Grafana instances. The server enables powerful AI-assisted incident response workflows: an AI agent can query metrics, analyze logs, correlate with alerts, and even acknowledge incidents — all through a single MCP interface.

The server is written in Go, reflecting Grafana's core implementation language, and is distributed as a binary or container image.

## Key Features
- Dashboard search and panel query execution
- Datasource listing and direct query execution (Prometheus PromQL, LogQL, SQL)
- Alert rule management: list, query, and acknowledge alerts
- Incident management: create, update, and resolve Grafana Incident incidents
- Grafana OnCall: manage on-call schedules, shifts, and escalations
- Support for Grafana 9.0+ (Cloud and self-hosted)
- Go binary distribution (no Node.js/Python runtime required)
- Service account or API key authentication

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 3 | Official Grafana Labs, 510 commits, but still beta maturity |
| **Security** | 4 | Service account tokens; Grafana RBAC applies; read operations are safe |
| **Scalability** | 4 | Go binary with low resource footprint; connects to Grafana's APIs |
| **Support/Community** | 4 | Official Grafana Labs, 2.7k stars, Grafana community forums |
| **Documentation** | 3 | Good README; relies on Grafana docs for context |
| **Integration Ease** | 4 | Binary download or Docker; requires Grafana service account setup |

## Use Cases
1. Incident investigation: query Prometheus metrics and Loki logs via AI to diagnose production issues
2. Dashboard exploration: natural language queries over Grafana dashboards for non-technical stakeholders
3. Alert triage: AI agent acknowledges and categorizes incoming alerts, creates incident tickets
4. Capacity planning: query historical metrics and generate trend reports via AI
5. On-call automation: query OnCall schedules to determine current on-call engineer and notify them
6. Post-incident analysis: correlate metrics, logs, and alert timelines for incident post-mortems

## Getting Started
```bash
# Download the binary (Linux example)
curl -L https://github.com/grafana/mcp-grafana/releases/latest/download/mcp-grafana-linux-amd64 \
  -o mcp-grafana && chmod +x mcp-grafana

# Claude Desktop config:
{
  "mcpServers": {
    "grafana": {
      "command": "/path/to/mcp-grafana",
      "env": {
        "GRAFANA_URL": "http://localhost:3000",
        "GRAFANA_API_KEY": "your_service_account_token"
      }
    }
  }
}

# Docker alternative
docker run -i --rm \
  -e GRAFANA_URL=http://grafana:3000 \
  -e GRAFANA_API_KEY=your_token \
  grafana/mcp-grafana
```

## Architecture / How It Works
The Grafana MCP Server is a Go binary that implements the MCP stdio protocol. It wraps Grafana's HTTP REST API and direct datasource query APIs. Authentication uses a Grafana service account token, which inherits Grafana RBAC permissions — so the server can only access resources the service account has permission to view or modify. For direct datasource queries, it uses Grafana's `/api/ds/query` endpoint which proxies queries to the underlying datasource (Prometheus, Loki, etc.).

## Strengths
- Official Grafana Labs product with enterprise backing
- Covers the full observability stack: metrics, logs, dashboards, alerts, incidents
- Go binary is lightweight and fast with no runtime dependencies
- Grafana RBAC integration provides fine-grained access control
- Incident management integration enables full AI-assisted on-call workflows

## Limitations
- Beta maturity — API surface may change between releases
- Requires Grafana 9.0+ (older versions not supported)
- Direct datasource queries depend on Grafana's proxy endpoint (not all datasource features exposed)
- No built-in caching — each tool call hits the Grafana API
- Binary distribution means platform-specific downloads needed

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Prometheus MCP (community) | Direct Prometheus API access without Grafana layer |
| Datadog MCP (community) | Datadog monitoring platform; different tooling ecosystem |
| AWS CloudWatch MCP | CloudWatch via AWS MCP servers; AWS-native monitoring |

## References
- [GitHub Repository](https://github.com/grafana/mcp-grafana)
- [Grafana Documentation](https://grafana.com/docs/)
- [Grafana Service Accounts](https://grafana.com/docs/grafana/latest/administration/service-accounts/)
- [Grafana Incident Documentation](https://grafana.com/docs/grafana-cloud/alerting-and-irm/incident/)

## Notes
For incident response automation, the combination of Grafana MCP + GitHub MCP + Atlassian MCP creates a powerful AI-orchestrated incident workflow: Grafana detects the alert, GitHub provides code context (recent commits, PRs), and Jira/Confluence provides runbooks and creates tickets. This multi-server pattern is a key use case for enterprise MCP adoption. Ensure the service account token is scoped to the minimum necessary permissions for security.
