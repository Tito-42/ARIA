# Table Transformer

> Microsoft's deep learning model for accurate detection and structural recognition of tables in PDFs and document images, accompanied by the PubTables-1M benchmark dataset.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 17 - multimodal / document-ai |
| **URL** | https://github.com/microsoft/table-transformer |
| **GitHub** | https://github.com/microsoft/table-transformer |
| **Stars** | 2 900 |
| **License** | MIT |
| **Pricing** | Free / Open Source |
| **Last Verified** | 2026-04-02 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Table Transformer (TATR) is a Microsoft Research model that uses object detection (DETR-based) to detect and recognize the structure of tables in PDFs and document images. It addresses two distinct tasks: Table Detection (finding where tables are in a document image) and Table Structure Recognition (identifying rows, columns, spanning cells, and their relationships within a detected table).

The project introduces PubTables-1M, a large-scale dataset of 947,000 annotated tables from scientific papers, along with the GriTS (Grid Table Similarity) metric for quantitative evaluation of table structure recognition quality. These contributions have made Table Transformer the standard reference for table extraction research and a key component in document AI pipelines.

Table Transformer is used as a component in Docling, Unstructured (hi-res mode), and various other document parsing pipelines where precise table extraction is critical.

## Key Features
- Two-model approach: Table Detection (TD) + Table Structure Recognition (TSR)
- DETR-based architecture (Detection Transformer) adapted for table parsing
- PubTables-1M dataset: 947K annotated tables from scientific papers (public)
- GriTS evaluation metric for structural table similarity
- Detects: table boundaries, rows, columns, spanning cells
- MIT license
- HuggingFace model hub integration
- Used as component in Docling, Unstructured, and others
- Produces structured output suitable for CSV/JSON conversion

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | MIT license, Microsoft backing, widely used as component in production systems |
| **Security** | 5 | MIT license; local inference; no data leaves premises |
| **Scalability** | 3 | Standard DETR inference; no special high-throughput optimizations |
| **Support/Community** | 3 | 2.9K stars; Microsoft backing; used by many but niche community |
| **Documentation** | 4 | Good README, training code, evaluation scripts, paper |
| **Integration Ease** | 4 | HuggingFace compatible; used as component rather than standalone tool |

## Use Cases
1. **Table extraction from scientific papers** - Extract tabular data from research publications for meta-analysis or knowledge base population
2. **Financial document parsing** - Extract financial tables from annual reports, balance sheets, and regulatory filings
3. **Invoice and receipt table extraction** - Identify and structure line items from commercial documents
4. **Document digitization pipeline** - Component in broader document parsing systems requiring high-quality table handling
5. **Table benchmark evaluation** - Use GriTS and PubTables-1M to evaluate table extraction models

## Getting Started
```bash
pip install transformers torch pillow

from transformers import AutoImageProcessor, TableTransformerForObjectDetection
from PIL import Image
import torch

# Table Detection
image = Image.open("document.pdf_page.png")
processor = AutoImageProcessor.from_pretrained(
    "microsoft/table-transformer-detection"
)
model = TableTransformerForObjectDetection.from_pretrained(
    "microsoft/table-transformer-detection"
)

inputs = processor(images=image, return_tensors="pt")
outputs = model(**inputs)
target_sizes = torch.tensor([image.size[::-1]])
results = processor.post_process_object_detection(
    outputs, threshold=0.9, target_sizes=target_sizes
)[0]

# Table Structure Recognition
tsr_model = TableTransformerForObjectDetection.from_pretrained(
    "microsoft/table-transformer-structure-recognition"
)
# Crop detected table region and run TSR
```

## Architecture / How It Works
Table Transformer adapts the DETR (DEtection TRansformer) object detection architecture for table analysis tasks. DETR uses a CNN backbone (ResNet) to extract image features, which are then processed by a transformer encoder-decoder with learned queries. For Table Detection, queries predict table bounding boxes and confidence scores. For Table Structure Recognition, a separate model processes the cropped table image and predicts structural elements (row, column, spanning cell) with their bounding boxes. The model is trained on PubTables-1M with a Hungarian matching loss that assigns predictions to ground truth elements.

## Strengths
- MIT license — no restrictions on commercial use
- Microsoft Research backing provides quality assurance
- PubTables-1M is a valuable public resource for table extraction research
- GriTS metric is a better table evaluation metric than IoU-based approaches
- Already integrated into major document parsing tools (Docling)
- Handles spanning cells and complex table structures

## Limitations
- Specialized tool (table extraction only) — needs to be combined with broader document parsing
- Performance drops on tables with unusual visual styles or no visible borders
- Trained primarily on scientific papers; may underperform on other document types without fine-tuning
- Inference requires rendering PDFs to images first
- Smaller community than general-purpose document parsers

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Docling (TableFormer) | TableFormer inside Docling is more accurate; fully integrated pipeline |
| MinerU table parsing | Integrated in MinerU pipeline; no standalone use |
| Camelot | Traditional non-DL approach; faster; less accurate on complex tables |
| pdfplumber | Text-based extraction; fast; fails on scanned tables |

## References
- https://github.com/microsoft/table-transformer
- https://arxiv.org/abs/2110.00061 (Table Transformer paper)
- https://huggingface.co/microsoft/table-transformer-detection
- https://huggingface.co/microsoft/table-transformer-structure-recognition
- https://huggingface.co/datasets/bsmock/pubtables-1m (PubTables-1M)

## Notes
Table Transformer is most useful as a component within a larger document parsing pipeline, not as a standalone tool. It is already embedded in Docling and Unstructured, so most users benefit from it indirectly. For teams building custom pipelines where table extraction quality is critical (financial docs, scientific papers), Table Transformer is the reference model to start from or fine-tune.
