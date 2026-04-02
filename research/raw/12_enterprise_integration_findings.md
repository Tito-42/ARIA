# Research Findings - Catégorie 12: Enterprise Integration

- **Date de recherche**: 2026-04-02
- **Chercheur**: Agent OSINT ARIA
- **Sources explorées**: GitHub direct fetch, documentation officielle
- **Méthode**: WebFetch sur les repos GitHub + pages docs officielles

---

## Synthèse

27 outils identifiés répartis en 6 sous-catégories. Le catalogue actuel (3 fiches : anthropic-api, ai-gateway-patterns, model-routing) couvre uniquement les patterns architecturaux génériques. Il manque tous les outils concrets d'implémentation.

**Priorités de catalogage recommandées** (par impact enterprise) :
1. LiteLLM - gateway le plus adopté (41.9k stars, Stripe/Netflix)
2. Langfuse - observabilité LLM leader open source (24.2k stars)
3. MLflow - standard MLOps avec LLM support (25.1k stars, Databricks)
4. Portkey Gateway - gateway enterprise complet (11.2k stars)
5. Promptfoo - testing/CI pour LLM apps (19.1k stars)
6. DeepEval - framework eval LLM (14.4k stars)
7. NeMo Guardrails - guardrails enterprise NVIDIA (5.9k stars)
8. Microsoft Presidio - PII detection (7.5k stars)

---

## 1. OBSERVABILITE / MONITORING LLM

### 1.1 Langfuse
- **URL**: https://langfuse.com
- **GitHub**: https://github.com/langfuse/langfuse
- **Stars**: 24 200
- **Licence**: MIT (sauf dossiers `ee/`)
- **Pricing**: Freemium - Cloud (free tier) + self-hosted gratuit
- **Source de découverte**: GitHub direct
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 12_enterprise_integration
- **Sous-catégorie**: observability
- **Description**: Plateforme d'engineering LLM open source pour monitorer, évaluer et déboguer les applications IA. Traces, prompt management, datasets, évaluations LLM-as-judge.
- **Pourquoi c'est pertinent**: Leader open source de l'observabilité LLM. Self-hosted en minutes (Docker, K8s, Helm, Terraform AWS/Azure/GCP). Battle-tested en production. Intègre 20+ frameworks (OpenAI, LangChain, LlamaIndex, LiteLLM). Couvre le cycle complet dev→prod.
- **Enterprise**: Self-hosted possible, SOC2 (cloud), 24.2k stars, très actif

---

### 1.2 OpenLLMetry (Traceloop)
- **URL**: https://www.traceloop.com
- **GitHub**: https://github.com/traceloop/openllmetry
- **Stars**: 7 000
- **Licence**: Apache 2.0
- **Pricing**: Open source + Traceloop cloud (freemium)
- **Source de découverte**: GitHub direct
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 12_enterprise_integration
- **Sous-catégorie**: observability
- **Description**: Observabilité GenAI basée sur OpenTelemetry. Instrumente 16+ providers LLM, 7 vector DBs, et se connecte à 24+ backends (Datadog, Honeycomb, Grafana, New Relic, Splunk...).
- **Pourquoi c'est pertinent**: Approche standards-first (OpenTelemetry) - idéal pour les enterprises qui ont déjà Datadog/Grafana. 2 lignes de code pour instrumenter. Pas de vendor lock-in sur l'observabilité.
- **Enterprise**: Intégration native dans stack observabilité existante, Apache 2.0

---

### 1.3 Phoenix (Arize AI)
- **URL**: https://phoenix.arize.com
- **GitHub**: https://github.com/arize-ai/phoenix
- **Stars**: 9 100
- **Licence**: Open source (voir repo)
- **Pricing**: Open source + Arize Cloud (enterprise payant)
- **Source de découverte**: GitHub direct
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 12_enterprise_integration
- **Sous-catégorie**: observability
- **Description**: Plateforme d'observabilité IA open source pour expérimentation, évaluation et troubleshooting des LLM apps. Tracing OpenTelemetry, évaluations, datasets, prompt management.
- **Pourquoi c'est pertinent**: Made by Arize (leader ML observabilité enterprise). Self-hosted sur local/Jupyter/Docker/K8s ou cloud. Intègre OpenAI, Anthropic, Bedrock, LlamaIndex, LangChain. Complément naturel à Arize Platform enterprise.
- **Enterprise**: Arize = company enterprise solide, option cloud avec SLA

