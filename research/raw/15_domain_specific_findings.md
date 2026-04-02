# Domain-Specific AI Tools - Research Findings
**Date de recherche**: 2026-04-02
**Categorie**: 15_domain_specific
**Sources**: GitHub topics, GitHub search, Hugging Face, WebFetch direct

---

## HEALTHCARE / MEDICAL

---

### MONAI - Medical Open Network for AI

- **URL**: https://monai.io
- **GitHub**: https://github.com/Project-MONAI/MONAI
- **Stars**: ~8,000
- **Licence**: Apache 2.0
- **Source de decouverte**: GitHub topics/medical-imaging
- **Date de recherche**: 2026-04-02
- **Categorie suggeree**: 15_domain_specific / healthcare
- **Domaine metier**: Imagerie medicale (radiology, pathology, ophthalmology)
- **Description**: Framework PyTorch open-source pour le deep learning en imagerie medicale. Fournit des composants modulaires pour le preprocessing, l'entrainement et l'evaluation sur des modalites DICOM/NIfTI (CT, MRI, PET).
- **Ce que ca fait**: Pre-processing de donnees d'imagerie medicale multi-dimensionnelle, entrainement de modeles de segmentation/classification/detection, integration avec des workflows cliniques.
- **Maturite**: Production - version 1.5.2 (Jan 2026), activement maintenu par NVIDIA et la communaute PyTorch
- **Dernier commit**: Janvier 2026
- **Pourquoi c'est pertinent**: Reference de l'industrie pour l'IA en imagerie medicale. Supporte GPU multi-noeuds. Utilise dans des hopitaux et par des chercheurs cliniques. Partie de l'ecosysteme PyTorch officiel.

---

### MedSAM - Segment Anything in Medical Images

- **URL**: https://github.com/bowang-lab/MedSAM
- **GitHub**: https://github.com/bowang-lab/MedSAM
- **Stars**: ~4,200
- **Licence**: Apache 2.0
- **Source de decouverte**: GitHub topics/medical-imaging
- **Date de recherche**: 2026-04-02
- **Categorie suggeree**: 15_domain_specific / healthcare
- **Domaine metier**: Imagerie medicale - segmentation
- **Description**: Adaptation du modele SAM (Segment Anything de Meta) specifiquement entraine sur des images medicales. Supporte CT, MRI et d'autres modalites avec ajustement automatique des niveaux de fenetrage.
- **Ce que ca fait**: Segmentation interactive de structures anatomiques par boite englobante, utilisable en CLI, notebook Jupyter ou GUI PyQt5. Inclut LiteMedSAM (10x plus rapide) et un plugin 3D Slicer.
- **Maturite**: Beta/Research - dernier commit septembre 2024
- **Pourquoi c'est pertinent**: Comble le gap entre SAM generique et les besoins medicaux specifiques. Le plugin 3D Slicer facilite l'adoption clinique. Tres cite dans la litterature.

---

### MedicalGPT - Training Medical LLMs

- **URL**: https://github.com/shibing624/MedicalGPT
- **GitHub**: https://github.com/shibing624/MedicalGPT
- **Stars**: ~5,200
- **Licence**: Apache 2.0
- **Source de decouverte**: GitHub search medical LLM
- **Date de recherche**: 2026-04-02
- **Categorie suggeree**: 15_domain_specific / healthcare
- **Domaine metier**: Medical NLP, clinical LLM training
- **Description**: Pipeline complet pour entrainer des modeles LLM medicaux a la maniere ChatGPT. Supporte incremental pretraining, SFT, RLHF, DPO, ORPO, GRPO. Base sur 2.4 millions d'exemples medicaux chinois.
- **Ce que ca fait**: Entraine des LLMs medicaux multi-etapes sur Llama, Qwen, Baichuan, ChatGLM. Inclut un module RAG (ChatPDF) pour QA sur dossiers patients. v2.4 (Avril 2025) ajoute GRPO.
- **Maturite**: Production - actif jusqu'en avril 2025
- **Pourquoi c'est pertinent**: Pipeline le plus complet pour creer des LLMs medicaux custom. Particulierement adapte au marche chinois mais generalisable.

---

