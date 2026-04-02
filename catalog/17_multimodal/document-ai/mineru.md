# MinerU

> High-accuracy open-source document parsing tool that converts PDFs, images and DOCX into machine-readable Markdown and JSON with strong support for formulas, tables, and 109 languages.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 17 - multimodal / document-ai |
| **URL** | https://github.com/opendatalab/MinerU |
| **GitHub** | https://github.com/opendatalab/MinerU |
| **Stars** | 57 800 |
| **License** | AGPL-3.0 + CLA |
| **Pricing** | Free / Open Source (AGPL-3.0) |
| **Last Verified** | 2026-04-02 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
MinerU is an open-source document parsing tool developed by OpenDataLab (Shanghai AI Lab) that converts PDFs, images, and DOCX files into Markdown and structured JSON. It is specifically engineered to handle the complexity found in scientific and technical documents: LaTeX mathematical formulas, nested tables rendered as HTML, multi-column layouts, and scanned content.

The tool uses a pipeline combining layout detection (YOLO-based), formula recognition, OCR (supporting 109 languages), table parsing (HTML output), and header/footer removal. It outputs clean Markdown or structured JSON with spatial coordinates, making it ideal for downstream RAG pipelines or document analysis workflows.

MinerU competes directly with Docling in terms of stars (~58K) and use cases, but differs in its stronger focus on scientific/academic documents and its AGPL-3.0 license, which has implications for commercial SaaS use.

## Key Features
- PDF to Markdown and JSON conversion with layout preservation
- LaTeX formula recognition and export
- Table parsing to HTML with structure preservation
- OCR support for 109 languages
- Automatic header, footer, and watermark removal
- Multi-column layout detection and correct reading order
- DOCX and image input support
- GPU-accelerated processing
- Structured JSON output with bounding box coordinates
- CLI and Python API
- Part of the opendatalab ecosystem (sibling of PDF-Extract-Kit)

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | 58K stars, actively maintained, widely used in research/industry |
| **Security** | 3 | Local processing is safe; AGPL-3.0 requires careful legal review for SaaS |
| **Scalability** | 4 | GPU acceleration, can be batched; no native distributed mode |
| **Support/Community** | 4 | Very active GitHub, Shanghai AI Lab backing, active issue tracker |
| **Documentation** | 4 | Good docs and examples, though primarily Chinese-community-focused |
| **Integration Ease** | 3 | Python API available but fewer native RAG framework integrations than Docling |

## Use Cases
1. **Scientific paper processing** - Extract clean text, formulas, and tables from academic PDFs for knowledge bases or research tools
2. **Technical documentation parsing** - Parse manuals, datasheets, and standards documents with complex layouts
3. **Multilingual document digitization** - Process documents in 109 languages including CJK scripts
4. **RAG pipeline ingestion** - Convert enterprise documents to Markdown for vector store loading
5. **Dataset creation** - Generate structured training data from large PDF corpora

## Getting Started
```bash
pip install mineru

# Basic PDF to Markdown conversion
from mineru.utils.pdf_to_markdown import pdf_to_markdown

markdown_content = pdf_to_markdown("path/to/document.pdf")
print(markdown_content)

# CLI usage
mineru parse --input document.pdf --output output_dir/ --method auto
```

## Architecture / How It Works
MinerU's pipeline consists of: (1) layout detection using a fine-tuned YOLO model to identify text blocks, figures, tables, and formulas; (2) reading order recovery based on spatial coordinates; (3) OCR applied to detected text regions using PaddleOCR as the default engine; (4) specialized formula recognition converting equations to LaTeX; (5) table structure analysis outputting HTML; (6) assembly into a unified Markdown or JSON document. The pipeline is modular and configurable, with options to swap the OCR engine.

## Strengths
- Exceptional accuracy on mathematical formulas (LaTeX output)
- Very strong multilingual OCR coverage (109 languages)
- Spatial coordinate metadata in JSON output enables downstream layout analysis
- 57.8K stars validates widespread adoption
- Consistently outperforms alternatives on scientific/technical documents
- Handles complex nested tables well

## Limitations
- AGPL-3.0 license requires SaaS/commercial products to open-source their code or obtain a commercial license
- Fewer pre-built integrations with RAG frameworks compared to Docling
- Primarily focused on PDF; fewer document types than Docling
- Chinese-first community can slow down English-language issue resolution
- Heavy model dependencies on first run

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Docling | MIT license, better RAG framework integrations, broader format support |
| Marker | Faster and simpler; GPL license; less formula/table accuracy |
| PDF-Extract-Kit | Lower-level companion toolkit from same org for custom pipelines |
| PaddleOCR | Broader OCR toolkit; MinerU uses it internally |

## References
- https://github.com/opendatalab/MinerU
- https://mineru.readthedocs.io/
- https://github.com/opendatalab/PDF-Extract-Kit

## Notes
MinerU is the preferred choice when document accuracy on formulas and scientific content takes priority over license simplicity. For commercial products where AGPL is a concern, Docling with MIT is the safer default. The two tools are roughly equivalent in capability and stars — choose based on license requirements and specific document characteristics.
