# Model Routing - Optimisation des Couts LLM

> Reduire les couts API de 50-80% en routant intelligemment les requetes vers le bon modele

## Problem
Les modeles frontier (Claude Opus, GPT-5.2) sont puissants mais chers. 70-80% des requetes enterprise sont assez simples pour etre traitees par des modeles plus petits et rapides.

## Solution
Le model routing analyse chaque requete et la dirige vers le modele optimal en termes de cout/qualite.

## Architecture
```
Requete utilisateur
    |
    v
Router (classifieur de complexite)
    |
    ├── Complexite FAIBLE (70% requetes)
    │   → Haiku 4.5 / GPT-4o-mini / Gemma
    │   → Cout: ~$0.001 / requete
    │
    ├── Complexite MOYENNE (20% requetes)
    │   → Sonnet 4.6 / GPT-4o / Mistral Large
    │   → Cout: ~$0.01 / requete
    │
    └── Complexite HAUTE (10% requetes)
        → Opus 4.6 / GPT-5.2 / Gemini 3.1 Pro
        → Cout: ~$0.10 / requete

Economie estimee: 60-80% vs tout envoyer au modele le plus cher
```

## Strategies de Routage

### 1. Classification par regles
- Longueur du prompt < 100 tokens → petit modele
- Mots-cles techniques complexes → gros modele
- Simple : rapide a implementer, fragile

### 2. Classification par LLM petit
- Un petit modele (Haiku) evalue la complexite
- Route vers le modele approprie
- Cout additionnel minime du classifieur

### 3. Routage par tache
- Traduction → modele specialise
- Code generation → modele fort en code
- Conversation simple → petit modele rapide

### 4. Cascade / Escalation
- Commencer par le petit modele
- Si la reponse est incertaine → escalader vers un plus gros
- Latence potentiellement plus elevee

## Implementation avec Outils

| Approche | Outil | Complexite |
|----------|-------|-----------|
| Multi-provider proxy | LiteLLM | Faible |
| Rules-based routing | Custom + LiteLLM | Moyenne |
| ML-based routing | Martian, Portkey | Moyenne |
| Cascade | Custom logic | Haute |

## Economies Typiques

| Scenario | Sans routing | Avec routing | Economie |
|----------|-------------|-------------|----------|
| 10K req/jour, tout Opus | $1,000/jour | $200/jour | **80%** |
| Chatbot support client | $500/jour | $150/jour | **70%** |
| Code review pipeline | $300/jour | $120/jour | **60%** |

## Enterprise Considerations
- **Qualite** : monitorer la satisfaction utilisateur par modele
- **Latence** : le routage ajoute 10-50ms, negligeable
- **Fallback** : si le gros modele est down, utiliser le moyen
- **Metriques** : tracker cout/requete, satisfaction, latence par modele

## References
- [LiteLLM](https://github.com/BerriAI/litellm) - Proxy multi-provider
- [Martian](https://withmartian.com) - AI model router
- Voir aussi : catalog/12_enterprise_integration/architecture/ai-gateway-patterns.md
