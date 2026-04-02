# Anthropic / Claude Hackathons

> Projets gagnants des hackathons Claude et écosystème de compétitions IA

## Claude for Good UVA Hackathon 2025

### Overall Winner: CoRA (Course Research Assistant)
- **URL**: https://github.com/njdelapaz/cora-extension
- **Team**: Nathan Dela Paz, Kayla Kim, Livs Sun, Elyse Undan
- **What**: Chrome extension intégrant des insights IA sur les cours/professeurs dans le système d'information étudiant UVA
- **Tech**: Chrome Extension Manifest V3, Google Custom Search API, OpenAI GPT-5-mini pour filtering, cache local (30 jours, 100 entrées)
- **Pipeline**: Search web → scrape → filter IA (modèle léger) → summarize (modèle lourd) → rate → cache
- **Pourquoi ça a gagné**: Utilité pratique résolvant un vrai problème étudiant, utilisation intelligente de modèles légers pour le filtrage + raisonnement lourd seulement où nécessaire

## Écosystème Hackathons IA

### Plateformes
| Plateforme | URL | Description |
|------------|-----|-------------|
| **Devpost** | devpost.com | Principale plateforme de hackathons tech, nombreux projets Claude/Anthropic |
| **LabLab.ai** | lablab.ai | Hackathons IA spécialisés, catégorie Claude/Anthropic dédiée |
| **Strong Compute** | strongcompute.com | Hackathons avec GPU sponsorisés |

### Projets Notables
- **ArcifiedAI** (Strong Compute Hackathon) : solution gagnante pour ARC-AGI-2
- Nombreux projets sur Devpost utilisant Claude pour : agents, RAG, automation, education

## Patterns des Projets Gagnants

1. **Résolution d'un vrai problème** : les gagnants résolvent des problèmes pratiques, pas techniques
2. **Architecture intelligente** : modèles légers pour filtrage, lourds pour raisonnement
3. **Integration dans l'existant** : extensions, plugins, pas de standalone
4. **Pipeline efficace** : search → filter → process → cache
5. **Coût maîtrisé** : optimisation du nombre d'appels API

## Key Takeaways for Enterprise
- Les hackathons sont une source excellente de **patterns d'architecture** validés
- Les projets gagnants montrent des approches **multi-model** (léger + lourd)
- La **mise en cache** et l'**optimisation des coûts** sont des critères de victoire
- L'**intégration dans des systèmes existants** est valorisée vs solutions standalone

## Où Trouver Plus de Projets
- Devpost : `site:devpost.com "anthropic" OR "claude"`
- LabLab.ai : `lablab.ai/technology/anthropic/claude`
- GitHub : `"claude hackathon" github solution`
