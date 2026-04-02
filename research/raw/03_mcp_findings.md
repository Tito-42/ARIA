# MCP (Model Context Protocol) - Research Findings
- **Date de recherche**: 2026-04-02
- **Sources explorées**: github.com/modelcontextprotocol/servers, github.com/punkpeye/awesome-mcp-servers, github.com/wong2/awesome-mcp-servers, GitHub direct searches
- **Catégorie**: 03_mcp

---

## Contexte

Le catalogue ARIA dispose déjà de 2 fiches MCP génériques (mcp-protocol-overview, registry).
Ces findings documentent les SERVEURS MCP concrets les plus populaires avec données vérifiées (URLs, stars, licences, dates).

L'écosystème MCP est massif : punkpeye/awesome-mcp-servers compte 84.1k stars et 8,600 forks.
Le dépôt modelcontextprotocol/servers lui-même a 82.8k stars et 10.2k forks.

---

## 1. FRAMEWORKS / OUTILS DE DÉVELOPPEMENT MCP

### FastMCP
- **URL**: https://github.com/jlowin/fastmcp
- **GitHub**: https://github.com/jlowin/fastmcp
- **Stars**: 24,200
- **Licence**: Apache-2.0
- **Dernière release**: v3.2.0 (30 mars 2026)
- **Source de découverte**: punkpeye/awesome-mcp-servers + recherche directe
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 03_mcp
- **Description**: Framework Python haut niveau pour construire des serveurs et clients MCP. Décorateur @mcp.tool() sur des fonctions Python suffit à exposer des outils. Intégré dans le SDK Python officiel MCP.
- **Pourquoi c'est pertinent**: De facto standard pour écrire des serveurs MCP en Python. Téléchargé ~1 million de fois par jour, propulse ~70% des serveurs MCP. v3.2.0 très récente.

### MCP Python SDK (officiel)
- **URL**: https://github.com/modelcontextprotocol/python-sdk
- **GitHub**: https://github.com/modelcontextprotocol/python-sdk
- **Stars**: 22,500
- **Licence**: MIT
- **Dernière release**: active (mars 2026)
- **Source de découverte**: modelcontextprotocol org GitHub
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 03_mcp
- **Description**: SDK Python officiel pour construire serveurs et clients MCP. Supporte stdio, SSE, et Streamable HTTP. Inclut FastMCP en high-level API.
- **Pourquoi c'est pertinent**: SDK officiel Anthropic/MCP. Base de tout développement MCP en Python.

### MCP TypeScript SDK (officiel)
- **URL**: https://github.com/modelcontextprotocol/typescript-sdk
- **GitHub**: https://github.com/modelcontextprotocol/typescript-sdk
- **Stars**: 12,100
- **Licence**: Apache-2.0 (MIT pour code existant)
- **Dernière release**: v1.29.0 (30 mars 2026)
- **Source de découverte**: modelcontextprotocol org GitHub
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 03_mcp
- **Description**: SDK TypeScript officiel pour serveurs et clients MCP. Supporte Node.js, Bun, Deno. Inclut middleware pour Express et Hono.
- **Pourquoi c'est pertinent**: SDK officiel pour JavaScript/TypeScript. v1.29.0 récente, v2 en préparation.

### MCP Inspector (officiel)
- **URL**: https://github.com/modelcontextprotocol/inspector
- **GitHub**: https://github.com/modelcontextprotocol/inspector
- **Stars**: 9,300
- **Licence**: MIT
- **Dernière release**: active (2026)
- **Source de découverte**: modelcontextprotocol org GitHub + catalog existant
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 03_mcp
- **Description**: Outil de debug et test visuel pour serveurs MCP. UI web React + proxy Node.js. Supporte stdio, SSE, StreamableHTTP.
- **Pourquoi c'est pertinent**: Outil indispensable de développement MCP. 9.3k stars, outil officiel.

### mcp-proxy
- **URL**: https://github.com/sparfenyuk/mcp-proxy
- **GitHub**: https://github.com/sparfenyuk/mcp-proxy
- **Stars**: 2,400
- **Licence**: open source (à confirmer)
- **Dernière release**: v0.3.2-alpine disponible
- **Source de découverte**: punkpeye/awesome-mcp-servers
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 03_mcp
- **Description**: Proxy de transport MCP permettant de basculer entre stdio, SSE et StreamableHTTP. Expose des serveurs stdio locaux comme endpoints SSE, ou connecte des clients stdio à des serveurs SSE distants.
- **Pourquoi c'est pertinent**: Résout un problème courant : Claude Desktop ne supporte que stdio mais les serveurs distants utilisent SSE/HTTP. Installable via PyPI (uv tool install mcp-proxy).

