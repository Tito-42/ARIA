# LayoutLMv3

> Microsoft's multimodal pre-trained model that jointly learns text, layout, and image features for document AI tasks through unified masked learning.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 17 - multimodal / document-ai |
| **URL** | https://github.com/microsoft/unilm/tree/master/layoutlmv3 |
| **GitHub** | https://github.com/microsoft/unilm |
| **Stars** | 22 100 (unilm repo) |
| **License** | CC BY-NC-SA 4.0 (non-commercial) |
| **Pricing** | Free / Open Weights (non-commercial) |
| **Last Verified** | 2026-04-02 |
| **Status** | Maintained |
| **Maturity** | Production |

## What It Does
LayoutLMv3 is a multimodal pre-trained transformer from Microsoft that jointly learns representations from text tokens, layout (bounding box coordinates), and document images in a single unified model. Unlike its predecessors (LayoutLM, LayoutLMv2) that processed these modalities with separate encoders, LayoutLMv3 uses a unified architecture with masked pre-training objectives covering all three modalities simultaneously.

The model is pre-trained using Masked Language Modeling (MLM) on text tokens and Masked Image Modeling (MIM) on image patches, as well as Word-Patch Alignment (WPA) that teaches the model to align textual and visual patches. This joint pre-training produces representations that are highly effective for document understanding tasks where text position and visual layout are both important signals.

LayoutLMv3 achieves state-of-the-art on multiple document understanding benchmarks: Form Understanding (FUNSD), Receipt Understanding (CORD), Document Image Classification (RVL-CDIP), and Document Visual QA (DocVQA). It is part of the broader UniLM project which also includes Kosmos-2 and BEiT-3.

## Key Features
- Unified multimodal pre-training: text + layout + image patches simultaneously
- Masked Language Modeling + Masked Image Modeling + Word-Patch Alignment
- State-of-the-art on FUNSD (forms), CORD (receipts), RVL-CDIP (classification), DocVQA
- Base (133M) and Large (368M) variants
- HuggingFace Transformers compatible
- Part of Microsoft UniLM project
- Fine-tuned variants available for specific document tasks
- Strong on text-centric (forms, invoices) and image-centric tasks

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Mature model, widely fine-tuned for production; CC BY-NC-SA limits commercial use |
| **Security** | 3 | CC BY-NC-SA 4.0 prohibits commercial use without licensing arrangement |
| **Scalability** | 4 | Base/Large variants; standard transformer inference; HuggingFace serving |
| **Support/Community** | 4 | 22K stars (unilm repo), widely referenced, strong HuggingFace community |
| **Documentation** | 4 | Good academic documentation, HuggingFace model cards, tutorials |
| **Integration Ease** | 5 | HuggingFace Transformers drop-in; standard pipeline API |

## Use Cases
1. **Form information extraction** - Extract key-value pairs from business forms, surveys, tax documents
2. **Invoice and receipt processing** - Structured extraction from commercial documents with layout-dependent information
3. **Document classification** - Classify document types from their visual and textual content
4. **Document Visual QA** - Answer questions about specific document pages using layout context
5. **Academic research baseline** - Fine-tune and benchmark for document AI research

## Getting Started
```bash
pip install transformers

# Token classification (key-value extraction from forms)
from transformers import AutoProcessor, AutoModelForTokenClassification
import torch

processor = AutoProcessor.from_pretrained("microsoft/layoutlmv3-base", apply_ocr=True)
model = AutoModelForTokenClassification.from_pretrained(
    "microsoft/layoutlmv3-base",
    num_labels=7  # depends on your label set
)

from PIL import Image
image = Image.open("form.png").convert("RGB")
encoding = processor(image, return_tensors="pt")
outputs = model(**encoding)
predictions = outputs.logits.argmax(-1).squeeze().tolist()

# Document QA
from transformers import pipeline
qa_pipeline = pipeline(
    "document-question-answering",
    model="microsoft/layoutlmv3-base",
    processor="microsoft/layoutlmv3-base"
)
result = qa_pipeline(image="invoice.png", question="What is the total amount?")
```

## Architecture / How It Works
LayoutLMv3 uses a single unified transformer backbone that takes three input streams: (1) text tokens from OCR with their bounding box coordinates embedded as 2D position encodings; (2) image patches from the document image encoded as visual tokens with patch position embeddings; (3) a special CLS token for classification tasks. All three streams are concatenated and processed by a standard multi-layer transformer encoder. Pre-training uses MLM on text tokens, MIM on image patches, and WPA alignment supervision to align text tokens with their corresponding image patches.

## Strengths
- Unified multimodal representation for text, layout, and visual content
- Strong performance on form and receipt understanding benchmarks
- HuggingFace Transformers native — very easy to fine-tune and deploy
- Compact base model (133M) enables fast inference
- Part of well-regarded Microsoft UniLM research family

## Limitations
- CC BY-NC-SA 4.0 license prohibits commercial use without a licensing arrangement with Microsoft
- Requires OCR as a pre-processing step (when apply_ocr=False, must provide OCR output)
- Not designed for general VQA; best on document-specific tasks
- Superseded by newer document AI models (Docling, MinerU) for extraction pipelines
- Not suitable for formula or complex scientific document content

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Docling | MIT license; end-to-end pipeline; better formula handling |
| Unstructured | Apache 2.0; ETL focus; less layout-aware at token level |
| Qwen-VL | General VLM with strong document understanding; commercial license available |
| DiT (Document Image Transformer) | Visual-only backbone; from same UniLM project |

## References
- https://github.com/microsoft/unilm/tree/master/layoutlmv3
- https://arxiv.org/abs/2204.08387 (LayoutLMv3 paper)
- https://huggingface.co/microsoft/layoutlmv3-base
- https://huggingface.co/microsoft/layoutlmv3-large

## Notes
LayoutLMv3 is the go-to academic baseline for document understanding tasks involving forms, invoices, and receipts. The CC BY-NC-SA license makes it unsuitable for commercial products without a licensing arrangement. For commercial document AI, consider Docling (MIT) for extraction pipelines, or Qwen-VL for layout-aware document QA. LayoutLMv3 remains valuable for research, benchmarking, and internal enterprise tools that don't constitute commercial redistribution.