---

### 1.4 Helicone
- **URL**: https://helicone.ai
- **GitHub**: https://github.com/Helicone/helicone
- **Stars**: 5 400
- **Licence**: Apache 2.0
- **Pricing**: Freemium - 10k requests/mois gratuit, plans payants au-delà
- **Source de découverte**: GitHub direct
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 12_enterprise_integration
- **Sous-catégorie**: observability
- **Description**: Plateforme LLM observabilité "one line of code". Monitor coûts, latence, qualité. AI Gateway intégré (100+ modèles). Prompt management avec déploiement sans code. SOC 2 et GDPR compliant.
- **Pourquoi c'est pertinent**: Combinaison observabilité + gateway en un seul outil. Self-hosting Docker/K8s disponible. SOC 2 et GDPR = prêt pour enterprise européen et américain. Intègre 15+ providers.
- **Enterprise**: SOC 2, GDPR, self-hosting, Apache 2.0

---

### 1.5 AgentOps
- **URL**: https://agentops.ai
- **GitHub**: https://github.com/AgentOps-AI/agentops
- **Stars**: 5 400
- **Licence**: MIT
- **Pricing**: Freemium
- **Source de découverte**: GitHub direct
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 12_enterprise_integration
- **Sous-catégorie**: observability
- **Description**: Plateforme d'observabilité spécialisée agents IA. Session replays, graphs d'exécution pas-à-pas, tracking des coûts LLM, self-hosting disponible.
- **Pourquoi c'est pertinent**: Seul outil de cette liste spécialisé agents (vs LLM calls génériques). Intègre CrewAI, AutoGen, LangGraph, OpenAI Agents SDK. Debug des workflows multi-agents complexes en production.
- **Enterprise**: Self-hosting, MIT, focus agents - complément à Langfuse

---

### 1.6 Opik (Comet ML)
- **URL**: https://www.comet.com/site/products/opik/
- **GitHub**: https://github.com/comet-ml/opik
- **Stars**: 18 600
- **Licence**: Open source (voir repo)
- **Pricing**: Open source (self-hosted gratuit) + Comet Cloud
- **Source de découverte**: GitHub direct
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 12_enterprise_integration
- **Sous-catégorie**: observability
- **Description**: Plateforme lifecycle LLM complète : tracing, évaluation, monitoring production. Gère 40M+ traces/jour. Intègre 50+ frameworks incluant Google ADK, Autogen, Flowise.
- **Pourquoi c'est pertinent**: Scale prouvé (40M traces/jour), Docker Compose/K8s self-hosted, CI/CD via pytest, guardrails intégrés. Made by Comet (company MLOps établie depuis 2018).
- **Enterprise**: Scale validé, self-hosted, company backing solide

---

### 1.7 W&B Weave
- **URL**: https://weave.wandb.ai
- **GitHub**: https://github.com/wandb/weave (separé de wandb/wandb)
- **Stars (wandb core)**: 10 900
- **Licence**: MIT (core), Enterprise plan
- **Pricing**: Freemium - Developer gratuit, Team/Enterprise payant
- **Source de découverte**: GitHub direct
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 12_enterprise_integration
- **Sous-catégorie**: observability
- **Description**: Suite GenAI de Weights & Biases pour monitoring, debugging et évaluation des applications LLM. Intégré dans l'écosystème W&B experiment tracking.
- **Pourquoi c'est pertinent**: W&B = standard de facto pour ML experiment tracking. Weave étend cette légitimité au GenAI. Déploiement Dedicated Cloud ou self-managed pour enterprise. Idéal si l'organisation utilise déjà W&B pour le ML.
- **Enterprise**: Dedicated Cloud, self-managed, company etablie

---

### 1.8 Langtrace
- **URL**: https://langtrace.ai
- **GitHub**: https://github.com/Scale3-Labs/langtrace
- **Stars**: 1 200
- **Licence**: AGPL-3.0 (app) / Apache 2.0 (SDKs)
- **Pricing**: Open source self-hosted + cloud
- **Source de découverte**: GitHub direct
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 12_enterprise_integration
- **Sous-catégorie**: observability
- **Description**: Outil observabilité end-to-end basé OpenTelemetry pour LLM apps. Monitoring des coûts, latence, qualité. Supporte 11+ LLM providers et 6+ vector DBs.
- **Pourquoi c'est pertinent**: Licence AGPL pour l'app (attention enterprise), Apache 2.0 pour SDKs. OpenTelemetry native. Moins mature que Langfuse mais alternative self-hosted sérieuse.
- **Limitation enterprise**: AGPL-3.0 sur l'application = attention aux obligations de copyleft en enterprise

