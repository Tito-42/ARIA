# Surya OCR

> OCR multilingue avec détection de layout, reconnaissance de texte et LaTeX OCR — 90+ langues.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 07 - Computer Vision / OCR |
| **URL** | https://github.com/VikParuchuri/surya |
| **GitHub** | https://github.com/VikParuchuri/surya |
| **Stars** | ~19,500 |
| **License** | GPL / Rail-M |
| **Pricing** | Free (Open Source, restrictions commerciales) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Surya est un OCR multilingue qui se distingue par son support de 90+ langues, sa détection de layout, et surtout son OCR LaTeX pour les formules mathématiques. Développé par Vik Paruchuri (aussi créateur de Marker), Surya est particulièrement adapté aux documents académiques et techniques.

## Key Features
- **90+ langues**: Couverture linguistique large
- **LaTeX OCR**: Reconnaissance de formules mathématiques
- **Layout detection**: Détection de structure de documents
- **Text detection + recognition**: Pipeline OCR complet
- **PyTorch natif**: Intégration naturelle dans l'écosystème

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 3 | Bon mais licence restrictive |
| **Security** | 3 | GPL/Rail-M — **vérifier licence pour commercial** |
| **Scalability** | 3 | GPU recommandé, batch possible |
| **Support/Community** | 4 | 19.5k stars, communauté active |
| **Documentation** | 3 | README complet |
| **Integration Ease** | 4 | PyTorch natif, pip install |

## Use Cases
1. **Documents académiques** — OCR de papers avec formules LaTeX
2. **OCR multilingue** — Extraction de texte en 90+ langues
3. **Layout analysis** — Compréhension de structure de documents

## Getting Started
```python
from surya.ocr import run_ocr
from surya.model.detection.model import load_model as load_det
from surya.model.recognition.model import load_model as load_rec

det_model = load_det()
rec_model = load_rec()
results = run_ocr([image], [["en"]], det_model, rec_model)
```

## Architecture / How It Works
Surya utilise des modèles transformer séparés pour la détection de texte et la reconnaissance. Le pipeline LaTeX OCR utilise un modèle encoder-decoder spécialisé pour convertir les images de formules en code LaTeX.

## Strengths
- LaTeX OCR unique dans l'open-source
- 90+ langues
- PyTorch natif
- Bon pour documents académiques

## Limitations
- **Licence GPL/Rail-M** — restrictive pour usage commercial
- Moins production-ready que PaddleOCR
- Nécessite GPU pour de bonnes performances

## Alternatives
| Tool | Key Difference |
|------|---------------|
| PaddleOCR | **Recommandé production** — Apache 2.0, 100+ langues |
| DocTR | Apache 2.0, PyTorch natif |
| Marker | Même auteur, spécialisé PDF→Markdown |

## References
- https://github.com/VikParuchuri/surya

## Notes
Surya excelle pour les documents académiques avec LaTeX. Pour la production commerciale, vérifier la licence GPL/Rail-M avec le service juridique. PaddleOCR est l'alternative Apache 2.0.
