# Blueprint : Chatbot Enterprise avec RAG

> Architecture complete pour un chatbot d'entreprise connecte aux donnees internes

## Besoins Identifies
- Chatbot conversationnel pour employes ou clients
- Acces aux documents internes (policies, procedures, FAQ)
- Reponses precises et sourcees (pas d'hallucination)
- Securite et controle d'acces

## Stack Recommande

| Composant | Outil | Alternative | Categorie |
|-----------|-------|-------------|-----------|
| LLM principal | Claude Sonnet 4.6 | GPT-4o | 12 |
| LLM fallback | Haiku 4.5 | GPT-4o-mini | 12 |
| Framework RAG | LlamaIndex | LangChain | 05 |
| Vector DB | Qdrant | Pinecone, pgvector | 05 |
| Embeddings | Voyage AI | OpenAI text-embedding-3 | 05 |
| Document Parsing | Unstructured + Marker | Docling | 17 |
| Extraction structuree | Instructor | Outlines | 08 |
| AI Gateway | LiteLLM | Portkey | 12 |
| Observabilite | Langfuse | LangSmith | 16 |
| Guardrails | NeMo Guardrails | Guardrails AI | 16 |
| Frontend | React + Vercel AI SDK | CopilotKit | 04 |

## Architecture
```
┌─────────────────────────────────────────────────┐
│                    FRONTEND                      │
│  React App + Vercel AI SDK (streaming)           │
└────────────────────┬────────────────────────────┘
                     │
┌────────────────────▼────────────────────────────┐
│                  AI GATEWAY                       │
│  LiteLLM (routing, caching, rate limiting)       │
│  + Langfuse (observabilite)                      │
│  + NeMo Guardrails (securite)                    │
└────────────────────┬────────────────────────────┘
                     │
┌────────────────────▼────────────────────────────┐
│              RAG PIPELINE                        │
│                                                  │
│  1. Query → Embedding (Voyage AI)                │
│  2. Vector Search (Qdrant) → Top-K docs          │
│  3. Re-ranking (Cohere Rerank)                   │
│  4. Prompt Construction (contexte + question)     │
│  5. LLM Generation (Claude Sonnet 4.6)           │
│  6. Source Attribution (citations)                │
└────────────────────┬────────────────────────────┘
                     │
┌────────────────────▼────────────────────────────┐
│           KNOWLEDGE BASE                         │
│                                                  │
│  Documents → Unstructured (parsing)              │
│           → Marker (PDF → Markdown)              │
│           → Chunking (LlamaIndex)                │
│           → Embedding (Voyage AI)                │
│           → Qdrant (stockage vectoriel)          │
│                                                  │
│  Sources: SharePoint, Confluence, Google Drive,  │
│           PDF policies, FAQ, procedures          │
└──────────────────────────────────────────────────┘
```

## Pipeline d'Ingestion des Documents
```
1. Collecte (SharePoint API, Google Drive API, file system)
2. Parsing (Unstructured pour multi-format)
3. Conversion (Marker pour PDF → Markdown)
4. Chunking semantique (LlamaIndex, 512-1024 tokens)
5. Embedding (Voyage AI, batch processing)
6. Indexation (Qdrant, metadata enrichment)
7. Validation (RAGAS pour evaluer la qualite)
```

## Estimation de Complexite
- **Setup initial** : 2-4 semaines (MVP)
- **Production-ready** : 6-10 semaines (guardrails, observabilite, tests)
- **Equipe** : 1-2 devs backend + 1 frontend
- **Cout mensuel** : $200-2000 selon le volume (API + infra)

## Justification des Choix
- **Claude Sonnet 4.6** : meilleur rapport qualite/cout pour le conversationnel
- **Qdrant** : open source, self-hostable, performant, API simple
- **Voyage AI** : embeddings optimises pour RAG (meilleur que OpenAI sur retrieval)
- **Langfuse** : open source, self-hostable, pas de vendor lock-in
- **LlamaIndex** : plus specialise RAG que LangChain, API plus simple

## Points d'Attention
- **Hallucinations** : toujours sourcer les reponses, utiliser des guardrails
- **Fresh data** : pipeline d'ingestion doit tourner regulierement (daily/hourly)
- **Permissions** : respecter les ACLs des documents sources
- **Evaluation** : utiliser RAGAS pour mesurer la qualite continuellement
