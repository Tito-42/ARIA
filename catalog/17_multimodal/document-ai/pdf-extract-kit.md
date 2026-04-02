# PDF-Extract-Kit

> Modular high-quality PDF extraction toolkit from OpenDataLab that combines leading models for layout detection, formula recognition, OCR, and table parsing in a configurable pipeline.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 17 - multimodal / document-ai |
| **URL** | https://github.com/opendatalab/PDF-Extract-Kit |
| **GitHub** | https://github.com/opendatalab/PDF-Extract-Kit |
| **Stars** | 9 500 |
| **License** | AGPL-3.0 |
| **Pricing** | Free / Open Source (AGPL-3.0) |
| **Last Verified** | 2026-04-02 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
PDF-Extract-Kit is a modular PDF extraction toolkit developed by OpenDataLab (the same organization behind MinerU) that assembles state-of-the-art specialized models into a configurable pipeline for high-quality document content extraction. Unlike MinerU which is a more integrated end-to-end solution, PDF-Extract-Kit is designed for use cases where fine-grained control over the extraction pipeline is needed.

The toolkit integrates dedicated best-of-breed models for each extraction task: DocLayout-YOLO for layout analysis, UniMERNet for mathematical formula recognition, PaddleOCR for multilingual text recognition, and specialized table detection and structure recognition models. Each component can be swapped or configured independently, making it suitable for custom pipeline development and research.

PDF-Extract-Kit also serves as the underlying model hub for MinerU, providing the modular components that MinerU assembles into its higher-level API.

## Key Features
- Modular architecture: each component independently configurable/replaceable
- Layout analysis: DocLayout-YOLO (text blocks, figures, tables, formulas)
- Formula recognition: UniMERNet (LaTeX output for math formulas)
- OCR: PaddleOCR integration (100+ languages)
- Table detection and structure recognition
- Bounding box coordinates in output for spatial analysis
- JSON output with fine-grained element metadata
- GPU acceleration support
- Serves as the underlying model hub for MinerU
- Useful for building custom extraction pipelines

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 3 | Lower-level toolkit; requires more integration work than MinerU/Docling |
| **Security** | 3 | AGPL-3.0 creates SaaS licensing concerns; local processing |
| **Scalability** | 3 | GPU-accelerated components; no native orchestration for distributed processing |
| **Support/Community** | 3 | 9.5K stars; OpenDataLab backing; smaller community than MinerU |
| **Documentation** | 3 | Adequate component documentation; fewer end-to-end tutorials |
| **Integration Ease** | 2 | Lower-level API; requires more custom integration work |

## Use Cases
1. **Custom PDF extraction pipelines** - Build tailored extraction workflows where specific components need to be swapped or tuned for domain-specific documents
2. **Formula-heavy document processing** - Extract mathematical content from academic papers, technical manuals, or scientific reports using UniMERNet
3. **Research and model evaluation** - Benchmark individual extraction components independently
4. **Dataset creation** - Generate high-quality labeled document datasets with precise spatial coordinates
5. **Foundation for custom tools** - Use as the building block layer under a higher-level document processing application

## Getting Started
```bash
pip install pdf-extract-kit

# Basic pipeline usage
from pdf_extract_kit.pipeline import DocumentPipeline
from pdf_extract_kit.config import PipelineConfig

config = PipelineConfig(
    layout_model="DocLayout-YOLO",
    formula_model="UniMERNet",
    ocr_engine="PaddleOCR",
    table_model="TableStructureRecognizer"
)

pipeline = DocumentPipeline(config)
result = pipeline.process("path/to/document.pdf")

# Access individual results
for page in result.pages:
    for element in page.elements:
        print(element.type, element.text, element.bbox)
```

## Architecture / How It Works
PDF-Extract-Kit operates as a modular pipeline where each stage runs an independent specialized model. Stage 1: PDF rendering to images at configurable DPI. Stage 2: DocLayout-YOLO detects and classifies regions (text, figure, table, formula, caption). Stage 3: Formula regions are processed by UniMERNet for LaTeX recognition. Stage 4: Text and table regions are processed by PaddleOCR. Stage 5: Table regions additionally go through table structure recognition. Stage 6: Results are assembled into a structured JSON output with element types, text content, and bounding box coordinates.

## Strengths
- Fine-grained control over each pipeline stage
- Best-of-breed specialized models for each extraction task
- Coordinates in output enable advanced spatial analysis
- Reusable components used by MinerU (battle-tested)
- AGPL-3.0 is acceptable for internal enterprise use and research

## Limitations
- AGPL-3.0 creates commercial SaaS licensing complications
- More complex to use than MinerU (intended for developers building pipelines)
- No high-level RAG framework integrations out of the box
- Requires more setup and configuration than end-to-end solutions
- Smaller community and fewer tutorials than Docling or MinerU

## Alternatives
| Tool | Key Difference |
|------|---------------|
| MinerU | High-level API over PDF-Extract-Kit components; easier to use |
| Docling | MIT license; better RAG integrations; less modular |
| Unstructured | Apache 2.0; more document types; less formula accuracy |
| Layout-Parser | Older; less maintained; broader layout analysis scope |

## References
- https://github.com/opendatalab/PDF-Extract-Kit
- https://github.com/opendatalab/MinerU (higher-level sibling project)

## Notes
PDF-Extract-Kit is the right choice when you need maximum flexibility in your document extraction pipeline and are comfortable with the lower-level API. For most use cases, MinerU (which uses PDF-Extract-Kit internally) provides a simpler entry point. The AGPL-3.0 license means enterprises building commercial SaaS products should either use Docling (MIT) or obtain a commercial license.
