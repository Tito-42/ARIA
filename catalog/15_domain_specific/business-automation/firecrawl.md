# Firecrawl

> Web data extraction API converting any URL into LLM-ready structured Markdown, HTML, or JSON

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 15_domain_specific / business-automation |
| **URL** | https://firecrawl.dev |
| **GitHub** | https://github.com/mendableai/firecrawl |
| **Stars** | ~103,000 |
| **License** | Open source (AGPL-3.0) |
| **Pricing** | Free (self-hosted) / Freemium cloud API (mendable.ai) |
| **Last Verified** | 2026-04-02 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Firecrawl is a web scraping and data extraction API specifically engineered for LLM pipelines. Unlike general web scrapers that return raw HTML requiring extensive cleaning, Firecrawl converts any URL directly into clean Markdown, structured HTML, or typed JSON that LLMs can process immediately. It handles JavaScript rendering, anti-bot mechanisms, proxy rotation, and content cleaning so that AI applications can focus on logic rather than web scraping infrastructure.

The API provides several extraction modes: single-page scraping, full site crawling, natural language search across the web, interactive page manipulation via AI prompts (click, fill, navigate), and an agent mode that collects data from multiple pages based on a plain description of what you need. A companion Spark AI model (Spark-1-mini and Spark-1-pro) is optimized for web data structuring tasks.

With 103,000 stars and 5,186+ commits, Firecrawl is the dominant open-source tool for web data acquisition in LLM pipelines. It installs as a Claude Code skill and has native MCP server support, making it directly accessible within AI agent workflows.

## Key Features
- Scrape: convert any URL to clean Markdown/HTML/JSON in one API call
- Crawl: recursively crawl an entire website and return all pages
- Search: Google-scale web search returning LLM-ready content
- Map: discover all URLs within a domain
- Interact: AI-driven browser interaction (fill forms, click buttons, navigate)
- Agent: describe what to collect in plain language; agent handles multi-page gathering
- Batch Scrape: parallel processing of URL lists
- Spark-1 AI models optimized for web data structuring
- Claude Code skill and MCP server available
- JavaScript rendering with headless browser

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | 103k stars; 5186+ commits; production cloud API; widely adopted |
| **Security** | 3 | Cloud API processes URLs; self-host for sensitive scraping |
| **Scalability** | 5 | Cloud API handles millions of pages; batch scraping; async crawl |
| **Support/Community** | 5 | Mendable.ai backing; 103k community; official SDKs |
| **Documentation** | 5 | Comprehensive API docs; SDKs for Python, JS, Go; Claude Code guide |
| **Integration Ease** | 5 | One-line install; official Python/JS SDKs; MCP native; Claude Code skill |

## What It Automates
Firecrawl automates **90%** of web data acquisition workflows. Web scraping that previously required custom scrapers, proxy management, JavaScript rendering infrastructure, and data cleaning pipelines is reduced to a single API call. The remaining 10% consists of sites with aggressive anti-scraping, login-gated content, or CAPTCHA-protected pages.

## Use Cases
1. **RAG knowledge base building**: Crawling company documentation, competitor websites, or industry resources to populate vector databases for AI applications
2. **Competitive intelligence automation**: Scheduling periodic crawls of competitor pricing, product pages, and job postings to track market changes
3. **AI research workflows**: Enabling GPT Researcher and similar multi-source research agents to gather real-time web data reliably
4. **Data enrichment pipelines**: Extracting structured company data, contact information, or product specifications from websites at scale

## Getting Started
```bash
pip install firecrawl-py

# or install as Claude Code skill
claude install firecrawl

from firecrawl import FirecrawlApp

app = FirecrawlApp(api_key="fc-your_api_key")

# Single page scrape
result = app.scrape_url(
    'https://example.com',
    formats=['markdown', 'html']
)
print(result['markdown'])

# Crawl entire site
crawl_result = app.crawl_url(
    'https://docs.example.com',
    limit=100
)

# Extract structured data with schema
structured = app.scrape_url(
    'https://shop.example.com/product/123',
    formats=['json'],
    json_options={
        'schema': {
            'name': 'string',
            'price': 'number',
            'in_stock': 'boolean'
        }
    }
)
```

## Architecture / How It Works
Firecrawl operates as a managed scraping infrastructure: requests are routed through distributed scrapers with rotating proxies and headless browser pools (Playwright-based) that handle JavaScript rendering. The content pipeline applies ML-based boilerplate removal to strip navigation, ads, and footer content, leaving only meaningful page content. Clean content is then formatted as Markdown (preserving structure), HTML, or extracted as typed JSON using the Spark AI model for schema-based extraction. The MCP server exposes all endpoints as typed MCP functions callable by AI agents.

## Strengths
- 103k stars makes it the validated standard for web data in LLM pipelines
- Eliminates the entire web scraping infrastructure problem in one API call
- MCP native integration enables direct use within Claude agent workflows
- Handles JavaScript SPAs that traditional scrapers cannot parse
- Cloud and self-hosted options accommodate different data governance requirements

## Limitations
- AGPL-3.0 for self-hosted; cloud API requires Mendable.ai pricing review
- Some sites with aggressive anti-scraping (Cloudflare Enterprise) may still block
- Login-gated content requires authentication handling (Interact mode helps but is complex)
- Cloud API costs can accumulate for high-volume production workloads
- Crawl depth and page limits require careful configuration to avoid runaway crawls

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Scrapy | Python framework; more control but requires custom code for each site |
| BeautifulSoup + Requests | Lightweight; no JavaScript; no AI cleaning |
| Playwright / Selenium | Browser automation; no content processing |
| Jina Reader (r.jina.ai) | Simpler single-page; less capable than Firecrawl for structured extraction |

## References
- https://firecrawl.dev
- https://github.com/mendableai/firecrawl
- https://docs.firecrawl.dev/
- https://docs.firecrawl.dev/integrations/claude (Claude Code skill guide)

## Notes
Firecrawl should be the default choice for any AI application that needs to ingest web data. Its combination of JavaScript rendering, content cleaning, and structured extraction eliminates weeks of web scraping engineering. For self-hosting in GDPR-compliant environments, deploy the open-source version to keep all web request data within your infrastructure. The MCP integration makes it immediately useful within Claude-based agent workflows without any custom integration code.
