# OpenAI Embeddings

> Modeles d'embedding de texte par OpenAI pour la recherche semantique et le RAG

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 05_rag_knowledge |
| **URL** | https://platform.openai.com/docs/guides/embeddings |
| **GitHub** | N/A (API proprietaire) |
| **Stars** | N/A |
| **License** | Proprietary (API commerciale) |
| **Pricing** | text-embedding-3-small: $0.02/1M tokens, text-embedding-3-large: $0.13/1M tokens |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Enterprise |

## What It Does
OpenAI Embeddings est un service API qui convertit du texte en vecteurs numeriques denses capturant le sens semantique. Ces vecteurs peuvent etre utilises pour la recherche semantique, le clustering, la classification et le RAG (Retrieval-Augmented Generation).

La generation text-embedding-3 (lancee en janvier 2024) a apporte des ameliorations significatives en performance et en flexibilite par rapport a la generation precedente (ada-002), avec notamment le support des dimensions variables (Matryoshka representations) permettant de choisir entre precision et cout de stockage.

Les embeddings OpenAI restent le choix par defaut pour de nombreuses applications RAG en raison de leur facilite d'utilisation, leur performance solide sur les benchmarks MTEB, et leur integration transparente dans l'ecosysteme LLM.

## Key Features
- **text-embedding-3-small** : 1536 dimensions, performant et economique ($0.02/1M tokens)
- **text-embedding-3-large** : 3072 dimensions, performance maximale ($0.13/1M tokens)
- **Dimensions variables** : reduction de dimensions via Matryoshka representations (ex: 256, 512, 1024)
- **Performance MTEB** : scores competitifs sur le benchmark MTEB
- **Batch processing** : jusqu'a 2048 textes par appel API
- **Multilingual** : support de dizaines de langues
- **Context window** : jusqu'a 8191 tokens par texte
- **Normalisation** : vecteurs normalises pour cosine similarity

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | API enterprise battle-tested, SLA disponible |
| **Security** | 4 | SOC 2, donnees non utilisees pour training, mais cloud-only |
| **Scalability** | 5 | API scalable, rate limits geneureux en tier enterprise |
| **Support/Community** | 5 | Documentation OpenAI, immense communaute, support enterprise |
| **Documentation** | 5 | Docs completes, cookbooks, exemples |
| **Integration Ease** | 5 | API simple, SDKs officiels, integrations partout |

## Use Cases
1. **RAG standard** : embedding de documents pour recherche semantique dans des pipelines RAG
2. **Recherche semantique** : moteur de recherche par sens plutot que par mots-cles
3. **Classification de texte** : clustering et categorisation de documents
4. **Detection de similarite** : deduplication, plagiat, recommandation

## Getting Started
```python
from openai import OpenAI
client = OpenAI()

# Embedding simple
response = client.embeddings.create(
    input="Texte a embedder",
    model="text-embedding-3-small"
)
vector = response.data[0].embedding  # [0.023, -0.041, ...]

# Avec dimensions reduites
response = client.embeddings.create(
    input="Texte a embedder",
    model="text-embedding-3-large",
    dimensions=512  # reduction de 3072 a 512
)
```

## Architecture / How It Works
```
Texte input → OpenAI API
                  ↓
          Tokenization (tiktoken)
                  ↓
          Transformer Encoder
          (modele proprietaire)
                  ↓
          Pooling + Normalisation
                  ↓
          Vecteur dense [float32 x N dimensions]
```

## Strengths
- Facilite d'utilisation extreme (une ligne de code)
- Performance solide et constante sur les benchmarks
- Dimensions variables via Matryoshka pour optimiser stockage/cout
- Excellent support multilingual
- Ecosysteme d'integrations le plus large (LangChain, LlamaIndex, tous les vector DB)
- Pricing competitif (text-embedding-3-small est tres abordable)

## Limitations
- **Cloud-only** : pas de version locale, dependance API
- **Proprietaire** : impossible d'auditer ou fine-tuner le modele
- **Latence reseau** : appel API pour chaque embedding
- **Privacy** : les donnees transitent par les serveurs OpenAI
- **Pas le meilleur** : depasse par des modeles specialises (Voyage AI, Cohere) sur certains benchmarks
- **Pas de sparse embeddings** : uniquement dense, pas de hybrid search natif

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Voyage AI | Meilleur sur certains benchmarks, specialise retrieval |
| Cohere Embed v3 | Multilingual superieur, compression int8/binary |
| Sentence Transformers | Open source, local, fine-tunable |
| Nomic Embed | Open source, performant, dimensions variables |
| Google Gecko | Alternative Google, multilingual |

## References
- [Documentation officielle](https://platform.openai.com/docs/guides/embeddings)
- [OpenAI Cookbook - Embeddings](https://cookbook.openai.com/examples/search_reranking)
- [MTEB Leaderboard](https://huggingface.co/spaces/mteb/leaderboard)

## Notes
- text-embedding-3-small a un excellent ratio performance/cout pour la plupart des use cases
- La feature Matryoshka dimensions est tres utile pour optimiser le stockage (256 dim au lieu de 1536)
- Pour les cas sensibles en termes de privacy, preferer Sentence Transformers ou Nomic Embed en local
- text-embedding-ada-002 est deprece en faveur de la serie text-embedding-3
