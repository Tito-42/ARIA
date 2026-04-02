# 06_finetuning_training — Research Findings
**Date**: 2026-04-01
**Sources**: GitHub repos, HuggingFace, web search, awesome lists

---

## Outils Identifiés

### 1. LLaMA-Factory
- **URL**: https://github.com/hiyouga/LLaMA-Factory
- **Stars**: ~69.3k
- **Licence**: Apache 2.0
- **Description**: Framework unifié de fine-tuning supportant 100+ LLMs. Interface web intégrée (LLaMA Board). Supporte SFT, RLHF, DPO, GRPO, PPO, KTO.
- **Forces**: Très large compatibilité modèles, UI web intuitive, communauté massive, documentation exhaustive
- **Faiblesses**: Peut être overwhelming pour débutants, dépendances lourdes
- **Statut**: Très actif (commit 2026-04-01)

### 2. Unsloth
- **URL**: https://github.com/unslothai/unsloth
- **Stars**: ~58.8k
- **Licence**: Apache 2.0 (core) / AGPL (certains modules)
- **Description**: Fine-tuning 2x plus rapide avec 70% moins de VRAM. Optimisations kernel custom pour hardware consommateur.
- **Forces**: Performance inégalée sur GPU consommateur, intégration HuggingFace native, supporte GRPO/DPO/SFT
- **Faiblesses**: Licence mixte (AGPL pour certains composants), moins flexible pour architectures custom
- **Statut**: Très actif

### 3. DeepSpeed
- **URL**: https://github.com/microsoft/DeepSpeed
- **Stars**: ~42k
- **Licence**: Apache 2.0
- **Description**: Bibliothèque d'optimisation deep learning par Microsoft. ZeRO stages 1-3, pipeline parallelism, offloading CPU/NVMe.
- **Forces**: Standard industrie pour training distribué, ZeRO-3 permet de fine-tuner des modèles très larges, bien intégré partout
- **Faiblesses**: Configuration complexe, debugging distribué difficile
- **Statut**: Actif

### 4. Label Studio
- **URL**: https://github.com/HumanSignal/label-studio
- **Stars**: ~26.9k
- **Licence**: Apache 2.0
- **Description**: Plateforme d'annotation de données multi-format (texte, image, audio, vidéo). ML-assisted labeling.
- **Forces**: Multi-modal, interface web intuitive, intégration ML pour pre-labeling, extensible
- **Faiblesses**: Peut être lourd pour petits projets, version enterprise payante pour features avancées
- **Statut**: Très actif (commit 2026-04-01)

### 5. PEFT (Parameter-Efficient Fine-Tuning)
- **URL**: https://github.com/huggingface/peft
- **Stars**: ~20.9k
- **Licence**: Apache 2.0
- **Description**: Bibliothèque HuggingFace pour LoRA, QLoRA, AdaLoRA, IA3, prefix tuning et autres méthodes PEFT.
- **Forces**: Standard de facto pour LoRA, intégration parfaite écosystème HF, léger, bien documenté
- **Faiblesses**: Dépend de l'écosystème HuggingFace
- **Statut**: Actif (v0.18.1)

### 6. VERL
- **URL**: https://github.com/volcengine/verl
- **Stars**: ~20.4k
- **Licence**: Apache 2.0
- **Description**: Framework RL post-training par ByteDance/Volcengine. Spécialisé GRPO, PPO pour LLMs. Nouveau standard RL production.
- **Forces**: Optimisé pour GRPO (post-DeepSeek-R1), scalable multi-GPU, performance production
- **Faiblesses**: Relativement nouveau, documentation en développement
- **Statut**: Actif (jan 2026)

### 7. TRL (Transformer Reinforcement Learning)
- **URL**: https://github.com/huggingface/trl
- **Stars**: ~17.9k
- **Licence**: Apache 2.0
- **Description**: Bibliothèque HuggingFace pour RLHF, DPO, GRPO, KTO, PPO. 15+ trainers spécialisés. v1.0.0 sortie mars 2026.
- **Forces**: Écosystème HF natif, large choix d'algorithmes, milestone v1.0.0, communauté active
- **Faiblesses**: Peut être lent sans optimisations (Unsloth/DeepSpeed)
- **Statut**: Très actif (v1.0.0 mars 2026)

### 8. NVIDIA NeMo
- **URL**: https://github.com/NVIDIA/NeMo
- **Stars**: ~17k
- **Licence**: Apache 2.0
- **Description**: Framework NVIDIA pour training, fine-tuning et déploiement de LLMs et modèles speech/vision à grande échelle.
- **Forces**: Optimisé GPU NVIDIA, supporte Megatron, pipeline complet train→deploy, enterprise-grade
- **Faiblesses**: Fortement couplé à l'écosystème NVIDIA, courbe d'apprentissage
- **Statut**: Actif (v2.7.2 mars 2026)

### 9. Megatron-LM
- **URL**: https://github.com/NVIDIA/Megatron-LM
- **Stars**: ~15.9k
- **Licence**: Apache 2.0
- **Description**: Framework de training distribué NVIDIA pour modèles à très grande échelle. Tensor/pipeline/sequence parallelism.
- **Forces**: Référence pour training de modèles 100B+, parallelism avancé, optimisations NVIDIA
- **Faiblesses**: Très complexe, nécessite infrastructure multi-GPU significative
- **Statut**: Actif (v0.16.1 mars 2026)

