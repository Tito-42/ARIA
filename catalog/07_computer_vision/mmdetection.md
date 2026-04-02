# MMDetection

> Toolbox de détection d'objets OpenMMLab — 500+ configurations, architectures state-of-the-art.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 07 - Computer Vision / Object Detection |
| **URL** | https://mmdetection.readthedocs.io |
| **GitHub** | https://github.com/open-mmlab/mmdetection |
| **Stars** | ~32,600 |
| **License** | Apache 2.0 |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
MMDetection est la toolbox de référence pour la détection d'objets, développée par OpenMMLab. Elle fournit des implémentations de plus de 500 configurations couvrant les architectures state-of-the-art : Faster R-CNN, DETR, DINO, Co-DETR, Mask R-CNN, Cascade R-CNN, et bien d'autres.

C'est l'outil de choix pour la recherche et le benchmarking en détection d'objets, avec un système de configuration modulaire permettant de mixer et matcher backbones, necks, et heads.

## Key Features
- **500+ configs**: Architectures SOTA pré-configurées
- **Modulaire**: Backbone, neck, head interchangeables
- **Multi-tâches**: Détection, segmentation d'instance, panoptique
- **Benchmarking**: Résultats reproductibles sur COCO, VOC, etc.
- **Training pipeline**: Entraînement, évaluation, export intégrés
- **Model Zoo**: Poids pré-entraînés pour toutes les architectures

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Utilisé en production, export ONNX/TensorRT |
| **Security** | 4 | Apache 2.0, self-hosted |
| **Scalability** | 4 | Multi-GPU training, distributed |
| **Support/Community** | 5 | 32.6k stars, OpenMMLab ecosystem |
| **Documentation** | 4 | Docs complètes, tutoriels |
| **Integration Ease** | 3 | Écosystème OpenMMLab = courbe d'apprentissage |

## Use Cases
1. **Recherche** — Benchmarker et comparer des architectures de détection
2. **Custom detection** — Fine-tuner un détecteur sur un dataset custom
3. **Production** — Exporter des modèles optimisés (ONNX, TensorRT)

## Getting Started
```bash
pip install mmdet mmengine
```
```python
from mmdet.apis import init_detector, inference_detector

model = init_detector('configs/faster_rcnn/faster-rcnn_r50_fpn_1x_coco.py',
                       'checkpoints/faster_rcnn_r50_fpn_1x_coco.pth')
result = inference_detector(model, 'image.jpg')
```

## Architecture / How It Works
MMDetection utilise le framework MMEngine avec un système de registres et configurations YAML/Python. Chaque modèle est décomposé en backbone (ResNet, Swin), neck (FPN), et head (RPN, RoI). Le training pipeline gère le data loading, augmentation, et scheduling.

## Strengths
- La plus complète toolbox de détection d'objets
- 500+ configurations reproductibles
- Modularité exceptionnelle
- Communauté OpenMMLab massive

## Limitations
- Écosystème OpenMMLab complexe (MMEngine, MMCV)
- Courbe d'apprentissage pour la configuration
- Overhead vs implémentations standalone

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Ultralytics YOLO | Plus simple, temps réel, production-first |
| Detectron2 | Meta/FAIR, plus modulaire, moins de modèles |
| Grounding DINO | Open-set detection, zero-shot |

## References
- https://mmdetection.readthedocs.io
- https://github.com/open-mmlab/mmdetection

## Notes
MMDetection est le choix pour la recherche et le benchmarking en détection d'objets. Pour la production simple et rapide, Ultralytics YOLO est souvent préféré. Les deux se complètent bien.
