# Cohere Embed v3

> Modele d'embedding multilingual avec compression native pour la recherche semantique

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 05_rag_knowledge |
| **URL** | https://cohere.com/embed |
| **GitHub** | N/A (API proprietaire, SDK: https://github.com/cohere-ai/cohere-python) |
| **Stars** | N/A |
| **License** | Proprietary (API commerciale) |
| **Pricing** | embed-v3.0: $0.10/1M tokens, embed-english-light-v3.0: $0.10/1M tokens, free trial disponible |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Enterprise |

## What It Does
Cohere Embed v3 est la troisieme generation de modeles d'embedding de Cohere, concue pour la recherche semantique multilingual de haute qualite. Le modele se distingue par son support natif de la compression des embeddings (int8 et binary), permettant de reduire drastiquement les couts de stockage sans perte significative de qualite.

Embed v3 excelle particulierement en contexte multilingual, supportant plus de 100 langues avec des performances elevees. Le modele introduit egalement un systeme d'input types (search_document, search_query, classification, clustering) qui optimise les embeddings selon le cas d'usage.

Cohere fournit aussi un modele de reranking (Rerank) qui peut etre combine avec les embeddings pour ameliorer la precision du retrieval.

## Key Features
- **Multilingual** : 100+ langues avec performances elevees
- **Compression native** : embeddings int8 et binary pour reduction drastique du stockage
- **Input types** : search_document, search_query, classification, clustering
- **embed-english-v3.0** : 1024 dimensions, optimise anglais
- **embed-multilingual-v3.0** : 1024 dimensions, 100+ langues
- **embed-english-light-v3.0** : 384 dimensions, leger et rapide
- **Rerank** : modele de reranking complementaire
- **Batch processing** : jusqu'a 96 textes par appel
- **Context window** : 512 tokens par texte

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | Utilise en production par des enterprises, Cohere for AI |
| **Security** | 5 | SOC 2, deploiement on-premise possible (Cohere Toolkit), HIPAA |
| **Scalability** | 5 | API scalable, compression reduit les couts de stockage |
| **Support/Community** | 4 | Support enterprise Cohere, documentation solide |
| **Documentation** | 4 | Bonne documentation, guides multilingual |
| **Integration Ease** | 4 | SDK Python/Node/Java/Go, integrations vector DB |

## Use Cases
1. **RAG multilingual** : recherche semantique sur des corpus en plusieurs langues
2. **E-commerce international** : recherche de produits cross-language
3. **Enterprise search** : recherche interne sur des documents dans differentes langues
4. **Classification multilingual** : categorisation de documents independamment de la langue

## Getting Started
```python
import cohere

co = cohere.Client("YOUR_API_KEY")

# Embedding de documents
response = co.embed(
    texts=["Texte a embedder", "Another text"],
    model="embed-multilingual-v3.0",
    input_type="search_document",
    embedding_types=["float", "int8", "binary"]  # compression native
)
float_embeddings = response.embeddings.float
int8_embeddings = response.embeddings.int8  # 4x moins de stockage
binary_embeddings = response.embeddings.binary  # 32x moins de stockage

# Reranking
rerank_response = co.rerank(
    query="ma question",
    documents=["doc1", "doc2", "doc3"],
    model="rerank-multilingual-v3.0"
)
```

## Architecture / How It Works
```
Texte input → Cohere API
                  ↓
          Tokenizer multilingual
                  ↓
          Transformer Encoder
          (modele proprietaire, 100+ langues)
                  ↓
          Embedding + Input Type Optimization
                  ↓
          ┌─────────────────┐
          │ float32 (1024d) │ → Precision maximale
          │ int8 (1024d)    │ → 4x compression
          │ binary (1024d)  │ → 32x compression
          └─────────────────┘
```

## Strengths
- Meilleur modele multilingual du marche (100+ langues)
- Compression int8/binary native - reduction massive des couts de stockage
- Input types optimisent les embeddings par cas d'usage
- Reranking multilingual complementaire
- Option de deploiement on-premise pour la privacy

## Limitations
- **Proprietaire** : pas open source (sauf Cohere Toolkit)
- **Context window** : 512 tokens par defaut, plus court que OpenAI (8191)
- **Cout** : plus cher que OpenAI text-embedding-3-small
- **Communaute** : moins large que OpenAI
- **Dimensions** : 1024 dimensions max (vs 3072 pour OpenAI large)

## Alternatives
| Tool | Key Difference |
|------|---------------|
| OpenAI Embeddings | Plus ubiquitaire, context window plus long, mais multilingual inferieur |
| Voyage AI | Meilleur pour retrieval anglais et domaines specialises |
| Sentence Transformers | Open source, local, fine-tunable |
| Nomic Embed | Open source, dimensions variables |
| BGE-M3 | Open source, multilingual, hybrid dense+sparse |

## References
- [Documentation Embed](https://docs.cohere.com/docs/embeddings)
- [Blog Embed v3](https://cohere.com/blog/introducing-embed-v3)
- [Documentation Rerank](https://docs.cohere.com/docs/reranking)
- [Cohere SDK Python](https://github.com/cohere-ai/cohere-python)

## Notes
- La compression binary (32x) est un game-changer pour les deployments a grande echelle
- L'utilisation d'input types est importante pour des performances optimales
- Le context window de 512 tokens est une limitation significative pour les longs documents
- Cohere propose aussi un deploiement on-premise (Cohere Platform) pour les entreprises sensibles
