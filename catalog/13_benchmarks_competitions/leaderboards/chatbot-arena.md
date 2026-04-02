# LMSys Chatbot Arena (LM Arena)

> Classement des LLMs par préférence humaine via 1.5M+ votes - le benchmark de référence

## Metadata
| Field | Value |
|-------|-------|
| **Platform** | LM Arena (LMSys) |
| **URL** | https://lmarena.ai |
| **Year** | 2023-present |
| **Status** | Active |

## Problem Description
Chatbot Arena évalue les LLMs via des batailles côte-à-côte anonymes où les utilisateurs votent pour le meilleur modèle. Avec 1.5M+ votes humains et 10M+ requêtes sur 70+ LLMs, c'est le benchmark le plus fiable pour mesurer la qualité perçue des modèles.

## Top 5 Modèles (Février 2026)

| Rank | Model | Arena Elo | SWE-bench Pro | Context | Force |
|------|-------|-----------|---------------|---------|-------|
| 1 | **Gemini 3.1 Pro** | 1505 ±9 | 80.6% | 2M+ | Multimodal, vidéo RAG |
| 2 | **Claude Opus 4.6** | 1505 ±8 | 80.8% | 1M | Architecture complexe, coding |
| 3 | **GPT-5.2 (High)** | 1478 ±12 | 76.9% | 400K | Business logic, instruction following |
| 4 | **Grok-4.1 (Thinking)** | 1473 ±4 | 72.4% | 2M | Real-time data |
| 5 | **DeepSeek R1-0528** | 1418 ±5 | 70.2% | 128K | Open-source deployment |

## Key Takeaways for Enterprise

### Le top converge
Gemini 3.1 Pro, Claude Opus 4.6 et GPT-5.2 sont dans le bruit statistique (~1478-1505 Elo). La différenciation se fait sur :
- **Contexte** : Gemini 2M+ vs Claude 1M vs GPT 400K
- **Coût** : DeepSeek R1 est dramatiquement moins cher
- **Spécialisation** : Claude excelle en coding, Gemini en multimodal

### "Best" dépend du use case
Le "meilleur" modèle dépend maintenant de la profondeur de raisonnement, du coût par token et de l'autonomie agentique.

### Open source est compétitif
DeepSeek R1-0528 (1418 Elo) délivre des résultats solides pour du self-hosted.

## Tracking Resources
| Resource | URL | Description |
|----------|-----|-------------|
| Arena Leaderboard Snapshots | github.com/oolong-tea-2026/arena-ai-leaderboards | Snapshots JSON auto-updated |
| Arena History | github.com/nakasyou/lmarena-history | Historique scores Elo en JSON |
| Best AI Models | github.com/AgileWoW/best-ai-models-leaderboard | Rankings curatés |

## References
- [LM Arena](https://lmarena.ai)
- [Search Arena (ICLR 2026)](https://github.com/lmarena/search-arena)
