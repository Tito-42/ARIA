# 07_computer_vision — Research Findings
**Date**: 2026-04-01
**Sources**: GitHub repos, HuggingFace, web search, awesome lists

---

## Outils Identifiés (22 outils)

### Détection d'objets

### 1. Grounding DINO
- **URL**: https://github.com/IDEA-Research/GroundingDINO
- **Stars**: ~9.9k
- **Licence**: Apache 2.0
- **Description**: Détection d'objets open-set par prompt texte. Combine DINO avec grounding textuel pour détecter n'importe quel objet décrit en langage naturel.
- **Forces**: Zero-shot detection par texte, 52.5 AP COCO zero-shot, pas besoin d'entraînement spécifique
- **Faiblesses**: Plus lent que YOLO, nécessite GPU
- **Statut**: Actif

### 2. Grounded-SAM
- **URL**: https://github.com/IDEA-Research/Grounded-Segment-Anything
- **Stars**: ~17.5k
- **Licence**: Apache 2.0
- **Description**: Pipeline combinant Grounding DINO + SAM. Texte → détection → segmentation automatique.
- **Forces**: Pipeline complet texte→masque, combinaison puissante, zero-shot
- **Faiblesses**: Pipeline lourd, latence élevée
- **Statut**: Actif

### 3. MMDetection
- **URL**: https://github.com/open-mmlab/mmdetection
- **Stars**: ~32.6k
- **Licence**: Apache 2.0
- **Description**: Toolbox de détection d'objets par OpenMMLab. 500+ configurations, architectures state-of-the-art.
- **Forces**: Très complet, 500+ configs, référence recherche, bien documenté
- **Faiblesses**: Courbe d'apprentissage, écosystème OpenMMLab complexe
- **Statut**: Actif

---

### Segmentation

### 4. SAM 2 (Segment Anything Model 2)
- **URL**: https://github.com/facebookresearch/sam2
- **Stars**: ~18.8k
- **Licence**: Apache 2.0
- **Description**: Modèle de segmentation universel par Meta/FAIR. Images + vidéo, streaming memory, 4 tailles de modèle.
- **Forces**: Segmentation universelle images+vidéo, zero-shot, streaming, Apache 2.0
- **Faiblesses**: Lourd pour edge, nécessite GPU
- **Statut**: Actif

---

### Génération d'images

### 5. FLUX.1
- **URL**: https://github.com/black-forest-labs/flux
- **Stars**: ~25.4k
- **Licence**: Apache 2.0 (schnell) / propriétaire (pro)
- **Description**: Modèle de génération d'images par Black Forest Labs. Rectified flow transformers, standard 2025-2026.
- **Forces**: Qualité state-of-the-art, rectified flow, Apache 2.0 (schnell), remplace SD
- **Faiblesses**: Pro model propriétaire, lourd en VRAM
- **Statut**: Standard actuel

### 6. ComfyUI
- **URL**: https://github.com/comfyanonymous/ComfyUI
- **Stars**: ~107k
- **Licence**: GPL-3.0
- **Description**: Interface node-based pour génération d'images. Supporte tous les modèles (FLUX, SD, SDXL).
- **Forces**: Workflows visuels puissants, tous modèles, extensible via nodes custom, communauté massive
- **Faiblesses**: GPL-3.0 (restrictif), courbe d'apprentissage
- **Statut**: Très actif

### 7. Stable Diffusion WebUI (A1111)
- **URL**: https://github.com/AUTOMATIC1111/stable-diffusion-webui
- **Stars**: ~162k
- **Licence**: AGPL-3.0
- **Description**: Interface web de référence pour Stable Diffusion. Extensions massives, legacy mais encore très utilisé.
- **Forces**: Plus grand écosystème d'extensions, 162k stars, communauté massive
- **Faiblesses**: Legacy (supercédé par ComfyUI pour workflows avancés), AGPL licence
- **Statut**: Maintenance / Legacy

