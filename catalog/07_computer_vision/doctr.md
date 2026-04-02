# DocTR

> OCR deep learning par Mindee — pure PyTorch/TensorFlow, Apache 2.0, production-friendly.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 07 - Computer Vision / OCR |
| **URL** | https://mindee.github.io/doctr |
| **GitHub** | https://github.com/mindee/doctr |
| **Stars** | ~6,000 |
| **License** | Apache 2.0 |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
DocTR est une bibliothèque OCR deep learning développée par Mindee, conçue pour la production. Contrairement à PaddleOCR (PaddlePaddle) et Surya (GPL), DocTR est Apache 2.0 et pure PyTorch/TensorFlow, ce qui la rend idéale pour l'intégration enterprise dans l'écosystème ML standard.

DocTR inclut un template FastAPI pour le déploiement en production.

## Key Features
- **Apache 2.0**: Licence permissive pour commercial
- **PyTorch + TensorFlow**: Dual backend
- **FastAPI template**: Prêt pour la production
- **Text detection + recognition**: Pipeline OCR complet
- **Modèles optimisés**: CRNN, SAR, ViTSTR
- **Document understanding**: Layout + OCR

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | FastAPI template, Apache 2.0 |
| **Security** | 5 | Apache 2.0, self-hosted, pas de licence restrictive |
| **Scalability** | 3 | Batch processing, FastAPI |
| **Support/Community** | 3 | 6k stars, Mindee backing |
| **Documentation** | 4 | Docs complètes, API reference |
| **Integration Ease** | 5 | PyTorch natif, FastAPI template |

## Use Cases
1. **OCR production** — Déployer un service OCR avec licence Apache 2.0
2. **Document processing** — Extraction de texte dans l'écosystème PyTorch
3. **API OCR** — Service REST via le template FastAPI

## Getting Started
```python
from doctr.io import DocumentFile
from doctr.models import ocr_predictor

model = ocr_predictor(pretrained=True)
doc = DocumentFile.from_pdf("document.pdf")
result = model(doc)
print(result.export())
```

## Architecture / How It Works
DocTR utilise un pipeline détection (DBNet) + reconnaissance (CRNN/SAR/ViTSTR). Les documents sont d'abord analysés pour détecter les zones de texte, puis chaque zone est reconnue individuellement. Le template FastAPI wrappe le pipeline pour le serving REST.

## Strengths
- Apache 2.0 — licence la plus permissive
- PyTorch/TensorFlow natif
- FastAPI template production-ready
- Mindee backing commercial

## Limitations
- Moins de langues que PaddleOCR (100+) ou Surya (90+)
- Communauté plus petite
- Pas de LaTeX OCR

## Alternatives
| Tool | Key Difference |
|------|---------------|
| PaddleOCR | 100+ langues, mais PaddlePaddle dependency |
| Surya | LaTeX OCR, mais GPL licence |
| EasyOCR | Simple, mais moins performant |

## References
- https://mindee.github.io/doctr
- https://github.com/mindee/doctr

## Notes
DocTR est le meilleur choix OCR quand la licence Apache 2.0 et l'écosystème PyTorch sont des requirements. Pour la couverture linguistique maximale, PaddleOCR reste supérieur.
