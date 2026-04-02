# Business Process Automation with AI - Research Findings
**Date de recherche :** 2026-04-02  
**Agent :** researcher  
**Scope :** Processus business automatises a 60%+ par des LLMs open-source ou integrables

---

## Methodologie

Recherche conduite via GitHub Topics, GitHub Search, et WebFetch direct sur les repos pertinents.
Termes de recherche utilises :
- `ai sales automation`, `ai cold email outreach`, `ai lead scoring`, `ai customer support`
- `ai invoice processing`, `ai recruitment screening`, `ai content generation`
- `ai seo automation`, `ai social media automation`, `ai ticket triage`
- `ai contract review`, `ai devops monitoring`, `ai report generation`
- Topics : `sales-automation`, `customer-support`, `content-generation`, `workflow-automation`
- Topics : `document-processing`, `seo`, `marketing-automation`, `hr-automation`, `email-automation`

---

## 1. COMMERCIAL / VENTES

---

### 1.1 Sales Outreach Automation (LangGraph)

- **Processus automatise :** Prospection B2B - recherche de leads, qualification, generation de messages personnalises
- **URL GitHub :** https://github.com/kaymen99/sales-outreach-automation-langgraph
- **Stars :** ~260
- **Licence :** Non specifiee (repo public)
- **LLM utilise :** Google Gemini Flash/Pro + embeddings Google
- **Frameworks :** LangGraph, LangChain, RAG
- **Source de decouverte :** GitHub Topics `sales-automation`
- **% automatisation estime :** 70-80% - automatise la recherche LinkedIn, la qualification et la generation du premier contact
- **Comment ca marche :** Un agent recupere les leads depuis HubSpot/Airtable/Google Sheets, scrape les profils LinkedIn et la presence digitale de l'entreprise, qualifie selon des criteres metier (industrie, taille), puis genere des emails personnalises, rapports et scripts d'interview. Les resultats sont sauvegardes dans Google Docs et synchronises vers le CRM.
- **Maturite :** Actif (dernier commit janvier 2025), projet demonstrateur mais architecture production-ready

---

### 1.2 OpenOutreach - LinkedIn AI Lead Generation

- **Processus automatise :** Prospection LinkedIn - recherche de cibles, connexion, generation de messages
- **URL GitHub :** https://github.com/getOpenOutreach/openoutreach (inferred from 1.4k stars listing)
- **Stars :** 1 400
- **Licence :** Non specifiee
- **LLM utilise :** LLMs + Playwright browser automation
- **Source de decouverte :** GitHub Topics `marketing-automation`
- **% automatisation estime :** 75% - automatise la recherche de prospects, connexion et envoi de messages
- **Comment ca marche :** Decrit comme "LinkedIn Automation Tool: Describe your product. Define your target market. The AI finds leads for you." Utilise des agents IA et LLMs pour identifier automatiquement les prospects correspondant au ICP (Ideal Customer Profile) et automatise les connexions et messages via Playwright.
- **Maturite :** Active (infere du star count eleve et description recente)

---

### 1.3 B2B Lead Generation System

- **Processus automatise :** Generation de leads B2B - scraping multi-sources + enrichissement IA
- **Stars :** ~35
- **LLM utilise :** Google Gemini
- **Source de decouverte :** GitHub Topics `sales-automation`
- **% automatisation estime :** 70% - scrappe Apollo.io, LinkedIn, enrichit via IA, genere outreach personnalise
- **Comment ca marche :** Combine le scraping Apollo.io et LinkedIn avec Google Gemini pour enrichir les donnees de leads et generer automatiquement des messages de prospection personnalises.
- **Maturite :** Emergent (35 stars, actif)

---

### 1.4 AI Voice Lead Reactivation

- **Processus automatise :** Reactivation de leads froids par appels vocaux automatises
- **Stars :** ~44
- **Integrations :** HubSpot CRM
- **Source de decouverte :** GitHub Topics `sales-automation`
- **% automatisation estime :** 80% - appels automatiques, qualification vocale, mise a jour CRM
- **Comment ca marche :** Systeme d'appels automatises par IA vocale qui reactiven les leads dormants dans HubSpot, qualifie via conversation naturelle et met a jour le CRM avec les resultats.
- **Maturite :** Emergent (44 stars)

---

### 1.5 Autonomous Sales Inbox and CRM Assistant

- **Processus automatise :** Gestion inbox commerciale + redaction automatique des reponses
- **Stars :** ~50
- **LLM utilise :** Non specifie (OpenAI probable)
- **Source de decouverte :** GitHub Topics `sales-automation`
- **% automatisation estime :** 65% - lit les emails entrants, genere des drafts selon les playbooks commerciaux
- **Comment ca marche :** Agent IA qui surveille l'inbox sales, comprend le contexte des conversations, et genere automatiquement des reponses basees sur les playbooks et la connaissance produit de l'entreprise.
- **Maturite :** Actif (dernier commit juin 2024, 50 stars)

---

## 2. MARKETING

---

### 2.1 AI Marketing Claude Skills