### 8. Stable Diffusion 3.5 / SDXL
- **URL**: https://github.com/Stability-AI/generative-models
- **Stars**: ~27.1k
- **Licence**: MIT / CreativeML
- **Description**: Modèles de génération d'images par Stability AI. MM-DiT architecture, supercédé par FLUX.
- **Forces**: Écosystème mature, fine-tuning accessible, nombreux modèles communautaires
- **Faiblesses**: Supercédé par FLUX en qualité, Stability AI instable financièrement
- **Statut**: Actif mais supercédé

### 9. HuggingFace Diffusers
- **URL**: https://github.com/huggingface/diffusers
- **Stars**: ~33.2k
- **Licence**: Apache 2.0
- **Description**: Bibliothèque Python standard pour modèles de diffusion. Supporte FLUX, SD, SDXL, Kandinsky, etc.
- **Forces**: Standard Python pour diffusion, multi-modèles, pipeline composable, bien documenté
- **Faiblesses**: Overhead vs implémentations natives
- **Statut**: Très actif

---

### OCR / Document AI

### 10. PaddleOCR
- **URL**: https://github.com/PaddlePaddle/PaddleOCR
- **Stars**: ~74.6k
- **Licence**: Apache 2.0
- **Description**: Suite OCR complète par Baidu. 100+ langues, détection + reconnaissance + layout analysis.
- **Forces**: Référence production, 100+ langues, NPU support, pipeline complet, Apache 2.0
- **Faiblesses**: Dépend de PaddlePaddle (pas PyTorch)
- **Statut**: Très actif

### 11. Surya OCR
- **URL**: https://github.com/VikParuchuri/surya
- **Stars**: ~19.5k
- **Licence**: GPL / Rail-M
- **Description**: OCR multilingue avec détection de layout, reconnaissance de texte et LaTeX OCR. 90+ langues.
- **Forces**: 90+ langues, LaTeX OCR, layout detection, bon pour documents académiques
- **Faiblesses**: Licence restrictive (GPL/Rail-M), moins production-ready que PaddleOCR
- **Statut**: Actif

### 12. Marker
- **URL**: https://github.com/VikParuchuri/marker
- **Stars**: ~33.2k
- **Licence**: GPL / Rail-M
- **Description**: Convertisseur PDF/DOCX → Markdown haute fidélité. Optimal pour preprocessing RAG.
- **Forces**: PDF→Markdown excellent, tables et formules, idéal pour RAG
- **Faiblesses**: Licence restrictive (GPL/Rail-M)
- **Statut**: Actif

### 13. DocTR
- **URL**: https://github.com/mindee/doctr
- **Stars**: ~6k
- **Licence**: Apache 2.0
- **Description**: OCR deep learning par Mindee. Pure PyTorch/TensorFlow, FastAPI template inclus.
- **Forces**: Apache 2.0, pure PyTorch, API template, production-friendly
- **Faiblesses**: Moins de langues que PaddleOCR
- **Statut**: Actif

---

### Depth Estimation / 3D Vision

### 14. Depth Anything V2
- **URL**: https://github.com/DepthAnything/Depth-Anything-V2
- **Stars**: ~7.8k
- **Licence**: Apache 2.0 (Small model)
- **Description**: Estimation de profondeur monoculaire state-of-the-art. Multiple tailles, très précis.
- **Forces**: Référence depth estimation, Apache 2.0 (small), multiple tailles
- **Faiblesses**: Grands modèles sous licence restrictive
- **Statut**: Actif

### 15. 3D Gaussian Splatting
- **URL**: https://github.com/graphdeco-inria/gaussian-splatting
- **Stars**: ~21.2k
- **Licence**: Recherche / Non-commercial
- **Description**: Rendu 3D temps réel par gaussian splatting. Reconstruction de scènes 3D à partir de photos.
- **Forces**: Rendu temps réel révolutionnaire, qualité photo-réaliste
- **Faiblesses**: **Licence non-commerciale** — bloquant pour enterprise
- **Statut**: Actif (recherche)