### Supergateway
- **URL**: https://github.com/supercorp-ai/supergateway
- **GitHub**: https://github.com/supercorp-ai/supergateway
- **Stars**: 2,500
- **Licence**: MIT
- **Dernière release**: active (dernière commit décembre 2024)
- **Source de découverte**: punkpeye/awesome-mcp-servers
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 03_mcp
- **Description**: Outil pour exécuter des serveurs MCP stdio sur SSE ou WebSocket. Utile pour accès distant, debug, ou connexion de clients non-stdio.
- **Pourquoi c'est pertinent**: Complément de mcp-proxy, approche différente (WebSocket support). 2.5k stars.

### mcpo (MCP-to-OpenAPI)
- **URL**: https://github.com/open-webui/mcpo
- **GitHub**: https://github.com/open-webui/mcpo
- **Stars**: 4,100
- **Licence**: MIT
- **Dernière release**: v0.0.20 (27 février 2026)
- **Source de découverte**: recherche directe GitHub
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 03_mcp
- **Description**: Proxy qui expose n'importe quel serveur MCP stdio comme une API REST OpenAPI standard avec documentation auto-générée. "Dead-simple" conversion MCP → HTTP/REST.
- **Pourquoi c'est pertinent**: Permet d'intégrer des serveurs MCP dans n'importe quelle application HTTP. 4.1k stars, activement maintenu par l'équipe Open WebUI.

### Agentgateway (Linux Foundation)
- **URL**: https://github.com/mcp-proxy/mcp-proxy
- **GitHub**: https://github.com/mcp-proxy/mcp-proxy
- **Stars**: 2,300
- **Licence**: Apache-2.0
- **Dernière release**: v1.0.1 (20 mars 2026)
- **Source de découverte**: recherche directe GitHub
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 03_mcp
- **Description**: Proxy open-source basé sur MCP et A2A (Agent-to-Agent). Fournit sécurité, observabilité, et gouvernance pour la communication agent-LLM, agent-outil, agent-agent. Supporte RBAC, rate limiting, OTel.
- **Pourquoi c'est pertinent**: Initiative Linux Foundation. Production-ready. Rust + Go. Support A2A protocole Google. v1.0.1 très récente.

### Punkpeye Awesome MCP Servers (référence)
- **URL**: https://github.com/punkpeye/awesome-mcp-servers
- **GitHub**: https://github.com/punkpeye/awesome-mcp-servers
- **Stars**: 84,100
- **Licence**: CC (liste curated)
- **Dernière release**: active (838 PRs)
- **Source de découverte**: recherche directe GitHub
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 03_mcp
- **Description**: Liste curated de serveurs MCP. La plus grande et active. 84k stars, 8600 forks. Organisée en 80+ catégories.
- **Pourquoi c'est pertinent**: Source principale pour découvrir des serveurs MCP. Plus large et plus à jour que wong2/awesome-mcp-servers.

---

## 2. SERVEURS MCP OFFICIELS (modelcontextprotocol org)

### MCP Filesystem (officiel)
- **URL**: https://github.com/modelcontextprotocol/servers/tree/main/src/filesystem
- **GitHub**: https://github.com/modelcontextprotocol/servers
- **Stars**: 82,800 (repo parent)
- **Licence**: MIT
- **Dernière release**: active (2026)
- **Source de découverte**: modelcontextprotocol/servers
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 03_mcp
- **Description**: Serveur MCP de référence pour les opérations sur le système de fichiers local. Lecture, écriture, listing, recherche avec contrôles d'accès configurables.
- **Pourquoi c'est pertinent**: Serveur officiel le plus utilisé. Présent dans presque toutes les configurations Claude Desktop.

