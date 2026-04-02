# GPTCache

> Semantic caching for LLMs — reduce API costs up to 10x and accelerate responses up to 100x by caching semantically similar queries.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 12 - Enterprise Integration |
| **URL** | https://gptcache.readthedocs.io |
| **GitHub** | https://github.com/zilliztech/GPTCache |
| **Stars** | 8 000 |
| **License** | MIT |
| **Pricing** | Open source free |
| **Last Verified** | 2026-04-02 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
GPTCache is a semantic caching layer for LLM applications, built by Zilliz (the company behind Milvus). Instead of making a new LLM API call for every query, GPTCache stores responses and retrieves them when a semantically similar query arrives. The similarity check uses embedding-based vector search, so "What is the capital of France?" and "What city is the capital of France?" can return the same cached response.

The performance improvement is significant: Zilliz reports up to 10x cost reduction and up to 100x latency improvement for workloads with recurring similar queries. The architecture is modular: the embedding model, similarity threshold, and storage backend are all configurable. Storage options include SQLite (development), Redis, PostgreSQL, and DynamoDB. GPTCache integrates natively with LangChain and LlamaIndex, and provides a Docker server for polyglot (non-Python) applications.

This tool is particularly valuable for customer-facing applications with FAQ-like patterns, internal chatbots, and any LLM application where users frequently ask similar questions.

## Key Features
- Semantic similarity caching via embedding vectors
- Exact-match caching for identical queries
- Configurable similarity threshold (precision vs. recall trade-off)
- Modular embedding backends: OpenAI, Sentence Transformers, local models
- Storage backends: SQLite, Redis, PostgreSQL, DynamoDB, Milvus
- LangChain and LlamaIndex native integration
- Docker server for non-Python polyglot applications
- Cache statistics: hit rate, latency savings, cost savings
- MIT license — no restrictions

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 3 | Production-capable; 8k stars; actively maintained by Zilliz |
| **Security** | 4 | MIT license; self-hosted; no data leaves org with on-prem deployment |
| **Scalability** | 4 | Redis/DynamoDB backends scale horizontally; Docker server for services |
| **Support/Community** | 3 | 8k stars; Zilliz backing; community-driven |
| **Documentation** | 3 | Adequate docs; readthedocs site with examples |
| **Integration Ease** | 4 | LangChain/LlamaIndex native; 3-5 lines to integrate |

## Use Cases
1. Customer-facing chatbots with FAQ patterns — cache common questions to reduce costs and latency
2. Internal knowledge base Q&A — recurring similar employee queries hit cache instead of LLM API
3. High-traffic LLM applications — reduce API costs at scale with measurable ROI
4. Development/testing cost reduction — cache responses during dev/test cycles to avoid API charges
5. Latency-sensitive applications — return cached responses in milliseconds vs. 1-5 seconds for LLM call

## Getting Started
```python
pip install gptcache

from gptcache import cache
from gptcache.adapter import openai

# Initialize with default settings (SQLite + OpenAI embeddings)
cache.init()
cache.set_openai_key()

# Use exactly like the OpenAI SDK
response = openai.ChatCompletion.create(
    model="gpt-4o",
    messages=[{"role": "user", "content": "What is the capital of France?"}]
)
# Second identical/similar call returns from cache

# Production setup with Redis backend
from gptcache.manager import manager_factory
from gptcache.similarity_evaluation import SearchDistanceEvaluation

cache.init(
    embedding_func=...,  # your embedding model
    data_manager=manager_factory("redis", data_dir="gptcache_data"),
    similarity_evaluation=SearchDistanceEvaluation()
)
```

## Architecture / How It Works
GPTCache sits between the application and the LLM API as a middleware layer. When a query arrives: (1) generate an embedding vector for the query; (2) search the vector store for similar cached embeddings above a configurable threshold; (3) if found, return the cached response; (4) if not found, call the LLM API, store the response with its embedding, and return it. The embedding model, vector store, scalar storage (for response data), and similarity evaluator are all pluggable components. The Docker server exposes an HTTP API compatible with the OpenAI interface, enabling caching for any language that can make HTTP requests.

## Strengths
- Direct, measurable ROI on LLM API costs — up to 10x reduction validated
- Modular architecture — swap any component without changing the rest
- MIT license — zero commercial restrictions
- LangChain/LlamaIndex integration means minimal code changes for existing apps
- Zilliz (Milvus company) backing ensures continued vector search expertise

## Limitations
- Semantic caching only works well for workloads with recurring similar queries — low benefit for highly varied queries
- Embedding generation adds latency overhead on cache misses (but is offset by hit savings)
- Cache invalidation strategy requires careful tuning — stale cached responses are a risk
- Less maintained recently — verify latest commit activity before adoption
- Similarity threshold tuning requires experimentation per use case

## Alternatives
| Tool | Key Difference |
|------|---------------|
| LiteLLM built-in caching | Simpler setup if already using LiteLLM gateway |
| Portkey semantic caching | Gateway-level caching; no separate deployment |
| Redis Cache (custom) | More control; requires custom embedding integration |
| Helicone caching | Gateway-integrated; simpler; less configurable |

## References
- https://gptcache.readthedocs.io
- https://github.com/zilliztech/GPTCache
- https://zilliz.com/blog/building-gptcache-a-semantic-cache-for-llm-powered-applications

## Notes
GPTCache delivers clear ROI for the right use cases: applications with a significant proportion of semantically similar queries (FAQ chatbots, internal assistants, product search). For workloads with highly unique queries, the cache hit rate will be low and the overhead may not be justified. Before deploying, baseline your query similarity distribution to estimate expected hit rate. The Zilliz backing is a positive signal for long-term maintenance. Consider comparing with gateway-level caching (Portkey, LiteLLM) before adding a separate caching layer.
