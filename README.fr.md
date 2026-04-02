<div align="center">

**[English](README.md)** | **[Francais](#pourquoi-aria-existe)** | **[Espanol](README.es.md)** | **[Guide debutant](guides/how-to-use-aria.md)**

<br/>

<picture>
  <img alt="ARIA — Advanced Research in Artificial Intelligence" src="assets/aria-header.svg">
</picture>

<br/>

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Entries](https://img.shields.io/badge/Fiches-323+-blue)]()
[![Categories](https://img.shields.io/badge/Categories-18-green)]()
[![Updated](https://img.shields.io/badge/Derniere_MAJ-Avril_2026-brightgreen)]()
[![Agents](https://img.shields.io/badge/Maintenu_par-Agents_IA-purple)]()

[**Comment l'utiliser**](#comment-utiliser-aria) | [**Le catalogue**](#ce-quil-y-a-dedans) | [**Comment ca marche**](#comment-ca-marche) | [**Contribuer**](#contribuer)

</div>

---

## Pourquoi ARIA existe

Le monde de l'IA a trouve son accelerateur. De nouveaux outils, modeles et frameworks sortent **chaque jour**. Ce qui etait "le meilleur choix" la semaine derniere est deja depasse. Et chercher a l'ancienne — taper des mots-cles dans Google, scroller des articles de blog SEO ecrits en 2024 — c'est deja obsolete.

Le temps que tu trouves, compares et evalues un outil, trois nouvelles alternatives ont deja ete publiees.

**ARIA a ete construit pour resoudre ce probleme.**

C'est une base de connaissances vivante de l'ecosysteme IA — 323 outils repartis dans 18 categories — ou chaque entree est structuree, notee et verifiee. Mais le plus important : **ARIA ne depend pas d'humains pour rester a jour.** Une equipe de 5 agents IA specialises travaille chaque nuit pour parcourir le web, trouver les nouveautes, verifier ce qui a change, et mettre a jour le catalogue automatiquement.

Tu te reveilles le matin. La base est a jour. Tu poses une question. Tu obtiens une reponse.

> *"Le goulot d'etranglement n'est plus l'intelligence — c'est de savoir ce qui existe."*

---

## Comment utiliser ARIA

### La methode la plus simple : demander a Claude (recommande)

Pas besoin d'etre technique. Pas besoin d'installer quoi que ce soit. Ouvre [claude.ai](https://claude.ai) (gratuit) et colle ta question avec l'URL du catalogue. Claude lit du Markdown brut via GitHub Pages et cite les outils avec leurs scores enterprise exacts.

> **Pourquoi Claude ?** Apres plusieurs benchmarks, Claude est le seul LLM gratuit qui lit reellement le catalogue, cite les vrais outils avec les scores, et n'hallucine pas. ChatGPT et Gemini (gratuits) n'arrivent pas a lire l'URL et repondent avec leurs propres connaissances generiques. Voir le [benchmark complet](BENCHMARK_LLM.md).

> **Tu ne sais pas ce qu'est un chatbot IA ?** C'est comme un assistant personnel a qui tu peux poser des questions en langage naturel. Les plus connus : [Claude](https://claude.ai) (par Anthropic — **recommande**), [ChatGPT](https://chat.openai.com) (par OpenAI), [Gemini](https://gemini.google.com) (par Google).

**Exemples :**

| Ton besoin | Ce que tu ecris |
|------------|----------------|
| Mettre en place un chatbot client | Je veux creer un chatbot IA pour le support client. Quelles sont les meilleures options open-source ? Lis https://tito-42.github.io/ARIA/CATALOG_SUMMARY.md |
| Choisir une base de donnees pour du RAG | Je monte un pipeline RAG. Compare les bases vectorielles. Lis https://tito-42.github.io/ARIA/CATALOG_SUMMARY.md |
| Automatiser le traitement de factures | Quels outils IA peuvent automatiser l'extraction de factures ? Lis https://tito-42.github.io/ARIA/CATALOG_SUMMARY.md |
| Trouver un outil de synthese vocale | J'ai besoin d'un moteur text-to-speech open-source. Que recommandes-tu ? Lis https://tito-42.github.io/ARIA/CATALOG_SUMMARY.md |
| Automatiser le cold mailing | Quels outils open-source peuvent automatiser le cold emailing avec de l'IA ? Lis https://tito-42.github.io/ARIA/CATALOG_SUMMARY.md |

**C'est tout.** L'IA lit les fiches structurees, compare les outils, verifie les licences, et te donne une recommandation — avec les scores de maturite, les alternatives, et comment demarrer.

> **Pourquoi c'est mieux que Google ?** Google te donne des articles d'opinion, souvent sponsorises, souvent perimes. ARIA te donne des **fiches structurees, verifiees et mises a jour quotidiennement** par des agents IA. GitHub Pages sert du Markdown brut — les LLMs le lisent directement sans se battre avec le rendu JavaScript. Reponses plus rapides, plus fiables, moins couteuses en tokens.

> **Tutoriel complet pour debutants :** Si tu n'as jamais utilise de chatbot IA, consulte le [guide pas-a-pas](guides/how-to-use-aria.md) avec captures d'ecran et explications detaillees.

### Naviguer directement sur GitHub

Chaque outil est un fichier Markdown que tu peux lire directement. Clique sur le dossier [`catalog/`](catalog/) et explore.

### Utiliser avec Claude Code (avance)

```bash
git clone https://github.com/Tito-42/ARIA.git
cd ARIA
claude
```
Puis demande ce que tu veux :
```
> Quel est l'outil de code review IA le plus mature ?
> Compare Langfuse vs Helicone pour le monitoring LLM
> Quels processus metier peut-on automatiser a 80% avec l'IA ?
```

---

## Ce qu'il y a dedans

### 18 categories, 323+ fiches

| | Categorie | Fiches | Exemples |
|---|----------|:-------:|----------|
| 01 | **Generation de code** | 11 | Claude Code, Cursor, Gemini CLI, Aider, OpenHands |
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
| 15 | **Domaine & Metier** | 29 | Sante, Finance, Juridique, Cybersec, **Automatisation** |
| 16 | **Securite IA** | 15 | Promptfoo, Garak, NeMo Guardrails |
| 17 | **Multimodal** | 19 | LLaVA, Qwen-VL, Docling, MinerU, ImageBind |
| 18 | **Infrastructure** | 19 | llama.cpp, TensorRT-LLM, Flash Attention |

### Automatisation des processus metier

La categorie la plus concrete : des outils open-source qui automatisent **aujourd'hui** des taches business reelles.

| Outil | Ce qu'il automatise | Combien | Stars |
|-------|-------------------|:--------:|:-----:|
| [Firecrawl](catalog/15_domain_specific/business-automation/firecrawl.md) | Extraction de donnees web | ~90% | 103K |
| [Flowise](catalog/15_domain_specific/business-automation/flowise.md) | Creation d'agents IA (visuel) | 70-90% | 51K |
| [MindsDB](catalog/15_domain_specific/business-automation/mindsdb.md) | Analytics IA sur donnees live | ~75% | 39K |
| [Chatwoot](catalog/15_domain_specific/business-automation/chatwoot.md) | Support client | 60-70% | 28K |
| [WrenAI](catalog/15_domain_specific/business-automation/wrenai.md) | Business intelligence (text-to-SQL) | ~80% | 15K |
| [PR-Agent](catalog/15_domain_specific/business-automation/pr-agent.md) | Code review | 70-80% | 11K |
| [GPT Researcher](catalog/15_domain_specific/business-automation/gpt-researcher.md) | Recherche automatique | ~85% | 10K+ |
| [Unstract](catalog/15_domain_specific/business-automation/unstract.md) | Traitement factures et contrats | 85-90% | 6.5K |

---

## Chaque fiche ressemble a ca

Chaque outil est documente avec une structure coherente pour t'aider a decider vite :

> **Metadata** — Stars GitHub, licence, prix, date de verification, niveau de maturite
>
> **Ce que ca fait** — Explication en langage simple
>
> **Fonctionnalites cles** — Ce qui le distingue
>
> **Score Enterprise** — Note de 1 a 5 sur : Maturite, Securite, Scalabilite, Communaute, Documentation, Facilite d'integration
>
> **Cas d'usage** — Scenarios concrets
>
> **Pour demarrer** — Commandes a copier-coller
>
> **Forces & Limites** — Evaluation honnete
>
> **Alternatives** — Ce qui existe d'autre et comment ca se compare

---

## Comment ca marche

### Le systeme multi-agents

ARIA n'est pas maintenu a la main. Il est maintenu par une equipe de **5 agents IA specialises**, chacun avec un role precis — comme une petite entreprise de recherche qui ne dort jamais.

<div align="center">
  <picture>
    <img alt="ARIA Pipeline Multi-Agents" src="assets/aria-pipeline.svg" width="800">
  </picture>
</div>

| Agent | Ce qu'il fait |
|-------|--------------|
| **Chercheur** | Parcourt GitHub Trending, Awesome Lists, HuggingFace, arXiv, Reddit, Hacker News, Product Hunt. Trouve les nouveaux outils et les tendances. |
| **Catalogeur** | Transforme les decouvertes brutes en fiches structurees selon le template standard. |
| **Evaluateur** | Note chaque outil sur 6 dimensions : Maturite, Securite, Scalabilite, Communaute, Documentation, Integration. |
| **Veilleur** | Lance le script de verification de versions sur 200+ repos GitHub. Detecte les nouvelles releases, les changements de stars, les projets archives. |
| **Architecte** | Pour un besoin donne ("J'ai besoin d'un pipeline RAG pour des documents juridiques"), recommande la meilleure combinaison d'outils du catalogue. |

### Le script de veille

Un script leger qui maintient le catalogue a jour. Il verifie chaque repo GitHub et signale ce qui a change — pour que les agents ne perdent pas de temps a re-rechercher des outils qui n'ont pas bouge.

Ce qu'il detecte :
- Nouvelles releases et changements de version
- Variations significatives du nombre de stars
- Projets archives ou abandonnes
- Repos recemment actifs (push < 7 jours)

Il gere automatiquement les limites de l'API GitHub — s'il atteint la limite, il attend et reprend. Concu pour tourner sans surveillance sur un serveur.

### D'ou viennent les donnees

| Niveau | Sources |
|--------|---------|
| **Primaire** | GitHub Trending, Awesome Lists, HuggingFace, Papers with Code |
| **Communaute** | Reddit (r/LocalLLaMA, r/MachineLearning), Hacker News, Product Hunt |
| **Recherche** | arXiv, LabLab.ai, Devpost, LMSys Chatbot Arena |

### Barre de qualite

Tout n'entre pas dans ARIA :
- **Open source de preference** (code source disponible au minimum)
- **Activement maintenu** (commits dans les 6 derniers mois)
- **Traction reelle** (500+ stars GitHub, ou valeur unique dans sa niche)
- **Liens verifies** (toutes les URLs testees avant catalogage)
- **Notation honnete** (forces ET limites documentees)

---

## En chiffres

| | |
|---|---|
| Fiches catalogue | **323+** |
| Categories | **18** |
| Repos GitHub surveilles | **200+** |
| Agents IA | **5** |
| Frequence de MAJ | **Quotidienne** (23h-7h CET) |
| Derniere MAJ | **Avril 2026** |

---

## Contribuer

ARIA est open source. Si tu trouves un outil manquant, une fiche perimee, ou une categorie a completer — les contributions sont les bienvenues.

**Ajouter un outil :**
1. Copie le template depuis `catalog/_schema/template-tool.md`
2. Remplis toutes les sections (metadata, fonctionnalites, score enterprise, etc.)
3. Place-le dans le bon dossier de categorie
4. Ouvre une Pull Request

**Signaler un probleme :**
Lien casse ? Info fausse ? Version perimee ? Ouvre une issue.

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

### Arretez de googler. Commencez a interroger.

L'ecosysteme IA va trop vite pour la recherche manuelle.<br/>
Laissez les agents faire le travail. Vous, prenez les decisions.

---

**[Licence MIT](LICENSE)** | Construit avec [Claude Code](https://claude.ai/code) | Maintenu par des agents IA

*Cree par [Tito_42](https://github.com/Tito-42)*

</div>
