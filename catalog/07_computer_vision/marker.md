# Marker

> Convertisseur PDF/DOCX → Markdown haute fidélité — optimal pour le preprocessing RAG.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 07 - Computer Vision / Document AI |
| **URL** | https://github.com/VikParuchuri/marker |
| **GitHub** | https://github.com/VikParuchuri/marker |
| **Stars** | ~33,200 |
| **License** | GPL / Rail-M |
| **Pricing** | Free (Open Source, restrictions commerciales) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Marker convertit des PDF et DOCX en Markdown de haute fidélité, préservant la structure, les tableaux, les formules et les images. C'est l'outil optimal pour le preprocessing de documents dans les pipelines RAG, transformant des documents non structurés en texte structuré facilement indexable.

## Key Features
- **PDF → Markdown**: Conversion haute fidélité
- **Tables**: Extraction et formatage des tableaux
- **Formules**: Conversion des formules en LaTeX
- **Images**: Extraction et référencement des images
- **DOCX support**: Support Word en plus du PDF
- **Batch processing**: Conversion en lot de documents

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Très bon pour preprocessing RAG |
| **Security** | 3 | GPL/Rail-M — **vérifier licence pour commercial** |
| **Scalability** | 3 | GPU pour vitesse, batch possible |
| **Support/Community** | 5 | 33.2k stars, très populaire |
| **Documentation** | 3 | README clair |
| **Integration Ease** | 4 | CLI et API Python simples |

## Use Cases
1. **RAG preprocessing** — Convertir des PDF en Markdown pour indexation
2. **Document digitization** — Numériser des documents pour recherche
3. **Knowledge base** — Construire des bases de connaissances à partir de PDF

## Getting Started
```bash
pip install marker-pdf
marker_single input.pdf output/ --langs English
```
```python
from marker.convert import convert_single_pdf
text, images, metadata = convert_single_pdf("document.pdf")
```

## Architecture / How It Works
Marker utilise une pipeline : (1) extraction du texte natif du PDF, (2) OCR Surya pour le texte en images, (3) détection de layout pour identifier la structure, (4) conversion en Markdown avec préservation de la hiérarchie, des tableaux et des formules.

## Strengths
- Meilleure conversion PDF→Markdown du marché
- Préservation des tableaux et formules
- 33.2k stars, très populaire
- Idéal pour RAG

## Limitations
- **Licence GPL/Rail-M** — restrictive pour commercial
- Dépend de Surya pour l'OCR
- Qualité variable selon la complexité du PDF

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Unstructured.io | Plus complet, multi-format, Apache 2.0 |
| PyMuPDF | Extraction texte brut, Apache 2.0 |
| Docling (IBM) | Document understanding, Apache 2.0 |

## References
- https://github.com/VikParuchuri/marker

## Notes
Marker est le gold standard pour PDF→Markdown. La licence GPL/Rail-M est le principal frein enterprise. Unstructured.io (Apache 2.0) est l'alternative pour les entreprises ayant besoin d'une licence permissive.
