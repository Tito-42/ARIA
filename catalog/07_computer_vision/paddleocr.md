# PaddleOCR

> Suite OCR complète par Baidu — 100+ langues, détection + reconnaissance + layout analysis, référence production.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 07 - Computer Vision / OCR |
| **URL** | https://github.com/PaddlePaddle/PaddleOCR |
| **GitHub** | https://github.com/PaddlePaddle/PaddleOCR |
| **Stars** | ~74,600 |
| **License** | Apache 2.0 |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
PaddleOCR est la suite OCR la plus complète en open-source, développée par Baidu. Elle couvre l'ensemble du pipeline OCR : détection de texte, reconnaissance, layout analysis, et extraction de tableaux. Avec 100+ langues supportées et des modèles ultra-légers pour l'edge, c'est la référence production.

PaddleOCR est basé sur le framework PaddlePaddle (et non PyTorch), mais fournit des modèles ONNX exportables pour l'intégration dans d'autres écosystèmes.

## Key Features
- **100+ langues**: La couverture linguistique la plus large
- **Pipeline complet**: Détection → reconnaissance → layout → tables
- **Modèles légers**: PP-OCR mobile/server pour différents budgets
- **Layout analysis**: Extraction structurée de documents
- **Table recognition**: Extraction de tableaux
- **NPU support**: Huawei Ascend, Kunlunxin

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | Référence production OCR, 74.6k stars |
| **Security** | 4 | Apache 2.0, self-hosted |
| **Scalability** | 5 | Modèles server/mobile, batch processing |
| **Support/Community** | 5 | 74.6k stars, Baidu backing |
| **Documentation** | 4 | Docs complètes (anglais + chinois) |
| **Integration Ease** | 3 | PaddlePaddle dependency, ONNX export disponible |

## Use Cases
1. **Document processing** — OCR de documents, factures, formulaires
2. **Multilingual OCR** — Extraction de texte en 100+ langues
3. **Layout analysis** — Extraction structurée avec tables et colonnes

## Getting Started
```python
from paddleocr import PaddleOCR

ocr = PaddleOCR(use_angle_cls=True, lang='en')
result = ocr.ocr('document.jpg', cls=True)

for line in result[0]:
    print(line[1][0], line[1][1])  # texte, confiance
```

## Architecture / How It Works
PaddleOCR utilise un pipeline en 3 étapes : (1) Text Detection (DB, EAST) pour localiser le texte, (2) Text Recognition (CRNN, SVTR) pour lire le texte, (3) optionnellement, Layout Analysis pour comprendre la structure du document. Les modèles PP-OCR sont optimisés pour le bon ratio vitesse/précision.

## Strengths
- Référence production OCR, 74.6k stars
- 100+ langues
- Pipeline complet (détection, reconnaissance, layout, tables)
- Apache 2.0

## Limitations
- Dépend de PaddlePaddle (pas PyTorch natif)
- Documentation parfois meilleure en chinois
- ONNX export nécessaire pour intégration hors PaddlePaddle

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Surya OCR | 90+ langues, LaTeX OCR, PyTorch natif |
| DocTR | Apache 2.0, PyTorch/TensorFlow natif, plus léger |
| Tesseract | Historique, moins précis, mais très simple |

## References
- https://github.com/PaddlePaddle/PaddleOCR
- https://paddleocr.bj.bcebos.com/doc/doc_en/

## Notes
PaddleOCR est le choix production pour l'OCR multi-langues. Si la dépendance PaddlePaddle est un problème, Surya (PyTorch) ou DocTR (PyTorch) sont des alternatives dans l'écosystème PyTorch.