---

### 1.9 OpenLIT
- **URL**: https://openlit.io
- **GitHub**: https://github.com/openlit/openlit
- **Stars**: 2 300
- **Licence**: Apache 2.0
- **Pricing**: Open source gratuit
- **Source de découverte**: GitHub direct
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 12_enterprise_integration
- **Sous-catégorie**: observability
- **Description**: Plateforme AI engineering OpenTelemetry-native. Observabilité LLM + GPU monitoring + guardrails + évaluations + prompt management. 50+ intégrations.
- **Pourquoi c'est pertinent**: Seul outil combinant monitoring GPU + LLM en une plateforme. Apache 2.0 = enterprise-friendly. Idéal pour organizations avec infrastructure GPU on-premise.
- **Enterprise**: Apache 2.0, GPU monitoring unique, OpenTelemetry native

---

### 1.10 Evidently AI
- **URL**: https://evidentlyai.com
- **GitHub**: https://github.com/evidentlyai/evidently
- **Stars**: 7 400
- **Licence**: Apache 2.0
- **Pricing**: Open source + Evidently Cloud (freemium)
- **Source de découverte**: GitHub direct
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 12_enterprise_integration / 10_data_science_mlops
- **Sous-catégorie**: observability / monitoring
- **Description**: Framework Python d'évaluation, test et monitoring pour ML et LLM. 100+ métriques built-in : data drift, qualité LLM outputs, classification, régression. Reports interactifs et CI/CD integration.
- **Pourquoi c'est pertinent**: Couvre ML classique ET LLM dans une seule plateforme - idéal pour organizations en transition ML→GenAI. Apache 2.0, self-hosted possible. 100+ métriques dont détection de drift pour LLM apps.
- **Enterprise**: Apache 2.0, self-hosted, couvre ML + LLM

---

## 2. AI GATEWAYS / PROXY

### 2.1 LiteLLM (Gateway mode)
- **URL**: https://litellm.ai
- **GitHub**: https://github.com/BerriAI/litellm
- **Stars**: 41 900
- **Licence**: MIT (core), Enterprise plan
- **Pricing**: Open source + Enterprise (voir pricing page)
- **Source de découverte**: GitHub direct
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 12_enterprise_integration (gateway) / 02_ai_agents (SDK)
- **Sous-catégorie**: gateway
- **Description**: SDK Python + AI Gateway proxy unifié pour 100+ LLMs. Interface OpenAI-compatible. Cost tracking multi-tenant, virtual keys, admin dashboard, load balancing. 8ms P95 latency à 1k RPS.
- **Pourquoi c'est pertinent**: Standard de facto pour l'unification LLM. Utilisé par Stripe, Netflix, Google ADK. Virtual keys par projet/user pour cost tracking granulaire. MCP server integration. A2A protocol. Le plus étoilé dans sa catégorie.
- **Enterprise**: Adopté par Fortune 500, MIT, enterprise plan disponible, 41.9k stars

---

### 2.2 Portkey Gateway
- **URL**: https://portkey.ai
- **GitHub**: https://github.com/Portkey-AI/gateway
- **Stars**: 11 200
- **Licence**: MIT (voir repo)
- **Pricing**: Open source + Cloud (freemium)
- **Source de découverte**: GitHub direct
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 12_enterprise_integration
- **Sous-catégorie**: gateway
- **Description**: Gateway LLM enterprise-ready ultra-léger (122kb). Route vers 250+ LLMs. Retries auto, fallbacks, load balancing. 40+ guardrails built-in. RBAC. SOC2, HIPAA, GDPR, CCPA. 10B tokens/jour.
- **Pourquoi c'est pertinent**: Certifications enterprise complètes (SOC2, HIPAA, GDPR, CCPA) - rare pour un outil open source. Footprint minimal (122kb) = pas d'overhead. Deploy sur Cloudflare Workers/K8s/AWS/Azure/GCP.
- **Enterprise**: SOC2 + HIPAA + GDPR + CCPA, 10B tokens/jour validés en prod

---

