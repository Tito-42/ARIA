# OSINT Findings - Catégorie 18 : AI Infrastructure
**Date de recherche :** 2026-04-01
**Agent :** researcher
**Méthode :** WebFetch sur GitHub, sites officiels, documentation publique
**Sources explorées :** GitHub (repos individuels), documentation officielle des projets

---

## Synthèse

Cette recherche couvre les outils d'infrastructure IA pour avril 2026 : moteurs d'inférence, quantization, GPU cloud, orchestration, frameworks d'optimisation, edge deployment.

Certains outils sont déjà présents dans le catalogue existant (`catalog/18_ai_infrastructure/`) :
- **Déjà catalogués :** Lambda Labs, RunPod, Vast.ai, Modal, ONNX Runtime, Replicate, Together AI, Ray, SkyPilot
- **Nouveaux findings :** vLLM, llama.cpp, SGLang, TGI, TensorRT-LLM, Triton Inference Server, Ollama, ExLlamaV2, MLC LLM, DeepSpeed, Flash Attention, FlashInfer, BitNet, Unsloth, PyTorch AO, bitsandbytes, CoreML Tools, ExecuTorch, LoRAX, BentoML, GPUStack, Megatron-LM, OpenVINO, Triton (OpenAI), GGML, llama-cpp-python, GPTQModel, xFormers

---

## Findings détaillés

---

### 1. vLLM

- **URL :** https://vllm.ai
- **GitHub :** https://github.com/vllm-project/vllm
- **Stars :** ~74,900
- **Licence :** Apache-2.0
- **Source de découverte :** GitHub direct + référence dans TGI, SGLang, nombreux projets
- **Date de recherche :** 2026-04-01
- **Catégorie suggérée :** 18_ai_infrastructure
- **Sous-catégorie :** inference
- **Dernière release vérifiée :** v0.18.1 (31 mars 2026)

**Description :**
Moteur d'inférence LLM haute performance et mémoire-efficace. Référence industrielle pour le serving LLM en production. Développé initialement par UC Berkeley, maintenant un projet communautaire majeur.

**Technologies clés :**
- PagedAttention : gestion paginée du KV cache (inspiration du virtual memory OS)
- Continuous batching : fusion dynamique des requêtes entrantes
- CUDA/HIP graph execution pour réduire l'overhead CPU
- Speculative decoding, chunked prefill
- Intégrations FlashAttention et FlashInfer

**Cas d'usage principaux :**
1. Serving LLM en production (API OpenAI-compatible)
2. Inférence distribuée multi-GPU et multi-nœuds
3. Déploiement haute-disponibilité (HA) avec LoadBalancer
4. Serving modèles MoE (Mixtral, DeepSeek V3/R1)
5. Multi-LoRA serving (plusieurs adapters simultanés)

**Support hardware :**
- NVIDIA GPUs (principal), AMD GPUs (ROCm), Intel Gaudi, IBM Spyre, Huawei Ascend
- Intel/PowerPC/ARM CPUs, Google TPUs

**Quantization supportée :** GPTQ, AWQ, AutoRound, INT4, INT8, FP8

**Forces :**
- Leader de facto pour le serving LLM en production (400K+ GPUs en production selon SGLang)
- Throughput exceptionnel grâce à PagedAttention
- Écosystème énorme : intégrations natives avec LangChain, LlamaIndex, Kubernetes, Ray Serve
- API OpenAI-compatible (drop-in replacement)
- Support multi-hardware (NVIDIA, AMD, Intel, TPU)
- Maintenance très active (v0.18.1 le 31 mars 2026)
- Multi-LoRA, prefix caching, speculative decoding

**Faiblesses :**
- Latence Time-to-First-Token (TTFT) moins bonne que SGLang sur certains benchmarks
- Complexité de configuration pour le déploiement distribué
- Consommation mémoire plus importante que llama.cpp pour usage local
- Nécessite GPU NVIDIA (ou AMD) : pas adapté au CPU-only

**Statut en avril 2026 :** Actif, très actif. Release v0.18.1 la veille (31 mars 2026).

---

### 2. llama.cpp

- **URL :** https://github.com/ggml-org/llama.cpp
- **GitHub :** https://github.com/ggml-org/llama.cpp
- **Stars :** ~101,000
- **Licence :** MIT
- **Source de découverte :** GitHub direct
- **Date de recherche :** 2026-04-01
- **Catégorie suggérée :** 18_ai_infrastructure
- **Sous-catégorie :** inference (local/edge)

**Description :**
Inférence LLM en C/C++ pur, sans dépendances. Référence absolue pour l'exécution locale et edge de LLMs. Créé par Georgi Gerganov, maintenant sous l'organisation ggml-org. Base de nombreux outils en aval (Ollama, LM Studio, Jan.ai).

**Quantization GGUF supportée :**
- Q1.5 à Q8 (1.5-bit à 8-bit)
- Format GGUF : standard de facto pour les modèles quantifiés (remplace GGML)

**Cas d'usage principaux :**
1. Inférence LLM locale sur CPU (MacBook, PC, serveur sans GPU)
2. Edge computing (Raspberry Pi, mobile, IoT)
3. Hybride CPU+GPU (offload partiel sur GPU)
4. Base technique pour Ollama, LM Studio, Jan.ai

**Support hardware :**
- Apple Silicon (Metal, Accelerate) : performances excellentes
- x86 (AVX, AVX2, AVX512, AMX)
- NVIDIA GPUs (CUDA custom kernels)
- AMD GPUs (HIP/ROCm)
- Vulkan (GPU cross-platform), SYCL

**Forces :**
- Pas de dépendances (C/C++ pur)
- Fonctionne partout (CPU, GPU, hybride, mobile)
- Format GGUF devenu standard industriel
- Quantization extrême (1.5-bit) pour les contraintes mémoire les plus sévères
- 101K stars : projet le plus populaire d'inférence LLM

**Faiblesses :**
- Throughput inférieur à vLLM pour le serving haute-performance
- API moins élaborée que les frameworks dédiés au serving
- Optimisations GPU moins poussées que TensorRT-LLM
- Pas natif pour le multi-GPU distribué

**Statut en avril 2026 :** Extrêmement actif, commits quotidiens.

---

### 3. SGLang

- **URL :** https://sgl-project.github.io
- **GitHub :** https://github.com/sgl-project/sglang
- **Stars :** ~25,300
- **Licence :** Apache-2.0
- **Source de découverte :** GitHub direct + référence systématique dans TGI (recommandé comme replacement)
- **Date de recherche :** 2026-04-01
- **Catégorie suggérée :** 18_ai_infrastructure
- **Sous-catégorie :** inference

**Description :**
Framework de serving LLM et multimodal haute-performance, co-développé avec l'équipe DeepSeek. Challenger direct de vLLM avec des avantages sur le TTFT (Time-to-First-Token) et les workloads avec préfixes partagés.

**Innovations techniques :**
- RadixAttention : prefix caching avancé via arbre radix
- Zero-overhead CPU scheduler (v0.4)
- Prefill-decode disaggregation
- Cache-Aware Load Balancer
- Speculative decoding
- Structured output natif (JSON schema, regex)

**Cas d'usage principaux :**
1. Serving LLM à très haute performance (déploiement >400K GPUs globalement)
2. Workloads avec préfixes communs (RAG, prompts système longs)
3. Modèles de diffusion (Flux, etc.)
4. Serving DeepSeek, Qwen, Llama

**Support hardware :**
- NVIDIA (GB200, B300, H100, A100), AMD (MI355, MI300)
- Intel CPUs, Google TPUs, Ascend NPUs