### Meditron - Medical LLM (EPFL)

- **URL**: https://github.com/epfLLM/meditron
- **GitHub**: https://github.com/epfLLM/meditron
- **Stars**: ~2,200
- **Licence**: Apache 2.0 (code) / Llama 2 Community (modeles)
- **Source de decouverte**: GitHub search medical LLM
- **Date de recherche**: 2026-04-02
- **Categorie suggeree**: 15_domain_specific / healthcare
- **Domaine metier**: Medical LLM, clinical decision support
- **Description**: Suite de LLMs medicaux open-source de l'EPFL (7B et 70B). Adaptes depuis Llama-2 via pretraining specialise sur 48.1B tokens de guidelines cliniques, PubMed, et corpus general.
- **Ce que ca fait**: QA sur examens medicaux, support au diagnostic differentiel, information sur les pathologies. Meditron-70B surpasse GPT-3.5 et Flan-PaLM sur les benchmarks medicaux.
- **Maturite**: Research - publication Nov 2023, pas de mise a jour depuis
- **Pourquoi c'est pertinent**: Modele academique de reference avec validation rigoureuse sur benchmarks (MedQA, MedMCQA, PubMedQA). Bon point de depart pour fine-tuning clinique.
- **Note**: Modele statique, non mis a jour depuis 2023. A privilegier comme base de fine-tuning plutot qu'en production directe.

---

### BioGPT - Biomedical Text Generation (Microsoft)

- **URL**: https://github.com/microsoft/BioGPT
- **GitHub**: https://github.com/microsoft/BioGPT
- **Stars**: ~4,500
- **Licence**: MIT
- **Source de decouverte**: GitHub search medical LLM
- **Date de recherche**: 2026-04-02
- **Categorie suggeree**: 15_domain_specific / healthcare
- **Domaine metier**: Biomedical NLP, literature mining
- **Description**: Transformeur generatif pre-entraine de Microsoft specialise en texte biomedical. Entraine sur la litterature scientifique PubMed et disponible en variantes standard et Large.
- **Ce que ca fait**: Extraction de relations (interactions medicament-maladie), question-answering sur litterature medicale, classification de documents biomedicaux. Integre dans Hugging Face transformers.
- **Maturite**: Research - dernier commit aout 2022, mais integre dans HF (maintenu)
- **Pourquoi c'est pertinent**: Modele de reference academique de Microsoft. Bonne base pour des taches NLP biomedicales specifiques (extraction d'information, mining de litterature).

---

### BioMistral - Medical LLM Multilingue

- **URL**: https://huggingface.co/BioMistral
- **GitHub**: https://github.com/BioMistral/BioMistral
- **Stars**: ~53
- **Licence**: Apache 2.0 (a verifier selon variante)
- **Source de decouverte**: Recherche directe
- **Date de recherche**: 2026-04-02
- **Categorie suggeree**: 15_domain_specific / healthcare
- **Domaine metier**: Medical LLM, multilingual clinical AI
- **Description**: LLM medical open-source base sur Mistral, pre-entraine sur PubMed Central par des institutions academiques francaises. Notable pour son evaluation multilingueet ses variantes quantifiees (AWQ, 4-bit, 8-bit).
- **Ce que ca fait**: QA medicale multilingue (8 langues), inference avec 15GB VRAM ou 4.68GB en quantifie. Evaluation sur 10 benchmarks medicaux surpassant les modeles medicaux open-source concurrents.
- **Maturite**: Research - juin 2024
- **Pourquoi c'est pertinent**: Premier modele avec evaluation multilinguescale en medecine. Adapte pour des deployments europeens (RGPD) avec support francais natif. Variantes quantifiees accessibles sur GPU modeste.

---

### DeepChem - Drug Discovery & Molecular AI