- **Processus automatise :** Marketing complet - audits site, copywriting, sequences email, campagnes pub, analyse concurrentielle
- **URL GitHub :** (via Claude Skills ecosystem, ~1000 stars)
- **Stars :** ~1 000
- **Licence :** Non specifiee
- **LLM utilise :** Claude (Anthropic)
- **Source de decouverte :** GitHub Topics `marketing-automation`
- **% automatisation estime :** 70-80% - 15 skills marketing avec sous-agents parallelises, generation de rapports PDF clients
- **Comment ca marche :** Collection de 15 skills marketing pour Claude Code avec sous-agents paralleles couvrant audits de site web, copywriting, sequences email, campagnes publicitaires et analyse concurrentielle. Genere des rapports PDF prets a envoyer aux clients.
- **Maturite :** Actif (2025-2026)

---

### 2.2 GPT Researcher - Research & Content Automation

- **Processus automatise :** Recherche de contenu, veille concurrentielle, generation de rapports detailles
- **URL GitHub :** https://github.com/assafelovic/gpt-researcher
- **Stars :** >10 000 (infere de la popularite)
- **Licence :** Apache 2.0
- **LLM utilise :** OpenAI, Gemini, tout LLM compatible OpenAI
- **Source de decouverte :** GitHub Search direct
- **% automatisation estime :** 85% - genere des rapports >2000 mots depuis >20 sources automatiquement
- **Comment ca marche :** Architecture multi-agent : un planificateur genere les questions de recherche, des agents d'execution collectent les informations depuis plus de 20 sources, le publisher synthetise en rapport complet avec citations. Scraping JavaScript-enabled pour les sites dynamiques.
- **Maturite :** Production-ready, tres actif

---

### 2.3 AIWriter - Blog Automation via SERP

- **Processus automatise :** Creation d'articles de blog optimises SEO
- **Stars :** ~295
- **LLM utilise :** Non specifie (OpenAI probable)
- **Source de decouverte :** GitHub Topics `content-generation`
- **% automatisation estime :** 75% - recherche SERP + generation article complet + optimisation SEO
- **Comment ca marche :** Pipeline integrant la recherche SERP (analyse des resultats Google) avec la generation IA pour produire des articles de blog qui correspondent aux attentes de classement. Automatise la recherche de mots-cles, la structure et la redaction.
- **Maturite :** Actif (~295 stars)

---

### 2.4 automate-for-growth - Content Multi-Platform

- **Processus automatise :** Creation et publication de contenu multi-canal (video, posts, newsletters)
- **Stars :** ~630
- **LLM utilise :** Sora 2, modeles generatifs
- **Source de decouverte :** GitHub Topics `social-media-automation`
- **% automatisation estime :** 80% - generation video Sora, creation contenu, publication multi-plateforme
- **Comment ca marche :** Couvre l'automatisation complete du contenu pour la croissance : generation video avec Sora 2, automatisation de l'autorite de marque, publication multi-plateforme, creation en masse. Pipeline de A a Z depuis l'idee jusqu'a la publication.
- **Maturite :** Actif (630 stars)

---

### 2.5 Claude SEO Skills

- **Processus automatise :** SEO complet - audit technique, optimisation contenu, schema markup, rapports
- **URL GitHub :** (via Claude Skills ecosystem)
- **Stars :** ~3 800
- **Licence :** Non specifiee
- **LLM utilise :** Claude (Anthropic) + Google Search API
- **Source de decouverte :** GitHub Topics `seo`
- **% automatisation estime :** 70% - 19 sous-skills, 12 sous-agents, audits automatiques PDF/Excel
- **Comment ca marche :** Skill universel SEO pour Claude Code avec 19 sous-skills couvrant le SEO technique, schema markup, local search, integration Google API. Genere des rapports d'audit complets en PDF/Excel. Les 12 sous-agents travaillent en parallele pour analyser differents aspects du site.
- **Maturite :** Tres actif (3800 stars)

---

### 2.6 Agentfy - Social Media Multi-Platform

- **Processus automatise :** Gestion reseaux sociaux - creation, publication, engagement sur multiple plateformes
- **URL GitHub :** https://github.com/Agentfy/agentfy (inferred)
- **Stars :** ~386
- **LLM utilise :** OpenAI
- **Source de decouverte :** GitHub Topics `social-media-automation`
- **% automatisation estime :** 70% - microservices modulaires pour chaque plateforme sociale, pipeline complet
- **Comment ca marche :** Architecture microservices modulaire qui traite les requetes utilisateur et execute des workflows sur multiple plateformes sociales. Utilise Python et OpenAI pour generer le contenu et automatiser les interactions. Gere Instagram, Twitter/X, LinkedIn, TikTok.
- **Maturite :** Actif (386 stars)

---

### 2.7 YouTube Automation Agent

- **Processus automatise :** Gestion complete d'une chaine YouTube (contenu, upload, optimisation)
- **Stars :** ~113
- **LLM utilise :** Gemini (gratuit) ou OpenAI
- **Source de decouverte :** GitHub Topics `social-media-automation`
- **% automatisation estime :** 85% - creation video, upload, metadata, thumbnails automatises
- **Comment ca marche :** Gestion completement automatisee d'une chaine YouTube avec des agents IA : planification du contenu, creation, upload et publication. Supporte Gemini gratuit ou OpenAI selon le budget.
- **Maturite :** Actif (113 stars)