### MCP Fetch (officiel)
- **URL**: https://github.com/modelcontextprotocol/servers/tree/main/src/fetch
- **GitHub**: https://github.com/modelcontextprotocol/servers
- **Stars**: 82,800 (repo parent)
- **Licence**: MIT
- **Dernière release**: active (2026)
- **Source de découverte**: modelcontextprotocol/servers
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 03_mcp
- **Description**: Serveur MCP officiel pour récupérer et convertir du contenu web en format optimisé pour les LLMs. Conversion HTML → Markdown.
- **Pourquoi c'est pertinent**: Use case universel : permettre à l'IA de lire des pages web. Officiel et simple.

### MCP Memory (officiel)
- **URL**: https://github.com/modelcontextprotocol/servers/tree/main/src/memory
- **GitHub**: https://github.com/modelcontextprotocol/servers
- **Stars**: 82,800 (repo parent)
- **Licence**: MIT
- **Dernière release**: active (2026)
- **Source de découverte**: modelcontextprotocol/servers
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 03_mcp
- **Description**: Serveur MCP de mémoire persistante basé sur un knowledge graph. Permet de stocker et récupérer des entités et relations entre sessions.
- **Pourquoi c'est pertinent**: Résout le problème de mémoire cross-session des LLMs. Officiel et bien documenté.

### MCP Git (officiel)
- **URL**: https://github.com/modelcontextprotocol/servers/tree/main/src/git
- **GitHub**: https://github.com/modelcontextprotocol/servers
- **Stars**: 82,800 (repo parent)
- **Licence**: MIT
- **Dernière release**: active (2026)
- **Source de découverte**: modelcontextprotocol/servers
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 03_mcp
- **Description**: Serveur MCP officiel pour lire, rechercher et manipuler des repositories Git. Lecture des commits, branches, diffs, fichiers.
- **Pourquoi c'est pertinent**: Essentiel pour les workflows de développement. Officiel.

### MCP Sequential Thinking (officiel)
- **URL**: https://github.com/modelcontextprotocol/servers/tree/main/src/sequentialthinking
- **GitHub**: https://github.com/modelcontextprotocol/servers
- **Stars**: 82,800 (repo parent)
- **Licence**: MIT
- **Dernière release**: active (2026)
- **Source de découverte**: modelcontextprotocol/servers
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 03_mcp
- **Description**: Serveur MCP officiel pour la résolution de problèmes structurée via des séquences de pensée. Outil de raisonnement dynamique et réflexif.
- **Pourquoi c'est pertinent**: Améliore les capacités de raisonnement complexe des LLMs. Approche "chain-of-thought" via MCP.

---

## 3. SERVEURS MCP - CLOUD & INFRASTRUCTURE

### AWS MCP Servers (officiel AWS)
- **URL**: https://github.com/awslabs/mcp
- **GitHub**: https://github.com/awslabs/mcp
- **Stars**: 8,700
- **Licence**: Apache-2.0
- **Dernière release**: active (2026)
- **Source de découverte**: punkpeye/awesome-mcp-servers + wong2
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 03_mcp
- **Description**: Suite de serveurs MCP officiels AWS. Inclut : AWS Documentation, AWS IaC, Amazon EKS, ECS, Lambda, Serverless, CloudFormation, Support. Aide à utiliser AWS via langage naturel.
- **Pourquoi c'est pertinent**: Officiel AWS Labs. 8.7k stars. Couvre l'ensemble de l'écosystème AWS. Supporte uniquement stdio (SSE retiré en mai 2025).

### Cloudflare MCP Server (officiel Cloudflare)
- **URL**: https://github.com/cloudflare/mcp-server-cloudflare
- **GitHub**: https://github.com/cloudflare/mcp-server-cloudflare
- **Stars**: 3,600
- **Licence**: Apache-2.0
- **Dernière release**: @repo/mcp-common@0.20.4 (31 mars 2026)
- **Source de découverte**: punkpeye/awesome-mcp-servers
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 03_mcp
- **Description**: 16 serveurs MCP spécialisés pour les services Cloudflare : Workers, KV, R2, D1, observabilité, sécurité (CASB), analytics (Radar), AI Gateway, AutoRAG.
- **Pourquoi c'est pertinent**: Officiel Cloudflare. 3.6k stars. Release très récente (31 mars 2026). 314 releases au total.

