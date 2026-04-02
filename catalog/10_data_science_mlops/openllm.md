# OpenLLM

> Plateforme pour servir des LLMs en production par BentoML — projet potentiellement stalled.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 10 - Data Science & MLOps / LLM Inference |
| **URL** | https://github.com/bentoml/OpenLLM |
| **GitHub** | https://github.com/bentoml/OpenLLM |
| **Stars** | ~12,300 |
| **License** | Apache 2.0 |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Stalled |
| **Maturity** | Beta |

## What It Does
OpenLLM est une plateforme de BentoML pour servir des LLMs en production. Il simplifie le déploiement de modèles open-source avec quantization, adapter support (LoRA), et intégration BentoML pour le packaging et le cloud deploy.

Cependant, le dernier release date d'avril 2025 et le projet montre des signes d'abandon silencieux. BentoML semble rediriger les efforts vers le core BentoML framework.

## Key Features
- **Multi-modèles**: Llama, Mistral, Falcon, et plus
- **Quantization**: GPTQ, AWQ support
- **LoRA adapters**: Chargement d'adapters fine-tunés
- **BentoML integration**: Packaging et déploiement cloud
- **API OpenAI-compatible**: REST API standard

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 2 | **Stalled** — dernier release avril 2025 |
| **Security** | 3 | Apache 2.0, self-hosted |
| **Scalability** | 3 | Via BentoML, mais pas maintenu |
| **Support/Community** | 2 | Projet potentiellement abandonné |
| **Documentation** | 3 | Docs existantes mais potentiellement obsolètes |
| **Integration Ease** | 3 | Simple si BentoML déjà utilisé |

## Use Cases
1. **Déploiements existants** — Maintenir des services OpenLLM en place
2. **Non recommandé** — Pour de nouveaux projets, utiliser vLLM, SGLang ou BentoML directement

## Getting Started
```bash
pip install openllm
openllm start meta-llama/Llama-3-8B-Instruct
```

## Architecture / How It Works
OpenLLM wrappe les backends d'inférence (vLLM, PyTorch) avec l'écosystème BentoML pour le packaging (Bento format), le versioning et le déploiement cloud.

## Strengths
- Simple à utiliser si on connaît BentoML
- Apache 2.0

## Limitations
- **Dernier release avril 2025** — risque d'abandon
- Surpassé par vLLM et SGLang en performance
- Communauté inactive

## Alternatives
| Tool | Key Difference |
|------|---------------|
| vLLM | **Recommandé** — Standard production, activement maintenu |
| SGLang | **Recommandé** — RadixAttention, en forte croissance |
| BentoML | Même équipe, plus activement maintenu |

## References
- https://github.com/bentoml/OpenLLM

## Notes
**ALERTE: Projet potentiellement abandonné.** Dernier release avril 2025. Ne pas utiliser pour de nouveaux projets. Si besoin de l'écosystème BentoML, utiliser BentoML directement avec vLLM comme backend.
