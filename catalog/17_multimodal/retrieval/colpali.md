# ColPali / ColQwen

> Vision-language model family for efficient document retrieval using visual embeddings, eliminating the need for OCR or text extraction pipelines.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 17 - multimodal / retrieval |
| **URL** | https://github.com/illuin-tech/colpali |
| **GitHub** | https://github.com/illuin-tech/colpali |
| **Stars** | 2 600 |
| **License** | Apache 2.0 (ColQwen, ColSmol) / Gemma License (ColPali base) |
| **Pricing** | Free / Open Weights |
| **Last Verified** | 2026-04-02 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
ColPali is a family of models that revolutionizes document retrieval by processing document pages as images directly, using a vision-language model to generate multi-vector embeddings without any OCR, layout detection, or text extraction pipeline. Named after the late-interaction multi-vector retrieval approach (ColBERT), ColPali applies the same principle to visual tokens.

The approach takes a document page screenshot and produces a set of patch-level embeddings (one per visual patch, typically 1030 vectors per page). At query time, a text query is embedded into the same space, and MaxSim (maximum similarity) scoring across all patch vectors enables precise localization of the relevant visual regions. This is particularly powerful for documents with charts, tables, formulas, and complex visual layouts that OCR-based approaches struggle with.

The ColPali family includes: ColPali (original, Gemma-based), ColQwen2 (Qwen2-VL based, Apache 2.0, currently best performer), and ColSmol (SmolVLM-based, smallest). ColQwen2 achieves 80-91 points on the ViDoRe benchmark, surpassing all OCR-based retrieval approaches on visually complex documents.

## Key Features
- Document-page-as-image retrieval without OCR
- Multi-vector visual embeddings via late interaction (ColBERT approach)
- State-of-the-art on ViDoRe benchmark (80-91 points)
- Three variants: ColPali (Gemma, research), ColQwen2 (Qwen2-VL, best perf, Apache 2.0), ColSmol (smallest)
- MaxSim scoring for precise patch-level relevance detection
- Works on charts, tables, formulas, figures, and complex layouts
- HuggingFace Transformers compatible
- Integration with Byaldi library for easy RAG use
- Re-ranking capability for existing retrieval pipelines

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Novel but well-validated approach; Byaldi simplifies deployment; growing adoption |
| **Security** | 4 | Local deployment; Apache 2.0 for ColQwen2 |
| **Scalability** | 3 | Multi-vector storage is memory-intensive; requires PLAID or custom indexing at scale |
| **Support/Community** | 4 | Illuin Tech backing, HuggingFace support, active development |
| **Documentation** | 4 | Good papers, tutorials, Byaldi integration guide |
| **Integration Ease** | 4 | Byaldi library provides RAG-ready API; HuggingFace model hub |

## Use Cases
1. **Document RAG without OCR** - Build retrieval systems over PDF-heavy enterprise knowledge bases without fragile OCR preprocessing
2. **Visual document search** - Search over slide decks, annual reports, technical manuals with charts and graphs
3. **Re-ranking pipeline** - Use ColPali embeddings as a re-ranker over candidate documents retrieved by a first-stage retriever
4. **Knowledge base over visually complex documents** - Retrieve relevant pages from documents where textual content alone is insufficient
5. **Multi-lingual document retrieval** - Works regardless of document language since it operates on visual features

## Getting Started
```bash
pip install colpali-engine byaldi

# Using Byaldi for RAG (recommended)
from byaldi import RAGMultiModalModel

RAG = RAGMultiModalModel.from_pretrained("vidore/colqwen2-v1.0")
RAG.index(input_path="path/to/documents/", index_name="my_index", overwrite=True)

results = RAG.search("What is the revenue for Q3 2024?", k=5)

# Direct inference with colpali-engine
from colpali_engine.models import ColQwen2, ColQwen2Processor

model = ColQwen2.from_pretrained("vidore/colqwen2-v1.0").eval().cuda()
processor = ColQwen2Processor.from_pretrained("vidore/colqwen2-v1.0")

queries = ["What is the revenue trend?"]
query_embeddings = processor.process_queries(queries)
query_vecs = model(**query_embeddings)
```

## Architecture / How It Works
ColPali adapts the ColBERT late-interaction retrieval paradigm to the visual domain. Document pages are rendered as images and passed through a VLM (Qwen2-VL for ColQwen2) to produce a sequence of patch-level embedding vectors. Each page is represented by ~1030 vectors (one per 32x32 pixel patch). At query time, the text query is embedded by the same VLM's text encoder. Retrieval uses MaxSim: for each query token vector, find the maximum cosine similarity across all document patch vectors, then sum these maxima to get the final relevance score. This late-interaction approach allows precise localization of relevant visual regions.

## Strengths
- Eliminates brittle OCR/parsing pipelines — works directly on page images
- Handles visually complex documents (charts, tables, formulas) better than text-only retrieval
- SOTA on ViDoRe benchmark with significant margin
- Apache 2.0 for ColQwen2 enables commercial use
- Works across languages without language-specific OCR configuration
- Byaldi library provides a very simple RAG API

## Limitations
- Multi-vector storage is significantly more memory-intensive than single-vector embeddings (~1030x per document page)
- Indexing large document corpora requires specialized vector stores (PLAID index, or Qdrant with custom setup)
- Query-time MaxSim is more compute-intensive than single-vector cosine similarity
- Original ColPali uses Gemma license (more restrictive); use ColQwen2 for commercial work
- Less mature ecosystem for large-scale deployment compared to traditional text retrieval

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Docling + text embeddings | Text-based retrieval; faster/cheaper at scale; fails on visual documents |
| MinerU + text embeddings | Better OCR accuracy; still text-only retrieval |
| CLIP-based retrieval | Single-vector image retrieval; lower accuracy on document text |
| BM25 + OCR | Classic text retrieval; free; brittle on complex layouts |

## References
- https://github.com/illuin-tech/colpali
- https://arxiv.org/abs/2407.01449 (ColPali paper — ECCV 2024)
- https://huggingface.co/vidore/colqwen2-v1.0
- https://github.com/AnswerDotAI/byaldi (Byaldi integration library)
- https://huggingface.co/datasets/vidore/vidore-benchmark-667173f98e70a1c0fa4db00d (ViDoRe benchmark)

## Notes
ColPali/ColQwen2 is the recommended approach for document retrieval when documents contain significant visual structure (charts, tables, mixed layouts). For text-heavy documents with minimal visual complexity, traditional OCR + text embeddings remain more efficient at scale. Use ColQwen2 (Apache 2.0) over original ColPali (Gemma License) for commercial deployments.
