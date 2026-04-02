<div align="center">

**[English](README.md)** | **[Français](#pourquoi-aria-existe)** | **[Español](README.es.md)** | **[Guide débutant](guides/how-to-use-aria.fr.md)**

<br/>

<picture>
  <img alt="ARIA — Analyse et Recherche en Intelligence Artificielle" src="assets/aria-header.svg">
</picture>

<br/>

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Entries](https://img.shields.io/badge/Fiches-323+-blue)]()
[![Categories](https://img.shields.io/badge/Categories-18-green)]()
[![Updated](https://img.shields.io/badge/Derniere_MAJ-Avril_2026-brightgreen)]()
[![Agents](https://img.shields.io/badge/Maintenu_par-Agents_IA-purple)]()

[**Comment l'utiliser**](#comment-utiliser-aria) | [**Le catalogue**](#ce-quil-y-a-dedans) | [**Comment ça marche**](#comment-ca-marche) | [**Contribuer**](#contribuer)

</div>

---

## Pourquoi ARIA existe

Le monde de l'IA a trouvé son accélérateur. De nouveaux outils, modèles et frameworks sortent **chaque jour**. Ce qui était "le meilleur choix" la semaine dernière est déjà dépassé. Et chercher à l'ancienne — taper des mots-clés dans Google, scroller des articles de blog SEO écrits en 2024 — c'est déjà obsolète.

Le temps que tu trouves, compares et évalues un outil, trois nouvelles alternatives ont déjà été publiées.

**ARIA a été construit pour résoudre ce problème.**

C'est une base de connaissances vivante de l'écosystème IA — 323 outils répartis dans 18 catégories — où chaque entrée est structurée, notée et vérifiée. Mais le plus important : **ARIA ne dépend pas d'humains pour rester à jour.** Une équipe de 5 agents IA spécialisés travaille chaque nuit pour parcourir le web, trouver les nouveautés, vérifier ce qui a changé, et mettre à jour le catalogue automatiquement.

Tu te réveilles le matin. La base est à jour. Tu poses une question. Tu obtiens une réponse.

> *"Le goulot d'étranglement n'est plus l'intelligence — c'est de savoir ce qui existe."*

---

## Comment utiliser ARIA

### La méthode la plus simple : demander à Claude (recommandé)

Pas besoin d'être technique. Pas besoin d'installer quoi que ce soit. Ouvre [claude.ai](https://claude.ai) (gratuit) et colle ta question avec l'URL du catalogue. Claude lit du Markdown brut via GitHub Pages et cite les outils avec leurs scores enterprise exacts.

> **Pourquoi Claude ?** Après plusieurs benchmarks, Claude est le seul LLM gratuit qui lit réellement le catalogue, cite les vrais outils avec les scores, et n'hallucine pas. ChatGPT et Gemini (gratuits) n'arrivent pas à lire l'URL et répondent avec leurs propres connaissances génériques. Voir le [benchmark complet](BENCHMARK_LLM.md).

> **Tu ne sais pas ce qu'est un chatbot IA ?** C'est comme un assistant personnel à qui tu peux poser des questions en langage naturel. Les plus connus : [Claude](https://claude.ai) (par Anthropic — **recommandé**), [ChatGPT](https://chat.openai.com) (par OpenAI), [Gemini](https://gemini.google.com) (par Google).

**Exemples :**

| Ton besoin | Ce que tu écris |
|------------|----------------|
| Mettre en place un chatbot client | Je veux créer un chatbot IA pour le support client. Quelles sont les meilleures options open-source ? Lis https://tito-42.github.io/ARIA/CATALOG_SUMMARY.md |
| Choisir une base de données pour du RAG | Je monte un pipeline RAG. Compare les bases vectorielles. Lis https://tito-42.github.io/ARIA/CATALOG_SUMMARY.md |
| Automatiser le traitement de factures | Quels outils IA peuvent automatiser l'extraction de factures ? Lis https://tito-42.github.io/ARIA/CATALOG_SUMMARY.md |
| Trouver un outil de synthèse vocale | J'ai besoin d'un moteur text-to-speech open-source. Que recommandes-tu ? Lis https://tito-42.github.io/ARIA/CATALOG_SUMMARY.md |
| Automatiser le cold mailing | Quels outils open-source peuvent automatiser le cold emailing avec de l'IA ? Lis https://tito-42.github.io/ARIA/CATALOG_SUMMARY.md |

**C'est tout.** L'IA lit les fiches structurées, compare les outils, vérifie les licences, et te donne une recommandation — avec les scores de maturité, les alternatives, et comment démarrer.

> **Pourquoi c'est mieux que Google ?** Google te donne des articles d'opinion, souvent sponsorisés, souvent périmés. ARIA te donne des **fiches structurées, vérifiées et mises à jour quotidiennement** par des agents IA. GitHub Pages sert du Markdown brut — les LLMs le lisent directement sans se battre avec le rendu JavaScript. Réponses plus rapides, plus fiables, moins coûteuses en tokens.

> **Tutoriel complet pour débutants :** Si tu n'as jamais utilisé de chatbot IA, consulte le [guide pas-à-pas](guides/how-to-use-aria.fr.md) avec captures d'écran et explications détaillées.

### Naviguer directement sur GitHub

Chaque outil est un fichier Markdown que tu peux lire directement. Clique sur le dossier [`catalog/`](catalog/) et explore.

### Utiliser avec Claude Code (avancé)

```bash
git clone https://github.com/Tito-42/ARIA.git
cd ARIA
claude
```
Puis demande ce que tu veux :
```
> Quel est l'outil de code review IA le plus mature ?
> Compare Langfuse vs Helicone pour le monitoring LLM
> Quels processus métier peut-on automatiser à 80% avec l'IA ?
```

---

## Ce qu'il y a dedans

### 18 catégories, 323+ fiches

| | Catégorie | Fiches | Exemples |
|---|----------|:-------:|----------|
| 01 | **Génération de code** | 11 | Claude Code, Cursor, Gemini CLI, Aider, OpenHands |
| 02 | **Agents IA** | 35 | LangChain, CrewAI, AutoGPT, Dify, Browser Use |
| 03 | **Protocole MCP** | 17 | FastMCP, Playwright-MCP, GitHub-MCP, AWS-MCP |
| 04 | **Frontend / UI** | 9 | v0, Bolt, Lovable, Firebase Studio |
| 05 | **RAG & Connaissances** | 13 | Qdrant, ChromaDB, LlamaIndex, embeddings |
| 06 | **Fine-tuning** | 18 | Unsloth, Axolotl, TRL, PEFT, LLaMA-Factory |
| 07 | **Vision par ordinateur** | 24 | SAM2, Stable Diffusion, FLUX, ComfyUI, PaddleOCR |
| 08 | **NLP & Texte** | 20 | Instructor, Outlines, spaCy, HF Transformers |
| 09 | **Voix & Audio** | 22 | Whisper, Faster-Whisper, Kokoro TTS, LiveKit |
| 10 | **MLOps** | 24 | MLflow, vLLM, Ollama, Ray, W&B, Airflow |
| 11 | **Automatisation** | 8 | n8n, Skyvern, Activepieces, Temporal |
| 12 | **Enterprise** | 20 | Langfuse, Portkey, Kong AI Gateway, Infisical |
| 13 | **Benchmarks** | 7 | ARC-AGI, SWE-bench, Chatbot Arena |
| 14 | **LLMs Open Source** | 13 | Llama, Mistral, Qwen, DeepSeek, Phi |
| 15 | **Domaine & Métier** | 29 | Santé, Finance, Juridique, Cybersec, **Automatisation** |
| 16 | **Sécurité IA** | 15 | Promptfoo, Garak, NeMo Guardrails |
| 17 | **Multimodal** | 19 | LLaVA, Qwen-VL, Docling, MinerU, ImageBind |
| 18 | **Infrastructure** | 19 | llama.cpp, TensorRT-LLM, Flash Attention |

### Automatisation des processus métier

La catégorie la plus concrète : des outils open-source qui automatisent **aujourd'hui** des tâches business réelles.

| Outil | Ce qu'il automatise | Combien | Stars |
|-------|-------------------|:--------:|:-----:|
| [Firecrawl](catalog/15_domain_specific/business-automation/firecrawl.md) | Extraction de données web | ~90% | 103K |
| [Flowise](catalog/15_domain_specific/business-automation/flowise.md) | Création d'agents IA (visuel) | 70-90% | 51K |
| [MindsDB](catalog/15_domain_specific/business-automation/mindsdb.md) | Analytics IA sur données live | ~75% | 39K |
| [Chatwoot](catalog/15_domain_specific/business-automation/chatwoot.md) | Support client | 60-70% | 28K |
| [WrenAI](catalog/15_domain_specific/business-automation/wrenai.md) | Business intelligence (text-to-SQL) | ~80% | 15K |
| [PR-Agent](catalog/15_domain_specific/business-automation/pr-agent.md) | Code review | 70-80% | 11K |
| [GPT Researcher](catalog/15_domain_specific/business-automation/gpt-researcher.md) | Recherche automatique | ~85% | 10K+ |
| [Unstract](catalog/15_domain_specific/business-automation/unstract.md) | Traitement factures et contrats | 85-90% | 6.5K |

---

## Chaque fiche ressemble à ça

Chaque outil est documenté avec une structure cohérente pour t'aider à décider vite :

> **Metadata** — Stars GitHub, licence, prix, date de vérification, niveau de maturité
>
> **Ce que ça fait** — Explication en langage simple
>
> **Fonctionnalités clés** — Ce qui le distingue
>
> **Score Enterprise** — Note de 1 à 5 sur : Maturité, Sécurité, Scalabilité, Communauté, Documentation, Facilité d'intégration
>
> **Cas d'usage** — Scénarios concrets
>
> **Pour démarrer** — Commandes à copier-coller
>
> **Forces & Limites** — Évaluation honnête
>
> **Alternatives** — Ce qui existe d'autre et comment ça se compare

---

## Comment ça marche

### Le système multi-agents

ARIA n'est pas maintenu à la main. Il est maintenu par une équipe de **5 agents IA spécialisés**, chacun avec un rôle précis — comme une petite entreprise de recherche qui ne dort jamais.

<div align="center">
  <picture>
    <img alt="ARIA Pipeline Multi-Agents" src="assets/aria-pipeline.svg" width="800">
  </picture>
</div>

| Agent | Ce qu'il fait |
|-------|--------------|
| **Chercheur** | Parcourt GitHub Trending, Awesome Lists, HuggingFace, arXiv, Reddit, Hacker News, Product Hunt. Trouve les nouveaux outils et les tendances. |
| **Catalogeur** | Transforme les découvertes brutes en fiches structurées selon le template standard. |
| **Évaluateur** | Note chaque outil sur 6 dimensions : Maturité, Sécurité, Scalabilité, Communauté, Documentation, Intégration. |
| **Veilleur** | Lance le script de vérification de versions sur 200+ repos GitHub. Détecte les nouvelles releases, les changements de stars, les projets archivés. |
| **Architecte** | Pour un besoin donné ("J'ai besoin d'un pipeline RAG pour des documents juridiques"), recommande la meilleure combinaison d'outils du catalogue. |

### Le script de veille

Un script léger qui maintient le catalogue à jour. Il vérifie chaque repo GitHub et signale ce qui a changé — pour que les agents ne perdent pas de temps à re-rechercher des outils qui n'ont pas bougé.

Ce qu'il détecte :
- Nouvelles releases et changements de version
- Variations significatives du nombre de stars
- Projets archivés ou abandonnés
- Repos récemment actifs (push < 7 jours)

Il gère automatiquement les limites de l'API GitHub — s'il atteint la limite, il attend et reprend. Conçu pour tourner sans surveillance sur un serveur.

### D'où viennent les données

| Niveau | Sources |
|--------|---------|
| **Primaire** | GitHub Trending, Awesome Lists, HuggingFace, Papers with Code |
| **Communauté** | Reddit (r/LocalLLaMA, r/MachineLearning), Hacker News, Product Hunt |
| **Recherche** | arXiv, LabLab.ai, Devpost, LMSys Chatbot Arena |

### Barre de qualité

Tout n'entre pas dans ARIA :
- **Open source de préférence** (code source disponible au minimum)
- **Activement maintenu** (commits dans les 6 derniers mois)
- **Traction réelle** (500+ stars GitHub, ou valeur unique dans sa niche)
- **Liens vérifiés** (toutes les URLs testées avant catalogage)
- **Notation honnête** (forces ET limites documentées)

---

## En chiffres

| | |
|---|---|
| Fiches catalogue | **323+** |
| Catégories | **18** |
| Repos GitHub surveillés | **200+** |
| Agents IA | **5** |
| Fréquence de MAJ | **Quotidienne** (23h-7h CET) |
| Dernière MAJ | **Avril 2026** |

---

## Contribuer

ARIA est open source. Si tu trouves un outil manquant, une fiche périmée, ou une catégorie à compléter — les contributions sont les bienvenues.

**Ajouter un outil :**
1. Copie le template depuis `catalog/_schema/template-tool.md`
2. Remplis toutes les sections (metadata, fonctionnalités, score enterprise, etc.)
3. Place-le dans le bon dossier de catégorie
4. Ouvre une Pull Request

**Signaler un problème :**
Lien cassé ? Info fausse ? Version périmée ? Ouvre une issue.

---

## Structure du projet

```
ARIA/
  catalog/            323+ fiches structurees dans 18 categories
  research/raw/       Decouvertes brutes des agents chercheurs
  guides/             Tutoriels, frameworks de decision, blueprints
  state/              Suivi de progression, snapshots de versions
  .claude/agents/     Definitions des agents
```

---

<div align="center">

### Arrêtez de googler. Commencez à interroger.

L'écosystème IA va trop vite pour la recherche manuelle.<br/>
Laissez les agents faire le travail. Vous, prenez les décisions.

---

**[Licence MIT](LICENSE)** | Construit avec [Claude Code](https://claude.ai/code) | Maintenu par des agents IA

*Créé par [Tito_42](https://github.com/Tito-42)*

</div>