---

### 2.8 LangGraph Email Automation - Multi-Agent Customer Support

- **Processus automatise :** Automation des emails clients - classification, reponse automatique, escalade
- **Stars :** ~236
- **LLM utilise :** LangChain/LangGraph (OpenAI ou autre)
- **Source de decouverte :** GitHub Topics `email-automation`
- **% automatisation estime :** 70% - multi-agents pour classification, reponse et routage des emails clients
- **Comment ca marche :** Systeme multi-agents LangGraph avec agents specialises : un agent classifie l'email, un agent recherche dans la base de connaissance, un agent redige la reponse, un superviseur valide avant envoi. Support de l'escalade humaine.
- **Maturite :** Actif (236 stars)

---

## 3. SERVICE CLIENT / SUPPORT

---

### 3.1 Chatwoot - Omnichannel Support Platform avec Captain AI

- **Processus automatise :** Support client omnicanal + resolution automatique des requetes courantes
- **URL GitHub :** https://github.com/chatwoot/chatwoot
- **Stars :** 28 200
- **Licence :** MIT
- **LLM utilise :** "Captain" (modele interne Chatwoot), Dialogflow
- **Source de decouverte :** GitHub Topics `customer-support`
- **% automatisation estime :** 60-70% - Captain AI resout les questions courantes automatiquement, escalade vers humain pour les cas complexes
- **Comment ca marche :** Plateforme de support omnicanal (chat, email, reseaux sociaux) avec Captain AI integre qui automatise les reponses aux questions frequentes. Google Translate pour le support multilingue. Human-in-the-loop quand necessaire. Le systeme apprend de la base de connaissance.
- **Maturite :** Production-ready, tres actif (mise a jour avril 2026)

---

### 3.2 TGO - Open-Source AI Agent Customer Service Platform

- **Processus automatise :** Service client multi-canal avec agents IA et RAG
- **URL GitHub :** https://github.com/tgoai/tgo
- **Stars :** ~416
- **Licence :** Open-source (double licence CN/Global)
- **LLM utilise :** OpenAI, Anthropic Claude, et autres via configuration
- **Source de decouverte :** GitHub Topics `customer-support`
- **% automatisation estime :** 75% - agents IA configures par scenario metier, RAG sur base de connaissance, 40+ outils MCP integres
- **Comment ca marche :** Plateforme d'orchestration multi-agents ou chaque agent est configure pour un scenario metier specifique. RAG sur documents uploades, Q&A, crawl de sites web. Recherche semantique vectorielle pour les reponses precises. 40+ outils MCP built-in pour les operations courantes.
- **Maturite :** Actif (416 stars, active development)

---

### 3.3 Tiledesk - LLM-Powered Agents avec HITL

- **Processus automatise :** Chatbot conversationnel avec agents LLM et transfert humain intelligent
- **URL GitHub :** https://github.com/Tiledesk/tiledesk-server
- **Stars :** ~376
- **Licence :** MIT
- **LLM utilise :** Claude (integre), et autres LLMs
- **Source de decouverte :** GitHub Topics `customer-support`
- **% automatisation estime :** 70% - agents LLM natives avec HITL quand necesaire
- **Comment ca marche :** Alternative open-source a Voiceflow. Deploiement multi-canal (WhatsApp, Facebook Messenger, Telegram) avec chatbots natifs et agents LLM avances. Le systeme detecte quand le cas necessite un humain et transfere automatiquement. Capacites RAG pour ancrer les reponses.
- **Maturite :** Actif (376 stars)

---

### 3.4 Production AI Customer Support (Multi-Agent Enterprise)

- **Processus automatise :** Support client enterprise multi-agent avec ticketing
- **Stars :** ~14
- **LLM utilise :** Gemini, OpenAI
- **Frameworks :** CrewAI, FastAPI, LangGraph
- **Source de decouverte :** GitHub Search
- **% automatisation estime :** 70-80% - systeme enterprise avec agents specialises, routing intelligent, analyse de sentiment
- **Comment ca marche :** Systeme enterprise-grade avec agents IA specialises (support general, technique, facturation). FastAPI pour les APIs, LangGraph pour l'orchestration des agents, analyse de sentiment pour la detection de l'urgence, integration ticketing.
- **Maturite :** Emergent (14 stars, mais architecture documentee)

---

### 3.5 AI Voice Appointment Booking

- **Processus automatise :** Prise de rendez-vous par voix IA 24/7
- **Stars :** ~24
- **Integrations :** FastAPI, Twilio, AWS
- **Source de decouverte :** GitHub Topics `business-automation`
- **% automatisation estime :** 85% - gestion complete des RDV par voix, sans intervention humaine
- **Comment ca marche :** Systeme vocale enterprise avec FastAPI, Twilio pour la telephonie, et AWS pour l'infrastructure. L'IA prend les appels, comprend la demande de RDV en langage naturel, verifie les disponibilites et confirme par SMS/email.
- **Maturite :** Actif (24 stars, octobre 2025)

