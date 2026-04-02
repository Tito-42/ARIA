# Unstructured

> ETL pour documents non structurés — parse PDF, DOCX, HTML, images en texte structuré pour RAG/NLP.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 08 - NLP & Text / Document Processing |
| **URL** | https://unstructured.io |
| **GitHub** | https://github.com/Unstructured-IO/unstructured |
| **Stars** | ~14,400 |
| **License** | Apache 2.0 |
| **Pricing** | Free (OSS) / Unstructured API (Paid SaaS) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Unstructured est une bibliothèque ETL qui parse des documents non structurés (PDF, DOCX, HTML, PowerPoint, images, emails) en éléments de texte structurés, prêts pour l'ingestion dans des pipelines RAG ou NLP. C'est le bridge entre les documents bruts et les applications IA.

## Key Features
- **Multi-format**: PDF, DOCX, HTML, PPTX, XLSX, images, emails
- **Partitioning**: Découpage intelligent en éléments (titres, paragraphes, tables)
- **Chunking**: Stratégies de chunking pour RAG
- **Connectors**: S3, GCS, Azure, Elasticsearch, Pinecone, etc.
- **OCR intégré**: Extraction de texte depuis images
- **API SaaS**: Unstructured API pour processing cloud

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Production, pipeline RAG standard |
| **Security** | 4 | Apache 2.0, self-hosted possible |
| **Scalability** | 4 | API SaaS ou batch processing |
| **Support/Community** | 4 | 14.4k stars |
| **Documentation** | 4 | Docs complètes |
| **Integration Ease** | 4 | Connectors pour sources et destinations |

## Use Cases
1. **RAG ingestion** — Parser des documents pour vector stores
2. **Document ETL** — Pipeline d'extraction de contenu multi-format
3. **Knowledge base** — Construire des bases de connaissances depuis des documents

## Getting Started
```python
from unstructured.partition.auto import partition
elements = partition(filename="document.pdf")
for element in elements:
    print(type(element).__name__, element.text[:100])
```

## Architecture / How It Works
Unstructured utilise des stratégies de partitioning par format : PDFMiner/Tesseract pour PDF, python-docx pour DOCX, BeautifulSoup pour HTML. Les éléments sont classifiés (Title, NarrativeText, Table, etc.) et peuvent être chunkés pour le RAG.

## Strengths
- Multi-format le plus complet
- Chunking intégré pour RAG
- Apache 2.0
- Connectors pour cloud storage et vector stores

## Limitations
- Peut être lourd (many dependencies)
- Certaines features avancées payantes (API SaaS)
- Qualité variable selon la complexité du document

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Marker | PDF→Markdown haute fidélité, GPL |
| LlamaIndex | Framework RAG complet, pas juste parsing |
| Docling (IBM) | Document understanding, Apache 2.0 |

## References
- https://docs.unstructured.io
- https://github.com/Unstructured-IO/unstructured

## Notes
Unstructured est le choix par défaut pour le document ETL dans les pipelines RAG. Pour du PDF→Markdown spécifiquement, Marker est supérieur en fidélité mais a une licence restrictive.
