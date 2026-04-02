# Grounding DINO

> Détection d'objets open-set par prompt texte — détecte n'importe quel objet décrit en langage naturel, zero-shot.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 07 - Computer Vision / Object Detection |
| **URL** | https://github.com/IDEA-Research/GroundingDINO |
| **GitHub** | https://github.com/IDEA-Research/GroundingDINO |
| **Stars** | ~9,900 |
| **License** | Apache 2.0 |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Grounding DINO combine le détecteur d'objets DINO avec un grounding textuel pour permettre la détection d'objets open-set. Contrairement aux détecteurs classiques limités à des classes prédéfinies (COCO 80 classes), Grounding DINO détecte n'importe quel objet décrit en langage naturel, sans entraînement spécifique.

Il atteint 52.5 AP sur COCO en zero-shot, ce qui est comparable aux détecteurs entraînés spécifiquement. C'est un composant clé des pipelines vision modernes, souvent combiné avec SAM pour la segmentation.

## Key Features
- **Open-set detection**: Détecte tout objet décrit par texte
- **Zero-shot**: Pas d'entraînement nécessaire pour de nouvelles classes
- **52.5 AP COCO**: Performance zero-shot comparable aux modèles entraînés
- **Multi-phrase**: Détection de plusieurs catégories simultanément
- **Grounding**: Alignement texte-vision précis
- **Composable**: S'intègre avec SAM, SAM 2 pour segmentation

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 3 | Recherche mature, utilisable en production avec optimisation |
| **Security** | 4 | Apache 2.0, self-hosted |
| **Scalability** | 3 | GPU requis, batch processing possible |
| **Support/Community** | 4 | 9.9k stars, IDEA Research actif |
| **Documentation** | 3 | README complet, exemples de base |
| **Integration Ease** | 3 | API Python, nécessite GPU |

## Use Cases
1. **Détection flexible** — Détecter des objets sans dataset d'entraînement custom
2. **Pipeline Grounded-SAM** — Texte → détection → segmentation automatique
3. **Annotation assistée** — Pré-annoter des images pour le labeling

## Getting Started
```python
from groundingdino.util.inference import load_model, predict

model = load_model("GroundingDINO/groundingdino/config/GroundingDINO_SwinT_OGC.py",
                    "weights/groundingdino_swint_ogc.pth")

boxes, logits, phrases = predict(
    model=model, image=image, caption="person . dog . car",
    box_threshold=0.35, text_threshold=0.25
)
```

## Architecture / How It Works
Grounding DINO utilise un encodeur image (Swin Transformer) et un encodeur texte (BERT) avec des couches de cross-attention pour aligner les features visuelles et textuelles. Le décodeur génère des boîtes englobantes conditionnées par les features textuelles. L'architecture permet la détection open-vocabulary sans ré-entraînement.

## Strengths
- Détection de n'importe quel objet par texte, zero-shot
- Performance comparable aux modèles entraînés
- Apache 2.0
- Composable avec SAM/SAM 2

## Limitations
- Plus lent que YOLO (non temps réel)
- Nécessite un GPU
- Moins précis que des modèles fine-tunés pour des domaines spécifiques

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Ultralytics YOLO | Temps réel, mais classes fixes |
| OWLv2 | Google, open-vocabulary detection |
| Florence-2 | Multi-tâche, plus léger |

## References
- https://github.com/IDEA-Research/GroundingDINO
- https://arxiv.org/abs/2303.05499

## Notes
Grounding DINO est un composant fondamental des pipelines vision modernes. Souvent utilisé avec SAM 2 (Grounded-SAM) pour créer un pipeline texte → détection → segmentation entièrement automatique.