**Forces :**
- TTFT souvent meilleur que vLLM sur workloads complexes
- RadixAttention : prefix caching très efficace
- Recommandé par TGI (Hugging Face) pour les nouveaux projets
- Support modèles de diffusion (vLLM ne couvre pas)
- Adoption industrielle massive

**Faiblesses :**
- Communauté plus petite que vLLM (mais croît vite)
- Moins d'intégrations tierces que vLLM
- Documentation parfois en retard sur les features

**Statut en avril 2026 :** Très actif, croissance accélérée.

---

### 4. Ollama

- **URL :** https://ollama.com
- **GitHub :** https://github.com/ollama/ollama
- **Stars :** ~167,000
- **Licence :** MIT
- **Source de découverte :** GitHub direct
- **Date de recherche :** 2026-04-01
- **Catégorie suggérée :** 18_ai_infrastructure / 14_open_source_llms
- **Sous-catégorie :** inference (local)

**Description :**
Plateforme "tout-en-un" pour exécuter des LLMs localement. Construit sur llama.cpp, ajoute une couche de gestion de modèles, une API REST et un CLI. Le moyen le plus simple de déployer un LLM local en 2026.

**Features :**
- CLI simple : `ollama run llama3.3`
- API REST OpenAI-compatible
- Bibliothèque 100+ modèles (Gemma 3, DeepSeek, Qwen, Llama, etc.)
- Python et JavaScript SDKs
- Support RAG et embeddings
- Intégration Claude Code, Codex, et autres outils de dev

**Cas d'usage principaux :**
1. Développement et test de LLMs en local
2. Privacy-first : données ne quittent pas la machine
3. Prototypage rapide d'applications LLM
4. Intégration dans outils de dev (Claude Code, VS Code extensions)

**Support plateformes :** macOS, Windows, Linux, Docker

**Forces :**
- 167K stars : le projet le plus populaire de la catégorie
- Installation 1-commande
- API OpenAI-compatible
- Gestion automatique des modèles (download, versioning)
- Intégration dans tous les outils modernes

**Faiblesses :**
- Pas conçu pour le serving production haute-performance
- Throughput limité vs vLLM pour des cas d'usage multi-utilisateurs
- Couche d'abstraction au-dessus de llama.cpp : moins de contrôle

**Statut en avril 2026 :** Très actif. Standard de facto pour l'inférence locale.

---

### 5. TensorRT-LLM

- **URL :** https://developer.nvidia.com/tensorrt-llm
- **GitHub :** https://github.com/NVIDIA/TensorRT-LLM
- **Stars :** ~13,200
- **Licence :** Apache-2.0
- **Source de découverte :** GitHub direct
- **Date de recherche :** 2026-04-01
- **Catégorie suggérée :** 18_ai_infrastructure
- **Sous-catégorie :** inference (NVIDIA optimisé)
- **Dernière release vérifiée :** v1.3.0rc11

**Description :**
Framework d'optimisation et de serving LLM de NVIDIA, conçu exclusivement pour les GPUs NVIDIA. Offre les meilleures performances absolues sur hardware NVIDIA en exploitant TensorRT et les fonctionnalités matérielles de bas niveau.

**Techniques d'optimisation :**
- Custom attention kernels hautement optimisés
- Inflight batching (continuous batching NVIDIA-native)
- Paged KV caching
- FP8, FP4, INT4 AWQ, INT8 SmoothQuant
- Speculative decoding
- Architecture PyTorch-native (depuis v1.x)

**Cas d'usage principaux :**
1. Performance maximale sur NVIDIA (H100, A100, GB200)
2. Déploiement avec NVIDIA Triton Inference Server
3. Production enterprise NVIDIA-only
4. Benchmarking et optimisation fine

**Forces :**
- Performances maximales sur hardware NVIDIA
- Intégration native Triton Inference Server
- Support FP4 (NVIDIA Blackwell GB200)
- Modèles pré-supportés : DeepSeek, Llama, Mixtral
- NVIDIA backing (support, roadmap)

**Faiblesses :**
- NVIDIA uniquement (lock-in fort)
- Complexité de configuration élevée
- Documentation parfois insuffisante
- Courbe d'apprentissage plus raide que vLLM
- Moins flexible que vLLM pour les cas d'usage non-standard

**Statut en avril 2026 :** Actif, 5,814 commits.

---

### 6. Hugging Face TGI (Text Generation Inference)

- **URL :** https://huggingface.co/docs/text-generation-inference
- **GitHub :** https://github.com/huggingface/text-generation-inference
- **Stars :** ~10,800
- **Licence :** Apache-2.0
- **Source de découverte :** GitHub direct
- **Date de recherche :** 2026-04-01
- **Catégorie suggérée :** 18_ai_infrastructure
- **Sous-catégorie :** inference

**Description :**
Serveur d'inférence LLM de Hugging Face (Rust + Python + gRPC). Utilisé en production sur les plateformes HF (chat, Inference API, Endpoints). Entré en mode maintenance en mars 2026, les mainteneurs recommandent vLLM ou SGLang pour les nouveaux projets.

**Features :**
- Tensor parallelism multi-GPU
- Continuous batching, Flash Attention, Paged Attention
- API Messages OpenAI-compatible
- Quantization : bitsandbytes, GPTQ, EETQ, AWQ, Marlin, FP8
- Speculative decoding (~2x amélioration latence)
- JSON/guidance output formatting, watermarking

**Forces :**
- Intégration native HuggingFace Hub
- Serving production éprouvé (infrastructure HF)
- Docker simple pour déploiement rapide

**Faiblesses :**
- En mode maintenance depuis mars 2026 (non recommandé pour nouveaux projets)
- Communauté se déplace vers vLLM/SGLang
- Moins de features avancées que les alternatives actives

**Statut en avril 2026 :** MAINTENANCE MODE (mars 2026). Bugs mineurs et docs uniquement.

---

### 7. NVIDIA Triton Inference Server

- **URL :** https://developer.nvidia.com/triton-inference-server
- **GitHub :** https://github.com/triton-inference-server/server
- **Stars :** ~10,500
- **Licence :** BSD-3-Clause
- **Source de découverte :** GitHub direct + TensorRT-LLM intégration
- **Date de recherche :** 2026-04-01
- **Catégorie suggérée :** 18_ai_infrastructure
- **Sous-catégorie :** inference / orchestration
- **Dernière release :** v2.67.0 (NGC container 26.03)

**Description :**
Serveur d'inférence multi-framework de NVIDIA, standard industriel pour le déploiement de modèles en production sur infrastructure NVIDIA. Support cloud, datacenter, edge et embedded.

**Backends supportés :**
- TensorRT, PyTorch, ONNX, OpenVINO, Python, RAPIDS FIL
- Exécution concurrente de modèles multiples
- Dynamic batching et sequence batching

**Features :**
- HTTP/REST et gRPC (protocoles KServe)
- APIs C et Java pour intégration in-process
- Model ensembling, Business Logic Scripting
- Métriques Prometheus : GPU utilization, throughput, latence

**Cas d'usage :**
1. Serving multi-framework en production (pytorch + tensorrt + onnx simultanés)
2. Pipeline de modèles complexes (model ensemble)
3. Déploiement standardisé KServe
4. Backend pour TensorRT-LLM

**Forces :**
- Standard industriel pour les déploiements NVIDIA enterprise
- Multi-backend (gère plusieurs frameworks en parallèle)
- Métriques production avancées
- Intégration KServe pour Kubernetes

