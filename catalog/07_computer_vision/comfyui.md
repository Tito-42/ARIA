# ComfyUI

> Interface node-based pour la génération d'images — supporte FLUX, SD, SDXL avec workflows visuels.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 07 - Computer Vision / Image Generation |
| **URL** | https://www.comfy.org |
| **GitHub** | https://github.com/comfyanonymous/ComfyUI |
| **Stars** | ~107,000 |
| **License** | GPL-3.0 |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
ComfyUI est une interface node-based pour la génération d'images qui a supercédé AUTOMATIC1111 comme outil principal de l'écosystème. Avec 107k stars, c'est l'un des projets open-source les plus populaires en IA. Il permet de construire des workflows visuels complexes en connectant des nodes (modèles, samplers, ControlNet, LoRA, etc.).

ComfyUI supporte tous les modèles majeurs : FLUX, Stable Diffusion 3.5, SDXL, et permet des workflows impossibles à créer avec des interfaces simples.

## Key Features
- **Node-based**: Workflows visuels par connexion de nodes
- **Multi-modèles**: FLUX, SD3.5, SDXL, Kandinsky, etc.
- **ControlNet/IP-Adapter**: Contrôle précis de la génération
- **Custom nodes**: Écosystème massif d'extensions communautaires
- **Queue & batch**: Génération en batch avec queue
- **API**: REST API pour intégration programmatique

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Production, utilisé par des studios créatifs |
| **Security** | 3 | GPL-3.0 (restrictif pour produits propriétaires) |
| **Scalability** | 3 | Single-node, mais API pour batch |
| **Support/Community** | 5 | 107k stars, communauté massive |
| **Documentation** | 3 | Docs communautaires, tutoriels vidéo nombreux |
| **Integration Ease** | 3 | Courbe d'apprentissage node-based |

## Use Cases
1. **Workflows créatifs** — Pipelines complexes de génération d'images
2. **Content pipeline** — Production batch de visuels
3. **Prototypage** — Tester des combinaisons de modèles, LoRA, ControlNet

## Getting Started
```bash
git clone https://github.com/comfyanonymous/ComfyUI
cd ComfyUI
pip install -r requirements.txt
python main.py
# Ouvrir http://localhost:8188
```

## Architecture / How It Works
ComfyUI utilise un graphe de nodes où chaque node est une opération (charger modèle, sampler, encoder texte, sauver image). Le backend exécute le graphe dans l'ordre topologique, avec caching intelligent des résultats intermédiaires. L'API REST permet de soumettre des workflows en JSON.

## Strengths
- Workflows visuels infiniment flexibles
- Support de tous les modèles génératifs
- Écosystème de custom nodes massif
- 107k stars, communauté la plus large

## Limitations
- GPL-3.0 (restrictif pour intégration dans produits propriétaires)
- Courbe d'apprentissage pour les workflows complexes
- Single-node (pas de distributed rendering)

## Alternatives
| Tool | Key Difference |
|------|---------------|
| AUTOMATIC1111 | Plus simple, legacy, AGPL-3.0 |
| Fooocus | Simplifié, Midjourney-like UX |
| InvokeAI | Node-based aussi, Apache 2.0 |

## References
- https://github.com/comfyanonymous/ComfyUI
- https://www.comfy.org

## Notes
ComfyUI est le standard pour les workflows de génération d'images avancés. La licence GPL-3.0 est à considérer pour les intégrations commerciales. InvokeAI (Apache 2.0) est une alternative si la licence est un blocage.