### 2.3 Kong AI Gateway
- **URL**: https://konghq.com/products/kong-ai-gateway
- **GitHub**: https://github.com/Kong/kong
- **Stars**: 43 100
- **Licence**: Apache 2.0
- **Pricing**: Open source + Enterprise (Kong Konnect)
- **Source de découverte**: GitHub direct
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 12_enterprise_integration
- **Sous-catégorie**: gateway
- **Description**: API Gateway battle-tested (43k stars) avec couche IA complète. 60+ AI features : observabilité, semantic caching, semantic routing, sécurité. Support OpenAI, Anthropic, Bedrock, Azure AI, Databricks, Mistral, HuggingFace. MCP traffic governance.
- **Pourquoi c'est pertinent**: Pour les enterprises qui ont déjà Kong comme API gateway - ajout naturel de l'IA. 393+ contributeurs, battle-tested en production à grande échelle. Kubernetes native. Plugin ecosystem extensible.
- **Enterprise**: Déjà en production dans des centaines d'enterprises, Kong Inc. backing, enterprise support

---

### 2.4 Cloudflare AI Gateway
- **URL**: https://developers.cloudflare.com/ai-gateway/
- **GitHub**: N/A (service cloud)
- **Stars**: N/A
- **Licence**: Proprietary (Cloudflare service)
- **Pricing**: Free tier (100k neurones/jour) + Workers paid plans
- **Source de découverte**: Documentation officielle
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 12_enterprise_integration
- **Sous-catégorie**: gateway
- **Description**: Gateway IA managé par Cloudflare. Caching sémantique, rate limiting, analytics, logging. Proxifie les appels vers OpenAI, Anthropic, HuggingFace, Replicate, Workers AI. Déploiement mondial sur edge network Cloudflare.
- **Pourquoi c'est pertinent**: Pour les enterprises déjà sur Cloudflare - zero infrastructure supplémentaire. Edge deployment mondial = latence réduite. GDPR compliant (data localisation). Free tier généreux.
- **Enterprise**: Infrastructure Cloudflare enterprise-grade, GDPR, global edge
- **Note**: Pas open source - pertinent uniquement si déjà dans l'écosystème Cloudflare

---

## 3. COST MANAGEMENT

### 3.1 TokenCost
- **URL**: https://github.com/AgentOps-AI/tokencost
- **GitHub**: https://github.com/AgentOps-AI/tokencost
- **Stars**: 2 000
- **Licence**: MIT
- **Pricing**: Open source gratuit
- **Source de découverte**: GitHub direct
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 12_enterprise_integration
- **Sous-catégorie**: cost-management
- **Description**: Librairie Python de calcul de coûts LLM. Supporte 400+ modèles. Token counting précis (Tiktoken + API Anthropic pour Claude 3+). Fonctions `calculate_prompt_cost()`, `calculate_completion_cost()`.
- **Pourquoi c'est pertinent**: Utilitaire léger et précis pour intégrer le cost tracking dans n'importe quelle application. 400+ modèles couverts, mis à jour régulièrement au fil des changements de pricing. MIT - aucune restriction.
- **Enterprise**: Librairie légère à intégrer, MIT, 400+ modèles

---

### 3.2 GPTCache
- **URL**: https://gptcache.readthedocs.io
- **GitHub**: https://github.com/zilliztech/GPTCache
- **Stars**: 8 000
- **Licence**: MIT
- **Pricing**: Open source gratuit
- **Source de découverte**: GitHub direct
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 12_enterprise_integration
- **Sous-catégorie**: cost-management
- **Description**: Semantic caching pour LLMs. Réduit les coûts API jusqu'à 10x et accélère les réponses jusqu'à 100x en cachant les réponses LLM pour des requêtes sémantiquement similaires. Intégré LangChain et LlamaIndex.
- **Pourquoi c'est pertinent**: ROI immédiat et mesurable sur les coûts API. Architecture modulaire (embeddings personnalisables, stockage personnalisable : SQLite, PostgreSQL, DynamoDB). Docker server pour usage polyglotte. MIT = aucune restriction.
- **Enterprise**: MIT, Docker, modular, ROI direct sur coûts

---

### 3.3 Note sur le Cost Management intégré
Les outils suivants incluent du cost tracking nativement et peuvent servir de solution primaire :
- **LiteLLM** : cost tracking multi-tenant par projet/user (virtual keys)
- **Langfuse** : analytics coûts et tokens par trace
- **Helicone** : cost analytics dashboard natif
- **AgentOps** : LLM cost tracking par session agent