**Faiblesses :**
- Complexité de configuration
- Principalement optimisé NVIDIA
- Overhead vs serving direct pour cas simples

**Statut en avril 2026 :** Actif, release mensuelle.

---

### 8. ExLlamaV2

- **URL :** https://github.com/turboderp/exllamav2
- **GitHub :** https://github.com/turboderp/exllamav2
- **Stars :** ~4,500
- **Licence :** MIT
- **Source de découverte :** GitHub direct
- **Date de recherche :** 2026-04-01
- **Catégorie suggérée :** 18_ai_infrastructure
- **Sous-catégorie :** inference (consumer GPU)

**Description :**
Bibliothèque d'inférence LLM rapide pour GPUs grand public modernes. Spécialité : format EXL2 (2-8 bits, mixage flexible) permettant des compressions agressives avec contrôle précis du trade-off qualité/vitesse.

**Formats de quantization :**
- **GPTQ :** Format 4-bit standard (compatible ExLlama v1)
- **EXL2 :** Propriétaire, 2-8 bits avec mixage intra-modèle. Llama2-70B sur GPU 24GB à 2.55 bpw, contexte 2048 tokens.

**Features :**
- Flash Attention 2.5.7+ avec paged attention
- Dynamic generator avec batching, prompt caching, K/V cache deduplication
- Async streaming
- Multi-GPU
- Intégration TabbyAPI, text-generation-webui, lollms-webui

**Cas d'usage :**
1. Inférence de grands modèles sur GPU consumer (24GB VRAM)
2. Quantization personnalisée pour optimiser qualité vs mémoire
3. Backend pour interfaces locales (TabbyAPI)

**Forces :**
- Format EXL2 très flexible (mixage de précision par couche)
- Excellentes performances sur GPU grand public
- Intégration interfaces populaires (webui, TabbyAPI)

**Faiblesses :**
- Niche (GPU grand public uniquement)
- Moins de support hardware que vLLM
- Format EXL2 propriétaire (vendor lock-in doux)

**Statut en avril 2026 :** Actif.

---

### 9. MLC LLM

- **URL :** https://llm.mlc.ai
- **GitHub :** https://github.com/mlc-ai/mlc-llm
- **Stars :** ~22,300
- **Licence :** Apache-2.0
- **Source de découverte :** GitHub direct
- **Date de recherche :** 2026-04-01
- **Catégorie suggérée :** 18_ai_infrastructure
- **Sous-catégorie :** inference (cross-platform, edge)

**Description :**
Moteur de déploiement LLM universel basé sur la compilation ML (TVM). Cible une portabilité maximale : du navigateur Web aux téléphones iOS/Android en passant par les GPUs NVIDIA, AMD, Intel et Apple Silicon.

**Platforms supportées :**
- Linux/Windows : NVIDIA (CUDA), AMD (Vulkan, ROCm), Intel (Vulkan)
- macOS : Apple Metal (M1/M2/M3/M4)
- Web : WebGPU + WASM
- iOS/iPadOS : Metal (Apple A-series)
- Android : OpenCL (Adreno, Mali)

**API :** MLCEngine avec OpenAI-compatible API (REST, Python, JavaScript)

**Cas d'usage :**
1. LLM en navigateur (WebGPU)
2. Applications mobiles natives iOS/Android
3. Portabilité maximale (même modèle partout)
4. Edge deployment sur Apple Silicon

**Forces :**
- Support Web/Mobile unique (aucun concurrent direct)
- Compilation ML = performances portables
- API unifiée multi-plateforme

**Faiblesses :**
- Throughput inférieur à vLLM sur serveur GPU
- Temps de compilation requis avant déploiement
- Moins de modèles supportés que llama.cpp

**Statut en avril 2026 :** Actif.

---

### 10. DeepSpeed

- **URL :** https://www.deepspeed.ai
- **GitHub :** https://github.com/microsoft/DeepSpeed
- **Stars :** ~42,000
- **Licence :** Apache-2.0
- **Source de découverte :** GitHub direct
- **Date de recherche :** 2026-04-01
- **Catégorie suggérée :** 18_ai_infrastructure
- **Sous-catégorie :** training / inference optimization

**Description :**
Bibliothèque d'optimisation deep learning de Microsoft pour l'entraînement et l'inférence distribués. Référence pour l'entraînement de LLMs à très grande échelle (a permis MT-530B et BLOOM 176B).

**Innovations clés :**
- **ZeRO (Zero Redundancy Optimizer) :** Supprime les redondances en mémoire distribuée
- **ZeRO-Infinity :** Offloading sur CPU/NVMe pour modèles dépassant la VRAM
- **3D-Parallelism :** Data + Tensor + Pipeline parallelism combinés
- **Ulysses Sequence Parallelism :** Pour séquences très longues
- **DeepSpeed-MoE :** Optimisation architectures MoE

**Support hardware :** NVIDIA GPUs, AMD MI series, Intel Gaudi, CPU

**Cas d'usage :**
1. Pré-entraînement de LLMs (multi-GPU, multi-nœuds)
2. Fine-tuning mémoire-efficace (ZeRO + offloading)
3. Inférence à grande échelle
4. Optimisation de modèles MoE

**Forces :**
- Référence absolue pour l'entraînement à grande échelle
- Intégrations : HuggingFace Transformers, PyTorch Lightning, Accelerate
- ZeRO = révolution mémoire pour les grands modèles
- Microsoft backing

**Faiblesses :**
- Complexité de configuration élevée
- Moins adapté à l'inférence pure que vLLM
- Certaines features ZeRO peuvent avoir des incompatibilités
- Courbe d'apprentissage raide

**Statut en avril 2026 :** Actif, très mature.

---

### 11. Flash Attention

- **URL :** https://github.com/Dao-AILab/flash-attention
- **GitHub :** https://github.com/Dao-AILab/flash-attention
- **Stars :** ~23,100
- **Licence :** BSD-style (open-source)
- **Source de découverte :** GitHub direct + références dans vLLM, TGI, SGLang, etc.
- **Date de recherche :** 2026-04-01
- **Catégorie suggérée :** 18_ai_infrastructure
- **Sous-catégorie :** kernel optimization

**Description :**
Implémentation de référence de l'attention IO-aware pour transformers. FlashAttention a révolutionné l'entraînement et l'inférence LLM en réduisant la complexité mémoire de O(N²) à O(N) pour la mémoire HBM. Intégré dans pratiquement tous les frameworks d'inférence modernes.

**Versions :**
- FlashAttention-2 : ~2x plus rapide que v1, meilleure parallélisation
- FlashAttention-3 (beta) : optimisé H100/H800
- FlashAttention-4 : CuTeDSL, Hopper/Blackwell

**Features :**
- Attention exacte (pas approximative) avec mémoire optimisée
- MQA/GQA (Multi-Query / Grouped-Query Attention)
- Causal masking, sliding window, ALiBi
- KV cache pour inférence
- Rotary embeddings, Paged KV cache
- AMD ROCm MI200/MI300

**Forces :**
- Intégré dans tous les frameworks majeurs (PyTorch, vLLM, SGLang, TGI, DeepSpeed)
- Contribution fondamentale à l'écosystème LLM
- Réduction drastique de la VRAM pour les longs contextes

**Faiblesses :**
- Principalement NVIDIA (ROCm en cours)
- Nécessite Ampere+ (SM 8.0) pour FlashAttention-2
- Pas un framework complet : brique bas-niveau

**Statut en avril 2026 :** Actif, FlashAttention-4 en développement.

---

### 12. FlashInfer

