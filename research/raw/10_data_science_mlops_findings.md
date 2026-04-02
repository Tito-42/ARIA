# 10_data_science_mlops — Research Findings
**Date**: 2026-04-01
**Sources**: GitHub repos, web search, awesome lists

---

## Outils Identifiés (24 outils)

### LLM Inference Serving

### 1. Ollama
- **URL**: https://github.com/ollama/ollama
- **Stars**: ~167k
- **Licence**: MIT
- **Description**: Standard pour exécuter des LLMs en local. Interface simple, gestion de modèles, API compatible OpenAI.
- **Forces**: Ultra-simple, standard de facto pour LLM local, multi-OS, API OpenAI-compatible
- **Faiblesses**: Moins optimisé que vLLM pour production haute performance
- **Statut**: Très actif

### 2. vLLM
- **URL**: https://github.com/vllm-project/vllm
- **Stars**: ~74.9k
- **Licence**: Apache 2.0
- **Description**: Moteur d'inférence LLM haute performance. PagedAttention, continuous batching, tensor parallelism.
- **Forces**: Standard production, PagedAttention, throughput maximal, multi-GPU
- **Faiblesses**: Complexe à configurer, NVIDIA-focused
- **Statut**: Production critique (v0.18.1, 31/03/2026)

### 3. SGLang
- **URL**: https://github.com/sgl-project/sglang
- **Stars**: ~25.3k
- **Licence**: Apache 2.0
- **Description**: Moteur d'inférence LLM avec RadixAttention. Concurrent/challenger de vLLM avec prefix caching avancé.
- **Forces**: RadixAttention innovant, bat vLLM sur prefix caching, 400k+ GPUs en déploiement
- **Faiblesses**: Écosystème moins mature que vLLM
- **Statut**: Production, en forte croissance

### 4. TGI (HuggingFace Text Generation Inference)
- **URL**: https://github.com/huggingface/text-generation-inference
- **Stars**: ~10.8k
- **Licence**: Apache 2.0
- **Description**: Serveur d'inférence HuggingFace pour LLMs. **EN MODE MAINTENANCE depuis mars 2026**.
- **Forces**: Intégration HF native, simple à déployer
- **Faiblesses**: **MODE MAINTENANCE** — pas de nouvelles features, migrer vers vLLM/SGLang
- **Statut**: Maintenance

### 5. Triton Inference Server (NVIDIA)
- **URL**: https://github.com/triton-inference-server/server
- **Stars**: ~10.5k
- **Licence**: BSD-3
- **Description**: Serveur d'inférence enterprise multi-framework par NVIDIA. Supporte PyTorch, TensorFlow, ONNX, TensorRT.
- **Forces**: Multi-framework, enterprise-grade, model ensemble, dynamic batching
- **Faiblesses**: Configuration complexe, NVIDIA-centric
- **Statut**: Actif (v2.67.0, mars 2026)

### 6. OpenLLM
- **URL**: https://github.com/bentoml/OpenLLM
- **Stars**: ~12.3k
- **Licence**: Apache 2.0
- **Description**: Plateforme pour servir des LLMs en production par BentoML.
- **Forces**: Simple, intégration BentoML
- **Faiblesses**: **Stalled** — dernier release avril 2025, risque d'abandon
- **Statut**: Stalled

### 7. BentoML
- **URL**: https://github.com/bentoml/BentoML
- **Stars**: ~8.6k
- **Licence**: Apache 2.0
- **Description**: Framework pour packager et déployer des modèles ML/LLM. Bento format, cloud deploy, monitoring.
- **Forces**: Polyvalent, packaging simple, cloud-native, monitoring intégré
- **Faiblesses**: Écosystème plus petit que MLflow
- **Statut**: Actif (v1.4.37)

---

### Experiment Tracking

### 8. MLflow
- **URL**: https://github.com/mlflow/mlflow
- **Stars**: ~25k
- **Licence**: Apache 2.0
- **Description**: Plateforme MLOps open-source. Experiment tracking, model registry, serving, GenAI tracing. Repositionné comme "AI engineering platform".
- **Forces**: Standard industrie, 60M+ téléchargements/mois, complet, bonne intégration GenAI
- **Faiblesses**: UI moins moderne que W&B, peut être lourd
- **Statut**: Production standard