---

## 4. SECURITY & COMPLIANCE ENTERPRISE

### 4.1 Microsoft Presidio
- **URL**: https://microsoft.github.io/presidio/
- **GitHub**: https://github.com/microsoft/presidio
- **Stars**: 7 500
- **Licence**: MIT
- **Pricing**: Open source gratuit
- **Source de découverte**: GitHub direct
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 12_enterprise_integration
- **Sous-catégorie**: security
- **Description**: Framework Microsoft de détection et redaction de PII (données personnelles). Analyse texte, images DICOM, données tabulaires/JSON. NER + pattern matching + règles métier. Composants : Analyzer, Anonymizer, Image-Redactor, Structured.
- **Pourquoi c'est pertinent**: Microsoft = crédibilité enterprise maximale. MIT = aucune restriction commerciale. Dernière release mars 2026 = activement maintenu. Supporte DICOM (médical) et PySpark (data engineering). Customizable pour PII métier-spécifiques (IBAN, numéros contrats...).
- **Enterprise**: Microsoft backing, MIT, DICOM/PySpark support, K8s deployment

---

### 4.2 NeMo Guardrails (NVIDIA)
- **URL**: https://docs.nvidia.com/nemo-guardrails/
- **GitHub**: https://github.com/NVIDIA/NeMo-Guardrails
- **Stars**: 5 900
- **Licence**: Apache 2.0
- **Pricing**: Open source gratuit
- **Source de découverte**: GitHub direct
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 12_enterprise_integration
- **Sous-catégorie**: security
- **Description**: Toolkit NVIDIA de guardrails programmables pour LLM apps. 5 types de rails (input, dialog, retrieval, execution, output). Langage Colang pour modéliser les flux. Protection jailbreak/prompt injection, fact-checking, modération contenu, masquage données sensibles.
- **Pourquoi c'est pertinent**: NVIDIA backing = longevité garantie. Apache 2.0. Guardrails enterprise complets : pas seulement output filtering mais aussi contrôle dialogues et flux. LangChain integration, HTTP API server, Docker.
- **Enterprise**: NVIDIA backing, Apache 2.0, guardrails complets production-grade

---

### 4.3 Guardrails AI
- **URL**: https://guardrailsai.com
- **GitHub**: https://github.com/guardrails-ai/guardrails
- **Stars**: 6 600
- **Licence**: Apache 2.0
- **Pricing**: Open source + Hub (validators marketplace)
- **Source de découverte**: GitHub direct
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 12_enterprise_integration / 16_ai_security_safety
- **Sous-catégorie**: security
- **Description**: Framework Python de validation I/O pour LLMs. Détecte et mitige les risques (toxicité, données sensibles, concurrents, regex...). Guardrails Hub = marketplace de validators. Serveur Flask REST pour déploiement standalone.
- **Pourquoi c'est pertinent**: Approche "validators as code" = intégrable dans CI/CD. Hub de validators communautaires. Benchmark Guardrails Index (24 guardrails × 6 catégories). Compatible tout LLM.
- **Enterprise**: Apache 2.0, serveur standalone, ecosystem Hub

---

### 4.4 Infisical
- **URL**: https://infisical.com
- **GitHub**: https://github.com/infisical/infisical
- **Stars**: 25 700
- **Licence**: MIT (core) / Enterprise (ee/)
- **Pricing**: Open source + Cloud + Enterprise
- **Source de découverte**: GitHub direct
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 12_enterprise_integration
- **Sous-catégorie**: security
- **Description**: Plateforme open source de secrets management, certificats PKI et gestion des accès privilégiés. Centralise les API keys LLM, credentials, tokens. Rotation automatique, dynamic secrets, audit logging complet. SDKs Node/Python/Go/Java/.NET.
- **Pourquoi c'est pertinent**: Critique pour la sécurité des projets LLM enterprise : gestion centralisée des API keys Anthropic/OpenAI/etc. Self-hosted pour data sovereignty. RBAC + approval workflows + audit trail. 25.7k stars = adoption massive.
- **Enterprise**: Self-hosted, RBAC, audit logging, 25.7k stars, alternative à HashiCorp Vault

---

## 5. DEPLOYMENT & ORCHESTRATION ENTERPRISE