### Terraform MCP Server (officiel HashiCorp)
- **URL**: https://github.com/hashicorp/terraform-mcp-server
- **GitHub**: https://github.com/hashicorp/terraform-mcp-server
- **Stars**: 1,300
- **Licence**: non précisée (à vérifier)
- **Dernière release**: v0.5.0
- **Source de découverte**: punkpeye/awesome-mcp-servers
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 03_mcp
- **Description**: Serveur MCP officiel HashiCorp pour Terraform. Accès au Terraform Registry, gestion des workspaces HCP Terraform, discovery de providers et modules, support OTel.
- **Pourquoi c'est pertinent**: Officiel HashiCorp. Infrastructure as Code via MCP. 1.3k stars.

### LocalStack MCP Server
- **URL**: https://github.com/localstack/localstack-mcp-server
- **GitHub**: https://github.com/localstack/localstack-mcp-server
- **Stars**: non confirmé
- **Licence**: non confirmée
- **Dernière release**: active
- **Source de découverte**: punkpeye/awesome-mcp-servers
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 03_mcp
- **Description**: Serveur MCP pour gérer les environnements AWS locaux via LocalStack. Opérations de cycle de vie et déploiement d'infrastructure locale.
- **Pourquoi c'est pertinent**: Développement et test AWS en local. Officiel LocalStack.

### Kubernetes MCP Server (manusa)
- **URL**: https://github.com/manusa/kubernetes-mcp-server
- **GitHub**: https://github.com/manusa/kubernetes-mcp-server
- **Stars**: 1,400
- **Licence**: Apache-2.0
- **Dernière release**: active (2026)
- **Source de découverte**: punkpeye/awesome-mcp-servers
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 03_mcp
- **Description**: Serveur MCP Kubernetes natif Go (pas de wrapping kubectl). Gère pods, namespaces, ressources, logs, Helm, multi-cluster. Support OpenShift. Binaire léger sans dépendances.
- **Pourquoi c'est pertinent**: Implémentation native la plus complète pour K8s. Support OpenTelemetry. Distribué via npm, PyPI, et binaires natifs.

### Pulumi MCP Server (officiel Pulumi)
- **URL**: https://github.com/pulumi/mcp-server
- **GitHub**: https://github.com/pulumi/mcp-server
- **Stars**: non confirmé (à vérifier)
- **Licence**: non confirmée
- **Dernière release**: active
- **Source de découverte**: punkpeye/awesome-mcp-servers
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 03_mcp
- **Description**: Serveur MCP officiel Pulumi pour l'Infrastructure as Code. Interagit avec l'Automation API et Pulumi Cloud API.
- **Pourquoi c'est pertinent**: Officiel Pulumi. Alternative Terraform pour IaC via MCP.

---

## 4. SERVEURS MCP - BASES DE DONNÉES

### Supabase MCP (communautaire Supabase)
- **URL**: https://github.com/supabase-community/supabase-mcp
- **GitHub**: https://github.com/supabase-community/supabase-mcp
- **Stars**: 2,600
- **Licence**: Apache-2.0
- **Dernière release**: active (361 commits)
- **Source de découverte**: wong2/awesome-mcp-servers
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 03_mcp
- **Description**: Serveur MCP pour Supabase : gestion base de données Postgres, edge functions, auth, storage, branching. Permet aux IA (Cursor, Claude, Windsurf) de gérer des projets Supabase. Export TypeScript via createToolSchemas().
- **Pourquoi c'est pertinent**: 2.6k stars. Supabase est une plateforme BaaS très populaire. Mode read-only disponible pour la sécurité.

### Neon MCP Server (officiel Neon)
- **URL**: https://github.com/neondatabase/mcp-server-neon
- **GitHub**: https://github.com/neondatabase/mcp-server-neon
- **Stars**: 569
- **Licence**: MIT
- **Dernière release**: 189 commits, actif
- **Source de découverte**: wong2/awesome-mcp-servers
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 03_mcp
- **Description**: Serveur MCP officiel Neon pour interagir en langage naturel avec des bases Postgres serverless. Gestion de projets, branches, queries, migrations. Authentification OAuth ou API key.
- **Pourquoi c'est pertinent**: Officiel Neon. Postgres serverless pour AI workflows. Mode lecture seule pour sécurité.