---

## 4. ADMINISTRATION / BACK-OFFICE

---

### 4.1 Unstract - Document Intelligence Platform

- **Processus automatise :** Extraction de donnees structurees depuis tout type de document (factures, contrats, formulaires)
- **URL GitHub :** https://github.com/Zipstack/unstract
- **Stars :** ~6 500
- **Licence :** Non specifiee (open-source)
- **LLM utilise :** OpenAI, Anthropic Claude, Google Gemini, AWS Bedrock, Mistral, Ollama (local)
- **Source de decouverte :** GitHub Topics `document-processing`
- **% automatisation estime :** 85-90% - extraction schema en langage naturel, API deployment, ETL pipeline
- **Comment ca marche :** Trois approches : Prompt Studio pour definir les schemas d'extraction en langage naturel, API REST pour envoyer des documents et recevoir du JSON structure, Pipeline ETL pour traiter automatiquement des flux de documents. Supporte PDF, images, scans, tableurs. Integration MCP pour agents IA.
- **Maturite :** Production-ready, tres actif (6500 stars)

---

### 4.2 ExtractThinker - Document Intelligence ORM

- **Processus automatise :** Extraction de donnees depuis documents avec workflows flexibles (factures, recus, contrats)
- **URL GitHub :** https://github.com/enoch3712/ExtractThinker
- **Stars :** ~1 500
- **Licence :** Non specifiee
- **LLM utilise :** Multi-LLM via ORM-style interface
- **Source de decouverte :** GitHub Topics `document-processing`
- **% automatisation estime :** 80% - extraction ORM-style, workflows flexibles, PDFs et OCR
- **Comment ca marche :** Framework de document intelligence avec une interface style ORM qui abstrait l'interaction LLM. Permet de definir des schemas de donnees et d'extraire automatiquement depuis PDFs et images OCR. Workflows flexibles pour chaining de transformations.
- **Maturite :** Actif (1500 stars)

---

### 4.3 DocETL - Agentic Document Processing & ETL

- **Processus automatise :** Traitement de documents non-structures, ETL avec intelligence semantique
- **URL GitHub :** https://github.com/ucbepic/docetl
- **Stars :** ~3 700
- **Licence :** Non specifiee
- **LLM utilise :** OpenAI GPT-4o-mini, AWS Bedrock, multi-LLM via liteLLM
- **Source de decouverte :** GitHub Topics `document-processing`
- **% automatisation estime :** 80% - pipeline ETL complet avec intelligence LLM, UI DocWrangler pour iteration
- **Comment ca marche :** Systeme de traitement de documents complexes avec operateurs agentic (gleaning, resolve). Interface UI DocWrangler pour le prompt engineering iteratif avec visualisation en temps reel. Supporte des pipelines complexes de transformation semantique.
- **Maturite :** Actif (3700 stars, UC Berkeley)

---

### 4.4 AI Resume Screening System

- **Processus automatise :** Recrutement - screening automatique des CVs, classement des candidats
- **URL GitHub :** https://github.com/312323205202/ai-resume-screening-system
- **Stars :** ~50
- **Licence :** Non specifiee
- **LLM utilise :** Non specifie (NLP + ML)
- **Source de decouverte :** GitHub Search `recruitment automation`
- **% automatisation estime :** 75% - extraction depuis AWS S3, classification selon criteres RH, scoring automatique
- **Comment ca marche :** Systeme Python qui extrait les CVs depuis AWS S3, applique des criteres de classification definis par les RH, score les candidats automatiquement. Reduit le temps de screening de semaines a heures. Genere des rapports de classement.
- **Maturite :** Actif (50 stars, actif il y a 29 jours)

---

### 4.5 Frappe AI Hiring - ERP Recruitment Automation

- **Processus automatise :** Pipeline de recrutement complet integre a ERPNext/Frappe HRMS
- **URL GitHub :** https://github.com/connectionloops/frappe_ai_hiring
- **Stars :** ~5
- **Licence :** Frappe (open-source)
- **LLM utilise :** Non specifie (IA integree)
- **Source de decouverte :** GitHub Search `recruitment automation`
- **% automatisation estime :** 70% - de la reception du CV a la preparation des entretiens, integre dans ERP
- **Comment ca marche :** Application Frappe integree dans ERPNext/Frappe HRMS qui automatise le pipeline de recrutement complet : parsing CV, scoring, scheduling entretiens, suivi candidats, et preparation des questions d'entretien.
- **Maturite :** Actif (janvier 2026)

---

### 4.6 n8n Resume Screening Automation