### 5.1 MLflow (avec AI Gateway)
- **URL**: https://mlflow.org
- **GitHub**: https://github.com/mlflow/mlflow
- **Stars**: 25 100
- **Licence**: Apache 2.0
- **Pricing**: Open source + Databricks Managed MLflow
- **Source de découverte**: GitHub direct
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 12_enterprise_integration / 10_data_science_mlops
- **Sous-catégorie**: deployment
- **Description**: Plateforme AI engineering open source la plus large. Agents, LLMs, ML models. Tracing OpenTelemetry, 50+ métriques d'évaluation, prompt management avec versioning, AI Gateway avec credential management et guardrails. 60M+ téléchargements/mois.
- **Pourquoi c'est pertinent**: Standard de facto en enterprise pour ML tracking - maintenant étendu aux LLMs. Apache 2.0, 60M downloads/mois. Databricks (valorisation $60B+) backing. Support AWS SageMaker, Azure ML, GCP Vertex, K8s. AI Gateway intégré avec A/B testing.
- **Enterprise**: Standard industrie, Databricks backing, 60M downloads, Apache 2.0

---

### 5.2 BentoML
- **URL**: https://bentoml.com
- **GitHub**: https://github.com/bentoml/BentoML
- **Stars**: 8 600
- **Licence**: Apache 2.0
- **Pricing**: Open source + BentoCloud (managed)
- **Source de découverte**: GitHub direct
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 12_enterprise_integration / 18_ai_infrastructure
- **Sous-catégorie**: deployment
- **Description**: Framework Python pour construire des APIs de serving ML/LLM optimisées. Auto-génère Docker, supporte dynamic batching, model parallelism, GPU inference. Latest release 2 avril 2026 (v1.4.38).
- **Pourquoi c'est pertinent**: Release du 2 avril 2026 = très actif. Couvre LLMs, embeddings, image generation, audio, computer vision dans un même framework. Apache 2.0. Dynamic batching = performance enterprise.
- **Enterprise**: Apache 2.0, GPU support, autoscaling, K8s ready

---

### 5.3 ZenML
- **URL**: https://zenml.io
- **GitHub**: https://github.com/zenml-io/zenml
- **Stars**: 5 300
- **Licence**: Apache 2.0
- **Pricing**: Open source + Pro/Enterprise
- **Source de découverte**: GitHub direct
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 12_enterprise_integration / 10_data_science_mlops
- **Sous-catégorie**: deployment
- **Description**: Plateforme MLOps "One Platform from Pipelines to Agents". Orchestre pipelines ML/LLM/agents sur n'importe quelle infrastructure. Intègre MLflow, Langfuse, LangGraph, LlamaIndex, SageMaker, GCP Vertex. MCP server pour requêtes en langage naturel.
- **Pourquoi c'est pertinent**: Clients enterprise : Airbus, AXA, JetBrains, Rivian. Kubernetes orchestrator natif. MCP server = accessible via Claude Desktop/Cursor. Bridge entre ML classique et agents GenAI dans une seule plateforme.
- **Enterprise**: Airbus/AXA/JetBrains references, Apache 2.0, K8s native

---

## 6. EVALUATION & TESTING LLM APPS

### 6.1 Promptfoo
- **URL**: https://promptfoo.dev
- **GitHub**: https://github.com/promptfoo/promptfoo
- **Stars**: 19 100
- **Licence**: MIT
- **Pricing**: Open source (100% local) + Pro (cloud features)
- **Source de découverte**: GitHub direct
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 12_enterprise_integration / 16_ai_security_safety
- **Sous-catégorie**: evaluation
- **Description**: CLI et librairie d'évaluation et red-teaming des LLM apps. Evaluation automatisée des prompts, comparaison multi-modèles, intégration CI/CD, code scanning pour sécurité LLM. 100% local - les prompts ne quittent pas la machine.
- **Pourquoi c'est pertinent**: "Prompts never leave your machine" = argument enterprise fort. CI/CD integration pour quality gates sur LLM apps. Powers production systems serving 10M+ users. Maintenant partie d'OpenAI (mars 2026) tout en restant MIT. Latest release 24 mars 2026.
- **Enterprise**: 100% local, CI/CD native, MIT, now OpenAI-backed

---