### 9. Weights & Biases (W&B)
- **URL**: https://github.com/wandb/wandb
- **Stars**: ~10.9k
- **Licence**: MIT
- **Description**: Plateforme d'experiment tracking et MLOps. UI premium, Weave pour GenAI observabilité.
- **Forces**: Meilleure UI du marché, Weave pour GenAI, collaboration équipe, Sweeps pour hyperparams
- **Faiblesses**: Version SaaS payante pour teams, vendor lock-in possible
- **Statut**: Enterprise standard

### 10. ClearML
- **URL**: https://github.com/allegroai/clearml
- **Stars**: ~6.6k
- **Licence**: Apache 2.0
- **Description**: Suite MLOps complète. Experiment tracking, orchestration, data management, serving.
- **Forces**: All-in-one le plus complet, self-hosted, agent scheduling
- **Faiblesses**: Communauté plus petite, UI moins polish que W&B
- **Statut**: Production

---

### Pipeline Orchestration

### 11. Apache Airflow
- **URL**: https://github.com/apache/airflow
- **Stars**: ~44.8k
- **Licence**: Apache 2.0
- **Description**: Standard pour l'orchestration de workflows data/ML. DAGs Python, 500+ intégrations.
- **Forces**: Standard industrie, 500+ intégrations, communauté massive, Apache Foundation
- **Faiblesses**: Pas spécifique ML, DAGs complexes pour simples pipelines
- **Statut**: Très actif (v3.1.8)

### 12. Ray / Ray Serve
- **URL**: https://github.com/ray-project/ray
- **Stars**: ~41.9k
- **Licence**: Apache 2.0
- **Description**: Framework de computing distribué par Anyscale. Ray Serve pour model serving, Ray Train pour distributed training.
- **Forces**: Computing distribué puissant, 26k+ dependents, multi-usage (serve, train, tune)
- **Faiblesses**: Complexe à opérer, overhead pour tâches simples
- **Statut**: Enterprise (v2.54.1)

### 13. Prefect
- **URL**: https://github.com/PrefectHQ/prefect
- **Stars**: ~22k
- **Licence**: Apache 2.0
- **Description**: Orchestrateur de workflows Python-first. Alternative moderne à Airflow.
- **Forces**: Python-first, UI élégante, simple à démarrer, bonne DX
- **Faiblesses**: Moins d'intégrations qu'Airflow
- **Statut**: Production (v3.6.24)

### 14. Argo Workflows
- **URL**: https://github.com/argoproj/argo-workflows
- **Stars**: ~16.6k
- **Licence**: Apache 2.0
- **Description**: Moteur de workflows Kubernetes-natif. CNCF Graduated project.
- **Forces**: Kubernetes-natif, CNCF Graduated, containérisé, scalable
- **Faiblesses**: Nécessite Kubernetes, YAML verbose
- **Statut**: Actif (v4.0.3)

### 15. DVC (Data Version Control)
- **URL**: https://github.com/iterative/dvc
- **Stars**: ~15.5k
- **Licence**: Apache 2.0
- **Description**: Versioning de données et pipelines ML. Git-native, remote storage.
- **Forces**: Git-native, simple, remote storage flexible, pipelines reproductibles
- **Faiblesses**: Limité pour orchestration complexe
- **Statut**: Production (v3.67.1, 31/03/2026)

