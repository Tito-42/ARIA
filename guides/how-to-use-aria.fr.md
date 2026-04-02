# Comment utiliser ARIA — Guide pas à pas pour débutants

**[English](how-to-use-aria.md) | [Français](#quest-ce-quaria) | [Español](how-to-use-aria.es.md)**

---

# Qu'est-ce qu'ARIA ?

ARIA est comme une **encyclopédie géante des outils IA** — sauf qu'elle est toujours à jour parce que des agents IA la rafraîchissent chaque nuit. Elle contient 323+ fiches détaillées sur des outils qui peuvent t'aider à construire des chatbots, automatiser des tâches, traiter des documents, générer des images, et bien plus.

Tu n'as pas besoin d'être développeur ou expert en IA pour l'utiliser. Tu as juste besoin de savoir poser une question.

---

# C'est quoi un chatbot / assistant IA ?

Avant de commencer, mettons-nous d'accord sur les termes.

Un **chatbot IA** (ou assistant IA) est un site web où tu peux taper des questions en langage normal et obtenir des réponses intelligentes. Pense à un moteur de recherche très intelligent qui comprend vraiment ce que tu demandes et te donne une réponse directe au lieu d'une liste de liens.

Les plus populaires (tous gratuits pour commencer) :

| Nom | Créé par | Site web | Gratuit ? |
|-----|----------|----------|-----------|
| **Claude** | Anthropic | [claude.ai](https://claude.ai) | Oui (version gratuite) |
| **ChatGPT** | OpenAI | [chat.openai.com](https://chat.openai.com) | Oui (version gratuite) |
| **Gemini** | Google | [gemini.google.com](https://gemini.google.com) | Oui (version gratuite) |
| **Copilot** | Microsoft | [copilot.microsoft.com](https://copilot.microsoft.com) | Oui |

Ils fonctionnent tous de la même façon : tu tapes une question, l'IA répond. C'est tout.

---

# Comment utiliser ARIA (3 méthodes)

## Méthode 1 : Demander à Claude (la plus facile — recommandée)

C'est la méthode recommandée. Aucune installation, aucun code, aucune compétence technique nécessaire.

> **Important :** Après plusieurs benchmarks, **Claude est le seul LLM gratuit** qui lit réellement l'URL du catalogue, cite les vrais outils avec les scores enterprise, et n'hallucine pas. ChatGPT et Gemini (gratuits) n'arrivent pas à lire l'URL et donnent des réponses génériques. Voir le [benchmark complet](../BENCHMARK_LLM.md).

### Étape 1 — Ouvre Claude

Va sur [claude.ai](https://claude.ai) et crée un compte gratuit si tu n'en as pas.

- **Recommandé :** [claude.ai](https://claude.ai) — lit le catalogue, cite les scores, pas d'hallucination
- Non recommandé : [chat.openai.com](https://chat.openai.com) — ne lit pas l'URL, réponses génériques
- Non recommandé : [gemini.google.com](https://gemini.google.com) — ne lit pas l'URL, réponses génériques

### Étape 2 — Écris ta question + le lien ARIA

Dans la zone de texte, écris ce que tu cherches ET inclus l'URL du catalogue. L'IA va lire les fiches et te répondre.

### Étape 3 — Obtiens ta réponse

L'IA va :
1. Lire le catalogue ARIA
2. Trouver les outils pertinents pour ta question
3. Les comparer
4. Te donner une recommandation avec les avantages, inconvénients, et comment démarrer

### Exemples concrets à copier-coller

**Exemple 1 — Tu veux créer un chatbot pour ton entreprise :**
```
Je veux mettre en place un chatbot IA pour le support client sur mon site web.
Quelles sont les meilleures options open-source ? J'ai besoin de quelque chose
de gratuit, facile à installer, et qui fonctionne en français.
Lis https://tito-42.github.io/ARIA/CATALOG_SUMMARY.md
```

**Exemple 2 — Tu veux automatiser le traitement de factures :**
```
Mon entreprise traite des centaines de factures par mois manuellement.
J'aimerais automatiser ça avec l'IA. Recommande des outils qui peuvent
extraire les données de factures PDF automatiquement.
Lis https://tito-42.github.io/ARIA/CATALOG_SUMMARY.md
```

**Exemple 3 — Tu veux ajouter l'IA à ton application existante :**
```
J'ai une application web et je veux ajouter un assistant IA qui peut répondre
aux questions sur notre documentation. Quels outils RAG dois-je utiliser ?
Explique-moi simplement, je ne suis pas expert en IA.
Lis https://tito-42.github.io/ARIA/CATALOG_SUMMARY.md
```

**Exemple 4 — Tu veux explorer ce que l'IA peut automatiser :**
```
Je dirige une petite agence marketing. Quels processus métier l'IA peut-elle
automatiser pour moi aujourd'hui ? Concentre-toi sur les outils open-source
qui peuvent automatiser au moins 60% d'une tâche.
Lis https://tito-42.github.io/ARIA/CATALOG_SUMMARY.md
```

**Exemple 5 — Tu veux comparer des outils :**
```
Je dois choisir un outil de génération de code par IA. Compare les 5 meilleures
options — dis-moi lequel est le meilleur pour une équipe de 10 développeurs
qui travaillent en Python et JavaScript.
Lis https://tito-42.github.io/ARIA/CATALOG_SUMMARY.md
```

### Astuces pour de meilleurs résultats

- **Sois précis sur tes besoins :** "J'ai besoin d'un chatbot pour un cabinet dentaire" est mieux que "J'ai besoin d'un chatbot"
- **Mentionne tes contraintes :** budget, langue, taille d'équipe, niveau technique
- **Demande des comparaisons :** "Compare X vs Y" te donne une réponse prête à l'emploi
- **Demande des explications simples :** "Explique-moi comme si je n'étais pas technique" — l'IA s'adaptera

---

## Méthode 2 : Naviguer directement sur GitHub (sans IA)

Tu peux explorer le catalogue comme un site web, directement sur GitHub.

### Étape 1 — Va sur le catalogue

Ouvre : [https://github.com/Tito-42/ARIA/tree/main/catalog](https://github.com/Tito-42/ARIA/tree/main/catalog)

### Étape 2 — Choisis une catégorie

Tu verras des dossiers numérotés de 01 à 18. Chacun couvre un domaine différent :

| Dossier | Ce qu'il contient |
|---------|------------------|
| `01_code_generation/` | Outils pour écrire du code avec l'IA |
| `02_ai_agents/` | Frameworks pour construire des agents IA autonomes |
| `03_mcp/` | Connecteurs entre l'IA et des outils externes |
| `04_frontend_ui/` | Outils qui génèrent des sites web et interfaces |
| `05_rag_knowledge/` | Bases de données et outils pour l'IA qui fouille tes documents |
| `06_finetuning_training/` | Outils pour personnaliser des modèles IA |
| `07_computer_vision/` | Reconnaissance d'images, génération, OCR |
| `08_nlp_text/` | Analyse de texte, classification, traduction |
| `09_voice_audio/` | Reconnaissance vocale, synthèse vocale, voice IA |
| `10_data_science_mlops/` | Outils pour déployer et gérer l'IA en production |
| `11_automation_workflows/` | Automatisation de workflows (comme Zapier, mais avec l'IA) |
| `12_enterprise_integration/` | Monitoring, sécurité, gestion des coûts pour l'IA |
| `13_benchmarks_competitions/` | Compétitions IA et classements |
| `14_open_source_llms/` | Modèles IA gratuits que tu peux faire tourner toi-même |
| `15_domain_specific/` | IA pour santé, finance, juridique, éducation, **automatisation métier** |
| `16_ai_security_safety/` | Outils pour sécuriser l'IA |
| `17_multimodal/` | IA qui comprend images, vidéo et documents |
| `18_ai_infrastructure/` | Matériel et optimisation pour faire tourner l'IA |

### Étape 3 — Clique sur un outil

Chaque fichier `.md` est une fiche complète avec tout ce que tu as besoin de savoir.

---

## Méthode 3 : Utiliser avec Claude Code (pour développeurs)

Si tu es développeur avec [Claude Code](https://claude.ai/code) installé :

```bash
git clone https://github.com/Tito-42/ARIA.git
cd ARIA
claude
```

Ensuite, demande ce que tu veux en langage naturel. Claude a accès à l'ensemble des 323+ fiches en local et peut chercher, comparer et recommander instantanément.

---

# Questions fréquentes

### ARIA est-il gratuit ?
Oui, complètement. C'est open source sous licence MIT. Le catalogue, les scripts, tout.

### J'ai besoin de savoir coder ?
Non. La méthode 1 (demander à un chatbot) ne demande aucune compétence technique. Tu tapes juste une question en langage normal.

### Quel chatbot IA utiliser ?
On recommande **Claude** (claude.ai). Après plusieurs benchmarks, c'est le seul LLM gratuit qui lit réellement l'URL du catalogue, cite les vrais outils avec les scores enterprise, et n'hallucine pas. ChatGPT et Gemini (gratuits) n'arrivent pas à lire l'URL et donnent des réponses génériques.

### ARIA est mis à jour quand ?
Chaque nuit entre 23h00 et 07h00 (heure de Paris). Les agents IA vérifient les nouveaux outils, les changements de versions, et les repos tendance.

### Je peux faire confiance aux informations ?
Chaque fiche inclut une date de vérification, des liens vers la source, et une évaluation honnête des forces ET des limites. On ne cache pas les défauts. Cela dit, les outils IA évoluent vite — vérifie toujours la doc officielle avant de prendre une décision critique.

### Et si l'outil que je cherche n'est pas dans le catalogue ?
Demande au chatbot quand même ! Il peut trouver quelque chose de proche. Et tu peux ouvrir une issue sur GitHub pour le demander — ou le contribuer toi-même.

### Je ne parle pas bien anglais. Je peux utiliser ARIA dans ma langue ?
Les fiches du catalogue sont principalement en anglais, mais tu peux poser ta question au chatbot dans n'importe quelle langue. Par exemple :
```
Lis https://tito-42.github.io/ARIA/CATALOG_SUMMARY.md et dis-moi en français quel outil utiliser pour un chatbot
```

L'IA lira les fiches en anglais et te répondra dans ta langue.

---

# Carte de référence rapide

Garde ça sous le coude :

```
[Ta question]. Lis https://tito-42.github.io/ARIA/CATALOG_SUMMARY.md

Fonctionne avec : Claude, ChatGPT, Gemini, Copilot,
ou n'importe quel chatbot IA.
```

---

<div align="center">

*ARIA — Arrête de googler. Commence à interroger.*

</div>
