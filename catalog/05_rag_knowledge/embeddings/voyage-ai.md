# Voyage AI Embeddings

> Modeles d'embedding et de reranking haute performance specialises pour le retrieval

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 05_rag_knowledge |
| **URL** | https://www.voyageai.com |
| **GitHub** | https://github.com/voyage-ai/voyageai-python |
| **Stars** | ~95 (client Python) |
| **License** | MIT (client), Proprietary (modeles) |
| **Pricing** | API usage-based: voyage-3: $0.06/1M tokens, voyage-3-lite: $0.02/1M tokens, free tier disponible |
| **Last Verified** | 2026-04-01 |
| **Status** | Active (acquis par Pinecone en 2025) |
| **Maturity** | Production |

## What It Does
Voyage AI fournit des modeles d'embedding et de reranking de pointe, specialement optimises pour les taches de retrieval et de RAG. Fonde par des chercheurs de Stanford, Voyage AI s'est distingue par des performances superieures aux embeddings OpenAI sur de nombreux benchmarks MTEB, particulierement dans les domaines specialises (code, juridique, finance).

En 2025, Voyage AI a ete acquis par Pinecone, integrant ses modeles directement dans l'infrastructure Pinecone. Les modeles restent accessibles via API independante et continuent d'etre mis a jour.

Voyage AI supporte l'embedding de texte, images, audio, video et donnees tabulaires, ainsi que des modeles de reranking pour ameliorer la precision du retrieval.

## Key Features
- **voyage-3** : modele phare, meilleur que text-embedding-3-large sur MTEB retrieval
- **voyage-3-lite** : version plus legere et economique
- **voyage-code-3** : specialise pour le code source
- **voyage-finance-2** : optimise pour le domaine financier
- **voyage-law-2** : optimise pour le domaine juridique
- **Reranking models** : reranker-2, reranker-2-lite pour ameliorer la precision
- **Multimodal** : embedding de texte, images, audio, video, tabulaire
- **Context window** : jusqu'a 32K tokens pour certains modeles
- **Batch processing** : traitement par lots efficace

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Utilise en production, acquis par Pinecone |
| **Security** | 4 | API securisee, maintenant sous Pinecone (SOC 2) |
| **Scalability** | 4 | API scalable, rate limits raisonnables |
| **Support/Community** | 3 | Communaute plus petite que OpenAI, mais support Pinecone |
| **Documentation** | 4 | Bonne documentation, exemples |
| **Integration Ease** | 4 | SDK Python simple, integrations LlamaIndex/LangChain |

## Use Cases
1. **RAG haute precision** : quand la qualite du retrieval est critique
2. **Retrieval de code** : recherche semantique dans des codebases
3. **Domaines specialises** : finance, juridique, medical avec modeles dedies
4. **Reranking pipeline** : amelioration de la precision d'un pipeline RAG existant

## Getting Started
```python
import voyageai

client = voyageai.Client(api_key="YOUR_API_KEY")

# Embedding
result = client.embed(
    ["Texte a embedder", "Autre texte"],
    model="voyage-3",
    input_type="document"
)
vectors = result.embeddings

# Reranking
reranking = client.rerank(
    query="ma question",
    documents=["doc1", "doc2", "doc3"],
    model="reranker-2"
)
```

## Architecture / How It Works
```
Texte/Image/Audio input → Voyage AI API
                              ↓
                    Preprocessing specifique au domaine
                              ↓
                    Transformer Encoder (proprietaire)
                    (optimise pour retrieval)
                              ↓
                    Vecteur dense normalise

Query + Documents → Reranker API
                        ↓
                    Cross-Encoder (proprietaire)
                        ↓
                    Scores de pertinence
```

## Strengths
- Performance superieure a OpenAI embeddings sur les benchmarks retrieval
- Modeles specialises par domaine (code, finance, juridique)
- Reranking integre pour pipeline RAG complet
- Context window tres large (32K tokens)
- Integration Pinecone native suite a l'acquisition

## Limitations
- **Proprietaire** : pas de modele local, dependance API
- **Communaute** : plus petite que OpenAI ou Sentence Transformers
- **Acquisition Pinecone** : incertitude sur l'avenir en tant qu'API independante
- **Cout** : plus cher que OpenAI text-embedding-3-small
- **Moins d'integrations** : moins ubiquitaire que les embeddings OpenAI

## Alternatives
| Tool | Key Difference |
|------|---------------|
| OpenAI Embeddings | Plus ubiquitaire, moins cher, mais performances retrieval inferieures |
| Cohere Embed v3 | Multilingual superieur, compression int8/binary native |
| Sentence Transformers | Open source, local, fine-tunable, gratuit |
| Nomic Embed | Open source, performant, communaute Nomic |

## References
- [Site officiel](https://www.voyageai.com)
- [Documentation](https://docs.voyageai.com)
- [GitHub Python Client](https://github.com/voyage-ai/voyageai-python)
- [Blog technique](https://blog.voyageai.com)

## Notes
- Acquis par Pinecone en 2025 - modeles integres dans Pinecone Inference
- voyage-3 est recommande comme premier choix pour le retrieval haute precision
- Les modeles domain-specific sont un avantage competitif unique
- Le reranker-2 peut significativement ameliorer la precision de n'importe quel pipeline RAG