- **URL**: https://deepchem.io
- **GitHub**: https://github.com/deepchem/deepchem
- **Stars**: ~6,700
- **Licence**: MIT
- **Source de decouverte**: GitHub topics/drug-discovery
- **Date de recherche**: 2026-04-02
- **Categorie suggeree**: 15_domain_specific / healthcare / drug-discovery
- **Domaine metier**: Drug discovery, computational chemistry, materials science
- **Description**: Toolchain open-source democratisant le deep learning pour la decouverte de medicaments, la chimie quantique et la biologie moleculaire. Supporte TensorFlow, PyTorch et JAX.
- **Ce que ca fait**: Prediction de proprietes moleculaires, processing de structures chimiques avec RDKit, modeles pour QSAR, toxicologie, et drug-target interactions. Version 2.8.0 (Avril 2024).
- **Maturite**: Production - 10,659 commits, release reguliere
- **Pourquoi c'est pertinent**: Reference de l'industrie pharma pour l'IA moleculaire. Utilisee dans de vraies pipelines de R&D. Tutorials Google Colab accessibles. MIT license pour usage commercial.

---

### Chemprop - Molecular Property Prediction

- **URL**: https://chemprop.readthedocs.io
- **GitHub**: https://github.com/chemprop/chemprop
- **Stars**: ~2,300
- **Licence**: MIT
- **Source de decouverte**: GitHub topics/drug-discovery
- **Date de recherche**: 2026-04-02
- **Categorie suggeree**: 15_domain_specific / healthcare / drug-discovery
- **Domaine metier**: Drug discovery, cheminformatics
- **Description**: Reseaux de neurones a passage de messages (MPNN) pour la prediction de proprietes moleculaires. Outil standard en cheminformatique computationnelle.
- **Ce que ca fait**: Prediction multi-tache de proprietes chimiques, prediction de reactions, interpretabilite au niveau atomique/liaison. A identifie la Halicin (antibiotique novel) en recherche publiee. Alimente ADMET-AI.
- **Maturite**: Production - version 2.2.3 (Mars 2026), activement maintenu
- **Pourquoi c'est pertinent**: Dernier commit Mars 2026 - tres actif. Valide en production reelle (decouverte d'antibiotiques). Standard dans l'industrie pharma et la recherche computationnelle.

---

## FINANCE

---

### FinGPT - Open Source Financial LLM

- **URL**: https://github.com/AI4Finance-Foundation/FinGPT
- **GitHub**: https://github.com/AI4Finance-Foundation/FinGPT
- **Stars**: ~19,000
- **Licence**: MIT
- **Source de decouverte**: Recherche directe AI4Finance Foundation
- **Date de recherche**: 2026-04-02
- **Categorie suggeree**: 15_domain_specific / finance
- **Domaine metier**: Finance - analyse de sentiment, prevision, NLP financier
- **Description**: LLM financier open-source de l'AI4Finance Foundation. Alternative democratique a BloombergGPT, permettant un fine-tuning a moins de 300$ sur des donnees de marche et actualites financieres.
- **Ce que ca fait**: Analyse de sentiment sur actualites financieres, extraction de relations, classification de titres, prediction de prix (FinGPT-Forecaster). Supporte Llama-2, Falcon, ChatGLM2.
- **Maturite**: Production/Research - activement maintenu
- **Pourquoi c'est pertinent**: 19k stars, reference en finance AI open-source. Ecosysteme complet avec datasets, modeles et benchmarks. Utilisable pour des applications de trading et d'analyse financiere a moindre cout.

---

### FinRL - Financial Reinforcement Learning

- **URL**: https://github.com/AI4Finance-Foundation/FinRL
- **GitHub**: https://github.com/AI4Finance-Foundation/FinRL
- **Stars**: ~14,600
- **Licence**: MIT
- **Source de decouverte**: Recherche directe AI4Finance Foundation
- **Date de recherche**: 2026-04-02
- **Categorie suggeree**: 15_domain_specific / finance
- **Domaine metier**: Finance - trading algorithmique, optimisation de portefeuille
- **Description**: Premier framework open-source de reinforcement learning financier. Pipeline complet pour entrainer, tester et deployer des agents DRL pour le trading quantitatif.
- **Ce que ca fait**: Agents DRL (A2C, DDPG, PPO, TD3, SAC) sur 14+ sources de donnees (Yahoo Finance, Alpaca, Binance). Pipeline train-test-trade, indicateurs techniques MACD/RSI, optimisation MVO.
- **Maturite**: Production - 3,242 commits, activement maintenu
- **Pourquoi c'est pertinent**: Framework de reference academique et pratique pour le trading DRL. 14.6k stars. Nombreux tutoriels et publications associees. Pour production, voir FinRL-Trading.