### MongoDB MCP Server (officiel MongoDB Labs)
- **URL**: https://github.com/mongodb-labs/mongodb-mcp-server
- **GitHub**: https://github.com/mongodb-labs/mongodb-mcp-server
- **Stars**: 985
- **Licence**: non précisée (à vérifier dans repo)
- **Dernière release**: active (700+ commits)
- **Source de découverte**: recherche directe GitHub
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 03_mcp
- **Description**: Serveur MCP officiel MongoDB Labs pour interagir avec MongoDB et MongoDB Atlas. Opérations DB, gestion Atlas (clusters, users), Stream Processing. Mode read-only par défaut.
- **Pourquoi c'est pertinent**: Officiel MongoDB Labs. ~1000 stars. MongoDB est la DB NoSQL document la plus populaire.

### Redis MCP Server (officiel Redis)
- **URL**: https://github.com/redis/mcp-redis
- **GitHub**: https://github.com/redis/mcp-redis
- **Stars**: 468
- **Licence**: MIT
- **Dernière release**: active (323 commits)
- **Source de découverte**: recherche directe GitHub
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 03_mcp
- **Description**: Interface langage naturel pour gérer et chercher des données Redis. Supporte hashes, listes, sets, sorted sets, streams, JSON, vector search. Intégration Azure EntraID.
- **Pourquoi c'est pertinent**: Officiel Redis inc. Support des opérations vectorielles. Intégration Azure.

### Qdrant MCP Server (officiel Qdrant)
- **URL**: https://github.com/qdrant/mcp-server-qdrant
- **GitHub**: https://github.com/qdrant/mcp-server-qdrant
- **Stars**: 1,300
- **Licence**: non précisée (à confirmer)
- **Dernière release**: active (74 commits)
- **Source de découverte**: wong2/awesome-mcp-servers
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 03_mcp
- **Description**: Serveur MCP officiel Qdrant pour mémoire sémantique. Outils qdrant-store (sauvegarde avec métadonnées) et qdrant-find (recherche sémantique). Utilise FastEmbed pour les embeddings.
- **Pourquoi c'est pertinent**: Officiel Qdrant. Cas d'usage clé : mémoire sémantique pour agents AI. Stockage de snippets de code.

### Milvus MCP Server (officiel Zilliz)
- **URL**: https://github.com/zilliztech/mcp-server-milvus
- **GitHub**: https://github.com/zilliztech/mcp-server-milvus
- **Stars**: non confirmé
- **Licence**: non confirmée
- **Dernière release**: active
- **Source de découverte**: wong2/awesome-mcp-servers
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 03_mcp
- **Description**: Serveur MCP pour Milvus vector database. Recherche vectorielle, full-text, hybride. Gestion de collections et données.
- **Pourquoi c'est pertinent**: Officiel Zilliz/Milvus. Milvus est l'une des vector DBs les plus populaires.

---

## 5. SERVEURS MCP - DEV TOOLS & PRODUCTIVITY

### GitHub MCP Server (officiel GitHub)
- **URL**: https://github.com/github/github-mcp-server
- **GitHub**: https://github.com/github/github-mcp-server
- **Stars**: 28,500
- **Licence**: MIT (à confirmer)
- **Dernière release**: active, disponible sur ghcr.io
- **Source de découverte**: wong2/awesome-mcp-servers
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 03_mcp
- **Description**: Serveur MCP officiel GitHub. Gestion de repos, issues, PRs, analyse de code, sécurité, workflows CI/CD. Disponible en version hébergée (api.githubcopilot.com/mcp/) et locale (Docker).
- **Pourquoi c'est pertinent**: Officiel GitHub. 28.5k stars, le serveur MCP communautaire le plus étoilé. Intégration native avec GitHub Copilot.

### Playwright MCP (officiel Microsoft)
- **URL**: https://github.com/microsoft/playwright-mcp
- **GitHub**: https://github.com/microsoft/playwright-mcp
- **Stars**: 30,100
- **Licence**: non précisée (Microsoft)
- **Dernière release**: active (504 commits)
- **Source de découverte**: wong2/awesome-mcp-servers
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 03_mcp
- **Description**: Serveur MCP officiel Microsoft pour l'automatisation de navigateur via Playwright. Utilise des snapshots d'accessibilité (pas de screenshots) pour une approche token-efficace et déterministe.
- **Pourquoi c'est pertinent**: Officiel Microsoft. 30.1k stars - le plus populaire du catalogue. Approche accessibilité-first évite les modèles vision.

