# LlamaIndex

> The leading document agent and OCR platform for building RAG pipelines and agentic data applications.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 02 - AI Agents / 05 - RAG & Knowledge |
| **URL** | https://www.llamaindex.ai |
| **GitHub** | https://github.com/run-llama/llama_index |
| **Stars** | 48,200 |
| **License** | MIT |
| **Pricing** | Free (OSS) / LlamaParse & LlamaCloud (paid enterprise) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
LlamaIndex is a data framework for building LLM-powered applications, with a particular focus on connecting LLMs to diverse data sources. It provides data connectors (APIs, PDFs, docs, SQL), indexing structures (vector, keyword, knowledge graph), and advanced retrieval interfaces for building RAG (Retrieval-Augmented Generation) pipelines.

In 2025-2026, LlamaIndex has evolved from a pure RAG framework into a broader "document agent and OCR platform." **LlamaParse**, its enterprise product, provides agentic OCR and parsing for 130+ document formats, structured data extraction, document indexing, and RAG pipeline management. The open-source core (llama-index-core) remains the foundation, with 300+ integration packages available via LlamaHub.

LlamaIndex also supports agent workflows through its Workflows API and Agent Builder, enabling the creation of document agents that can reason over and interact with documents.

## Key Features
- **Data connectors**: Ingest from APIs, PDFs, docs, SQL, and virtually any data source
- **Index structures**: Vector, keyword, knowledge graph, and custom indices
- **Advanced retrieval**: Query engines, routers, and hybrid search
- **300+ integrations**: Via LlamaHub (models, embeddings, vector stores, data loaders)
- **Workflows API**: Build agentic document processing pipelines
- **Agent Builder**: Create document agents with tool access
- **LlamaParse**: Agentic OCR for 130+ document formats (enterprise)
- **Structured data extraction**: Extract typed data from documents
- **Modular architecture**: Use llama-index-core alone or with the full starter package

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | Mature framework; 7,700+ commits; enterprise products |
| **Security** | 4 | Enterprise-grade with LlamaCloud; data residency options |
| **Scalability** | 4 | Supports distributed indexing; cloud deployment |
| **Support/Community** | 5 | 48.2K stars; active community; extensive documentation |
| **Documentation** | 5 | Comprehensive docs, tutorials, and guides |
| **Integration Ease** | 5 | `pip install llama-index`; modular design |

## Use Cases
1. **RAG applications** - Connect LLMs to enterprise knowledge bases for accurate Q&A
2. **Document processing** - Agentic OCR and structured extraction from complex documents
3. **Knowledge management** - Build searchable indices over organizational knowledge
4. **Data analysis agents** - Agents that query, reason over, and summarize data

## Getting Started
```bash
# Full starter package
pip install llama-index
# Or core only with specific integrations
pip install llama-index-core llama-index-llms-openai
```

## Strengths
- Best-in-class RAG and data retrieval framework
- Massive integration ecosystem (300+ packages via LlamaHub)
- LlamaParse is a strong enterprise differentiator for document processing
- Clean modular architecture
- Strong community and documentation

## Limitations
- Agent capabilities are secondary to RAG/data focus (for agents, consider LangGraph)
- LlamaParse and LlamaCloud are paid products
- Can be complex for simple use cases
- Overlaps significantly with LangChain in many areas

## Alternatives
| Tool | Key Difference |
|------|---------------|
| LangChain | Broader agent focus; more general-purpose; larger ecosystem |
| Haystack | Similar RAG focus; more pipeline-oriented |
| DSPy | Programmatic prompt optimization; different paradigm |
| Unstructured.io | Document processing focus; simpler |

## References
- https://docs.llamaindex.ai
- https://github.com/run-llama/llama_index
- https://llamahub.ai
- https://www.llamaindex.ai/llamaparse

## Notes
LlamaIndex is the undisputed leader for RAG and data-centric LLM applications. While it has agent capabilities, teams looking primarily for agent orchestration should consider LangGraph or CrewAI instead. The ideal pattern is to use LlamaIndex for data retrieval and indexing within a broader agent framework. LlamaParse's agentic OCR is particularly valuable for enterprises with large document processing needs.
