# Florence-2 (Microsoft)

> Modèle vision multi-tâches par Microsoft — captioning, detection, segmentation, OCR dans un modèle léger.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 07 - Computer Vision / Foundation Model |
| **URL** | https://huggingface.co/microsoft/Florence-2-large |
| **GitHub** | https://huggingface.co/microsoft/Florence-2-large |
| **Stars** | ~1.2M téléchargements/mois |
| **License** | MIT |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Florence-2 est un modèle vision multi-tâches de Microsoft qui combine captioning, detection, segmentation, et OCR dans un seul modèle léger (0.23B-0.77B paramètres). C'est un "foundation model" vision qui peut être utilisé pour de nombreuses tâches sans modèles spécialisés.

Sa taille compacte le rend particulièrement adapté aux cas où la polyvalence est plus importante que la performance maximale sur une tâche spécifique.

## Key Features
- **Multi-tâches**: Captioning, detection, segmentation, OCR, grounding
- **Léger**: 0.23B (base) à 0.77B (large) paramètres
- **MIT licence**: Aucune restriction commerciale
- **Prompt-based**: Différentes tâches via différents prompts textuels
- **Fine-tunable**: Adaptable à des domaines spécifiques
- **HuggingFace**: Intégration native

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Production, MIT, modèle compact |
| **Security** | 5 | MIT, self-hosted, pas de dépendance externe |
| **Scalability** | 4 | Modèle léger, CPU possible pour certaines tâches |
| **Support/Community** | 4 | Microsoft, 1.2M téléchargements/mois |
| **Documentation** | 4 | HuggingFace docs, Microsoft paper |
| **Integration Ease** | 5 | HuggingFace Transformers, trivial |

## Use Cases
1. **Multi-tâche vision** — Un seul modèle pour captioning + detection + OCR
2. **Edge deployment** — Modèle léger pour les contraintes compute
3. **Prototypage rapide** — Tester plusieurs tâches vision sans modèles spécialisés

## Getting Started
```python
from transformers import AutoProcessor, AutoModelForCausalLM

model = AutoModelForCausalLM.from_pretrained("microsoft/Florence-2-large", trust_remote_code=True)
processor = AutoProcessor.from_pretrained("microsoft/Florence-2-large", trust_remote_code=True)

inputs = processor(text="<OD>", images=image, return_tensors="pt")
generated = model.generate(**inputs, max_new_tokens=1024)
result = processor.batch_decode(generated, skip_special_tokens=False)[0]
parsed = processor.post_process_generation(result, task="<OD>", image_size=image.size)
```

## Architecture / How It Works
Florence-2 utilise une architecture encoder-decoder : un image encoder (DaViT) encode l'image, et un decoder autorégressif génère des tokens de sortie. Les différentes tâches sont conditionnées par des prompts textuels spécifiques (<OD> pour detection, <CAPTION> pour captioning, etc.).

## Strengths
- Multi-tâche dans un modèle compact
- MIT licence
- 1.2M téléchargements mensuels
- Microsoft backing

## Limitations
- Moins spécialisé que les modèles dédiés (YOLO pour detection, SAM pour segmentation)
- Performance inférieure aux SOTA spécialisés sur chaque tâche
- 0.77B paramètres = besoin GPU pour temps réel

## Alternatives
| Tool | Key Difference |
|------|---------------|
| CLIP | Embeddings vision-language, pas multi-tâche |
| Ultralytics YOLO | Detection spécialisée, temps réel |
| SAM 2 | Segmentation spécialisée, meilleure qualité |

## References
- https://huggingface.co/microsoft/Florence-2-large
- https://arxiv.org/abs/2311.06242

## Notes
Florence-2 est le couteau suisse de la vision — polyvalent mais pas le meilleur sur chaque tâche. Idéal pour le prototypage et les cas où un seul modèle doit couvrir plusieurs besoins.