### Notion MCP Server (officiel Notion)
- **URL**: https://github.com/makenotion/notion-mcp-server
- **GitHub**: https://github.com/makenotion/notion-mcp-server
- **Stars**: 4,100
- **Licence**: non précisée
- **Dernière release**: active (86 commits, avril 2026)
- **Source de découverte**: recherche directe GitHub
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 03_mcp
- **Description**: Serveur MCP officiel Notion. 22 outils pour gérer workspaces Notion : query data sources, créer/modifier pages, gérer commentaires. Supporte stdio et Streamable HTTP. v2.0.0 migrate vers API 2025-09-03.
- **Pourquoi c'est pertinent**: Officiel Notion. 4.1k stars. Version 2.0.0 récente. Notion est très populaire pour la gestion de connaissances.

### Atlassian MCP (Jira + Confluence)
- **URL**: https://github.com/sooperset/mcp-atlassian
- **GitHub**: https://github.com/sooperset/mcp-atlassian
- **Stars**: 4,800
- **Licence**: MIT
- **Dernière release**: v0.21.0 (2 mars 2026)
- **Source de découverte**: recherche directe GitHub
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 03_mcp
- **Description**: Serveur MCP communautaire pour Atlassian (Jira + Confluence). 72 outils. Supporte Cloud et Server/Data Center. Gestion d'issues, transitions de statut, pages wiki.
- **Pourquoi c'est pertinent**: 4.8k stars. Jira est le tracker standard en entreprise. 72 outils, très complet.

### Sentry MCP Server (officiel Sentry)
- **URL**: https://github.com/getsentry/sentry-mcp
- **GitHub**: https://github.com/getsentry/sentry-mcp
- **Stars**: 615
- **Licence**: disponible dans LICENSE.md
- **Dernière release**: active (940 commits)
- **Source de découverte**: recherche directe GitHub
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 03_mcp
- **Description**: Serveur MCP officiel Sentry conçu pour les agents de coding (Cursor, Claude Code). Recherche d'événements, investigation d'issues, analyse de performance. Supporte remote et stdio transports.
- **Pourquoi c'est pertinent**: Officiel Sentry. 940 commits = très actif. Optimisé pour le contexte "human-in-the-loop coding".

### Grafana MCP Server (officiel Grafana)
- **URL**: https://github.com/grafana/mcp-grafana
- **GitHub**: https://github.com/grafana/mcp-grafana
- **Stars**: 2,700
- **Licence**: non précisée
- **Dernière release**: active (510 commits)
- **Source de découverte**: recherche directe GitHub
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 03_mcp
- **Description**: Serveur MCP officiel Grafana. Accès aux dashboards, datasources (Prometheus, Loki, ClickHouse, CloudWatch), alertes, incidents, OnCall. Supporte Grafana 9.0+.
- **Pourquoi c'est pertinent**: Officiel Grafana Labs. 2.7k stars. Monitoring et observabilité via MCP.

### Docker MCP Server
- **URL**: https://github.com/ckreiling/mcp-server-docker
- **GitHub**: https://github.com/ckreiling/mcp-server-docker
- **Stars**: 695
- **Licence**: GPL-3.0
- **Dernière release**: 53 commits, pas de release formelle
- **Source de découverte**: recherche directe GitHub
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 03_mcp
- **Description**: Serveur MCP pour gérer Docker en langage naturel. Compose, monitoring de conteneurs, gestion des volumes. Intégration Claude Desktop.
- **Pourquoi c'est pertinent**: 695 stars. Docker est omniprésent dans le dev workflow. Attention: GPL-3.0 (contrainte licence enterprise).

---

## 6. SERVEURS MCP - SEARCH & WEB

### Tavily MCP (officiel Tavily)
- **URL**: https://github.com/tavily-ai/tavily-mcp
- **GitHub**: https://github.com/tavily-ai/tavily-mcp
- **Stars**: 1,600
- **Licence**: MIT
- **Dernière release**: active (201 commits)
- **Source de découverte**: wong2/awesome-mcp-servers
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 03_mcp
- **Description**: Serveur MCP officiel Tavily. Recherche web temps réel (tavily-search), extraction de données (tavily-extract), mapping et crawling de sites. Support OAuth et déploiement remote/local.
- **Pourquoi c'est pertinent**: Tavily est optimisé pour les agents IA (pas juste les humains). 1.6k stars. Endpoint hébergé disponible.

