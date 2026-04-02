# WrenAI

> Text-to-SQL GenBI agent for querying databases and generating business intelligence from natural language

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 15_domain_specific / business-automation |
| **URL** | https://getwren.ai |
| **GitHub** | https://github.com/Canner/WrenAI |
| **Stars** | ~14,800 |
| **License** | AGPL-3.0 |
| **Pricing** | Free (self-hosted) / Cloud available |
| **Last Verified** | 2026-04-02 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
WrenAI is a GenBI (Generative Business Intelligence) platform that enables business users to query their databases using plain English questions and receive accurate SQL queries, visualizations, and AI-generated insights. It solves the fundamental problem of text-to-SQL: naive LLM-to-SQL generation often produces incorrect queries because LLMs do not understand the business meaning of database tables and columns.

WrenAI's key innovation is its Modeling Definition Language (MDL) semantic layer, which allows data engineers to encode business meaning into the database schema: define what "revenue" means in your context, specify which joins are valid, declare reusable metrics, and document domain-specific terminology. When a business user asks "What was our revenue in Q1 by region?", the LLM receives not just the raw schema but the business-enriched semantic layer, dramatically improving SQL accuracy.

The platform supports 10+ LLMs and 8 major databases, making it deployable across diverse data infrastructure. With 14,800 stars, it is the most popular open-source text-to-SQL BI tool.

## Key Features
- Natural language to SQL with semantic layer for accuracy
- MDL (Modeling Definition Language) semantic layer for business context encoding
- Supports 10+ LLMs: OpenAI, Anthropic Claude, DeepSeek, Azure OpenAI, Groq, Gemini, Vertex AI, AWS Bedrock, Ollama
- 8+ database connectors: PostgreSQL, MySQL, BigQuery, Snowflake, DuckDB, Trino, ClickHouse, MSSQL
- AI-written insights in natural language explaining query results
- Automated chart/visualization generation
- Report generation with business narrative
- Conversation history and follow-up questions

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | 14.8k stars; production deployments; active maintenance |
| **Security** | 4 | AGPL self-hosted option; database credentials stay local; Ollama for air-gapped |
| **Scalability** | 4 | Semantic layer caching; handles complex multi-table queries |
| **Support/Community** | 4 | Canner Inc backing; 14.8k stars; enterprise support available |
| **Documentation** | 4 | Good docs; semantic layer guide; deployment instructions |
| **Integration Ease** | 4 | Docker deployment; 8+ database connectors; API for embedding |

## What It Automates
WrenAI automates **80%** of business intelligence query workflows. Ad-hoc data analysis that previously required a data analyst to write SQL and create charts is replaced by conversational queries any business user can perform. The remaining 20% involves highly complex analyses requiring custom SQL, statistical modeling, or data that requires contextual business knowledge beyond the semantic layer.

## Use Cases
1. **Self-service BI for non-technical users**: Enabling sales managers, marketing teams, and executives to query business data and generate reports without waiting for analyst support
2. **Embedded analytics**: Integrating WrenAI's API into a SaaS product to provide natural language analytics within the product UI
3. **Data democratization**: Reducing the bottleneck on data analyst teams by allowing business users to answer their own routine questions
4. **Executive dashboard generation**: Generating narrative reports combining KPI data with AI-written business context for leadership presentations

## Getting Started
```bash
# Docker deployment
git clone https://github.com/Canner/WrenAI
cd WrenAI
cp .env.example .env
# Configure database connections and LLM API key

docker-compose up -d
# Access at http://localhost:3000

# Example query via API
curl -X POST http://localhost:8080/api/v1/ask \
  -H "Content-Type: application/json" \
  -d '{
    "question": "What were the top 5 products by revenue last month?",
    "thread_id": "conversation-123"
  }'
```

## Architecture / How It Works
WrenAI uses a layered architecture: the UI (Next.js) accepts natural language questions, which are sent to the AI Service via Apollo GraphQL. The AI Service (FastAPI Python) retrieves the relevant MDL semantic layer context and constructs a prompt combining the business context with the user's question. The configured LLM generates SQL, which passes through the Wren Engine (Rust-based query engine) that validates, optimizes, and executes against the target database. Results are returned to the AI Service which generates natural language insights, charts, and reports from the query results. The semantic layer (MDL) is maintained by data engineers and updated as the business evolves.

## Strengths
- MDL semantic layer solves text-to-SQL accuracy problems that plague naive approaches
- 10+ LLM support enables cost optimization (use cheaper models for simple queries)
- Ollama support for fully air-gapped deployments in regulated environments
- Embedded API enables building natural language analytics into existing products
- AGPL self-hosted option keeps all sensitive business data on-premise

## Limitations
- AGPL-3.0: any product built on WrenAI and distributed must also be AGPL (unless using cloud)
- Semantic layer requires upfront investment to define MDL correctly for complex schemas
- Complex multi-hop analytical queries may still generate incorrect SQL
- Not a full BI tool (no pixel-perfect dashboards); focused on conversational analytics
- Data engineer required to maintain the semantic layer as the data model evolves

## Alternatives
| Tool | Key Difference |
|------|---------------|
| MindsDB | AI analytics query engine; broader ML features; less BI-focused |
| Metabase | Traditional BI with some AI; better dashboards; less conversational |
| Looker | Enterprise semantic layer; proprietary; no natural language focus |
| Cube | Semantic layer only; requires separate analytics layer |

## References
- https://getwren.ai
- https://github.com/Canner/WrenAI
- https://docs.getwren.ai/
- https://docs.getwren.ai/guide/wren-ai-overview (MDL semantic layer docs)

## Notes
WrenAI is the most serious open-source text-to-SQL BI platform. The MDL semantic layer is the critical differentiator — teams that invest in defining it properly will see dramatically better SQL accuracy than naive text-to-SQL approaches. Plan for 1-2 weeks of data engineer time to build the initial semantic layer for a complex data model. Consider the AGPL license implications carefully if building a commercial product on top of WrenAI — the cloud version may be more appropriate for commercial use cases.
