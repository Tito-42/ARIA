# Firecrawl MCP Server

> Official Firecrawl MCP server for AI-optimized web scraping, crawling, and data extraction

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 03 - MCP |
| **URL** | https://github.com/mendableai/firecrawl-mcp-server |
| **GitHub** | https://github.com/mendableai/firecrawl-mcp-server |
| **Stars** | 5,900 |
| **License** | {TODO} - check repo LICENSE file |
| **Pricing** | Freemium — free tier available; paid plans for higher rate limits |
| **Last Verified** | 2026-04-02 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
The Firecrawl MCP Server is the official MCP interface for Firecrawl, a web scraping and crawling service specifically designed to produce LLM-ready output. Unlike general-purpose scrapers, Firecrawl converts web pages into clean Markdown, handles JavaScript-rendered content, respects robots.txt, and provides structured data extraction — all optimized for consumption by language models.

With 5,900 stars and 255 commits, it is one of the most popular single-purpose MCP servers. The server exposes 6 specialized tools covering the full range of web data acquisition: single-page scraping, batch processing, site mapping, web search, an AI-powered research agent, and interactive browser automation. It is the recommended MCP tool for web scraping use cases in the Claude/Anthropic ecosystem.

Firecrawl can be used in two modes: via the hosted Firecrawl API (requires an API key) or with a self-hosted Firecrawl instance for data privacy requirements.

## Key Features
- **firecrawl_scrape**: Extract content from a single URL as clean Markdown
- **firecrawl_crawl**: Recursively crawl an entire website with depth/page controls
- **firecrawl_batch_scrape**: Scrape multiple URLs in parallel efficiently
- **firecrawl_map**: Get a complete sitemap/URL list of a website
- **firecrawl_search**: Web search with content extraction from results
- **firecrawl_deep_research**: AI research agent combining search, crawling, and synthesis
- JavaScript rendering support (handles SPAs and dynamic content)
- Structured data extraction with custom schemas
- Screenshot capture support
- Self-hosted deployment option for data privacy

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Official Mendable/Firecrawl, 5.9k stars, actively maintained |
| **Security** | 3 | API key authentication; self-hosted option for sensitive data; output is read-only |
| **Scalability** | 4 | Hosted API scales automatically; rate limits vary by plan |
| **Support/Community** | 4 | Official Firecrawl support, active Discord, responsive team |
| **Documentation** | 4 | Good README with tool descriptions; Firecrawl docs cover all parameters |
| **Integration Ease** | 5 | `npx firecrawl-mcp` with a single env var for API key |

## Use Cases
1. Competitive intelligence: scrape and analyze competitor websites via AI
2. Documentation ingestion: crawl external docs sites to build RAG knowledge bases
3. Market research: batch-scrape multiple sources and synthesize findings
4. Lead generation: extract structured data from business directories
5. Content monitoring: periodically scrape pages for change detection
6. Research assistance: deep research mode combines multiple sources into comprehensive answers

## Getting Started
```bash
# Using npx
FIRECRAWL_API_KEY=your_key npx firecrawl-mcp

# Claude Desktop config:
{
  "mcpServers": {
    "firecrawl": {
      "command": "npx",
      "args": ["firecrawl-mcp"],
      "env": {
        "FIRECRAWL_API_KEY": "fc-your_api_key"
      }
    }
  }
}

# Self-hosted Firecrawl (optional)
{
  "env": {
    "FIRECRAWL_API_URL": "http://localhost:3002",
    "FIRECRAWL_API_KEY": "optional_if_local"
  }
}
```

## Architecture / How It Works
The Firecrawl MCP Server is a TypeScript package (built on the MCP TypeScript SDK) that wraps the Firecrawl REST API. Each MCP tool call translates to one or more Firecrawl API requests. For crawling operations, the server polls the Firecrawl async job endpoint until completion and returns the aggregated results. The `firecrawl_deep_research` tool orchestrates multiple API calls internally: search → extract URLs → scrape pages → synthesize with an AI model on Firecrawl's infrastructure.

## Strengths
- Purpose-built for LLM workflows: output is clean Markdown, not raw HTML
- Handles JavaScript-heavy sites that simple HTTP scrapers cannot
- 6 specialized tools for different data acquisition patterns
- Self-hosted option for air-gapped or privacy-sensitive environments
- Actively maintained by the Firecrawl team with regular improvements

## Limitations
- Requires a Firecrawl API key for the hosted version (not free for high-volume use)
- Rate limits on free tier (500 credits/month) constrain production use
- `firecrawl_deep_research` can be slow (30-120 seconds) for complex queries
- Scraping legally restricted sites (paywalls, terms-of-service violations) is user's responsibility
- Self-hosted deployment adds infrastructure complexity

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Exa MCP | AI-native search engine; search-focused rather than full scraping |
| Tavily MCP | Search + extract; simpler toolset; optimized for agent search |
| Playwright MCP | Browser automation for interactive scraping; local execution |
| Browserbase MCP | Cloud browser automation; interactive sessions |

## References
- [GitHub Repository](https://github.com/mendableai/firecrawl-mcp-server)
- [Firecrawl Documentation](https://docs.firecrawl.dev)
- [Firecrawl API Reference](https://docs.firecrawl.dev/api-reference)
- [Firecrawl Self-Hosting Guide](https://docs.firecrawl.dev/self-host/guide)

## Notes
Firecrawl positions itself as the "LangChain for web data" — a high-level abstraction that handles the messy details of web scraping. The free tier (500 credits/month) is sufficient for development and light use. For production workflows, evaluate the paid plans against the volume of scraping needed. The `firecrawl_deep_research` tool is notable as it provides a near-Perplexity-level research capability directly through an MCP tool.