### Exa MCP Server (officiel Exa)
- **URL**: https://github.com/exa-labs/exa-mcp-server
- **GitHub**: https://github.com/exa-labs/exa-mcp-server
- **Stars**: 4,100
- **Licence**: non précisée
- **Dernière release**: active (304 commits)
- **Source de découverte**: wong2/awesome-mcp-servers
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 03_mcp
- **Description**: Serveur MCP officiel Exa pour recherche web, recherche de code (GitHub/StackOverflow), et crawling de pages. Endpoint hébergé sur mcp.exa.ai/mcp. 3 outils par défaut + outil avancé optionnel.
- **Pourquoi c'est pertinent**: 4.1k stars. Exa = moteur de recherche conçu pour l'IA. Très pertinent pour les agents de recherche.

### Firecrawl MCP Server (officiel Firecrawl)
- **URL**: https://github.com/mendableai/firecrawl-mcp-server
- **GitHub**: https://github.com/mendableai/firecrawl-mcp-server
- **Stars**: 5,900
- **Licence**: non précisée
- **Dernière release**: active (255 commits)
- **Source de découverte**: recherche directe GitHub
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 03_mcp
- **Description**: Serveur MCP officiel Firecrawl pour scraping, crawling et extraction de données web. Scraping single-page, batch processing, mapping, recherche web, research agent IA, automatisation browser interactive.
- **Pourquoi c'est pertinent**: 5.9k stars. Firecrawl est le standard pour web scraping destiné aux LLMs. 6 outils spécialisés.

---

## 7. SERVEURS MCP - BROWSER AUTOMATION

### Browserbase MCP (officiel Browserbase)
- **URL**: https://github.com/browserbase/mcp-server-browserbase
- **GitHub**: https://github.com/browserbase/mcp-server-browserbase
- **Stars**: 3,200
- **Licence**: Apache-2.0
- **Dernière release**: v3.0.0 (31 mars 2026)
- **Source de découverte**: wong2/awesome-mcp-servers
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 03_mcp
- **Description**: Serveur MCP officiel Browserbase pour browser cloud automation via Stagehand. 6 outils : start/end session, navigate, act, observe, extract. Hébergé sur mcp.browserbase.com/mcp.
- **Pourquoi c'est pertinent**: 3.2k stars. v3.0.0 très récente (31 mars 2026). Cloud browser automation vs Playwright local.

---

## 8. SERVEURS MCP - PAIEMENT & FINANCE

### Stripe MCP (officiel Stripe)
- **URL**: https://github.com/stripe/agent-toolkit
- **GitHub**: https://github.com/stripe/agent-toolkit
- **Stars**: 1,400
- **Licence**: MIT
- **Dernière release**: active (318 commits)
- **Source de découverte**: wong2/awesome-mcp-servers
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 03_mcp
- **Description**: Agent Toolkit officiel Stripe incluant un serveur MCP. Intègre Stripe avec LLMs via function calling. Support Python et TypeScript. Server MCP hébergé sur mcp.stripe.com. Compatible LangChain, CrewAI, OpenAI Agent SDK.
- **Pourquoi c'est pertinent**: Officiel Stripe. Paiements via MCP. Endpoint hébergé. 1.4k stars.

---

## 9. SERVEURS MCP - DATA EXTRACTION

