# SWE-bench

> Benchmark évaluant les agents sur la résolution d'issues GitHub réelles - le test de coding agentique

## Metadata
| Field | Value |
|-------|-------|
| **Platform** | Princeton / SWE-bench |
| **URL** | https://www.swebench.com |
| **GitHub** | https://github.com/SWE-bench/SWE-bench |
| **Stars** | 4,600 |
| **Year** | 2024-present |
| **Prize** | N/A (benchmark académique) |
| **Status** | Active |

## Problem Description
SWE-bench mesure la capacité des modèles/agents à générer des patches qui résolvent de vraies issues GitHub. Publié à ICLR 2024 (Oral) et ICLR 2025 (extension multimodale). Évaluation via containers Docker.

**Variants** : Full, Lite, Verified (500 problèmes validés humainement), Multimodal.

## Top Performing Systems

### SWE-bench Pro (dernières données)
| Model/System | Score | Notes |
|-------------|-------|-------|
| **Claude Opus 4.6** | 80.8% | Top 1 sur SWE-bench Pro |
| **Gemini 3.1 Pro** | 80.6% | Quasi ex-aequo |
| **GPT-5.2 (High)** | 76.9% | 3ème |
| **Grok-4.1 (Thinking)** | 72.4% | 4ème |
| **DeepSeek R1-0528** | 70.2% | Meilleur open source |

### SWE-bench Verified (systèmes agentiques)
| System | Score | Type |
|--------|-------|------|
| **SE-Agent** | ~80% | Open source, self-evolution, NeurIPS 2025 |
| **OpenHands** | 77.6% | MIT, utilisé par GAFAM |
| **SWE-agent 1.0** | SOTA | Princeton, NeurIPS 2024 |
| **Mini-SWE-Agent** | 65% | Seulement 100 lignes Python ! |

## Winning Approaches

### SE-Agent (Top-1 Open Source)
- **URL**: https://github.com/JARVIS-Xs/SE-Agent (245 stars)
- **Technique**: Self-evolution framework avec 3 opérations :
  1. **Revision** : réflexion sur les échecs
  2. **Recombination** : fusion des segments performants
  3. **Refinement** : optimisation des trajectoires
- **NeurIPS 2025 poster**

### OpenHands
- **URL**: https://github.com/All-Hands-AI/OpenHands (70.3K stars)
- **Score**: 77.6%
- **Utilisateurs**: TikTok, VMware, Amazon, Netflix, Apple, NVIDIA, Google

### SWE-agent
- **URL**: https://github.com/SWE-agent/SWE-agent (18.9K stars)
- **Config**: Single YAML file
- **Modèles**: GPT-4o, Claude Sonnet 4

## Key Takeaways for Enterprise
- **Les agents codeurs résolvent ~80% des vraies issues GitHub** - c'est production-ready
- **Tendance** : systèmes agentiques avec self-evolution et exploration multi-trajectoire
- **Open source compétitif** : OpenHands et SWE-agent livrent des résultats comparables aux solutions propriétaires
- **MMLU et HumanEval sont saturés** (~93% et ~99%) : SWE-bench est le nouveau discriminant

## References
- [swebench.com](https://www.swebench.com)
- [GitHub](https://github.com/SWE-bench/SWE-bench)
- [SE-Agent](https://github.com/JARVIS-Xs/SE-Agent)
- [OpenHands](https://github.com/All-Hands-AI/OpenHands)