### 16. Dagster
- **URL**: https://github.com/dagster-io/dagster
- **Stars**: ~15.2k
- **Licence**: Apache 2.0
- **Description**: Orchestrateur asset-centric pour data pipelines. Software-defined assets.
- **Forces**: Approche asset-centric innovante, UI excellente, type-safety
- **Faiblesses**: Paradigme différent (courbe d'apprentissage)
- **Statut**: Production (v1.12.21)

### 17. Kubeflow
- **URL**: https://github.com/kubeflow/kubeflow
- **Stars**: ~15.5k
- **Licence**: Apache 2.0
- **Description**: Plateforme ML sur Kubernetes. Pipelines, notebooks, training, serving.
- **Forces**: Full ML platform sur K8s, standard enterprise
- **Faiblesses**: Complexe à opérer, release annuel (dernier mars 2025)
- **Statut**: Enterprise

### 18. Metaflow
- **URL**: https://github.com/Netflix/metaflow
- **Stars**: ~10k
- **Licence**: Apache 2.0
- **Description**: Framework ML par Netflix. Python-first, data science oriented, 3000+ projets internes Netflix.
- **Forces**: Netflix-prouvé, DX excellente, cloud-native (AWS/Azure), Python simple
- **Faiblesses**: AWS-centric historiquement
- **Statut**: Production

### 19. ZenML
- **URL**: https://github.com/zenml-io/zenml
- **Stars**: ~5.3k
- **Licence**: Apache 2.0
- **Description**: Framework MLOps extensible. Supporte ML, LLM et agents. MCP Server natif pour Claude.
- **Forces**: ML + LLM + Agent, MCP Server natif, stack flexible, bonne abstraction
- **Faiblesses**: Communauté plus petite
- **Statut**: Production

---

### Feature Stores & Data Quality

### 20. Great Expectations
- **URL**: https://github.com/great-expectations/great_expectations
- **Stars**: ~11.3k
- **Licence**: Apache 2.0
- **Description**: Framework de validation et documentation de données. Tests de qualité automatisés.
- **Forces**: Standard data quality, tests déclaratifs, documentation auto, profiling
- **Faiblesses**: Configuration initiale verbose
- **Statut**: Production (v1.15.1)

### 21. Evidently AI
- **URL**: https://github.com/evidentlyai/evidently
- **Stars**: ~7.4k
- **Licence**: Apache 2.0
- **Description**: Monitoring de modèles ML et LLM. Détection de drift, métriques de performance, rapports.
- **Forces**: ML + LLM monitoring, rapports visuels, drift detection, CI/CD
- **Faiblesses**: Features avancées payantes
- **Statut**: Production (v0.7.21)

### 22. Feast
- **URL**: https://github.com/feast-dev/feast
- **Stars**: ~6.9k
- **Licence**: Apache 2.0
- **Description**: Feature store open-source. Online/offline serving, support Qdrant pour vector features.
- **Forces**: Standard feature store, online+offline, Qdrant support, simple
- **Faiblesses**: Écosystème restreint vs solutions cloud
- **Statut**: Production

---

### Infrastructure

### 23. SkyPilot
- **URL**: https://github.com/skypilot-org/skypilot
- **Stars**: ~9.7k
- **Licence**: Apache 2.0
- **Description**: Framework multi-cloud pour ML. Optimise coûts via spot instances, 3-6x d'économies.
- **Forces**: Multi-cloud automatique, spot instances, 3-6x cost savings, simple CLI
- **Faiblesses**: Dépend des clouds providers
- **Statut**: Production (v0.12.0)

### 24. Seldon Core
- **URL**: https://github.com/SeldonIO/seldon-core
- **Stars**: ~4.7k
- **Licence**: **BSL (Business Source License)**
- **Description**: Plateforme de déploiement ML sur Kubernetes. Model serving, A/B testing, canary.
- **Forces**: ML serving avancé, A/B testing, canary deployments, monitoring
- **Faiblesses**: **BSL licence — pas véritablement open-source pour usage commercial**, vérifier avec legal
- **Statut**: Actif

---

## Alertes Critiques

1. **TGI (HuggingFace)** — Officiellement en mode maintenance. Ne pas utiliser pour nouveaux projets, migrer vers vLLM/SGLang
2. **Seldon Core** — Changement vers BSL (Business Source License) — vérifier implications légales avant usage enterprise
3. **OpenLLM** — Pas de release depuis avril 2025 — risque d'abandon silencieux

---

## Tendances Clés (Avril 2026)

1. **vLLM + SGLang dominent le serving** — SGLang monte rapidement comme challenger
2. **MLflow se repositionne** — D'experiment tracker à "AI engineering platform" complet
3. **TGI en maintenance** — HuggingFace redirige vers vLLM/SGLang
4. **Orchestration mature** — Airflow reste le standard, Prefect et Dagster gagnent du terrain
5. **ZenML intègre MCP** — Première intégration native avec Claude via MCP Server
6. **Monitoring LLM** — Evidently et W&B Weave étendent le monitoring aux LLMs
