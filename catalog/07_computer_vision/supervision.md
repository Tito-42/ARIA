# Supervision (Roboflow)

> Bibliothèque de post-traitement model-agnostique — annotations, tracking, counting, zones.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 07 - Computer Vision / Utilities |
| **URL** | https://supervision.roboflow.com |
| **GitHub** | https://github.com/roboflow/supervision |
| **Stars** | ~36,800 |
| **License** | MIT |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Supervision est une bibliothèque Python model-agnostique pour le post-traitement en computer vision. Elle ne fait pas d'inférence elle-même, mais prend les sorties de n'importe quel modèle (YOLO, SAM, Grounding DINO, etc.) et fournit des outils de visualisation, tracking, counting, zone analysis, et plus.

C'est le "glue code" essentiel entre les modèles et l'application finale.

## Key Features
- **Model-agnostique**: Fonctionne avec YOLO, SAM, DETR, Florence-2, etc.
- **Annotations**: Bounding boxes, masques, labels, traces
- **Tracking**: ByteTrack, BoT-SORT multi-objets
- **Counting**: Comptage dans des zones définies
- **Zone analysis**: Polygones d'intérêt, line crossing
- **Video processing**: Frame-by-frame avec annotations

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | Production, MIT licence, Roboflow backed |
| **Security** | 5 | MIT, self-hosted, pas de modèle embarqué |
| **Scalability** | 4 | CPU-only (post-traitement), très rapide |
| **Support/Community** | 5 | 36.8k stars, Roboflow backing |
| **Documentation** | 5 | Docs excellentes, cookbooks |
| **Integration Ease** | 5 | Quelques lignes de code |

## Use Cases
1. **Visualisation** — Annoter des images/vidéos avec les résultats de détection
2. **Counting & monitoring** — Compter des personnes/véhicules dans des zones
3. **Video analytics** — Pipeline vidéo avec tracking et annotations

## Getting Started
```python
import supervision as sv
from ultralytics import YOLO

model = YOLO("yolov8n.pt")
results = model("image.jpg")

detections = sv.Detections.from_ultralytics(results[0])
annotator = sv.BoxAnnotator()
annotated = annotator.annotate(scene=image, detections=detections)
```

## Architecture / How It Works
Supervision fournit des classes `Detections` et `Classifications` comme structures de données unifiées. Les annotateurs (BoxAnnotator, MaskAnnotator, etc.) prennent ces structures et dessinent sur les images. Les trackers (ByteTrack) ajoutent des IDs persistants entre frames.

## Strengths
- Model-agnostique — fonctionne avec tout
- MIT licence
- Annotations visuelles de qualité
- Tracking et counting natifs

## Limitations
- Pas un modèle de détection (ne fait pas d'inférence)
- Dépend d'un modèle externe pour les détections
- Principalement CPU (post-traitement)

## Alternatives
| Tool | Key Difference |
|------|---------------|
| OpenCV | Plus bas niveau, plus de contrôle |
| CVAT | Annotation manuelle, labeling tool |

## References
- https://supervision.roboflow.com
- https://github.com/roboflow/supervision

## Notes
Supervision est un must-have dans tout pipeline computer vision. Il transforme des sorties de modèles brutes en visualisations et analyses exploitables. MIT licence = aucune restriction.