---

### FinRobot - AI Agent Platform for Finance

- **URL**: https://github.com/AI4Finance-Foundation/FinRobot
- **GitHub**: https://github.com/AI4Finance-Foundation/FinRobot
- **Stars**: ~6,500
- **Licence**: Apache 2.0
- **Source de decouverte**: AI4Finance Foundation org page
- **Date de recherche**: 2026-04-02
- **Categorie suggeree**: 15_domain_specific / finance
- **Domaine metier**: Finance - analyse d'actions, rapports d'investissement
- **Description**: Plateforme d'agents IA pour l'analyse financiere. Unifie LLMs, RL et analytique quantitative pour automatiser la recherche en investissement et generer des rapports d'equity research.
- **Ce que ca fait**: Generation automatique de rapports d'analyse financiere, integration de donnees (FMP, Finnhub, SEC), calcul de valorisation (P/E, EV/EBITDA), agents specialises multi-modeles (NVDA, MSFT, TSLA).
- **Maturite**: Beta/Production - Apache 2.0, 312 commits
- **Pourquoi c'est pertinent**: Cas d'usage enterprise concret : automatiser la production de rapports d'analyse financiere. Multi-agent avec "Smart Scheduler" pour selectionner le meilleur LLM par tache.

---

## LEGAL / JURIDIQUE

---

### LegalBench - Legal Reasoning Benchmark

- **URL**: https://hazyresearch.stanford.edu/legalbench/
- **GitHub**: https://github.com/HazyResearch/legalbench
- **Stars**: ~562
- **Licence**: Mixed (par dataset)
- **Source de decouverte**: Recherche directe benchmarks legaux
- **Date de recherche**: 2026-04-02
- **Categorie suggeree**: 15_domain_specific / legal
- **Domaine metier**: Legal AI - evaluation et benchmark
- **Description**: Effort scientifique collaboratif pour evaluer le raisonnement juridique des LLMs en anglais. 162 taches contribuees par 40 experts (avocats, professeurs, praticiens du droit).
- **Ce que ca fait**: Benchmark couvrant: classification hearsay, extraction de definitions, QA base sur regles, analyse de contrats. Compatible avec HELM et vals.ai. Disponible sur Hugging Face.
- **Maturite**: Research - paper arXiv:2308.11462
- **Pourquoi c'est pertinent**: Reference academique pour evaluer les capacites juridiques des LLMs. Essentiel pour valider un modele avant deploiement dans un contexte legal. Contribue par de vrais praticiens du droit.

---

### LexGLUE - Legal NLP Benchmark Suite

