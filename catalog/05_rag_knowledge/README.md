# 05 - RAG & Knowledge Management

> Retrieval-Augmented Generation : vector databases, embeddings, patterns et frameworks

## Vue d'ensemble
RAG (Retrieval-Augmented Generation) est le pattern le plus important pour connecter les LLMs aux données enterprise. Cette catégorie couvre les bases vectorielles, modèles d'embeddings, patterns RAG avancés et frameworks d'implémentation.

## Sous-catégories

### Vector Databases
- [ ] Pinecone - Managed vector DB
- [ ] Qdrant - Open source vector search
- [ ] ChromaDB - Open source embedding DB
- [ ] Milvus - Scalable vector DB
- [ ] Weaviate - AI-native vector DB
- [ ] pgvector - PostgreSQL extension

### Embeddings
- [ ] OpenAI Embeddings
- [ ] Voyage AI - Embeddings optimisés pour RAG
- [ ] Cohere Embed
- [ ] Sentence Transformers (open source)

### Patterns RAG
- [ ] Naive RAG - Base retrieval
- [ ] Advanced RAG - Re-ranking, query expansion
- [ ] Graph RAG - Knowledge graph + RAG
- [ ] Agentic RAG - Agents + RAG
- [ ] Contextual Retrieval (Anthropic)

### Frameworks
- [ ] LlamaIndex - Data framework for LLMs
- [ ] Haystack (deepset) - NLP framework
- [ ] RAGAS - RAG evaluation framework

## Matrice de Décision

| Besoin | Outil Recommandé |
|--------|-----------------|
| Managed, zero-ops | Pinecone |
| Open source, self-hosted | Qdrant ou Milvus |
| PostgreSQL existant | pgvector |
| Prototype rapide | ChromaDB |
| Framework RAG complet | LlamaIndex |
| Évaluation RAG | RAGAS |
