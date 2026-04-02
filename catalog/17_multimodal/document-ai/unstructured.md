# Unstructured

> Open-source ETL library that transforms unstructured documents (PDFs, HTML, Word, emails, images) into structured data ready for LLM and RAG pipelines.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 17 - multimodal / document-ai |
| **URL** | https://unstructured.io/ |
| **GitHub** | https://github.com/Unstructured-IO/unstructured |
| **Stars** | 14 400 |
| **License** | Apache 2.0 |
| **Pricing** | Free (open-source) / Unstructured API (paid SaaS) |
| **Last Verified** | 2026-04-02 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Unstructured is an open-source document preprocessing library designed to serve as the ETL (Extract, Transform, Load) layer for LLM and RAG pipelines. It ingests virtually any document type — PDFs, HTML pages, Word documents, PowerPoint files, Excel spreadsheets, emails, images, Markdown, and more — and converts them into a consistent list of structured Element objects (Title, NarrativeText, Table, Image, etc.) that can be directly consumed by vector stores and LLM frameworks.

The library applies intelligent chunking strategies that respect document structure, keeping related content together rather than splitting arbitrarily at token boundaries. It integrates directly with LangChain, LlamaIndex, and major vector stores (Pinecone, Weaviate, Chroma, Qdrant). For production use at scale, Unstructured offers a managed API (Unstructured.io) that handles the heavy processing.

Unstructured is the most widely used document preprocessing library in the RAG ecosystem, with native integrations in essentially every major LLM framework.

## Key Features
- Support for 30+ document types: PDF, HTML, DOCX, PPTX, XLSX, EML, MSG, RTF, EPUB, TXT, images
- Structured Element output with semantic type labeling (Title, Text, Table, Image, etc.)
- Multiple chunking strategies: basic, by title, by page, semantic chunking
- Native integrations: LangChain, LlamaIndex, Haystack
- Native connectors: Confluence, Dropbox, Google Drive, OneDrive, S3, Azure Blob, Salesforce, Slack
- Hi-res mode: vision-model-based extraction for complex PDFs
- Table extraction with HTML/CSV output
- OCR integration (Tesseract, Paddle)
- Metadata preservation: source, page number, element type, coordinates
- REST API compatible (local or managed)
- Managed SaaS: Unstructured API with enterprise features

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | 14K stars, production-proven in thousands of RAG deployments |
| **Security** | 4 | Apache 2.0; local processing available; SaaS option for scale |
| **Scalability** | 4 | API for scale; local mode limited by processing speed |
| **Support/Community** | 5 | Native integrations everywhere; dedicated enterprise support; very active |
| **Documentation** | 5 | Excellent docs, tutorials, integration guides, API reference |
| **Integration Ease** | 5 | Drop-in with LangChain, LlamaIndex; 30+ native connectors |

## Use Cases
1. **Enterprise RAG pipeline document ingestion** - Parse and chunk diverse enterprise documents (contracts, reports, wikis) for vector store loading
2. **Multi-source knowledge base creation** - Ingest documents from S3, Google Drive, Confluence, Slack simultaneously via native connectors
3. **Email and communication analysis** - Process EML/MSG files for compliance monitoring or customer service automation
4. **Legacy document digitization** - Convert large archives of mixed document types to LLM-ready format
5. **Hybrid cloud/local document processing** - Use local processing for sensitive documents, SaaS API for high-volume batch processing

## Getting Started
```bash
# Basic installation
pip install unstructured

# With all document type dependencies
pip install "unstructured[all-docs]"

# Basic usage
from unstructured.partition.auto import partition

elements = partition("path/to/document.pdf")
for element in elements:
    print(type(element).__name__, ":", element.text[:100])

# With LangChain
from langchain_unstructured import UnstructuredLoader
loader = UnstructuredLoader("path/to/document.pdf", strategy="hi_res")
docs = loader.load()

# Chunking
from unstructured.chunking.title import chunk_by_title
chunks = chunk_by_title(elements, max_characters=1000, overlap=200)
```

## Architecture / How It Works
Unstructured uses a partitioning approach where each document type has a dedicated partitioner (partition_pdf, partition_docx, partition_html, etc.). The auto-partition function detects the file type and routes to the correct partitioner. PDF processing has three strategies: fast (pdfminer text extraction), ocr_only (Tesseract), and hi_res (vision model-based layout detection using detectron2/YOLOX for high accuracy). All partitioners output a list of Element objects with standardized metadata. The chunking layer then applies structural or semantic rules to group elements into appropriate chunks for embedding.

## Strengths
- Broadest document format support in its category (30+ types)
- Native connectors to enterprise data sources (Google Drive, S3, Confluence, Slack)
- Well-established as the standard in the LangChain/LlamaIndex ecosystem
- Hi-res mode for complex PDFs using vision models
- Apache 2.0 license with commercial SaaS option for scale

## Limitations
- Hi-res mode is slow and resource-intensive
- Less accurate on formula-heavy or scientific documents compared to MinerU or Docling
- SaaS API adds cost and potential data privacy considerations
- Large dependency footprint for full installation
- Table extraction less precise than specialized tools (Table Transformer, Docling)

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Docling | Better PDF accuracy and table extraction; MIT; fewer connectors |
| MinerU | Better scientific/formula handling; AGPL-3.0; fewer format types |
| LlamaIndex SimpleDirectoryReader | Framework-native; similar but fewer features |
| Marker | Faster conversion; GPL; less chunking intelligence |

## References
- https://unstructured.io/
- https://github.com/Unstructured-IO/unstructured
- https://docs.unstructured.io/
- https://python.langchain.com/docs/integrations/document_loaders/unstructured_file/

## Notes
Unstructured is the most pragmatic choice for teams already using LangChain or LlamaIndex who need broad document format support and pre-built data source connectors. For teams needing maximum PDF accuracy (especially scientific docs or formula-heavy content), Docling or MinerU offer better extraction quality. Unstructured's SaaS API makes it the easiest path to scaling document processing without infrastructure management.
