# Docling

> Advanced document parsing library by IBM Research that converts PDFs and other formats into LLM-ready structured representations.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 17 - multimodal / document-ai |
| **URL** | https://github.com/DS4SD/docling |
| **GitHub** | https://github.com/DS4SD/docling |
| **Stars** | 56 900 |
| **License** | MIT |
| **Pricing** | Free / Open Source |
| **Last Verified** | 2026-04-02 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Docling is an open-source document processing library developed by IBM Research Zurich and contributed to the Linux Foundation AI & Data Foundation. It parses PDF files and a wide range of other document formats (DOCX, PPTX, XLSX, HTML, images, audio) into a unified, LLM-ready representation called DoclingDocument.

The library applies advanced layout analysis to accurately detect reading order, tables, formulas, figures, and text blocks. It exports to multiple formats (Markdown, JSON, HTML, Docx) and integrates natively with major RAG orchestration frameworks including LangChain, LlamaIndex, and Haystack, making it straightforward to embed into existing GenAI pipelines.

Docling has become the de facto standard for document parsing in enterprise GenAI pipelines due to its MIT license, IBM backing, active maintenance, and exceptional handling of complex document structures such as multi-column layouts, nested tables, and mathematical formulas.

## Key Features
- Advanced PDF layout analysis: reading order, columns, tables, formulas, figures
- Unified DoclingDocument representation with rich metadata
- Export to Markdown, JSON, HTML, Docx
- Native integrations: LangChain, LlamaIndex, Haystack, Quackling
- OCR support for scanned documents (Tesseract, EasyOCR, RapidOCR)
- Table structure recognition (TableFormer model)
- Formula detection and LaTeX export
- Image extraction and classification
- Chunking strategies optimized for RAG (hybrid chunking)
- Multi-format input: PDF, DOCX, PPTX, XLSX, HTML, Markdown, images, audio
- CLI and Python API
- Part of LF AI & Data Foundation

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | IBM-backed, 57K stars, used in production by many enterprises |
| **Security** | 4 | Local processing, no data sent to external APIs; MIT license |
| **Scalability** | 4 | Can be parallelized, GPU acceleration for OCR; no native distributed mode |
| **Support/Community** | 5 | LF AI & Data Foundation, IBM Research, very active GitHub issues |
| **Documentation** | 5 | Excellent docs, tutorials, integration guides |
| **Integration Ease** | 5 | Drop-in integrations for LangChain, LlamaIndex, Haystack |

## Use Cases
1. **RAG pipeline document ingestion** - Parse enterprise PDFs (contracts, reports, manuals) into clean Markdown/JSON for vector store ingestion
2. **Research paper processing** - Extract structured content from scientific PDFs with formulas and tables intact
3. **Enterprise document digitization** - Convert scanned documents and legacy PDFs into machine-readable formats
4. **Table extraction for analytics** - Extract tabular data from PDFs and convert to structured JSON/CSV
5. **Multi-format document ETL** - Unified pipeline processing DOCX, PPTX, XLSX, HTML and PDFs with consistent output

## Getting Started
```bash
pip install docling

# Basic usage
from docling.document_converter import DocumentConverter

converter = DocumentConverter()
result = converter.convert("path/to/document.pdf")
print(result.document.export_to_markdown())

# With LangChain integration
pip install "docling[langchain]"
from langchain_docling import DoclingLoader
loader = DoclingLoader(file_path="document.pdf")
docs = loader.load()
```

## Architecture / How It Works
Docling uses a pipeline architecture where each document passes through sequential stages: format detection, PDF backend parsing (native PDF text extraction or OCR fallback), layout model inference (a custom vision model detecting blocks, tables, figures), table structure recognition (TableFormer), formula detection, and finally assembly into the DoclingDocument format. The pipeline is configurable, allowing users to swap or disable individual stages. Models are downloaded automatically on first use.

## Strengths
- Best-in-class PDF layout analysis, especially for complex multi-column academic documents
- MIT license with IBM backing provides strong enterprise trust
- Native RAG framework integrations reduce integration effort to near zero
- Handles formulas as LaTeX, preserving mathematical content
- Excellent table recognition via the dedicated TableFormer model
- Active community with 57K+ stars and rapid issue resolution

## Limitations
- Heavy dependency footprint (vision models downloaded on first run)
- OCR adds significant processing time for scanned documents
- Audio parsing is experimental and limited
- No native distributed/cloud-scale processing mode
- Large PDFs with many pages can be slow without GPU

## Alternatives
| Tool | Key Difference |
|------|---------------|
| MinerU | Stronger on scientific docs/formulas; AGPL license; comparable stars |
| Marker | Faster, simpler API; GPL license; less metadata richness |
| Unstructured | Broader file type support; SaaS offering; heavier opinionated chunking |
| PDF-Extract-Kit | Lower-level modular toolkit; requires more integration work |

## References
- https://github.com/DS4SD/docling
- https://ds4sd.github.io/docling/
- https://arxiv.org/abs/2408.09869 (Docling Technical Report)
- https://lfaidata.foundation/projects/docling/

## Notes
Docling is the recommended default for enterprise PDF/document ingestion into RAG pipelines. Its combination of MIT license, IBM support, LF AI & Data Foundation governance, and native RAG integrations makes it the safest production choice. For purely scientific/formula-heavy documents, MinerU may offer better accuracy.