- **Processus automatise :** Workflow complet de screening RH via n8n
- **URL GitHub :** https://github.com/krishnapriya-nynaru/Resume-Screening-automation-n8n
- **Stars :** ~4
- **Licence :** Non specifiee
- **LLM utilise :** Via n8n AI nodes (OpenAI, Gemini)
- **Source de decouverte :** GitHub Search `recruitment automation`
- **% automatisation estime :** 80% - parsing CV, evaluation, scoring, notifications automatiques
- **Comment ca marche :** Workflow n8n qui integre le parsing de CV, l'evaluation IA des candidats et le scoring automatique. Notifications automatiques aux candidats et aux recruteurs selon les seuils definis.
- **Maturite :** Actif

---

## 5. DEVELOPPEMENT / IT

---

### 5.1 PR-Agent (Codium AI) - AI Code Review

- **Processus automatise :** Code review automatique des Pull Requests
- **URL GitHub :** https://github.com/codium-ai/pr-agent
- **Stars :** ~10 700
- **Licence :** AGPL-3.0
- **LLM utilise :** OpenAI GPT-4, Claude, DeepSeek, et autres
- **Source de decouverte :** GitHub Topics `code-review`
- **% automatisation estime :** 70-80% - review complete en ~30 secondes, suggestions d'amelioration, description PR
- **Comment ca marche :** Trois commandes principales : `/describe` (genere la description de la PR), `/review` (analyse les changements et fournit du feedback), `/improve` (suggestions d'amelioration). Un seul appel LLM par commande (~30 secondes). Support GitHub, GitLab, Bitbucket, Azure DevOps, Gitea.
- **Maturite :** Production-ready, tres actif (10 700 stars)

---

### 5.2 Shippie - Code Review and QA Agent

- **Processus automatise :** Review de code et QA automatique, extensible
- **Stars :** ~2 300
- **Licence :** Non specifiee
- **LLM utilise :** Multi-providers (GitHub, et autres)
- **Source de decouverte :** GitHub Topics `code-review`
- **% automatisation estime :** 70% - review extensible, integration CI/CD, suggestions QA
- **Comment ca marche :** Agent de code review et QA extensible qui s'integre dans les pipelines CI/CD. Supporte plusieurs providers LLM, analyse la qualite du code, identifie les problemes de securite et suggere des ameliorations.
- **Maturite :** Actif (2300 stars)

---

### 5.3 Robusta - AI-Powered Kubernetes Monitoring

- **Processus automatise :** Monitoring DevOps, enrichissement d'alertes IA, auto-remediation
- **URL GitHub :** https://github.com/robusta-dev/robusta
- **Stars :** ~3 000
- **Licence :** MIT
- **LLM utilise :** HolmesGPT (composant IA de Robusta)
- **Source de decouverte :** GitHub Search `ai devops monitoring remediation`
- **% automatisation estime :** 65-70% - groupement intelligent des alertes, enrichissement IA, auto-remediation des patterns connus
- **Comment ca marche :** Plateforme de monitoring Kubernetes avec HolmesGPT pour l'enrichissement IA des alertes. Groupement intelligent des alertes dans des threads Slack, enrichissement automatique avec logs et donnees contextuelles, auto-remediation pour les issues communes. Integration Prometheus, Slack, PagerDuty, Jira, ServiceNow.
- **Maturite :** Production-ready, actif (3000 stars)

---

### 5.4 Browser-Use - AI Web Automation

- **Processus automatise :** Automatisation de taches web complexes via agents IA (formulaires, scraping, workflows)
- **URL GitHub :** https://github.com/browser-use/browser-use
- **Stars :** 85 600
- **Licence :** MIT
- **LLM utilise :** Claude (Anthropic), ChatBrowserUse, OpenAI, Gemini, Ollama local
- **Source de decouverte :** GitHub Search direct
- **% automatisation estime :** 80-90% - execution d'instructions en langage naturel sur n'importe quel site web
- **Comment ca marche :** Framework Python qui permet a des agents IA de controler un navigateur web. Supporte : remplissage de formulaires, extraction de donnees, comparaison de prix, gestion de comptes. ChatBrowserUse est optimise pour les taches browser (3-5x plus rapide que GPT-4). Peut s'executer avec des modeles locaux via Ollama.
- **Maturite :** Production-ready, extremement actif (85 600 stars, mis a jour en continu)

---

### 5.5 Skyvern - LLM Browser Automation for Workflows

- **Processus automatise :** Workflows navigateur complexes - formulaires, extraction, e-commerce, compliance
- **URL GitHub :** https://github.com/Skyvern-AI/skyvern
- **Stars :** 21 000+
- **Licence :** Non specifiee (open-source + cloud)
- **LLM utilise :** Claude, et autres LLMs
- **Source de decouverte :** GitHub Search direct
- **% automatisation estime :** 85% - remplace les scripts XPath fragiles par du langage naturel
- **Comment ca marche :** Extension Playwright avec capacites LLM + vision. API simple : `page.act()` pour les actions, `page.extract()` pour l'extraction, `page.validate()` pour la verification. Utilise LLM + computer vision pour comprendre les pages dynamiquement plutot que de se baser sur des selecteurs fragiles.
- **Maturite :** Production-ready (21 000 stars, 4347 commits)

---

## 6. PLATEFORME / ORCHESTRATION TRANSVERSALE

---

### 6.1 n8n - AI-Native Workflow Automation Platform

- **Processus automatise :** Orchestration de workflows metier cross-fonctionnels avec IA native
- **URL GitHub :** https://github.com/n8n-io/n8n
- **Stars :** 182 000
- **Licence :** Fair-code (Sustainable Use License + Enterprise)
- **LLM utilise :** LangChain-based AI workflows, tous LLMs via nodes
- **Source de decouverte :** GitHub Topics `workflow-automation`
- **% automatisation estime :** 70-90% selon workflow - 400+ integrations, 900+ templates
- **Comment ca marche :** Plateforme d'automatisation avec interface visuelle + code (JavaScript/Python). Workflows IA bases sur LangChain avec modeles et donnees propres. 400+ integrations pre-buildees. Auto-hebergeable ou cloud. Support SSO, permissions avancees, deploiement air-gapped pour enterprise.
- **Maturite :** Production-ready, leader du marche (182 000 stars, mis a jour quotidiennement)

---

### 6.2 Activepieces - AI-First Automation avec MCP

- **Processus automatise :** Automatisation business avec agents IA et MCP servers
- **URL GitHub :** https://github.com/activepieces/activepieces
- **Stars :** 21 500
- **Licence :** MIT (community) + Commercial (enterprise)
- **LLM utilise :** OpenAI, et autres via AI SDK ; tous pieces = MCP servers pour Claude/Cursor/Windsurf
- **Source de decouverte :** GitHub Topics `workflow-automation`
- **% automatisation estime :** 70-85% - 200+ pieces, loops, branches, human-in-the-loop
- **Comment ca marche :** Plateforme d'automatisation "AI-First" ou toutes les pieces deviennent automatiquement des MCP servers utilisables avec Claude Desktop, Cursor ou Windsurf. 200+ integrations dont 60% community-contributed. Support des workflows humains (approbation, delai). Chat et formulaires natifs.
- **Maturite :** Production-ready, tres actif (21 500 stars, mis a jour quotidiennement)

---

### 6.3 Flowise - Visual AI Agent Builder

- **Processus automatise :** Construction visuelle d'agents IA pour n'importe quel processus metier
- **URL GitHub :** https://github.com/FlowiseAI/Flowise
- **Stars :** 51 400
- **Licence :** Apache 2.0
- **LLM utilise :** OpenAI, Claude, Mistral, Llama, tous LLMs via LangChain
- **Source de decouverte :** GitHub Topics `workflow-automation`
- **% automatisation estime :** 70-90% selon cas d'usage - builder visuel RAG, chatbots, agents
- **Comment ca marche :** Interface drag-and-drop pour construire des chatbots IA, pipelines RAG et agents sans code. Supporte tous les LLMs via LangChain. Deploy via API. Populaire pour le prototypage rapide et les deployments production.
- **Maturite :** Production-ready, leader (51 400 stars, mis a jour quotidiennement)

---

### 6.4 Budibase - AI Agents for Business Operations

- **Processus automatise :** Construction d'outils internes IA, dashboards, operations business
- **URL GitHub :** https://github.com/Budibase/budibase
- **Stars :** 27 800
- **Licence :** GPL-3.0 + Budibase commercial
- **LLM utilise :** Integrations IA natives
- **Source de decouverte :** GitHub Topics `workflow-automation`
- **% automatisation estime :** 70% - agents IA pour operations business, outils internes automatises
- **Comment ca marche :** Plateforme low-code pour construire des outils internes avec agents IA integres. Automatise les operations business recurrentes via des interfaces construites visuellement connectees a toutes les sources de donnees.
- **Maturite :** Production-ready, tres actif (27 800 stars)

---

## 7. JURIDIQUE

---

### 7.1 ContextGem - LLM Document Extraction

- **Processus automatise :** Extraction d'information legale et contractuelle depuis documents
- **URL GitHub :** https://github.com/contextgem/contextgem (inferred)
- **Stars :** ~1 800
- **Licence :** Non specifiee
- **LLM utilise :** Multi-LLM
- **Source de decouverte :** GitHub Topics `contract-analysis`
- **% automatisation estime :** 80% - extraction "effortless" depuis DOCX et donnees non structurees
- **Comment ca marche :** Framework Python pour l'extraction LLM depuis documents. Interface de type ORM pour definir ce qu'on veut extraire, le LLM s'occupe du reste. Specialise pour les documents legaux et techniques.
- **Maturite :** Actif (1800 stars)

---

### 7.2 Claude Legal Contract Review Skills

- **Processus automatise :** Review de contrats - detection des risques CUAD, benchmarks marche, redlines
- **Stars :** ~158
- **Licence :** Non specifiee
- **LLM utilise :** Claude (Anthropic)
- **Source de decouverte :** GitHub Topics `contract-analysis`
- **% automatisation estime :** 70% - detection automatique des clauses risquees (standard CUAD), comparaison benchmarks, generation de redlines
- **Comment ca marche :** Systeme de review de contrats base sur Claude Code utilisant le dataset CUAD (Contract Understanding Atticus Dataset) pour detecter les clauses risquees. Compare avec les benchmarks marche, genere des redlines et des notes pour les avocats. Compatible Cursor et 26+ outils d'integration.
- **Maturite :** Actif (158 stars)

---

### 7.3 Ally Legal Assistant - Word Plugin Azure OpenAI

- **Processus automatise :** Analyse contractuelle inline dans Microsoft Word
- **Stars :** ~68
- **Licence :** Non specifiee
- **LLM utilise :** Azure OpenAI
- **Source de decouverte :** GitHub Topics `contract-analysis`
- **% automatisation estime :** 65% - analyse en temps reel dans Word, Q&A sur le contrat, auto-markup
- **Comment ca marche :** Plugin Microsoft Word utilisant Azure OpenAI pour l'analyse de contrats en temps reel. Repond aux questions sur le document, identifie les clauses problematiques et applique automatiquement des markups de review.
- **Maturite :** Actif (68 stars)

---

## 8. DATA / ANALYTICS / BI

---

### 8.1 WrenAI - Text-to-SQL GenBI Agent

- **Processus automatise :** Business Intelligence - requetes SQL depuis langage naturel, rapports automatiques
- **URL GitHub :** https://github.com/Canner/WrenAI
- **Stars :** ~14 800
- **Licence :** AGPL-3.0
- **LLM utilise :** OpenAI, Anthropic Claude, DeepSeek, Groq, Azure OpenAI, Gemini, Vertex AI, AWS Bedrock, Ollama
- **Source de decouverte :** GitHub Search direct
- **% automatisation estime :** 80% - SQL genere depuis questions naturelles, insights et graphiques automatiques
- **Comment ca marche :** Architecture : UI Next.js -> Apollo GraphQL -> Service IA (RAG + LLM) -> Wren Engine (semantic layer) -> Base de donnees. La couche semantique (MDL) encode les definitions metier (schemas, metriques, jointures) pour que les requetes SQL generees soient correctes. Genere des insights IA ecrits, graphiques et rapports.
- **Maturite :** Production-ready, tres actif (14 800 stars)

---

### 8.2 MindsDB - AI Analytics Query Engine

- **Processus automatise :** Analytique avancee IA sur donnees live, agents analytiques autonomes
- **URL GitHub :** https://github.com/mindsdb/mindsdb
- **Stars :** 38 900
- **Licence :** GPL-3.0
- **LLM utilise :** OpenAI (exemple), et autres via configuration
- **Source de decouverte :** GitHub Topics `business-intelligence`
- **% automatisation estime :** 75% - agents analytiques sur 200+ sources de donnees live, requetes SQL IA
- **Comment ca marche :** Moteur de requetes IA qui connecte 200+ sources de donnees live. Permet aux agents IA d'acceder de facon federee a toutes les donnees enterprise. Knowledge bases combines tables structurees + donnees vectorisees pour recherche hybride. Workflow : Connect -> Unify -> Respond.
- **Maturite :** Production-ready, leader (38 900 stars)

---

### 8.3 Cube - Semantic Layer for AI BI

- **Processus automatise :** Couche semantique pour analytique IA, embedded analytics
- **URL GitHub :** https://github.com/cube-js/cube
- **Stars :** 19 700
- **Licence :** Apache 2.0 + Commercial
- **LLM utilise :** Multi-LLM via semantic layer
- **Source de decouverte :** GitHub Topics `business-intelligence`
- **% automatisation estime :** 70% - semantic layer unifie pour BI IA, interfaces conversationnelles
- **Comment ca marche :** Semantic layer open-source en Rust pour IA, BI et analytics embarque. Alimente les agents analytiques et les interfaces conversationnelles sur les principales plateformes de donnees. Garantit des donnees fiables pour les LLMs.
- **Maturite :** Production-ready (19 700 stars)

---

### 8.4 Airbyte - Data Integration Platform

- **Processus automatise :** ETL/ELT automatise, synchronisation de donnees cross-systemes
- **URL GitHub :** https://github.com/airbytehq/airbyte
- **Stars :** 21 000
- **Licence :** MIT + ELv2 (dual)
- **LLM utilise :** Integration Claude AI en cours de developpement
- **Source de decouverte :** GitHub Search direct
- **% automatisation estime :** 80% - 600+ connecteurs, pipelines no-code ou low-code
- **Comment ca marche :** Plateforme de data integration avec 600+ connecteurs. Construction de pipelines via interface no-code ou SDK low-code. Integration avec Airflow, Prefect, Dagster, Kestra pour l'orchestration. Integrations IA Claude en cours de developpement.
- **Maturite :** Production-ready (21 000 stars)

---

### 8.5 Open Interpreter - Natural Language Computer Automation

- **Processus automatise :** Analyse de donnees, visualisation, manipulation de fichiers par langage naturel
- **URL GitHub :** https://github.com/KillianLucas/open-interpreter
- **Stars :** Non specifie (populaire)
- **Licence :** AGPL-3.0
- **LLM utilise :** GPT-4, Claude-2, Cohere, modeles locaux via Ollama/LM Studio
- **Source de decouverte :** GitHub Search direct
- **% automatisation estime :** 70% - execute Python/JS/Shell localement sur instructions naturelles
- **Comment ca marche :** Interface en langage naturel vers votre ordinateur. Execute Python, JavaScript, Shell et autres langages localement. Use cases : analyse et visualisation de grandes donnees, creation de contenu (photos, videos, PDFs), recherche web, gestion de fichiers. Requiert approbation utilisateur avant execution (securite enterprise).
- **Maturite :** Production-ready, actif

---

## 9. SCRAPING / ENRICHISSEMENT DE DONNEES

---

### 9.1 Firecrawl - LLM-Ready Web Data API

- **Processus automatise :** Extraction de donnees web structurees pour agents IA et pipelines data
- **URL GitHub :** https://github.com/mendableai/firecrawl
- **Stars :** 103 000
- **Licence :** Open-source (badge visible)
- **LLM utilise :** Spark-1-mini / Spark-1-pro, compatible MCP, Claude Code skill disponible
- **Source de decouverte :** GitHub Search direct
- **% automatisation estime :** 90% - scrape, crawl, extraction structuree en un appel API
- **Comment ca marche :** API web qui convertit n'importe quelle URL en Markdown/HTML/JSON structures, optimises pour les LLMs. Endpoints : Search, Scrape, Interact (manipulation de pages avec prompts IA), Agent (collecte par description naturelle), Crawl (tout le site), Map (decouverte d'URLs), Batch Scrape. S'installe comme skill Claude Code.
- **Maturite :** Production-ready, leader (103 000 stars, 5186+ commits)

