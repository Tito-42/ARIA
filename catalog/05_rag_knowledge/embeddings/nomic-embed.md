# Nomic Embed

> Modeles d'embedding open source haute performance avec dimensions variables et support multimodal

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 05_rag_knowledge |
| **URL** | https://www.nomic.ai |
| **GitHub** | https://github.com/nomic-ai/contrastors |
| **Stars** | ~781 (contrastors), ~1,900 (nomic client) |
| **License** | Apache-2.0 |
| **Pricing** | Free (modeles open source), Nomic Atlas API: free tier + usage-based |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Nomic Embed est une famille de modeles d'embedding open source developpes par Nomic AI, offrant des performances competitives avec les modeles proprietaires tout en etant entierement ouverts (poids, code d'entrainement, donnees). La famille comprend des modeles texte et vision.

Le modele phare nomic-embed-text-v2-moe utilise une architecture Mixture of Experts (MoE) pour combiner haute performance et efficacite. Nomic Embed supporte les representations Matryoshka (dimensions variables), permettant de reduire la taille des embeddings sans reentrainement.

Nomic se distingue egalement par sa plateforme Atlas qui permet de visualiser et explorer des millions de points de donnees embeddes de maniere interactive.

## Key Features
- **nomic-embed-text-v2-moe** : modele texte MoE, state-of-the-art open source
- **nomic-embed-text-v1.5** : modele texte standard, 768 dimensions
- **nomic-embed-vision-v1.5** : modele vision pour images
- **nomic-xlm-2048** : modele multilingual, context window 2048 tokens
- **Matryoshka representations** : dimensions variables (64, 128, 256, 384, 768)
- **Open weights** : tous les poids disponibles sur Hugging Face
- **Open training** : code d'entrainement et donnees publics
- **Flash Attention** : optimise pour l'inference rapide
- **Multi-GPU training** : support distribue pour le fine-tuning
- **Nomic Atlas** : plateforme de visualisation des embeddings

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Modeles stables, utilises en production, mais ecosystem plus jeune |
| **Security** | 5 | Open source, execution locale, pas de dependance API |
| **Scalability** | 4 | Modeles legers, Flash Attention, inference rapide |
| **Support/Community** | 3 | Communaute en croissance, Nomic AI startup |
| **Documentation** | 3 | Documentation correcte, blog technique, mais moins fournie que Sentence Transformers |
| **Integration Ease** | 4 | Compatible Sentence Transformers, Hugging Face, LlamaIndex |

## Use Cases
1. **RAG open source** : alternative open source aux embeddings proprietaires
2. **Visualisation de donnees** : exploration de corpus via Atlas
3. **Applications edge/locale** : modeles legers pour inference sans cloud
4. **Fine-tuning custom** : code d'entrainement ouvert pour adaptation domaine

## Getting Started
```python
# Via Sentence Transformers
from sentence_transformers import SentenceTransformer

model = SentenceTransformer("nomic-ai/nomic-embed-text-v1.5", trust_remote_code=True)
embeddings = model.encode(["search_document: Mon texte a embedder"])

# Via Nomic SDK + Atlas
import nomic
from nomic import embed

output = embed.text(
    texts=["Texte 1", "Texte 2"],
    model="nomic-embed-text-v1.5",
    task_type="search_document"
)

# Dimensions reduites (Matryoshka)
embeddings_256d = model.encode(["search_query: ma question"], output_value="sentence_embedding")
# Puis truncate a 256 dimensions
```

## Architecture / How It Works
```
Texte input (avec prefixe task)
    ↓
Tokenizer (custom)
    ↓
Transformer Encoder
┌─────────────────────┐
│ v2-moe: MoE layers  │ → Mixture of Experts pour efficacite
│ v1.5: Standard      │ → Architecture BERT-like
└─────────────────────┘
    ↓
Mean Pooling + Normalisation
    ↓
Matryoshka Embedding [float32 x N dim]
(tronquable a 64/128/256/384/768)
```

## Strengths
- **Entierement open source** : poids, code d'entrainement, donnees
- Performance competitive avec les modeles proprietaires
- Matryoshka dimensions pour flexibilite stockage/precision
- Architecture MoE (v2) pour efficacite
- Atlas pour visualisation interactive des embeddings
- Compatible Sentence Transformers (drop-in replacement)

## Limitations
- **Communaute** : plus petite que Sentence Transformers ou OpenAI
- **Ecosystem** : moins d'integrations directes que les leaders
- **Documentation** : moins complete que Sentence Transformers
- **Modeles vision** : moins mature que les modeles texte
- **Context window** : 2048 tokens pour le multilingual (limite)

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Sentence Transformers | Ecosysteme plus large, 15K+ modeles, mais pas de visualisation |
| OpenAI Embeddings | API simple, pas de GPU, mais proprietaire |
| Cohere Embed v3 | Meilleur multilingual, compression, mais proprietaire |
| BGE (BAAI) | Open source concurrent, bons benchmarks |

## References
- [Site officiel Nomic](https://www.nomic.ai)
- [GitHub Contrastors](https://github.com/nomic-ai/contrastors)
- [Hugging Face - Nomic AI](https://huggingface.co/nomic-ai)
- [Nomic Atlas](https://atlas.nomic.ai)
- [Blog technique](https://blog.nomic.ai)

## Notes
- Les prefixes task (search_document:, search_query:, clustering:, classification:) sont importants pour de bonnes performances
- nomic-embed-text-v2-moe est le meilleur modele de la famille
- La plateforme Atlas est unique pour la visualisation et l'exploration de donnees embeddes
- Compatible avec fastembed de Qdrant pour une inference sans PyTorch
