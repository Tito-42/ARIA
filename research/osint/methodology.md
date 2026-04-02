# Méthodologie OSINT - Recherche IA

## Objectif
Identifier, évaluer et cataloguer systématiquement les meilleures solutions IA open-source et commerciales disponibles en avril 2026.

## Sources de Recherche

### Tier 1 - Signal fort (priorité haute)

| Source | URL | Quoi Chercher | Fréquence |
|--------|-----|---------------|-----------|
| GitHub Trending | github.com/trending | Repos trending Python, TypeScript, Rust | Hebdomadaire |
| Awesome Lists | github.com/topics/awesome-list | Listes "awesome-*" par catégorie | Mensuel |
| Papers with Code | paperswithcode.com | SOTA avec implémentations code | Bi-hebdomadaire |
| Hugging Face | huggingface.co | Modèles/Spaces trending | Hebdomadaire |
| Kaggle | kaggle.com | Solutions gagnantes, notebooks | Post-compétition |
| ARC Prize | arcprize.org | Résultats benchmark, writeups | Trimestriel |
| Anthropic | docs.anthropic.com, github.com/anthropics | Claude, MCP, SDK releases | Hebdomadaire |
| OpenAI | platform.openai.com, github.com/openai | GPT, API, agents SDK | Hebdomadaire |
| Google AI | ai.google.dev, github.com/google | Gemini, open models | Hebdomadaire |

### Tier 2 - Signal communautaire

| Source | URL | Quoi Chercher |
|--------|-----|---------------|
| r/LocalLLaMA | reddit.com/r/LocalLLaMA | Modèles locaux, quantization, benchmarks |
| r/MachineLearning | reddit.com/r/MachineLearning | Papers, discussions, tendances |
| Hacker News | news.ycombinator.com | Show HN IA, discussions techniques |
| Product Hunt | producthunt.com | Lancements AI tools |
| Dev.to / Medium | dev.to, medium.com | Tutorials, retours d'expérience |
| YouTube | youtube.com | Conférences (NeurIPS, ICML), demos |

### Tier 3 - Agrégateurs

| Source | URL | Quoi Chercher |
|--------|-----|---------------|
| There's An AI For That | theresanaiforthat.com | Découverte par use case |
| LabLab.ai | lablab.ai | Projets hackathon |
| Devpost | devpost.com | Soumissions hackathon IA |
| LMSys Chatbot Arena | chat.lmsys.org | Classement modèles par préférence utilisateur |
| AI Tool Tracker | various | Nouvelles releases, comparaisons |

## Stratégie de Requêtes

### Pattern général par catégorie
```
"best open source {keyword}" site:github.com
"awesome {keyword}" site:github.com
"{keyword}" stars:>1000 site:github.com
"{keyword} framework 2025 2026" site:reddit.com
"{keyword} enterprise production" site:medium.com OR site:dev.to
"{keyword}" site:paperswithcode.com
"{keyword} benchmark comparison 2026"
"{keyword} vs" (pour trouver des comparaisons)
```

### Requêtes spécialisées
```
# ARC-AGI
"ARC-AGI" OR "ARC Prize" solution github
"ARC-AGI-2" approach winning

# Kaggle
"kaggle competition winner 2025 2026" solution code
site:kaggle.com "1st place solution"

# Hackathons Anthropic
"anthropic hackathon" winning project
"claude hackathon" github solution
site:devpost.com "anthropic" OR "claude"

# MCP
"MCP server" site:github.com
"model context protocol" connector
"awesome-mcp" site:github.com
```

## Critères d'Évaluation

### Évaluation Rapide (go/no-go)
1. Dernier commit < 6 mois ? → Si non, marquer "potentially stale"
2. Plus de 100 stars ? → Si non, vérifier la qualité quand même
3. Licence identifiée ? → Si non, investiguer
4. Documentation existante ? → Si non, risque

### Évaluation Approfondie (pour les candidats retenus)
| Critère | Comment vérifier |
|---------|-----------------|
| **Activité** | Derniers commits, release frequency, issue response time |
| **Adoption** | GitHub stars, npm/PyPI downloads, community Discord/Slack |
| **Qualité** | Tests, CI/CD, code review process, architecture |
| **Enterprise Fit** | Licence, security audit, SSO/RBAC, compliance |
| **Longévité** | Funding, diversité contributeurs, roadmap, backing org |

### Score Enterprise (1-5)
- **Production Readiness** : peut-on l'utiliser en production demain ?
- **Security** : a-t-il été audité ? Gère-t-il les données sensibles ?
- **Scalability** : peut-il monter en charge ?
- **Support/Community** : qui va nous aider si ça casse ?
- **Documentation** : peut-on onboarder un dev rapidement ?
- **Integration Ease** : combien de temps pour l'intégrer ?

## Processus de Recherche par Catégorie

```
Pour chaque catégorie (01-18):
  1. Rechercher les awesome lists de référence
  2. Identifier les top 10-20 outils mentionnés
  3. Pour chaque outil:
     a. Vérifier GitHub (stars, activité, licence)
     b. Lire la documentation
     c. Chercher des retours d'expérience
     d. Évaluer le score enterprise
  4. Créer les fiches catalogue
  5. Créer les comparaisons
  6. Mettre à jour state/research_progress.json
```

## Organisation des Findings

```
research/
  raw/         → Findings bruts non structurés (temporaires)
  sources/     → Findings organisés par source
  osint/       → Cette méthodologie + requêtes utilisées
```

Les findings bruts dans `raw/` sont traités par l'agent `cataloger` pour devenir des fiches dans `catalog/`.