---

## Synthese par Niveau d'Automatisation

### 85-90% automatise (processus quasi-autonomes)
| Processus | Outil | Stars |
|-----------|-------|-------|
| Extraction documentaire | Unstract | 6 500 |
| Web scraping structure | Firecrawl | 103 000 |
| Research & report generation | GPT Researcher | >10 000 |
| Navigation web AI | Browser-Use | 85 600 |
| Workflows browser complexes | Skyvern | 21 000 |
| Prise de RDV vocale | AI Voice Appointment | 24 |
| Gestion chaine YouTube | YouTube Automation Agent | 113 |

### 70-80% automatise (processus majeurs)
| Processus | Outil | Stars |
|-----------|-------|-------|
| Workflow automation | n8n | 182 000 |
| Agent builder visuel | Flowise | 51 400 |
| Agent builder visuel | Activepieces | 21 500 |
| Business Intelligence BI | WrenAI | 14 800 |
| Analytics IA | MindsDB | 38 900 |
| Code review PR | PR-Agent | 10 700 |
| Marketing omnicanal | Claude SEO Skills | 3 800 |
| SEO automation | Claude SEO Skills | 3 800 |
| Support client omnicanal | Chatwoot + Captain | 28 200 |
| Support client IA | TGO | 416 |
| Document intelligence | DocETL | 3 700 |
| Extraction ORM docs | ExtractThinker | 1 500 |
| Text-to-SQL BI | WrenAI | 14 800 |
| Contract review | ContextGem | 1 800 |
| Contract review Claude | Claude Legal Skills | 158 |
| Sales outreach | Sales Outreach LangGraph | 260 |
| LinkedIn prospection | OpenOutreach | 1 400 |
| HR screening | AI Resume Screening | 50 |
| Email automation multi-agent | LangGraph Email | 236 |
| DevOps monitoring | Robusta | 3 000 |