### 10. LitGPT
- **URL**: https://github.com/Lightning-AI/litgpt
- **Stars**: ~13.3k
- **Licence**: Apache 2.0
- **Description**: Framework Lightning AI pour pretrain, fine-tune et déployer LLMs. Supporte 20+ architectures.
- **Forces**: Simple d'utilisation, bien intégré Lightning ecosystem, bon pour prototypage
- **Faiblesses**: Communauté plus petite, moins actif récemment (jan 2025)
- **Statut**: Modérément actif

### 11. LM Evaluation Harness
- **URL**: https://github.com/EleutherAI/lm-evaluation-harness
- **Stars**: ~12k
- **Licence**: MIT
- **Description**: Framework d'évaluation standardisé pour LLMs. 200+ benchmarks. Standard pour Open LLM Leaderboard.
- **Forces**: Standard de facto pour évaluation, reproductible, extensible, très large couverture de benchmarks
- **Faiblesses**: Peut être lent sur gros modèles, configuration parfois complexe
- **Statut**: Actif (déc 2025)

### 12. Ludwig
- **URL**: https://github.com/ludwig-ai/ludwig
- **Stars**: ~11.7k
- **Licence**: Apache 2.0
- **Description**: Framework declaratif (YAML) pour training ML/DL. Fine-tuning LLM inclus. Par Linux Foundation AI.
- **Forces**: Approche no-code/low-code, YAML-driven, AutoML intégré, multi-modal
- **Faiblesses**: Moins flexible que code pur, communauté modérée
- **Statut**: Actif

### 13. Axolotl
- **URL**: https://github.com/axolotl-ai-cloud/axolotl
- **Stars**: ~11.6k
- **Licence**: Apache 2.0
- **Description**: Outil de fine-tuning streamliné. Configuration YAML, supporte LoRA, QLoRA, FSDP, DeepSpeed, GRPO, DPO.
- **Forces**: Configuration simple, large compatibilité, communauté open-source forte, bien maintenu
- **Faiblesses**: Documentation peut manquer de profondeur
- **Statut**: Actif (mars 2026)

### 14. OpenRLHF
- **URL**: https://github.com/OpenRLHF/OpenRLHF
- **Stars**: ~9.3k
- **Licence**: Apache 2.0
- **Description**: Framework RLHF/GRPO haute performance avec Ray. Supporte modèles 70B+ sur multi-GPU.
- **Forces**: Scalable via Ray, supporte très gros modèles, GRPO natif
- **Faiblesses**: Moins actif récemment, setup Ray peut être complexe
- **Statut**: Moins actif (jan 2025)

### 15. Mergekit
- **URL**: https://github.com/arcee-ai/mergekit
- **Stars**: ~6.9k
- **Licence**: LGPL v3
- **Description**: Toolkit pour fusionner des LLMs. Méthodes: SLERP, TIES, DARE, linear, task arithmetic.
- **Forces**: Unique dans sa catégorie, multiple méthodes de merge, utilisé massivement par la communauté
- **Faiblesses**: Licence LGPL restrictive, résultats variables selon les modèles
- **Statut**: Modéré (mars 2025)

### 16. torchtune
- **URL**: https://github.com/pytorch/torchtune
- **Stars**: ~5.7k
- **Licence**: BSD
- **Description**: Bibliothèque PyTorch native pour fine-tuning LLMs. Recettes simples, intégration PyTorch ecosystem.
- **Forces**: PyTorch officiel, clean codebase, bonnes recettes, bien documenté
- **Faiblesses**: Communauté encore en croissance, moins de features que LLaMA-Factory
- **Statut**: Actif

### 17. Alignment Handbook
- **URL**: https://github.com/huggingface/alignment-handbook
- **Stars**: ~5.5k
- **Licence**: Apache 2.0
- **Description**: Recettes HuggingFace pour aligner les LLMs. SFT, DPO, RLHF avec exemples complets.
- **Forces**: Référence pédagogique, recettes reproductibles, écosystème HF
- **Faiblesses**: Plus orienté apprentissage que production
- **Statut**: Actif (juil 2025)

### 18. Argilla
- **URL**: https://github.com/argilla-io/argilla
- **Stars**: ~4.9k
- **Licence**: Apache 2.0
- **Description**: Plateforme de curation de données et feedback humain pour LLMs. Annotation, évaluation, RLHF data.
- **Forces**: Spécialisé données LLM/RLHF, intégration HF Datasets, UI collaborative
- **Faiblesses**: Moins généraliste que Label Studio
- **Statut**: Actif (mars 2025)

---

## Tendances Clés (Avril 2026)

1. **GRPO domine** — Post-DeepSeek-R1, GRPO est devenu l'algorithme RL de référence, supporté par presque tous les frameworks
2. **VERL (ByteDance)** — Nouveau venu à 20k+ stars, standard émergent pour RL production
3. **TRL v1.0.0** — Milestone majeur (mars 2026) consolidant l'écosystème HuggingFace
4. **Unsloth** — Reste sans égal pour le fine-tuning sur hardware consommateur
5. **Convergence** — Les outils convergent vers le support multi-algorithmes (SFT + DPO + GRPO + PPO)
