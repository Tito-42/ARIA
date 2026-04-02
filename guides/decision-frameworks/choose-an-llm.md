# Decision Framework : Choisir un LLM

> Guide de selection du meilleur modele LLM selon le use case enterprise

## Arbre de Decision Rapide

```
Besoin de privacy / on-premise ?
├── OUI → Modeles Open Source (voir ci-dessous)
│         Budget GPU ?
│         ├── Pas de GPU → Ollama + petit modele (Phi, Gemma)
│         ├── GPU consumer → Ollama/LM Studio + 7B-14B (Qwen, Llama)
│         └── GPU pro → vLLM + 70B+ (Llama 3.1 405B, DeepSeek)
│
└── NON → API Cloud
          Budget important ?
          ├── NON → Gemini CLI (gratuit) ou Haiku 4.5 (tres cheap)
          └── OUI → Quel use case ?
                    ├── Coding → Claude Opus 4.6 (SWE-bench #1)
                    ├── Raisonnement complexe → Claude Opus 4.6 ou o3
                    ├── Multimodal (images/video) → Gemini 3.1 Pro
                    ├── Conversation simple → Sonnet 4.6 ou GPT-4o
                    ├── Volume massif → Batch API (Claude/OpenAI)
                    └── Temps reel / low latency → Haiku 4.5 ou GPT-4o-mini
```

## Matrice de Selection par Use Case

| Use Case | Modele #1 | Modele #2 | Modele Budget |
|----------|-----------|-----------|---------------|
| **Coding / Dev** | Claude Opus 4.6 | GPT-5.2 | DeepSeek R1 |
| **Raisonnement** | Claude Opus 4.6 | o3-high | DeepSeek R1 |
| **Conversation** | Claude Sonnet 4.6 | GPT-4o | Llama 3.1 70B |
| **Multimodal** | Gemini 3.1 Pro | Claude Opus 4.6 | LLaVA |
| **Summarization** | Claude Sonnet 4.6 | GPT-4o | Mistral Large |
| **RAG** | Claude Sonnet 4.6 | Command R+ | Qwen 2.5 72B |
| **Classification** | Haiku 4.5 | GPT-4o-mini | Phi-4 |
| **Translation** | GPT-4o | Claude Sonnet | Qwen 2.5 |
| **Batch/Volume** | Claude Batch API | OpenAI Batch | Self-hosted |
| **Edge/Mobile** | Phi-4 | Gemma 2B | Llama 3.2 1B |

## Comparaison Couts (estimation avril 2026)

| Modele | Input $/1M tokens | Output $/1M tokens | Contexte |
|--------|-------------------|--------------------|---------|
| Claude Opus 4.6 | ~$15 | ~$75 | 1M |
| Claude Sonnet 4.6 | ~$3 | ~$15 | 200K |
| Claude Haiku 4.5 | ~$0.80 | ~$4 | 200K |
| GPT-5.2 | ~$15 | ~$60 | 400K |
| GPT-4o | ~$2.50 | ~$10 | 128K |
| GPT-4o-mini | ~$0.15 | ~$0.60 | 128K |
| Gemini 3.1 Pro | ~$2 | ~$8 | 2M+ |
| DeepSeek R1 | ~$0.55 | ~$2.19 | 128K |
| Llama 3.1 405B (self-hosted) | GPU cost only | GPU cost only | 128K |

*Prix indicatifs, verifier les tarifs actuels*

## Decision par Contrainte

### Contrainte : Budget limite
→ Gemini CLI (gratuit) ou DeepSeek R1 (tres peu cher) ou self-hosted

### Contrainte : Latence < 500ms
→ Haiku 4.5, GPT-4o-mini, ou modele local (Ollama)

### Contrainte : Compliance RGPD / souverainete
→ Self-hosted (Llama, Mistral, Qwen) ou API europeenne (Mistral)

### Contrainte : Contexte > 200K tokens
→ Gemini 3.1 Pro (2M+) ou Claude Opus 4.6 (1M)

### Contrainte : Multi-model (pas de lock-in)
→ LiteLLM comme gateway, Aider pour le coding

## References
- Voir catalog/13_benchmarks_competitions/leaderboards/ pour les scores
- Voir catalog/14_open_source_llms/ pour les modeles open source
- Voir catalog/12_enterprise_integration/cost-optimization/ pour le model routing
