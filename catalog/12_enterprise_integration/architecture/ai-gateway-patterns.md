# AI Gateway Patterns

> Architectures pour integrer l'IA en entreprise : gateway, routing, caching, observabilite

## Problem
Comment integrer l'IA (LLMs, agents) dans une architecture enterprise existante de maniere securisee, scalable et cost-effective ?

## Solution
Un AI Gateway centralise les appels aux LLMs et fournit : routing multi-model, caching, rate limiting, observabilite, securite et gestion des couts.

## Architecture Diagram
```
Applications (Web, Mobile, API, CI/CD)
    |
    v
┌─────────────────────────────────────┐
│          AI GATEWAY                  │
│                                      │
│  ┌──────────┐  ┌──────────────────┐ │
│  │ Auth &   │  │ Rate Limiting    │ │
│  │ RBAC     │  │ & Quotas         │ │
│  └──────────┘  └──────────────────┘ │
│                                      │
│  ┌──────────┐  ┌──────────────────┐ │
│  │ Prompt   │  │ Semantic Cache   │ │
│  │ Firewall │  │ (reduce costs)   │ │
│  └──────────┘  └──────────────────┘ │
│                                      │
│  ┌──────────┐  ┌──────────────────┐ │
│  │ Model    │  │ Observability    │ │
│  │ Router   │  │ (Langfuse, etc.) │ │
│  └──────────┘  └──────────────────┘ │
└─────────┬───────────┬───────────┬───┘
          │           │           │
     ┌────▼────┐ ┌────▼────┐ ┌───▼─────┐
     │ Claude  │ │ GPT-5   │ │ Local   │
     │ API     │ │ API     │ │ LLM     │
     └─────────┘ └─────────┘ └─────────┘
```

## Composants Cles

### 1. Model Router (routage intelligent)
- **Simple** : round-robin ou regles statiques
- **Intelligent** : routage par complexite de la requete
  - Requetes simples → modele petit/rapide/cheap (Haiku, GPT-4o-mini)
  - Requetes complexes → modele puissant/cher (Opus, GPT-5.2)
- **Outils** : LiteLLM (41.8K stars), Portkey AI, Martian

### 2. Semantic Cache
- Cache les reponses pour des requetes semantiquement similaires
- Reduction de 40-60% des couts API
- **Outils** : GPTCache, Redis + embeddings

### 3. Prompt Firewall
- Detection et blocage d'injections de prompt
- Filtrage de donnees sensibles (PII, secrets)
- **Outils** : Lakera Guard, Rebuff, custom rules

### 4. Observabilite
- Tracing des appels LLM (latence, tokens, couts)
- Evaluation de qualite des reponses
- **Outils** : Langfuse, LangSmith, Phoenix/Arize

### 5. Fallback & Retry
- Basculement automatique si un provider est down
- Retry avec exponential backoff
- Multi-provider pour resilience

## Implementation avec Outils Recommandes

| Composant | Outil Recommande | Alternative |
|-----------|-----------------|-------------|
| API Gateway | LiteLLM | Portkey, custom |
| Semantic Cache | GPTCache + Redis | Custom embeddings |
| Prompt Firewall | Lakera Guard | NeMo Guardrails |
| Observabilite | Langfuse | LangSmith, Arize |
| Model Router | LiteLLM | Martian, custom |
| Auth/RBAC | Existing IAM | Keycloak, Auth0 |

## When to Use
- Multiple modeles LLM utilises en production
- Volume >1000 requetes/jour
- Besoin de controle des couts
- Exigences compliance/securite

## When NOT to Use
- Prototype/POC avec un seul modele
- Volume faible (<100 requetes/jour)
- Application interne sans contrainte de securite

## Enterprise Considerations
- **Cout** : le gateway ajoute de la latence mais reduit les couts globaux via caching et routing
- **Vendor lock-in** : LiteLLM (100+ providers) evite le lock-in
- **Compliance** : le gateway est le point d'audit central (logs, traces)
- **Multi-region** : deployer le gateway pres des utilisateurs

## References
- [LiteLLM](https://github.com/BerriAI/litellm) - 41.8K stars, proxy multi-provider
- [Langfuse](https://langfuse.com) - Observabilite open source
- [Portkey AI](https://portkey.ai) - AI Gateway commercial
- Voir aussi : catalog/16_ai_security_safety/ pour guardrails et red-teaming