- **URL :** https://flashinfer.ai
- **GitHub :** https://github.com/flashinfer-ai/flashinfer
- **Stars :** ~5,300
- **Licence :** Apache-2.0
- **Source de découverte :** GitHub direct + utilisé dans vLLM, SGLang
- **Date de recherche :** 2026-04-01
- **Catégorie suggérée :** 18_ai_infrastructure
- **Sous-catégorie :** kernel optimization

**Description :**
Générateur de kernels d'attention pour l'inférence LLM, couvrant des architectures plus diverses que FlashAttention. Spécialisé dans les workloads d'inférence (decode, prefill, append) avec support du KV cache paginé et ragged.

**Features :**
- KV-cache paginé et ragged pour le serving dynamique
- Kernels pour decode, prefill, append
- DeepSeek MLA (Multi-Latent Attention) - support spécifique
- Cascade attention (KV-cache hiérarchique)
- POD-Attention : fused prefill+decode (mixed batching)
- Support Turing (SM 7.5) à Blackwell (SM 12.1)
- Backends : FlashAttention-2/3, cuDNN, CUTLASS, TensorRT-LLM

**Cas d'usage :**
1. Backend kernel pour vLLM et SGLang
2. Kernels pour architectures MLA (DeepSeek)
3. Inférence avec attention sparse ou variable

**Forces :**
- Couverture hardware plus large que FlashAttention (Turing à Blackwell)
- Support de cas spéciaux (MLA, sparse attention)
- Intégré dans vLLM et SGLang comme backend optionnel

**Faiblesses :**
- Outil bas-niveau (pas un framework complet)
- NVIDIA uniquement

**Statut en avril 2026 :** Actif.

---

### 13. Microsoft BitNet

- **URL :** https://github.com/microsoft/BitNet
- **GitHub :** https://github.com/microsoft/BitNet
- **Stars :** ~36,900
- **Licence :** MIT
- **Source de découverte :** GitHub direct
- **Date de recherche :** 2026-04-01
- **Catégorie suggérée :** 18_ai_infrastructure
- **Sous-catégorie :** quantization / edge inference

**Description :**
Framework d'inférence officiel de Microsoft pour les LLMs 1-bit (BitNet b1.58). Permet d'exécuter des modèles 100B de paramètres sur un seul CPU à vitesse utilisable (5-7 tokens/sec).

**Performances :**
- CPU ARM : 1.37x à 5.07x de speedup vs FP16
- CPU x86 : 2.37x à 6.17x de speedup
- Réduction énergie : 55-82%
- 100B modèle sur 1 CPU : ~5-7 tokens/sec (vitesse de lecture humaine)

**Quantization :**
- Ternary weights (1.58-bit) : valeurs -1, 0, +1
- Kernels I2_S, TL1, TL2 selon la taille du modèle
- Inférence lossless (précision maintenue)

**Features :**
- Kernels parallèles (tiling configurable) : +1.15x à +2.1x speedup additionnel
- Support CPU et GPU, NPU futur
- Implémentation officielle Microsoft Research

**Cas d'usage :**
1. Inférence LLM sur CPU sans GPU
2. Edge devices (laptops, serveurs CPU)
3. Réduction drastique des coûts d'inférence
4. Modèles LLM embarqués

**Forces :**
- Seul framework officiel pour BitNet 1-bit models
- Performances CPU exceptionnelles
- Réduction énergie massive
- Microsoft Research backing

**Faiblesses :**
- Nécessite des modèles spécifiquement entraînés en 1-bit (pas de quantization post-training)
- Écosystème de modèles encore limité (vs GGUF)
- Moins universel que llama.cpp

**Statut en avril 2026 :** Actif, 36.9K stars témoignent de l'intérêt.

---

### 14. Unsloth

- **URL :** https://unsloth.ai
- **GitHub :** https://github.com/unslothai/unsloth
- **Stars :** ~58,800
- **Licence :** Apache-2.0 (core) + AGPL-3.0 (Studio UI)
- **Source de découverte :** GitHub direct
- **Date de recherche :** 2026-04-01
- **Catégorie suggérée :** 06_finetuning_training / 18_ai_infrastructure
- **Sous-catégorie :** training optimization / fine-tuning

**Description :**
Framework d'optimisation pour le fine-tuning de LLMs. Kernels Triton custom permettant un entraînement 2x plus rapide avec 70% moins de VRAM que les approches standard, sans perte de précision.

**Performances revendiquées :**
- 2x plus rapide, 70% moins de VRAM (fine-tuning standard)
- RL (GRPO) : 80% moins de VRAM
- MoE : 12x plus rapide, 35% moins de VRAM
- Long context (500K+ tokens) : 3x plus rapide, 30% moins de VRAM

**Features :**
- Full fine-tuning, LoRA, QLoRA (4-bit, 16-bit, FP8)
- RL : PPO, DPO, GRPO
- Data Recipes (auto-création de datasets depuis PDF, CSV, DOCX)
- Unsloth Studio (web UI no-code pour fine-tuning)
- Kernels Triton custom + optimisations mathématiques

**Modèles supportés :**
Llama, Qwen3, DeepSeek, Gemma, Phi, Mistral, 500+ modèles

**Forces :**
- Réduction VRAM massive (accessible sur GPU grand public)
- Aucune perte de précision par rapport à la baseline
- Interface Studio no-code (démocratisation du fine-tuning)
- 58.8K stars : adoption massive

**Faiblesses :**
- Studio UI sous AGPL (contraintes commerciales)
- Multi-GPU limité par rapport à DeepSpeed
- Principalement GPU NVIDIA

**Statut en avril 2026 :** Très actif.

---

### 15. PyTorch AO (torch.ao)

- **URL :** https://github.com/pytorch/ao
- **GitHub :** https://github.com/pytorch/ao
- **Stars :** ~2,800
- **Licence :** BSD-3-Clause
- **Source de découverte :** GitHub direct
- **Date de recherche :** 2026-04-01
- **Catégorie suggérée :** 18_ai_infrastructure
- **Sous-catégorie :** quantization / optimization

**Description :**
Bibliothèque PyTorch native de quantization et sparsité pour l'entraînement et l'inférence. Intégrée dans l'écosystème PyTorch officiel, compatible `torch.compile()` et FSDP2. Base technique d'Unsloth, vLLM, HuggingFace Transformers, Axolotl.

**Performances mesurées :**
- Int4 weight-only : 1.89x plus rapide, 58% moins de mémoire (Llama-3-8B)
- FP8 dynamic : 1.5-1.6x speedup (Gemma-3-27b)
- Float8 training : 1.5x speedup (models 405B+)
- QAT : récupère 67% de la dégradation de précision (Gemma3-4B)
- 2:4 sparsity : 1.3x speedup entraînement (ViT)

**Formats supportés :** Int4, Int8, FP8, MXFP, NF4, semi-structured 2:4 sparsity

**Forces :**
- Intégration PyTorch native (compatible torch.compile, FSDP2)
- Support entraînement ET inférence
- Intégré dans les frameworks majeurs
- Multi-plateforme (CUDA, XPU, CPU, mobile/ExecuTorch)

