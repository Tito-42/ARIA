# GPT Researcher

> Autonomous multi-agent research system generating comprehensive reports from 20+ sources

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 15_domain_specific / business-automation |
| **URL** | https://gptr.dev |
| **GitHub** | https://github.com/assafelovic/gpt-researcher |
| **Stars** | >10,000 |
| **License** | Apache 2.0 |
| **Pricing** | Free / Open Source (cloud hosted at gptr.dev) |
| **Last Verified** | 2026-04-02 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
GPT Researcher is an autonomous multi-agent system that conducts comprehensive research on any topic by autonomously searching the web, collecting information from 20+ sources, synthesizing findings, and generating detailed research reports with citations. It transforms a single research question into a 2,000+ word report in minutes, a process that would take a human researcher several hours.

The system's multi-agent architecture mirrors how a research team works: a planner agent breaks the research question into specific sub-questions, specialized scraper agents collect and validate information from multiple sources simultaneously, and an editor agent synthesizes the findings into a coherent, well-structured report with citations. JavaScript-enabled scraping handles modern dynamic web content that simple scrapers miss.

GPT Researcher supports custom local documents as knowledge bases alongside web research, enabling hybrid research that combines proprietary internal knowledge with current web intelligence. The Apache 2.0 license enables commercial research automation applications.

## Key Features
- Multi-agent research: planner, executor, and publisher agents work autonomously
- 20+ source aggregation per research task
- JavaScript-enabled scraping for dynamic web content
- Generates reports >2,000 words with citations
- Hybrid research: web sources + local documents/PDFs
- Multiple report types: research report, resource report, outline, detailed report
- Multi-LLM support: OpenAI, Gemini, Groq, Claude, and OpenAI-compatible APIs
- Tavily, SerpAPI, Bing, Google, DuckDuckGo search integrations
- Python API and REST API
- Human feedback loop for research refinement

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Apache 2.0; active maintenance; >10k stars; production deployments |
| **Security** | 3 | Web scraping sends URLs externally; local document mode avoids cloud |
| **Scalability** | 4 | Async multi-agent; handles concurrent research tasks |
| **Support/Community** | 4 | Active GitHub; hosted cloud option; Discord community |
| **Documentation** | 4 | Good docs; tutorial notebooks; API reference |
| **Integration Ease** | 4 | Python API; REST API; FastAPI server; LangGraph integration |

## What It Automates
GPT Researcher automates **85%** of research and report generation workflows. Competitive analysis, market research, technical deep-dives, and literature reviews that previously required hours of manual searching, reading, and synthesizing are completed in minutes. The remaining 15% involves analysis requiring human expert judgment, proprietary data access, or nuanced interpretation that AI cannot yet reliably provide.

## Use Cases
1. **Competitive intelligence automation**: Running nightly research jobs on competitors (funding, product updates, executive changes, news) to generate weekly briefings for leadership
2. **Market research reports**: Automating the initial research phase of market analysis, generating a structured report with current market size data, key players, and recent trends
3. **Technical due diligence**: Researching technical aspects of acquisition targets or technology partners by aggregating information from documentation, GitHub, and technical articles
4. **Content marketing research**: Generating thoroughly researched article drafts with citations for marketing teams to review and refine

## Getting Started
```bash
pip install gpt-researcher

# Set API keys
export OPENAI_API_KEY=your_key
export TAVILY_API_KEY=your_key

# Python usage
from gpt_researcher import GPTResearcher
import asyncio

async def get_report():
    researcher = GPTResearcher(
        query="What are the key trends in AI agent frameworks in 2026?",
        report_type="research_report"
    )
    await researcher.conduct_research()
    report = await researcher.write_report()
    return report

report = asyncio.run(get_report())
print(report)
```

## Architecture / How It Works
GPT Researcher implements a multi-agent research loop: (1) A Planner Agent receives the research question and generates 5-10 targeted sub-questions; (2) For each sub-question, a Researcher Agent runs web searches, scrapes results with JavaScript rendering, and evaluates source quality and relevance; (3) The collected information is stored with citations; (4) A Writer Agent synthesizes all gathered information into a structured report following the specified format (research report, resource report, etc.). The entire process runs asynchronously with agents working in parallel where possible. Local document support adds PDF/file content to the research pool before web searching begins.

## Strengths
- Apache 2.0 enables commercial automation products built on top
- Multi-agent parallelism reduces research time significantly vs sequential approaches
- Citation tracking ensures all claims in the report are sourced
- Hybrid local + web research covers proprietary and public knowledge simultaneously
- Active development with LangGraph integration for complex research workflows

## Limitations
- Web search costs (Tavily, SerpAPI) accumulate in production at scale
- Research quality depends on web source quality; may include unreliable sources
- Reports require human review before being business-critical deliverables
- Does not access paywalled academic journals or proprietary databases
- May produce hallucinated connections between real sources in synthesis

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Perplexity AI | Commercial; better polish; not customizable |
| Tavily Researcher | Simpler; single-agent; GPT Researcher uses Tavily as a component |
| AgentSearch | Alternative search-augmented research; different architecture |
| LangGraph + custom | More flexible but requires building the research logic from scratch |

## References
- https://gptr.dev
- https://github.com/assafelovic/gpt-researcher
- https://docs.gptr.dev/
- Asaf Elovic blog: https://medium.com/@assafelovic

## Notes
GPT Researcher is the production-ready reference implementation for automated research workflows. For business use, always plan for a human review step — treat the output as an excellent first draft requiring expert review, not a final deliverable. The multi-LLM support is useful for cost optimization: use Gemini Flash or Groq for the search/collection agents and GPT-4o or Claude for the final synthesis agent to balance cost and quality.