### 6.2 DeepEval
- **URL**: https://docs.confident-ai.com
- **GitHub**: https://github.com/confident-ai/deepeval
- **Stars**: 14 400
- **Licence**: Open source (voir repo)
- **Pricing**: Open source + Confident AI platform (cloud)
- **Source de découverte**: GitHub direct
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 12_enterprise_integration
- **Sous-catégorie**: evaluation
- **Description**: Framework d'évaluation LLM "comme pytest mais pour les LLM apps". Métriques RAG (relevancy, faithfulness, recall), métriques agents (task completion, tool correctness), safety (bias, toxicity). LLM-as-judge. Génération synthetique de datasets.
- **Pourquoi c'est pertinent**: API pytest-like = adoption naturelle par les équipes dev. Couvre RAG + agents + multimodal dans un seul framework. Génération de datasets synthétiques pour test. Confident AI platform pour le management cloud.
- **Enterprise**: pytest-compatible, CI/CD ready, RAG + agents + multimodal

---

### 6.3 Ragas
- **URL**: https://docs.ragas.io
- **GitHub**: https://github.com/explodinggradients/ragas
- **Stars**: 13 200
- **Licence**: Apache 2.0
- **Pricing**: Open source + Ragas Cloud (beta)
- **Source de découverte**: GitHub direct
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 12_enterprise_integration / 05_rag_knowledge
- **Sous-catégorie**: evaluation
- **Description**: Framework d'évaluation spécialisé RAG pipelines. Métriques objectives : faithfulness, answer relevancy, context recall/precision. Génération automatique de datasets de test. Feedback loops production.
- **Pourquoi c'est pertinent**: Référence de facto pour évaluer les RAG pipelines. Apache 2.0. Intégré LangChain, LlamaIndex. v0.4.3 janvier 2026 - maintenu activement. Indispensable pour les projets RAG enterprise.
- **Enterprise**: Apache 2.0, standard RAG evaluation, intégration frameworks

---

### 6.4 LangKit (WhyLabs)
- **URL**: https://github.com/whylabs/langkit
- **GitHub**: https://github.com/whylabs/langkit
- **Stars**: 980
- **Licence**: Apache 2.0
- **Pricing**: Open source + WhyLabs Cloud
- **Source de découverte**: GitHub direct
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 12_enterprise_integration
- **Sous-catégorie**: monitoring / security
- **Description**: Toolkit de métriques texte pour monitoring LLM. Qualité texte, similarité thématique, détection PII, jailbreak, prompt injection, hallucinations, sentiments, toxicité. Intégré avec whylogs (data logging).
- **Pourquoi c'est pertinent**: Proche de la limite des 500 stars (980), mais spécialisé dans la détection de patterns de sécurité (jailbreak, injection) en production - cas d'usage enterprise distinct des outils précédents.
- **Enterprise**: Apache 2.0, sécurité LLM production, WhyLabs backing

---

## TABLEAU DE SYNTHESE

| Outil | Stars | Licence | Enterprise | Priorité catalogage |
|-------|-------|---------|------------|---------------------|
| LiteLLM | 41.9k | MIT | Stripe/Netflix, enterprise plan | P1 - URGENT |
| MLflow | 25.1k | Apache 2.0 | Databricks, 60M DL/mois | P1 - URGENT |
| Langfuse | 24.2k | MIT | Self-hosted, SOC2 cloud | P1 - URGENT |
| Infisical | 25.7k | MIT/EE | Self-hosted, RBAC, audit | P1 - URGENT |
| Promptfoo | 19.1k | MIT | 100% local, CI/CD, OpenAI-backed | P1 - URGENT |
| Opik | 18.6k | Open | Self-hosted, 40M traces/jour | P2 - HIGH |
| DeepEval | 14.4k | Open | pytest-compat, RAG+agents | P2 - HIGH |
| Ragas | 13.2k | Apache 2.0 | Standard RAG eval | P2 - HIGH |
| Portkey Gateway | 11.2k | MIT | SOC2+HIPAA+GDPR+CCPA | P2 - HIGH |
| W&B Weave | 10.9k | MIT | Dedicated cloud, self-managed | P2 - HIGH |
| Phoenix (Arize) | 9.1k | Open | Arize enterprise backing | P2 - HIGH |
| BentoML | 8.6k | Apache 2.0 | GPU, dynamic batching, K8s | P2 - HIGH |
| GPTCache | 8.0k | MIT | Cost 10x, Docker, modular | P3 - MEDIUM |
| Evidently | 7.4k | Apache 2.0 | ML+LLM monitoring | P3 - MEDIUM |
| Microsoft Presidio | 7.5k | MIT | Microsoft backing, PII | P2 - HIGH |
| Kong AI Gateway | 43.1k | Apache 2.0 | Enterprise standard API GW | P2 - HIGH |
| OpenLLMetry | 7.0k | Apache 2.0 | OTel native, Datadog/Grafana | P3 - MEDIUM |
| Guardrails AI | 6.6k | Apache 2.0 | REST server, validators Hub | P3 - MEDIUM |
| NeMo Guardrails | 5.9k | Apache 2.0 | NVIDIA backing, dialog control | P2 - HIGH |
| Helicone | 5.4k | Apache 2.0 | SOC2+GDPR, observ+gateway | P3 - MEDIUM |
| AgentOps | 5.4k | MIT | Agent-specific observability | P3 - MEDIUM |
| ZenML | 5.3k | Apache 2.0 | Airbus/AXA refs, ML+agents | P3 - MEDIUM |
| OpenLIT | 2.3k | Apache 2.0 | GPU+LLM monitoring combiné | P4 - LOW |
| TokenCost | 2.0k | MIT | Utilitaire cost calcul | P4 - LOW |
| Langtrace | 1.2k | AGPL/Apache | OTel, attention AGPL app | P4 - LOW |
| Cloudflare AI GW | N/A | Proprietary | Edge, GDPR, Cloudflare users | P3 - MEDIUM |
| Cohere Toolkit | 3.2k | MIT | RAG enterprise deployable | P4 - LOW |