**Faiblesses :**
- Moins de stars que les alternatives (outil bas-niveau, souvent utilisé via d'autres frameworks)
- API encore en évolution

**Statut en avril 2026 :** Actif, projet officiel PyTorch.

---

### 16. bitsandbytes

- **URL :** https://github.com/TimDettmers/bitsandbytes
- **GitHub :** https://github.com/TimDettmers/bitsandbytes
- **Stars :** ~8,100
- **Licence :** MIT
- **Source de découverte :** GitHub direct + référence dans TGI, HuggingFace Transformers
- **Date de recherche :** 2026-04-01
- **Catégorie suggérée :** 18_ai_infrastructure
- **Sous-catégorie :** quantization

**Description :**
Bibliothèque de quantization k-bit pour PyTorch. Pionnière du QLoRA et de la démocratisation du fine-tuning sur GPU grand public via INT8 et INT4. Intégration native dans HuggingFace Transformers.

**Features :**
- **8-bit optimizers :** Block-wise quantization, performances équivalentes FP32
- **LLM.int8() :** Inférence FP16 ~50% moins de mémoire avec décomposition des outliers
- **QLoRA (4-bit) :** Fine-tuning 4-bit avec NF4 (Normal Float 4)

**Intégrations :**
```python
from transformers import BitsAndBytesConfig
# Chargement modèle 4-bit natif dans HuggingFace
```

**Forces :**
- Pionnier du QLoRA (paper fondateur 2023)
- Intégration HuggingFace native
- Démocratisation du fine-tuning (70B sur 2x A100)

**Faiblesses :**
- Performances inférieures à GPTQ/AWQ pour l'inférence pure
- Moins actif depuis l'émergence de PyTorch AO
- Principalement NVIDIA

**Statut en avril 2026 :** Actif mais ralenti, supplanté en partie par torch.ao pour les nouvelles fonctionnalités.

---

### 17. Apple CoreML Tools

- **URL :** https://apple.github.io/coremltools
- **GitHub :** https://github.com/apple/coremltools
- **Stars :** ~5,200
- **Licence :** BSD-3-Clause
- **Source de découverte :** GitHub direct
- **Date de recherche :** 2026-04-01
- **Catégorie suggérée :** 18_ai_infrastructure
- **Sous-catégorie :** edge deployment (Apple ecosystem)
- **Dernière version :** 9.0 (novembre 2025)

**Description :**
Toolkit officiel Apple pour convertir des modèles ML vers le format Core ML, optimisé pour les appareils Apple (iPhone, iPad, Mac, Apple Watch). Exploite CPU, GPU et Neural Engine (ANE) pour une inférence on-device maximale.

**Sources supportées :** PyTorch, TensorFlow 1.x/2.x, scikit-learn, XGBoost, LibSVM

**Features :**
- Conversion vers Core ML (.mlmodel, .mlpackage)
- Optimisation pour Neural Engine (ANE), GPU, CPU
- Privacy-first : inférence 100% on-device
- Quantization post-training
- iOS, macOS, watchOS, tvOS

**Forces :**
- Seul chemin vers l'ANE Apple (meilleures performances sur Apple Silicon)
- Privacy garantie (pas de cloud)
- Optimisation automatique par hardware cible
- Backing Apple officiel

**Faiblesses :**
- Apple ecosystem uniquement (lock-in complet)
- Conversion parfois complexe (opérations non supportées)
- Moins de flexibilité que ONNX Runtime

**Statut en avril 2026 :** Actif, v9.0 en novembre 2025.

---

### 18. ExecuTorch

- **URL :** https://pytorch.org/executorch
- **GitHub :** https://github.com/pytorch/executorch
- **Stars :** ~4,500
- **Licence :** BSD
- **Source de découverte :** GitHub direct
- **Date de recherche :** 2026-04-01
- **Catégorie suggérée :** 18_ai_infrastructure
- **Sous-catégorie :** edge deployment (mobile/embedded)

**Description :**
Solution de déploiement on-device de PyTorch pour smartphones, systèmes embarqués et microcontrôleurs. Alternative PyTorch-native à TFLite et Core ML, sans conversion intermédiaire (.onnx ou .tflite).

**Features :**
- Runtime base : 50KB footprint (microcontrôleurs)
- 12+ backends hardware : ARM, Qualcomm, MediaTek, Apple
- Android (XNNPACK, Vulkan, Qualcomm), iOS (CoreML, XNNPACK)
- Embedded/MCU : ARM Ethos-U, NXP, Cadence DSP
- Quantization : 8-bit, 4-bit, dynamique (via torchao)
- Modèles supportés : Llama, LLaVA, Voxtral, Whisper, MobileNetV2

**Forces :**
- Export direct depuis PyTorch (pas de conversion intermédiaire)
- Footprint minimal (50KB)
- Support MCU unique (ARM Cortex-M)
- Backed by Meta/PyTorch officiel

**Faiblesses :**
- Écosystème jeune vs TFLite/Core ML
- Moins de modèles pré-optimisés disponibles
- Documentation encore incomplète sur certains backends

**Statut en avril 2026 :** Actif.

---

### 19. BentoML

- **URL :** https://bentoml.com
- **GitHub :** https://github.com/bentoml/BentoML
- **Stars :** ~8,600
- **Licence :** Apache-2.0
- **Source de découverte :** GitHub direct
- **Date de recherche :** 2026-04-01
- **Catégorie suggérée :** 18_ai_infrastructure
- **Sous-catégorie :** model serving / MLOps

**Description :**
Framework de serving ML et IA polyvalent : REST APIs, job queues, applications LLM, pipelines multi-modèles. Alternative plus flexible que TorchServe, plus focalisée IA que FastAPI.

**Features :**
- API inference depuis n'importe quel script Python (type hints)
- Docker auto-généré avec gestion des dépendances
- Dynamic batching, model parallelism
- Multi-stage pipeline, multi-model orchestration
- BentoCloud : déploiement managé avec autoscaling
- Adaptive batching, observabilité intégrée

**Cas d'usage :**
1. Packaging et déploiement de modèles custom
2. API microservices IA
3. Pipelines multi-modèles (RAG + LLM + reranking)

**Forces :**
- Framework-agnostic (PyTorch, TF, JAX, n'importe quel modèle)
- Simple : quelques lignes de Python pour exposer un modèle
- Pipeline multi-modèles natif

**Faiblesses :**
- Moins spécialisé LLM que vLLM
- BentoCloud propriétaire pour le serving managé
- Moins de stars que les alternatives LLM-spécifiques

**Statut en avril 2026 :** Actif.

---

### 20. GPUStack

- **URL :** https://gpustack.ai
- **GitHub :** https://github.com/gpustack/gpustack
- **Stars :** ~4,800
- **Licence :** Apache-2.0
- **Source de découverte :** GitHub direct
- **Date de recherche :** 2026-04-01
- **Catégorie suggérée :** 18_ai_infrastructure
- **Sous-catégorie :** orchestration / cluster management

**Description :**
Manager de cluster GPU qui orchestre automatiquement les moteurs d'inférence (vLLM, SGLang, TensorRT-LLM) pour le déploiement de modèles IA à grande échelle. Couche de gestion au-dessus des moteurs d'inférence existants.

**Features :**
- Multi-cluster (on-prem, Kubernetes, cloud)
- Auto-configuration vLLM/SGLang/TensorRT-LLM
- Modes pré-tuned (latency vs throughput)
- KV cache étendu (LMCache, HiCache)
- Speculative decoding configuré automatiquement
- Failover automatique, load balancing
- Auth, access control, monitoring

**Accelerators supportés :**
NVIDIA, AMD, Ascend NPU, Hygon DCU, MThreads, Iluvatar, MetaX, Cambricon, T-Head PPU

**Forces :**
- Couche de gestion unifiée (hardware hétérogène)
- Auto-configuration des moteurs (évite la complexité de vLLM config)
- Support accélérateurs chinois (Ascend, Hygon, etc.)
- Failover automatique

**Faiblesses :**
- Projet jeune (4.8K stars)
- Ajoute une couche d'abstraction (overhead potentiel)
- Documentation encore en développement

**Statut en avril 2026 :** Actif, croissance rapide.

---

### 21. NVIDIA Megatron-LM

- **URL :** https://github.com/NVIDIA/Megatron-LM
- **GitHub :** https://github.com/NVIDIA/Megatron-LM
- **Stars :** ~15,900
- **Licence :** Apache
- **Source de découverte :** GitHub direct
- **Date de recherche :** 2026-04-01
- **Catégorie suggérée :** 18_ai_infrastructure
- **Sous-catégorie :** distributed training (large scale)

**Description :**
Framework NVIDIA pour l'entraînement de transformers à très grande échelle. Référence pour les modèles >100B paramètres sur clusters H100/A100. Utilisé par les labos de recherche et les entreprises pour entraîner les plus grands modèles.

**Parallelism :** TP + PP + DP + EP + CP (Context Parallelism)

**Performances :**
- 47% MFU (Model FLOP Utilization) sur clusters H100
- Modèles entraînés : 2B à 462B paramètres
- FP16, BF16, FP8, FP4 training

**Features :**
- Architectures : GPT, BERT, T5, VLM, MoE
- FSDP + DDP
- Dynamic context parallelism
- Communication overlapping
- Export TensorRT-LLM
- Multi-datacenter training

**Cas d'usage :**
1. Pre-entraînement LLM à très grande échelle
2. Entraînement MoE (Mixtral-class, DeepSeek-class)
3. Recherche en architecture de transformers

**Forces :**
- Référence NVIDIA pour >100B modèles
- 47% MFU = très efficace
- Support 5 types de parallélisme simultanés

**Faiblesses :**
- NVIDIA uniquement
- Complexité extrême (réservé aux experts infrastructure)
- Pas adapté au fine-tuning de petits modèles

**Statut en avril 2026 :** Actif, très mature.

---

### 22. Intel OpenVINO

- **URL :** https://openvino.ai
- **GitHub :** https://github.com/openvinotoolkit/openvino
- **Stars :** ~10,000
- **Licence :** Apache-2.0
- **Source de découverte :** GitHub direct + HuggingFace Optimum intégration
- **Date de recherche :** 2026-04-01
- **Catégorie suggérée :** 18_ai_infrastructure
- **Sous-catégorie :** inference (Intel hardware)

**Description :**
Toolkit d'optimisation et de déploiement IA d'Intel. Cible les CPUs Intel (x86, ARM), GPUs intégrés et discrets Intel, et NPUs Intel (Core Ultra, Xeon). Alternative à TensorRT pour hardware Intel.

**Frameworks supportés :** PyTorch, TensorFlow, ONNX, Keras, PaddlePaddle, JAX/Flax

**Features :**
- APIs C++, Python, C, NodeJS
- GenAI API pour pipelines génératifs
- NNCF (Neural Network Compression Framework) : quantization, pruning
- OpenVINO Model Server : serving scalable
- Intégrations : HuggingFace Optimum, LangChain

**Cas d'usage :**
1. Inférence optimisée sur hardware Intel (CPU, GPU intégré, NPU)
2. Edge AI sur Intel Core Ultra (NPU intégré)
3. Déploiement cross-framework sans vendor lock-in GPU NVIDIA

**Forces :**
- Seule option optimale pour NPU Intel
- Aucune dépendance GPU NVIDIA
- Support large de frameworks via conversion
- Intel backing

**Faiblesses :**
- Intel hardware principalement (performances sur AMD/NVIDIA inférieures)
- Conversion ONNX→OpenVINO requise
- Moins de ressources communautaires que PyTorch/NVIDIA

**Statut en avril 2026 :** Actif.

---

### 23. LoRAX

- **URL :** https://loraexchange.ai
- **GitHub :** https://github.com/predibase/lorax
- **Stars :** ~3,700
- **Licence :** Apache-2.0
- **Source de découverte :** GitHub direct
- **Date de recherche :** 2026-04-01
- **Catégorie suggérée :** 18_ai_infrastructure
- **Sous-catégorie :** inference (multi-LoRA serving)

**Description :**
Framework spécialisé dans le serving de milliers d'adapters LoRA sur un seul GPU. Résout le problème économique du déploiement de nombreux modèles fine-tunés : au lieu d'un GPU par modèle, des centaines d'adapters sur un seul GPU.

**Features :**
- Dynamic adapter loading (just-in-time depuis HuggingFace/filesystem)
- Heterogeneous continuous batching (requêtes différents adapters en un seul batch)
- Adapter exchange scheduling (CPU↔GPU swap asynchrone)
- CUDA kernels SGMV pour multi-LoRA efficace
- Tensor parallelism, paged attention, quantization
- OpenAI-compatible API
- Kubernetes Helm charts, Prometheus, OpenTelemetry

**Cas d'usage :**
1. Serving multi-tenant (chaque client a son LoRA)
2. SaaS avec modèles personnalisés par utilisateur
3. A/B testing de fine-tunes

**Forces :**
- Cas d'usage unique (multi-LoRA à grande échelle)
- Économies massives (1 GPU vs N GPUs)
- Production-ready (Helm, monitoring, auth)

**Faiblesses :**
- Niche (multi-LoRA uniquement)
- Moins de features générales que vLLM
- Communauté plus petite

**Statut en avril 2026 :** Actif.

---

### 24. OpenAI Triton (GPU Kernel Language)

- **URL :** https://triton-lang.org
- **GitHub :** https://github.com/openai/triton
- **Stars :** ~18,800
- **Licence :** MIT
- **Source de découverte :** GitHub direct
- **Date de recherche :** 2026-04-01
- **Catégorie suggérée :** 18_ai_infrastructure
- **Sous-catégorie :** kernel development

**Description :**
Langage et compilateur pour écrire des kernels GPU personnalisés de deep learning, plus productif que CUDA tout en étant plus flexible que les DSLs restrictifs. Utilisé par PyTorch (torch.compile), Unsloth, et de nombreux frameworks pour leurs kernels optimisés.

**Features :**
- MLIR-based backend (v2.0)
- Abstraction tile-based (higher-level que CUDA threads)
- Kernels composables (back-to-back matmuls, Flash Attention possible)
- NVIDIA (SM 8.0+), AMD (ROCm 6.2+)
- Mode interpréteur pour debugging
- Optimisation automatique des configurations

**Cas d'usage :**
1. Écriture de kernels custom pour nouveaux opérateurs
2. Base pour torch.compile (optimisation end-to-end)
3. Kernels d'attention custom (Flash Attention 3 écrit en Triton)

**Forces :**
- Productivité >> CUDA pour écrire des kernels
- Intégration native torch.compile
- Support NVIDIA + AMD (rare pour un kernel language)

**Faiblesses :**
- Courbe d'apprentissage (pas trivial malgré l'abstraction)
- Performances parfois inférieures à CUDA écrit à la main
- Moins de contrôle bas-niveau que CUDA

**Statut en avril 2026 :** Très actif (base de tout l'écosystème PyTorch 2.x).

---

### 25. GGML

- **URL :** https://github.com/ggml-org/ggml
- **GitHub :** https://github.com/ggml-org/ggml
- **Stars :** ~14,300
- **Licence :** MIT
- **Source de découverte :** GitHub direct
- **Date de recherche :** 2026-04-01
- **Catégorie suggérée :** 18_ai_infrastructure
- **Sous-catégorie :** kernel/tensor library (base layer)

**Description :**
Bibliothèque tensor bas-niveau pour le machine learning, sans dépendances. Fondation de llama.cpp et whisper.cpp. Pionnier du format GGUF pour la quantization et portabilité des modèles.

**Features :**
- C pur, sans dépendances
- Quantization entière (1-8 bits)
- Differentiation automatique
- Optimiseurs ADAM et L-BFGS
- Zero memory allocations à runtime
- Support hardware large via llama.cpp (Metal, CUDA, Vulkan, etc.)

**Note :** Le développement principal se déroule désormais dans les repos llama.cpp et whisper.cpp.

**Forces :**
- Portabilité maximale (C pur, aucune dépendance)
- Base technique de l'écosystème llama.cpp/whisper.cpp
- Format GGUF = standard industriel

**Faiblesses :**
- Outil bas-niveau (pas utilisé directement en production)
- Développement migré vers llama.cpp

**Statut en avril 2026 :** Actif (via llama.cpp principalement).

---

### 26. llama-cpp-python

- **URL :** https://github.com/abetlen/llama-cpp-python
- **GitHub :** https://github.com/abetlen/llama-cpp-python
- **Stars :** ~10,100
- **Licence :** MIT
- **Source de découverte :** GitHub direct
- **Date de recherche :** 2026-04-01
- **Catégorie suggérée :** 18_ai_infrastructure
- **Sous-catégorie :** inference (Python bindings)

**Description :**
Bindings Python simples pour llama.cpp. Expose une API Python haute-niveau et une API OpenAI-compatible pour intégrer llama.cpp dans des applications Python sans complexité C++.

**Features :**
- API Python avec type hints
- API OpenAI-compatible (drop-in replacement)
- Chat multi-format (llama-2, chatml, gemma, auto-detect)
- JSON Schema constrained generation
- Function calling / tool use
- Multimodal (LLaVA, Moondream, Qwen2.5-VL)
- Backends : CUDA, Metal, ROCm, Vulkan, OpenBLAS, SYCL
- Intégrations : LangChain, LlamaIndex, HuggingFace Hub

**Forces :**
- La voie Python la plus simple vers llama.cpp
- API OpenAI-compatible pour migration facile
- Support multimodal
- 10K stars : adoption massive

**Faiblesses :**
- Wrapper sur llama.cpp : limitations héritées
- Moins de features que Ollama pour la gestion de modèles

**Statut en avril 2026 :** Actif.

---

### 27. GPTQModel (successeur AutoGPTQ)

- **URL :** https://github.com/ModelCloud/GPTQModel
- **GitHub :** https://github.com/ModelCloud/GPTQModel
- **Stars :** ~1,100
- **Licence :** Apache-2.0
- **Source de découverte :** GitHub direct + Note de dépréciation AutoGPTQ
- **Date de recherche :** 2026-04-01
- **Catégorie suggérée :** 18_ai_infrastructure
- **Sous-catégorie :** quantization

**Description :**
Successeur actif de AutoGPTQ (archivé avril 2025). Toolkit de quantization LLM multi-méthodes avec support hardware étendu. AutoGPTQ est archivé et redirige vers GPTQModel.

**Méthodes de quantization :**
GPTQ, AWQ, ParoQuant, QQQ, GGUF export, FP8, EXL3

**Hardware :** NVIDIA CUDA, AMD ROCm, Intel XPU, CPU (Intel/AMD/Apple)

**Features :**
- Data Parallelism multi-GPU : 80%+ de réduction du temps de quantization
- Python 3.13t (free threading) pour multi-GPU accéléré
- Support MoE avec routing controls
- Dynamic per-module quantization
- lm_head quant pour réduction VRAM supplémentaire
- GPTQ 4-bit = BF16 natif (benchmarks)
- Intégrations : HuggingFace, Optimum, Peft, vLLM, SGLang

**Forces :**
- Remplace officiellement AutoGPTQ (6K stars ancienne repo)
- Multi-méthodes (GPTQ, AWQ, EXL3...)
- Intégration vLLM et SGLang
- Hardware plus large qu'AutoGPTQ

**Faiblesses :**
- Jeune (1.1K stars, hérite de la notoriété d'AutoGPTQ)
- Moins de documentation que l'ancienne bibliothèque

**Note importante :** AutoGPTQ (5K stars) a été archivé le 11 avril 2025. GPTQModel est la continuation active.

**Statut en avril 2026 :** Actif, remplace AutoGPTQ.

---

### 28. xFormers

- **URL :** https://github.com/facebookresearch/xformers
- **GitHub :** https://github.com/facebookresearch/xformers
- **Stars :** ~10,400
- **Licence :** BSD
- **Source de découverte :** GitHub direct
- **Date de recherche :** 2026-04-01
- **Catégorie suggérée :** 18_ai_infrastructure
- **Sous-catégorie :** kernel optimization

**Description :**
Toolkit Meta pour des composants transformer optimisés et personnalisables. Focus sur la mémoire et la vitesse via des kernels CUDA custom et des opérations fusionnées.

**Features :**
- Memory-efficient attention (jusqu'à 10x plus rapide)
- Sparse et block-sparse attention
- Opérations fusionnées : softmax, linear, LayerNorm, dropout-activation-bias, SwiGLU
- Kernels CUDA custom + dispatch vers bibliothèques externes

**Forces :**
- Meta Research backing
- Attention mémoire-efficace
- Composants modulaires intégrables dans des architectures custom

**Faiblesses :**
- Moins pertinent depuis FlashAttention 3/4 (plus optimisé)
- Framework de recherche plus qu'outil production
- Usage déclinant au profit de FlashAttention

**Statut en avril 2026 :** Actif mais moins central qu'avant.

---

### 29. HuggingFace Text Embeddings Inference (TEI)

- **URL :** https://github.com/huggingface/text-embeddings-inference
- **GitHub :** https://github.com/huggingface/text-embeddings-inference
- **Stars :** ~4,600
- **Licence :** Apache-2.0
- **Source de découverte :** GitHub direct
- **Date de recherche :** 2026-04-01
- **Catégorie suggérée :** 18_ai_infrastructure / 05_rag_knowledge
- **Sous-catégorie :** inference (embeddings)

**Description :**
Solution de serving haute-performance spécialisée pour les modèles d'embeddings et de classification de séquences. Complément de TGI pour les modèles non-génératifs.

**Features :**
- Dynamic batching (token-based)
- Flash Attention, Candle framework, cuBLASLt
- Safetensors + ONNX
- Docker images légères (serverless-ready)
- gRPC API
- Multi-GPU backends
- OpenTelemetry + Prometheus
- macOS Metal, ARM64
- Modèles : BERT, Mistral, Qwen, GTE, et autres

**Cas d'usage :**
1. Serving d'embeddings pour RAG
2. Classification de texte haute-performance
3. Reranking dans les pipelines RAG

**Forces :**
- Démarrage immédiat (pas de compilation)
- Très rapide pour les embeddings
- Production-ready (Docker, monitoring)

**Faiblesses :**
- Spécialisé embeddings (pas de génération de texte)
- Moins connu que TGI

**Statut en avril 2026 :** Actif. TGI en maintenance mais TEI actif.

---

### 30. FastChat (LMSys)

- **URL :** https://github.com/lm-sys/FastChat
- **GitHub :** https://github.com/lm-sys/FastChat
- **Stars :** ~39,500
- **Licence :** Apache-2.0
- **Source de découverte :** GitHub direct
- **Date de recherche :** 2026-04-01
- **Catégorie suggérée :** 18_ai_infrastructure / 13_benchmarks
- **Sous-catégorie :** serving + benchmarking

**Description :**
Plateforme ouverte pour entraîner, server et évaluer des chatbots LLM. Moteur du Chatbot Arena (10M+ chats, 70+ LLMs, 1.5M votes humains). Inclut le modèle Vicuna.

**Features :**
- Système de serving distribué multi-modèles
- Web UI, API OpenAI-compatible
- Chatbot Arena (comparaison side-by-side)
- MT-Bench (benchmark multi-tour)
- Support Llama 2, Vicuna, Alpaca, ChatGLM, Falcon, 70+ modèles
- Single/multi-GPU, CPU-only, Metal (Mac), AMD ROCm

**Forces :**
- Référence benchmarking (Chatbot Arena = classement LLM)
- Serving multi-modèles natif
- Modèles Vicuna reconnus (fine-tunes Llama)

**Faiblesses :**
- Pas aussi performant que vLLM pour le serving pur
- Focus recherche/benchmark plus que production

**Statut en avril 2026 :** Actif (Chatbot Arena actif).

---

## Projets dépréciés / archivés à noter

| Projet | Statut | Remplaçant recommandé |
|--------|--------|----------------------|
| AutoGPTQ | Archivé (avril 2025) | GPTQModel |
| AutoAWQ | Archivé (mai 2025) | vLLM llm-compressor |
| HuggingFace TGI | Maintenance (mars 2026) | vLLM ou SGLang |

---

## Matrice de synthèse - Moteurs d'inférence

| Outil | Stars | Use Case Principal | Hardware | Status |
|-------|-------|-------------------|----------|--------|
| Ollama | 167K | Local dev, privacy | CPU+GPU | Actif |
| llama.cpp | 101K | CPU/edge, local | CPU+GPU | Actif |
| vLLM | 75K | Serving prod multi-GPU | NVIDIA, AMD | Actif |
| Unsloth | 59K | Fine-tuning | NVIDIA | Actif |
| FastChat | 39K | Serving+benchmark | Multi | Actif |
| BitNet | 37K | CPU 1-bit inference | CPU+GPU | Actif |
| DeepSpeed | 42K | Distributed training | Multi | Actif |
| SGLang | 25K | Serving prod + diffusion | NVIDIA, AMD, TPU | Actif |
| Flash Attention | 23K | Kernel attention | NVIDIA, AMD | Actif |
| MLC LLM | 22K | Mobile/Web/Edge | Universal | Actif |
| Megatron-LM | 16K | Pre-training >100B | NVIDIA | Actif |
| GGML | 14K | Tensor library base | Universal | Actif |
| TensorRT-LLM | 13K | Serving NVIDIA max perf | NVIDIA | Actif |
| llama-cpp-python | 10K | Python bindings local | CPU+GPU | Actif |
| xFormers | 10K | Attention kernels | NVIDIA | Actif |
| OpenVINO | 10K | Inference Intel | Intel | Actif |
| TGI | 11K | Serving HuggingFace | Multi | MAINTENANCE |
| Triton Server | 10K | Serving multi-framework | NVIDIA | Actif |
| bitsandbytes | 8K | QLoRA quantization | NVIDIA | Actif |
| BentoML | 9K | API serving | Multi | Actif |
| CoreML Tools | 5K | Apple edge | Apple | Actif |
| FlashInfer | 5K | Attention kernels | NVIDIA | Actif |
| ExLlamaV2 | 5K | Consumer GPU quant | NVIDIA | Actif |
| TEI | 5K | Embedding serving | NVIDIA | Actif |
| ExecuTorch | 5K | Mobile/MCU | ARM+Apple | Actif |
| GPUStack | 5K | Cluster management | Multi | Actif |
| CoreML Tools | 5K | Apple ecosystem | Apple | Actif |
| LoRAX | 4K | Multi-LoRA serving | NVIDIA | Actif |
| PyTorch AO | 3K | Quantization native | Multi | Actif |
| GPTQModel | 1K | GPTQ quantization | Multi | Actif |
| OpenAI Triton | 19K | Kernel language | NVIDIA, AMD | Actif |

---

## Recommandations pour le catalogage

### Priorité haute (outils manquants, très importants)
1. **vLLM** - Leader absolu serving production, 74.9K stars, release v0.18.1 hier
2. **llama.cpp** - 101K stars, standard edge/local, format GGUF
3. **SGLang** - 25K stars, challenger vLLM, recommandé par TGI
4. **Ollama** - 167K stars, standard absolu inférence locale
5. **TensorRT-LLM** - Référence NVIDIA production
6. **DeepSpeed** - 42K stars, standard distributed training
7. **Flash Attention** - Brique fondamentale tout l'écosystème
8. **BitNet** - 37K stars, inférence 1-bit révolutionnaire
9. **Unsloth** - 59K stars, fine-tuning accessible

### Priorité moyenne
10. **ExLlamaV2** - Consumer GPU quantization
11. **MLC LLM** - Mobile/Web (use case unique)
12. **bitsandbytes** - QLoRA, intégration HF
13. **NVIDIA Triton Server** - Serving enterprise NVIDIA
14. **BentoML** - Serving polyvalent
15. **GPUStack** - Cluster management unifié

### Priorité basse (outils plus spécialisés ou base layer)
16. **FlashInfer** - Kernel bas-niveau
17. **OpenVINO** - Intel-specific
18. **CoreML Tools** - Apple-specific
19. **ExecuTorch** - MCU/mobile PyTorch
20. **LoRAX** - Multi-LoRA niche
21. **PyTorch AO** - Base layer PyTorch
22. **OpenAI Triton** - Kernel language
23. **GGML** - Bibliothèque base (llama.cpp)
24. **llama-cpp-python** - Wrapper Python
25. **GPTQModel** - Successeur AutoGPTQ
26. **xFormers** - Kernels Meta (moins central)
27. **TEI** - Embedding serving spécialisé

### A documenter comme "deprecated/archived"
- AutoGPTQ (archivé avril 2025)
- AutoAWQ (archivé mai 2025)
- TGI (maintenance mars 2026)

---

## Sources utilisées

- https://github.com/vllm-project/vllm
- https://github.com/ggml-org/llama.cpp
- https://github.com/sgl-project/sglang
- https://github.com/ollama/ollama
- https://github.com/NVIDIA/TensorRT-LLM
- https://github.com/huggingface/text-generation-inference
- https://github.com/triton-inference-server/server
- https://github.com/turboderp/exllamav2
- https://github.com/mlc-ai/mlc-llm
- https://github.com/microsoft/DeepSpeed
- https://github.com/Dao-AILab/flash-attention
- https://github.com/flashinfer-ai/flashinfer
- https://github.com/microsoft/BitNet
- https://github.com/unslothai/unsloth
- https://github.com/pytorch/ao
- https://github.com/TimDettmers/bitsandbytes
- https://github.com/apple/coremltools
- https://github.com/pytorch/executorch
- https://github.com/predibase/lorax
- https://github.com/bentoml/BentoML
- https://github.com/gpustack/gpustack
- https://github.com/NVIDIA/Megatron-LM
- https://github.com/openvinotoolkit/openvino
- https://github.com/openai/triton
- https://github.com/ggml-org/ggml
- https://github.com/abetlen/llama-cpp-python
- https://github.com/ModelCloud/GPTQModel
- https://github.com/facebookresearch/xformers
- https://github.com/huggingface/text-embeddings-inference
- https://github.com/lm-sys/FastChat
- https://github.com/microsoft/onnxruntime (déjà catalogué)
- https://github.com/ray-project/ray (déjà catalogué)
- https://github.com/skypilot-org/skypilot (déjà catalogué)