- **URL**: https://github.com/coastalcph/lex-glue
- **GitHub**: https://github.com/coastalcph/lex-glue
- **Stars**: ~246
- **Licence**: Non specifiee
- **Source de decouverte**: Recherche directe benchmarks legaux
- **Date de recherche**: 2026-04-02
- **Categorie suggeree**: 15_domain_specific / legal
- **Domaine metier**: Legal NLP - evaluation multi-tache
- **Description**: Benchmark multi-tache pour evaluer les methodes NLP sur la comprehension du langage juridique. Unifie 7 datasets existants couvrant differents domaines juridiques (droits de l'homme, Cour Supreme US, legislation EU, contrats).
- **Ce que ca fait**: Classification multi-label/multi-classe, QA a choix multiples sur textes juridiques. Integre ECtHR, SCOTUS, EUR-LEX, LEDGAR, UNFAIR-ToS, CaseHOLD. API Hugging Face disponible.
- **Maturite**: Research - reference academique etablie
- **Pourquoi c'est pertinent**: Le "GLUE du droit". Reference pour comparer Legal-BERT vs RoBERTa vs autres transformers sur des taches juridiques reelles.

---

### Awesome Legal NLP - Ressources Curees

- **URL**: https://github.com/maastrichtlawtech/awesome-legal-nlp
- **GitHub**: https://github.com/maastrichtlawtech/awesome-legal-nlp
- **Stars**: ~313
- **Licence**: N/A (liste curee)
- **Source de decouverte**: GitHub topics/legal-ai
- **Date de recherche**: 2026-04-02
- **Categorie suggeree**: 15_domain_specific / legal
- **Domaine metier**: Legal NLP - ressources et outils
- **Description**: Liste curee de ressources LegalNLP de partout sur le web. Point d'entree unique pour les datasets, modeles, papiers et outils de traitement du langage juridique.
- **Ce que ca fait**: Repertorie modeles (Legal-BERT, CamemBERT-legal), datasets (ContractNLI, ECHR, CUAD), benchmarks, et outils de parsing de documents juridiques.
- **Maturite**: Ressource de reference
- **Pourquoi c'est pertinent**: Roadmap complete pour construire des solutions de legal AI. Reference pour identifier les datasets de fine-tuning et les modeles de base adaptes au juridique.

---

### CUAD - Contract Understanding Atticus Dataset

- **URL**: https://www.atticusprojectai.org/cuad
- **GitHub**: https://github.com/TheAtticusProject/cuad
- **Stars**: ~400 (repo principal)
- **Licence**: CC BY 4.0
- **Source de decouverte**: Recherche legal NLP
- **Date de recherche**: 2026-04-02
- **Categorie suggeree**: 15_domain_specific / legal
- **Domaine metier**: Legal AI - analyse de contrats
- **Description**: Dataset de reference pour la comprehension de contrats. 500 contrats commerciaux avec 13,000+ annotations couvrant 41 types de clauses par des avocats professionnels.
- **Ce que ca fait**: Dataset pour QA extractive sur contrats (NDA, contrats de service, accords de licence). Permet d'entrainer des modeles de detection de clauses specifiques (indemnisation, resiliation, propriete intellectuelle).
- **Maturite**: Production dataset - reference academique (NeurIPS 2021)
- **Pourquoi c'est pertinent**: Dataset de qualite professionnelle annoté par de vrais avocats. Standard de l'industrie pour evaluer les modeles d'analyse contractuelle. CC BY 4.0 = usage commercial permis.

---

## EDUCATION

---

### Mr. Ranedeer AI Tutor

- **URL**: https://github.com/JushBJJ/Mr.-Ranedeer-AI-Tutor
- **GitHub**: https://github.com/JushBJJ/Mr.-Ranedeer-AI-Tutor
- **Stars**: ~29,700
- **Licence**: Non specifiee (prompt open-source)
- **Source de decouverte**: GitHub search AI tutor
- **Date de recherche**: 2026-04-02
- **Categorie suggeree**: 15_domain_specific / education
- **Domaine metier**: Education - tuteur AI personalise
- **Description**: Prompt sophistique pour GPT-4 creant un tuteur AI hautement personnalisable. Ajuste le niveau de connaissance (elementaire a PhD), le style d'apprentissage, le ton et le cadre de raisonnement.
- **Ce que ca fait**: Cours adaptatifs, tests d'evaluation (/test), planification de lecons (/plan), support multilingue. Convient pour mathematiques, programmation, sciences, langues.
- **Maturite**: Production - v2.7 (Nov 2023), 29.7k stars
- **Note**: Necessite ChatGPT Plus avec GPT-4. N'est pas un logiciel deployable en standalone mais un meta-prompt puissant.
- **Pourquoi c'est pertinent**: Approche la plus populaire pour construire un tuteur AI sans coder. Methodology reproductible pour creer des experiences d'apprentissage personnalisees avec n'importe quel LLM puissant.

---

### Tutor-GPT - AI Tutor with Theory of Mind

- **URL**: https://bloomingmath.com
- **GitHub**: https://github.com/plastic-labs/tutor-gpt
- **Stars**: ~892
- **Licence**: GPL-3.0
- **Source de decouverte**: GitHub search AI tutor education
- **Date de recherche**: 2026-04-02
- **Categorie suggeree**: 15_domain_specific / education
- **Domaine metier**: Education - tuteur AI adaptatif
- **Description**: Compagnon d'apprentissage LLM qui adapte dynamiquement ses propres prompts via du raisonnement "Theory of Mind". Deploye en production sous le nom "Bloom" (reference au probleme Two Sigma de Benjamin Bloom).
- **Ce que ca fait**: Apprentissage personnalise, auto-amelioration des prompts selon la comprehension du learner, support OCR de documents (Mistral OCR), modelisation de l'utilisateur via Honcho.
- **Maturite**: Beta/Production - dernier commit Fevrier 2026, actif
- **Pourquoi c'est pertinent**: Approche theoriquement fondee (Theory of Mind) et activement maintenue. GPL-3.0 avec hebergement possible en local. Architecture interessante pour des plateformes EdTech.

---

### ChatTutor - Visual Interactive AI Teacher

- **URL**: https://chattutor.app
- **GitHub**: https://github.com/HugeCatLab/ChatTutor
- **Stars**: ~987
- **Licence**: AGPL-3.0
- **Source de decouverte**: GitHub search AI tutor education
- **Date de recherche**: 2026-04-02
- **Categorie suggeree**: 15_domain_specific / education
- **Domaine metier**: Education - tuteur visuel STEM
- **Description**: Professeur AI equipe d'un tableau blanc interactif. Adresse la limitation du texte seul pour l'enseignement des matieres STEM avec canvas mathematique et generation de mindmaps.
- **Ce que ca fait**: Enseignement interactif avec canvas math, generation de mindmaps conceptuels, support multi-modeles (OpenAI, Anthropic, DeepSeek), interface web accessible.
- **Maturite**: Beta/Production - dernier commit Janvier 2026, actif
- **Pourquoi c'est pertinent**: Differentie par l'aspect visuel/interactif. Utile pour des plateformes d'enseignement des mathematiques ou des sciences. AGPL-3.0.

---

## CYBERSECURITE (complement de soc-ai)

---

### Strix - AI Vulnerability Discovery

- **URL**: https://usestrix.com
- **GitHub**: https://github.com/usestrix/strix
- **Stars**: ~23,000
- **Licence**: Apache 2.0
- **Source de decouverte**: GitHub search cybersecurity LLM
- **Date de recherche**: 2026-04-02
- **Categorie suggeree**: 15_domain_specific / cybersecurity
- **Domaine metier**: Cybersecurite - pentest, vulnerability discovery
- **Description**: Agents IA offensifs open-source qui trouvent et valident les vulnerabilites applicatives comme de vrais hackers. Execution dynamique du code, validation avec preuves de concept (PoC).
- **Ce que ca fait**: Detection IDOR, SQLi, XSS, SSRF, CSRF, privilege escalation, business logic flaws. Integration GitHub Actions CI/CD. Pas de faux positifs car validation dynamique. v0.8.3 (Mars 2026).
- **Maturite**: Production - version 0.8.3 Mars 2026, tres actif (23k stars)
- **Pourquoi c'est pertinent**: 23k stars, dernier commit Mars 2026. Automatise le pentest applicatif avec validation PoC. Compatible CI/CD pour integration dans SDLC securise. Apache 2.0.

---

### CAI - Cybersecurity AI Framework (Alias Robotics)

- **URL**: https://github.com/aliasrobotics/cai
- **GitHub**: https://github.com/aliasrobotics/cai
- **Stars**: ~7,800
- **Licence**: Open source (usage recherche) / Commercial (entreprise)
- **Source de decouverte**: GitHub search cybersecurity LLM
- **Date de recherche**: 2026-04-02
- **Categorie suggeree**: 15_domain_specific / cybersecurity
- **Domaine metier**: Cybersecurite - framework offensif/defensif AI
- **Description**: Framework leger open-source pour construire et deployer de l'automatisation IA en cybersecurite. Supporte 300+ modeles AI (OpenAI, Anthropic, DeepSeek, Ollama). "De facto framework for AI Security".
- **Ce que ca fait**: Outils integres pour reconnaissance, exploitation, escalade de privileges. Architecture modulaire avec agents specialises. Guardrails anti-injection de prompts. Teste sur HackTheBox, bug bounties.
- **Maturite**: Production - 7.8k stars, tres actif
- **Pourquoi c'est pertinent**: Framework le plus complet pour l'IA en cybersecurite offensive/defensive. Validation sur des scenarios reels (CTF, bug bounty). Support multi-LLM dont local (Ollama).

---

### HexStrike AI - MCP Server for Security Tools

- **URL**: https://github.com/0x4m4/hexstrike-ai
- **GitHub**: https://github.com/0x4m4/hexstrike-ai
- **Stars**: ~7,800
- **Licence**: MIT
- **Source de decouverte**: GitHub search cybersecurity LLM
- **Date de recherche**: 2026-04-02
- **Categorie suggeree**: 15_domain_specific / cybersecurity
- **Domaine metier**: Cybersecurite - pentest automatise via MCP
- **Description**: Serveur MCP avance permettant aux agents IA (Claude, GPT, Copilot) de lancer 150+ outils de cybersecurite de maniere autonome pour le pentest et la decouverte de vulnerabilites.
- **Ce que ca fait**: 150+ outils integres (network scanning, web app testing, password cracking, binary analysis), 12+ agents specialises, dashboards temps reel, tests cloud multi (AWS, Azure, GCP), automation browser Chrome headless.
- **Maturite**: Beta - 61 commits, MIT
- **Pourquoi c'est pertinent**: Integration directe avec le protocole MCP pour Claude et autres LLMs. Approche prometteuse pour des workflows de securite pilotes par agents IA. Pertinent pour le catalogue MCP aussi.

---

### CISO Assistant Community - GRC Platform

- **URL**: https://intuitem.com/ciso-assistant
- **GitHub**: https://github.com/intuitem/ciso-assistant-community
- **Stars**: ~3,900
- **Licence**: AGPL-3.0 / Commercial enterprise
- **Source de decouverte**: GitHub search cybersecurity LLM
- **Date de recherche**: 2026-04-02
- **Categorie suggeree**: 15_domain_specific / cybersecurity
- **Domaine metier**: Cybersecurite - GRC (Governance, Risk, Compliance)
- **Description**: Plateforme GRC open-source comprehensive pour la gestion de la cybersecurite en entreprise. Supporte 130+ frameworks (ISO 27001, NIST CSF, SOC 2, PCI DSS, GDPR, HIPAA, NIS2).
- **Ce que ca fait**: Evaluation de risques, tracking de conformite multi-frameworks, mapping automatique des controles entre frameworks, reporting, librairies de menaces integrees. Dernier commit Jan 2025.
- **Maturite**: Production - version stable, usage entreprise avere
- **Pourquoi c'est pertinent**: Alternative open-source serieuse aux solutions GRC commerciales (ServiceNow, Archer). 130+ frameworks en natif. Tres pertinent pour la conformite RGPD/NIS2 en Europe.

---

### Beelzebub - AI-Powered Honeypot

- **URL**: https://github.com/beelzebub-labs/beelzebub
- **GitHub**: https://github.com/beelzebub-labs/beelzebub
- **Stars**: ~1,900
- **Licence**: Non specifiee dans le repo
- **Source de decouverte**: GitHub search cybersecurity LLM
- **Date de recherche**: 2026-04-02
- **Categorie suggeree**: 15_domain_specific / cybersecurity
- **Domaine metier**: Cybersecurite - detection d'intrusion, threat intelligence
- **Description**: Framework de honeypot avance utilisant LLMs pour simuler des systemes reels de maniere convincante. Supporte SSH, HTTP, TCP, TELNET, MCP. Detection d'attaques par prompt injection contre agents LLM.
- **Ce que ca fait**: Honeypots dynamiques via GPT-4 ou Ollama, metriques Prometheus, integration RabbitMQ, configuration YAML, deployment Docker/Kubernetes. Le protocole MCP detecete les attaques contre agents IA.
- **Maturite**: Beta - activement maintenu
- **Pourquoi c'est pertinent**: Pionnier dans la detection d'attaques contre les agents IA (prompt injection sur MCP). Dual use: threat intelligence classique + securite IA. Tres innovant pour 2026.

---

## AGRICULTURE

---

### Plant Disease Detection (mehra-deepak)

- **URL**: https://github.com/mehra-deepak/Plant-Disease-Detection
- **GitHub**: https://github.com/mehra-deepak/Plant-Disease-Detection
- **Stars**: ~208
- **Licence**: Non specifiee
- **Source de decouverte**: GitHub search plant disease detection deep learning
- **Date de recherche**: 2026-04-02
- **Categorie suggeree**: 15_domain_specific / agriculture
- **Domaine metier**: Agriculture - detection de maladies des cultures
- **Description**: Detection de maladies des plantes via deep learning. Implementation CNN sur le dataset PlantVillage (87,900+ images de feuilles de cultures).
- **Ce que ca fait**: Classification de maladies sur feuilles de plantes via CNN/ResNet. Point de depart educational pour des applications d'agriculture de precision.
- **Maturite**: Research/Educational - projet academique
- **Note**: Le domaine "agriculture AI" manque de projets open-source matures avec de nombreuses etoiles. Les solutions de production (John Deere AI, Climate Corp) sont proprietaires. Les meilleurs projets open-source sont academiques.
- **Pourquoi c'est pertinent**: Seul projet agriculture avec nombre de stars significatif. Le vrai terrain d'action est dans des organizations comme CGIAR, FAO qui utilisent YOLO/detectron2 pour la detection de cultures.

---

## RESSOURCES TRANSVERSALES

---

### Awesome-AI4Med - Liste Curee Medical AI

- **URL**: https://github.com/FreedomIntelligence/Awesome-AI4Med
- **GitHub**: https://github.com/FreedomIntelligence/Awesome-AI4Med
- **Stars**: ~2,600
- **Licence**: N/A (liste curee)
- **Source de decouverte**: GitHub topics/medical-imaging
- **Date de recherche**: 2026-04-02
- **Categorie suggeree**: 15_domain_specific / healthcare (ressource)
- **Domaine metier**: Healthcare - overview complet
- **Description**: Liste curee exhaustive de medical LLMs, systemes multimodaux medicaux, datasets et benchmarks. Point d'entree unique pour l'ecosysteme AI medical.
- **Ce que ca fait**: Repertorie: medical LLMs (MedPaLM, HuatuoGPT, Meditron, BioMistral), benchmarks (MedQA, PubMedQA, MedMCQA), datasets d'imagerie medicale, multimodal medical AI.
- **Maturite**: Ressource de reference - 2.6k stars
- **Pourquoi c'est pertinent**: Roadmap la plus complete pour evaluer l'etat de l'art en medical AI. Essentiel pour choisir le bon modele ou benchmark pour une application clinique specifique.

---

## NOTES DE RECHERCHE

### Domaines insuffisamment couverts

**RH / Recrutement**: Aucun projet open-source avec >100 stars n'existe sous les termes "resume screening AI", "recruitment AI". Le marche est domine par des solutions SaaS proprietaires (Workday AI, Greenhouse, Lever). Des librairies generales (spaCy + parsing custom) sont utilisees. Pas d'entree catalogable avec maturite suffisante.

**Immobilier**: Meme constat - pas de frameworks open-source etablis. Des implementations custom de price estimation (XGBoost + donnees cadastrales) existent mais ne constituent pas des outils catalogables.

**Finance - Fraud Detection**: Les projets open-source de fraud detection manquent de maturite (<100 stars). Les solutions en production (Stripe Radar, PayPal AI) sont fermees. Les approches open-source utilisent XGBoost/Isolation Forest sur Kaggle datasets mais sans framework dedie notable.

### Gaps identifies pour recherche future

1. **Medical Imaging - OHIF Viewers**: 4.1k stars, viewer DICOM zero-footprint + extension oncologie. A cataloguer.
2. **FinNLP (AI4Finance)**: 482 stars - NLP pour la finance, complemente FinGPT.
3. **BloombergGPT**: Modele ferme (Bloomberg), uniquement accessible via API Bloomberg Terminal. Non catalogable comme open-source.
4. **Med-PaLM (Google)**: Modele ferme Google, non open-source. Non catalogable.
5. **HuatuoGPT-o1**: 1.3k stars - "Medical o1" pour raisonnement medical complexe. Version plus recente de HuatuoGPT, a evaluer.
6. **ContractNLI (Stanford)**: Dataset pour NLI sur contrats, 37 stars mais reference academique EMNLP 2021.