### Apify MCP Server (officiel Apify)
- **URL**: https://github.com/apify/actors-mcp-server
- **GitHub**: https://github.com/apify/actors-mcp-server
- **Stars**: 1,000
- **Licence**: disponible (LICENSE.md)
- **Dernière release**: active
- **Source de découverte**: recherche directe GitHub
- **Date de recherche**: 2026-04-02
- **Catégorie suggérée**: 03_mcp
- **Description**: Serveur MCP officiel Apify donnant accès à 8,000+ "Actors" (scrapers et outils d'automatisation). Extraction de données depuis réseaux sociaux, moteurs de recherche, cartes, e-commerce. Endpoint hébergé sur mcp.apify.com.
- **Pourquoi c'est pertinent**: Officiel Apify. 8000+ tools disponibles via une seule configuration MCP. 1k stars.

---

## 10. SERVEURS MCP - ARCHIVÉS (référence, pas à cataloguer comme actifs)

Les serveurs suivants ont été archivés depuis modelcontextprotocol/servers vers modelcontextprotocol/servers-archived. Ils NE SONT PLUS MAINTENUS et ne recoivent plus de mises à jour de sécurité. Des remplacements communautaires existent pour chacun :

| Serveur archivé | Remplacement recommandé |
|----------------|------------------------|
| GitHub (officiel) | github/github-mcp-server (28.5k stars) |
| Slack (officiel) | jtalk22/slack-mcp-server |
| PostgreSQL (officiel) | supabase-community/supabase-mcp, neondatabase/mcp-server-neon |
| Redis (officiel) | redis/mcp-redis |
| Sentry (officiel) | getsentry/sentry-mcp |
| Puppeteer (officiel) | microsoft/playwright-mcp (30k stars) |
| Google Drive | intégration via Paragon ActionKit |
| Brave Search | tavily-ai/tavily-mcp, exa-labs/exa-mcp-server |
| GitLab | communautaire (via wong2/awesome-mcp-servers) |

---

## SYNTHESE : Priorités pour le catalogue ARIA

### Tier 1 - A cataloguer en priorité (stars élevées + activité récente)

| Outil | Stars | Type | Justification |
|-------|-------|------|---------------|
| microsoft/playwright-mcp | 30.1k | Browser automation | Stars #1, officiel Microsoft |
| github/github-mcp-server | 28.5k | Dev tools | Stars #2, officiel GitHub |
| jlowin/fastmcp | 24.2k | Framework | Standard de fait pour écrire des serveurs MCP |
| modelcontextprotocol/python-sdk | 22.5k | SDK | SDK officiel |
| awslabs/mcp | 8.7k | Cloud | Suite AWS officielle complète |
| modelcontextprotocol/inspector | 9.3k | Dev tool | Outil debug officiel |
| punkpeye/awesome-mcp-servers | 84.1k | Référence | Source principale de découverte |

### Tier 2 - A cataloguer (pertinence enterprise)

| Outil | Stars | Type |
|-------|-------|------|
| sooperset/mcp-atlassian | 4.8k | Productivity (Jira+Confluence) |
| mendableai/firecrawl-mcp-server | 5.9k | Web scraping |
| exa-labs/exa-mcp-server | 4.1k | Search |
| makenotion/notion-mcp-server | 4.1k | Productivity |
| open-webui/mcpo | 4.1k | Infrastructure (MCP→OpenAPI) |
| cloudflare/mcp-server-cloudflare | 3.6k | Cloud |
| browserbase/mcp-server-browserbase | 3.2k | Browser automation |
| grafana/mcp-grafana | 2.7k | Monitoring |
| supabase-community/supabase-mcp | 2.6k | Database |
| supercorp-ai/supergateway | 2.5k | Infrastructure |

### Tier 3 - A surveiller

| Outil | Stars | Type |
|-------|-------|------|
| hashicorp/terraform-mcp-server | 1.3k | IaC |
| tavily-ai/tavily-mcp | 1.6k | Search |
| manusa/kubernetes-mcp-server | 1.4k | K8s |
| stripe/agent-toolkit | 1.4k | Finance |
| mongodb-labs/mongodb-mcp-server | 985 | Database |
| getsentry/sentry-mcp | 615 | Monitoring |
| redis/mcp-redis | 468 | Database |
| neondatabase/mcp-server-neon | 569 | Database |

---

## Sources Utilisées

1. https://github.com/modelcontextprotocol/servers (82.8k stars) - serveurs officiels
2. https://github.com/modelcontextprotocol/servers-archived - serveurs archivés
3. https://github.com/punkpeye/awesome-mcp-servers (84.1k stars) - liste curated principale
4. https://github.com/wong2/awesome-mcp-servers (3.9k stars) - liste curated secondaire
5. Vérifications directes sur chaque repo GitHub individuel
6. https://github.com/modelcontextprotocol/python-sdk
7. https://github.com/modelcontextprotocol/typescript-sdk
8. https://github.com/modelcontextprotocol/inspector

*Toutes les URLs ont été vérifiées directement. Les serveurs archivés sont clairement identifiés.*
