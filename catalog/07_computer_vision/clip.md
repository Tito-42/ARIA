# OpenAI CLIP

> Modèle fondateur vision-language — embeddings image-texte alignés, zero-shot classification, MIT.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 07 - Computer Vision / Foundation Model |
| **URL** | https://openai.com/research/clip |
| **GitHub** | https://github.com/openai/CLIP |
| **Stars** | ~33,000 |
| **License** | MIT |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Stable / Legacy Influent |
| **Maturity** | Production |

## What It Does
CLIP (Contrastive Language-Image Pre-training) est le modèle fondateur de l'ère vision-language par OpenAI. Il produit des embeddings alignés entre images et textes, permettant la zero-shot classification d'images, la recherche image-texte, et servant de composant dans de nombreux systèmes (Stable Diffusion, DALL-E, etc.).

Bien que supercédé par SigLIP et EVA-CLIP pour certaines tâches, CLIP reste le modèle le plus influent et le plus utilisé pour les embeddings vision-language.

## Key Features
- **Embeddings alignés**: Images et textes dans le même espace vectoriel
- **Zero-shot classification**: Classifier des images sans entraînement
- **Image-text search**: Recherche sémantique cross-modale
- **Multiple architectures**: ViT-B/32, ViT-B/16, ViT-L/14, ViT-L/14@336px
- **MIT licence**: Aucune restriction
- **Composant universel**: Utilisé dans SD, DALL-E, etc.

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | Standard, très largement déployé |
| **Security** | 5 | MIT, self-hosted |
| **Scalability** | 4 | Modèle léger, CPU possible |
| **Support/Community** | 5 | 33k stars, fondamental dans l'écosystème |
| **Documentation** | 4 | Paper, OpenAI docs, communauté |
| **Integration Ease** | 5 | Trivial via openai/CLIP ou HuggingFace |

## Use Cases
1. **Image search** — Recherche d'images par texte naturel
2. **Zero-shot classification** — Classifier des images sans labels d'entraînement
3. **Composant de pipeline** — Guidage textuel dans les modèles génératifs

## Getting Started
```python
import clip
import torch
from PIL import Image

model, preprocess = clip.load("ViT-L/14", device="cuda")
image = preprocess(Image.open("image.jpg")).unsqueeze(0).to("cuda")
text = clip.tokenize(["a cat", "a dog", "a car"]).to("cuda")

with torch.no_grad():
    image_features = model.encode_image(image)
    text_features = model.encode_text(text)
    similarity = (image_features @ text_features.T).softmax(dim=-1)
    print(similarity)  # Probabilités par classe
```

## Architecture / How It Works
CLIP utilise un encodeur image (Vision Transformer) et un encodeur texte (Transformer) entraînés conjointement sur 400M de paires image-texte via contrastive learning. Les embeddings sont alignés dans un espace commun, permettant la comparaison directe entre images et textes.

## Strengths
- Modèle le plus influent en vision-language
- MIT licence
- Embeddings polyvalents (search, classification, generation)
- Léger et déployable partout

## Limitations
- Supercédé par SigLIP, EVA-CLIP sur certains benchmarks
- Embeddings statiques (pas de compréhension fine-grained)
- Pas de localisation (pas de bounding boxes)

## Alternatives
| Tool | Key Difference |
|------|---------------|
| SigLIP | Google, meilleur sur certains benchmarks |
| EVA-CLIP | Plus performant, plus lourd |
| Florence-2 | Multi-tâche, detection + segmentation |
| Grounding DINO | Detection par texte avec localisation |

## References
- https://github.com/openai/CLIP
- https://arxiv.org/abs/2103.00020
- https://openai.com/research/clip

## Notes
CLIP reste le modèle fondateur de l'ère vision-language. Même si des modèles plus récents le surpassent sur certaines métriques, son écosystème, sa simplicité et sa licence MIT en font un choix par défaut solide pour les embeddings image-texte.
