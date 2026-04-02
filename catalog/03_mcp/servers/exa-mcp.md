# Exa MCP Server

> Official Exa MCP server for AI-native web search, code search, and page crawling

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 03 - MCP |
| **URL** | https://github.com/exa-labs/exa-mcp-server |
| **GitHub** | https://github.com/exa-labs/exa-mcp-server |
| **Stars** | 4,100 |
| **License** | {TODO} - check repo LICENSE file |
| **Pricing** | Freemium — free tier available; paid plans for higher volume |
| **Last Verified** | 2026-04-02 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
The Exa MCP Server is the official MCP interface for Exa, a search engine built specifically for AI applications. Unlike traditional search engines optimized for human browsing, Exa uses neural semantic search to find conceptually relevant content and returns it in structured, LLM-ready formats — making it ideal for use in AI agent pipelines.

With 4,100 stars and 304 commits, the server is actively maintained and widely deployed. It exposes three default tools (web search, research paper search, and page crawling) plus an advanced combined tool, and is also available as a hosted remote endpoint at `mcp.exa.ai/mcp` — eliminating the need for local installation.

Exa differentiates itself from standard search APIs by offering semantic search (not just keyword matching), specialized academic/research paper search, and company/LinkedIn data endpoints — making it particularly valuable for knowledge-intensive AI workflows.

## Key Features
- **web_search**: Semantic neural search across the web with content extraction
- **research_paper_search**: Specialized search for academic papers (ArXiv, PubMed, etc.)
- **get_contents**: Direct URL content extraction and crawling
- **advanced_search**: Combined tool with date filtering, domain restrictions, and result count controls
- Hosted remote endpoint at `mcp.exa.ai/mcp` (no local install)
- Company and LinkedIn data search capabilities
- Date-range filtering for recency control
- Domain inclusion/exclusion for focused searches
- Content extraction with configurable detail levels

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Official Exa, 4.1k stars, hosted endpoint, 304 commits |
| **Security** | 3 | API key authentication; hosted endpoint managed by Exa |
| **Scalability** | 4 | Hosted endpoint scales with Exa's infrastructure |
| **Support/Community** | 4 | Official Exa support, active community, Exa Discord |
| **Documentation** | 4 | Good README, tool descriptions, Exa API docs |
| **Integration Ease** | 5 | Hosted endpoint: just add URL + API key; no local install needed |

## Use Cases
1. Research agents: semantic web search to find conceptually related content beyond keyword matches
2. Academic research assistance: search scholarly papers and extract key findings
3. Competitive intelligence: search for recent company news and product information
4. Content discovery: find relevant articles for RAG pipeline ingestion
5. Fact verification: search for current information to ground LLM responses
6. Technical research: find relevant GitHub repos, documentation, and tutorials

## Getting Started
```bash
# Option 1: Hosted remote endpoint (no install)
{
  "mcpServers": {
    "exa": {
      "url": "https://mcp.exa.ai/mcp",
      "authorization_token": "your_exa_api_key"
    }
  }
}

# Option 2: Local via npx
{
  "mcpServers": {
    "exa": {
      "command": "npx",
      "args": ["exa-mcp-server"],
      "env": {
        "EXA_API_KEY": "your_exa_api_key"
      }
    }
  }
}
```

## Architecture / How It Works
The Exa MCP Server is a TypeScript package built on the MCP TypeScript SDK that wraps the Exa REST API. Tool calls translate directly to Exa API requests using the `exa-js` client library. The server handles API authentication, parameter mapping, and response formatting to return clean text content suitable for LLM consumption. The hosted endpoint at `mcp.exa.ai/mcp` runs this server on Exa's infrastructure with Streamable HTTP transport.

## Strengths
- Neural semantic search finds conceptually relevant content, not just keyword matches
- Specialized academic/research paper search beyond general web search
- Hosted endpoint eliminates local installation and maintenance overhead
- Content extraction included — search + retrieve in one tool call
- Actively maintained by the Exa team with regular improvements

## Limitations
- Requires an Exa API key (free tier has rate limits)
- Exa's index may not cover all web content equally (biased toward English/tech content)
- Limited control over result ranking and personalization vs. traditional search APIs
- Company/LinkedIn data endpoints depend on Exa's data refresh frequency
- Free tier may be insufficient for high-volume production use

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Tavily MCP | Similar AI-focused search; also offers extract + search in one; more generous free tier |
| Firecrawl MCP | Broader web scraping/crawling; deep research mode; self-hosting option |
| Brave Search MCP (archived) | Privacy-focused; keyword-based; official server archived |

## References
- [GitHub Repository](https://github.com/exa-labs/exa-mcp-server)
- [Exa API Documentation](https://docs.exa.ai)
- [Hosted MCP Endpoint](https://mcp.exa.ai/mcp)
- [Exa Search API Reference](https://docs.exa.ai/reference/search)

## Notes
Exa's key differentiator is semantic search — the ability to find pages that are conceptually similar to a query, not just pages containing the exact keywords. This makes it particularly effective for research agents that need to explore a topic broadly. The hosted endpoint at `mcp.exa.ai/mcp` is the simplest integration path. Compare with Tavily MCP for similar functionality; Exa tends to excel at semantic/academic search while Tavily is stronger for news/real-time content.
