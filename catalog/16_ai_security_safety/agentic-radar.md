# Agentic Radar (Splx.ai)

> Analyse statique de sécurité pour systèmes agentiques — visualise les flux, identifie les vulnérabilités.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 16 - AI Security & Safety / Agent Security |
| **URL** | https://github.com/splx-ai/agentic-radar |
| **GitHub** | https://github.com/splx-ai/agentic-radar |
| **Stars** | ~941 |
| **License** | Apache 2.0 |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Beta |

## What It Does
Agentic Radar est le premier outil d'analyse statique de sécurité spécialisé pour les systèmes agentiques (LangChain, CrewAI, etc.). Il visualise les flux de données entre agents, identifie les vulnérabilités de sécurité (excessive agency, data leakage), et génère des rapports.

## Key Features
- **Analyse statique**: Scan du code des agents
- **Visualisation des flux**: Graphe des interactions agent
- **Détection de vulnérabilités**: Excessive agency, data leakage
- **Multi-framework**: LangChain, CrewAI, etc.
- **Apache 2.0**: Licence permissive

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 2 | Nouveau, beta |
| **Security** | 4 | Apache 2.0, conçu pour sécurité |
| **Scalability** | 3 | Analyse statique, léger |
| **Support/Community** | 2 | ~941 stars, nouveau |
| **Documentation** | 2 | README |
| **Integration Ease** | 3 | CLI |

## Use Cases
1. **Agent security audit** — Auditer la sécurité des systèmes agentiques
2. **Architecture review** — Visualiser les flux de données entre agents

## Getting Started
```bash
pip install agentic-radar
agentic-radar scan ./my_agent_project
```

## Strengths
- Unique dans son créneau
- Visualisation des flux agents
- Apache 2.0

## Limitations
- Très nouveau (2025)
- Communauté petite
- Beta

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Agentic Security | Tests runtime, pas statique |
| Promptfoo | Plus mature, pas agent-specific |

## References
- https://github.com/splx-ai/agentic-radar
