# Guide : Document AI - Parsing et Extraction

> Comment extraire des donnees structurees de documents (PDF, images, scans) avec l'IA

## Problem
Les entreprises traitent des millions de documents (factures, contrats, rapports, formulaires) mais l'extraction de donnees reste largement manuelle. Le Document AI combine OCR, NLP et vision pour automatiser ce processus.

## Solution
Un pipeline de document parsing moderne combine plusieurs etapes :

## Architecture Pipeline
```
Document Input (PDF, image, scan, DOCX)
    |
    v
1. INGESTION (Unstructured, Docling)
    ├── Detection du type de document
    ├── Extraction de la structure (titres, paragraphes, tableaux)
    └── OCR si necessaire (Surya, DocTR, Tesseract)
    |
    v
2. PARSING (Marker, Docling)
    ├── Conversion en Markdown/JSON structure
    ├── Extraction de tableaux
    └── Gestion des images embarquees
    |
    v
3. CHUNKING (LlamaIndex, LangChain)
    ├── Decoupe semantique
    ├── Preservation de la structure
    └── Metadata enrichment
    |
    v
4. EMBEDDING + INDEXATION (Vector DB)
    ├── Embeddings (Voyage AI, OpenAI, Cohere)
    └── Stockage vectoriel (Qdrant, Pinecone, pgvector)
    |
    v
5. RETRIEVAL + GENERATION (RAG)
    ├── Query → Recherche semantique
    ├── Re-ranking
    └── Generation avec LLM (Claude, GPT)
```

## Implementation avec Outils Recommandes

| Etape | Outil Recommande | Alternative | Categorie |
|-------|-----------------|-------------|-----------|
| Ingestion | Unstructured | Docling (IBM) | 17_multimodal |
| OCR | Surya | DocTR, Tesseract | 07_computer_vision |
| PDF → Markdown | Marker | Docling | 17_multimodal |
| Chunking | LlamaIndex | LangChain | 05_rag_knowledge |
| Embeddings | Voyage AI | OpenAI, Cohere | 05_rag_knowledge |
| Vector DB | Qdrant | Pinecone, pgvector | 05_rag_knowledge |
| Extraction structuree | Instructor | Outlines | 08_nlp_text |
| LLM | Claude Opus 4.6 | GPT-5.2, Gemini 3.1 | 12_enterprise |

## Outils Cles

### Unstructured
- **GitHub** : github.com/Unstructured-IO/unstructured
- **Stars** : ~10K+
- **Description** : ETL pour documents non structures, supporte PDF, DOCX, PPTX, HTML, images
- **License** : Apache 2.0

### Docling (IBM)
- **GitHub** : github.com/DS4SD/docling
- **Stars** : ~10K+
- **Description** : Parsing de documents par IBM, excellent sur les tableaux et structures complexes
- **License** : MIT

### Marker
- **GitHub** : github.com/VikParuchuri/marker
- **Stars** : ~15K+
- **Description** : Convertit PDF en Markdown avec haute fidelite
- **License** : GPL-3.0

### Surya
- **GitHub** : github.com/VikParuchuri/surya
- **Stars** : ~15K+
- **Description** : OCR multilingue (90+ langues), detection de layout, reconnaissance de tableaux
- **License** : GPL-3.0

## When to Use
- Documents a volume (>100 docs/jour)
- Extraction de donnees de contrats, factures, formulaires
- Base de connaissances enterprise depuis des documents
- Compliance et audit documentaire

## When NOT to Use
- Documents simples bien structures (CSV, JSON)
- Petit volume (<10 docs) - traitement manuel plus rapide
- Documents hautement confidentiels sans infrastructure privee

## Enterprise Considerations
- **Privacy** : Certains outils envoient des donnees au cloud. Preferer Docling/Marker/Surya pour on-premise
- **Cout** : Pipeline cloud (API embeddings + LLM) vs pipeline local (open source)
- **Qualite OCR** : Les scans de mauvaise qualite necessitent un pre-traitement
- **Tableaux** : Docling excelle sur les tableaux complexes, Marker sur le texte libre

## References
- Voir catalog/05_rag_knowledge/ pour les vector databases et RAG patterns
- Voir catalog/08_nlp_text/ pour l'extraction structuree
- Voir catalog/07_computer_vision/ocr/ pour les outils OCR