---

## GAPS IDENTIFIES (à rechercher ensuite)

1. **Semantic router** : outils de routing LLM par intent (aurelio-ai/semantic-router ?)
2. **LLM caching avancé** : solutions Redis-based pour LLM responses
3. **Rate limiting enterprise** : solutions dédiées au rate limiting d'APIs LLM
4. **Audit logging enterprise** : solutions d'audit trail dédiées LLM (compliance RGPD, SOC2)
5. **Multi-tenancy LLM** : patterns et outils pour SaaS multi-tenant avec LLM
6. **HumanLoop** : plateforme prompt management enterprise - site 404 sur GitHub, à vérifier via site officiel

---

## REFERENCES SOURCES

- GitHub: https://github.com/langfuse/langfuse (vérifié 2026-04-02)
- GitHub: https://github.com/traceloop/openllmetry (vérifié 2026-04-02)
- GitHub: https://github.com/arize-ai/phoenix (vérifié 2026-04-02)
- GitHub: https://github.com/Helicone/helicone (vérifié 2026-04-02)
- GitHub: https://github.com/Portkey-AI/gateway (vérifié 2026-04-02)
- GitHub: https://github.com/promptfoo/promptfoo (vérifié 2026-04-02)
- GitHub: https://github.com/confident-ai/deepeval (vérifié 2026-04-02)
- GitHub: https://github.com/explodinggradients/ragas (vérifié 2026-04-02)
- GitHub: https://github.com/BerriAI/litellm (vérifié 2026-04-02)
- GitHub: https://github.com/microsoft/presidio (vérifié 2026-04-02)
- GitHub: https://github.com/guardrails-ai/guardrails (vérifié 2026-04-02)
- GitHub: https://github.com/wandb/wandb (vérifié 2026-04-02)
- GitHub: https://github.com/mlflow/mlflow (vérifié 2026-04-02)
- GitHub: https://github.com/bentoml/BentoML (vérifié 2026-04-02)
- GitHub: https://github.com/infisical/infisical (vérifié 2026-04-02)
- GitHub: https://github.com/NVIDIA/NeMo-Guardrails (vérifié 2026-04-02)
- GitHub: https://github.com/AgentOps-AI/agentops (vérifié 2026-04-02)
- GitHub: https://github.com/AgentOps-AI/tokencost (vérifié 2026-04-02)
- GitHub: https://github.com/zilliztech/GPTCache (vérifié 2026-04-02)
- GitHub: https://github.com/comet-ml/opik (vérifié 2026-04-02)
- GitHub: https://github.com/evidentlyai/evidently (vérifié 2026-04-02)
- GitHub: https://github.com/zenml-io/zenml (vérifié 2026-04-02)
- GitHub: https://github.com/openlit/openlit (vérifié 2026-04-02)
- GitHub: https://github.com/Scale3-Labs/langtrace (vérifié 2026-04-02)
- GitHub: https://github.com/whylabs/langkit (vérifié 2026-04-02)
- GitHub: https://github.com/Kong/kong (vérifié 2026-04-02)