### 16. Instant-NGP (NVIDIA)
- **URL**: https://github.com/NVlabs/instant-ngp
- **Stars**: ~17.3k
- **Licence**: NVIDIA Non-Commercial
- **Description**: NeRF ultra-rapide par NVIDIA. Training en secondes, multi-resolution hash encoding.
- **Forces**: NeRF le plus rapide, training en secondes
- **Faiblesses**: **Licence NVIDIA non-commerciale** — bloquant pour enterprise
- **Statut**: Actif (recherche)

### 17. Nerfstudio
- **URL**: https://github.com/nerfstudio-project/nerfstudio
- **Stars**: ~11.4k
- **Licence**: Apache 2.0
- **Description**: Framework modulaire pour NeRF et 3D Gaussian Splatting. Le seul framework NeRF/3DGS Apache 2.0.
- **Forces**: **Seul NeRF/3DGS Apache 2.0**, modulaire, multi-méthodes, bien documenté
- **Faiblesses**: Communauté plus petite que les projets de recherche
- **Statut**: Actif — **recommandé pour enterprise**

---

### Utilitaires / Foundation Models

### 18. Supervision (Roboflow)
- **URL**: https://github.com/roboflow/supervision
- **Stars**: ~36.8k
- **Licence**: MIT
- **Description**: Bibliothèque de post-traitement model-agnostique. Annotations, tracking, counting, zones.
- **Forces**: Model-agnostique, MIT, annotations visuelles, tracking, très utile en production
- **Faiblesses**: Pas un modèle en soi
- **Statut**: Très actif

### 19. Florence-2 (Microsoft)
- **URL**: https://huggingface.co/microsoft/Florence-2-large
- **Stars**: ~1.2M téléchargements/mois
- **Licence**: MIT
- **Description**: Modèle vision multi-tâches par Microsoft. Captioning, detection, segmentation, OCR dans un seul modèle léger (0.23-0.77B).
- **Forces**: Multi-tâches dans un modèle léger, MIT, excellente polyvalence
- **Faiblesses**: Moins spécialisé que modèles dédiés par tâche
- **Statut**: Actif

### 20. Real-ESRGAN
- **URL**: https://github.com/xinntao/Real-ESRGAN
- **Stars**: ~34.9k
- **Licence**: BSD-3
- **Description**: Super-résolution d'images (upscaling). Restauration et amélioration de photos/vidéos.
- **Forces**: Référence upscaling, portable, BSD licence, fonctionne sur GPU consommateur
- **Faiblesses**: Modèle figé (pas de fine-tuning facile)
- **Statut**: Stable

### 21. Open-Sora
- **URL**: https://github.com/hpcaitech/Open-Sora
- **Stars**: ~28.8k
- **Licence**: Apache 2.0
- **Description**: Reproduction open-source de Sora (OpenAI). Génération vidéo à partir de texte.
- **Forces**: Génération vidéo open-source, Apache 2.0, communauté active
- **Faiblesses**: Qualité encore loin de Sora commercial
- **Statut**: Actif

### 22. OpenAI CLIP
- **URL**: https://github.com/openai/CLIP
- **Stars**: ~33k
- **Licence**: MIT
- **Description**: Modèle fondateur vision-language par OpenAI. Embeddings image-texte alignés, zero-shot classification.
- **Forces**: Fondateur de l'ère vision-language, embeddings polyvalents, MIT, très influent
- **Faiblesses**: Supercédé par SigLIP, EVA-CLIP pour certaines tâches
- **Statut**: Stable / Legacy influent

---

## Tendances Clés (Avril 2026)

1. **FLUX remplace Stable Diffusion** — Rectified flow transformers deviennent le standard
2. **ComfyUI domine les workflows** — 107k stars, supercède A1111 pour usage avancé
3. **SAM 2 universel** — Segmentation images+vidéo, zero-shot, Apache 2.0
4. **PaddleOCR référence production** — 74.6k stars, 100+ langues
5. **3D Vision: attention aux licences** — Gaussian Splatting et Instant-NGP sont non-commerciaux, seul Nerfstudio est Apache 2.0
6. **Florence-2 et CLIP** — Foundation models vision-language deviennent incontournables
7. **Open-Sora** — La génération vidéo open-source progresse mais reste loin du commercial