### 60-70% automatise (assistance significative)
| Processus | Outil | Stars |
|-----------|-------|-------|
| CRM + inbox sales | Autonomous Sales Inbox | 50 |
| Chatbot LLM + HITL | Tiledesk | 376 |
| Content multi-platform | Agentfy | 386 |
| Blog SEO generation | AIWriter | 295 |
| Data integration ETL | Airbyte | 21 000 |
| BI semantic layer | Cube | 19 700 |
| Word contract analysis | Ally Legal | 68 |
| Data analysis natural language | Open Interpreter | - |

---

## Technologies Transversales Observees

### Frameworks LLM dominants
1. **LangChain/LangGraph** : standard de facto pour les workflows d'agents
2. **n8n** : orchestration no-code/low-code la plus adoptee
3. **CrewAI** : multi-agents pour taches parallelisees
4. **Flowise** : builder visuel d'agents

### LLMs les plus utilises en production
1. **OpenAI GPT-4/GPT-4o** : default pour la plupart des projets
2. **Claude (Anthropic)** : code review, legal, contenu de qualite
3. **Google Gemini Flash/Pro** : rapide, economique pour la prospection
4. **Modeles locaux (Ollama/Mistral)** : use cases sensibles, air-gapped

### Patterns d'architecture dominants
1. **RAG** : base de connaissance + retrieval pour le support client
2. **Multi-agent** : agents specialises par sous-tache
3. **Human-in-the-loop** : approbation humaine pour les cas hors-norme
4. **Pipeline ETL IA** : documents -> extraction -> JSON -> systeme cible

---

*Fichier genere par l'agent researcher - ARIA Project - 2026-04-02*
