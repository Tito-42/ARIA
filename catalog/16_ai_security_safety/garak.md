# Garak (NVIDIA)

> Scanner de vulnérabilités LLM — tests automatisés pour hallucinations, toxicité, data leakage. Activité ralentie.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 16 - AI Security & Safety / Vulnerability Scanning |
| **URL** | https://github.com/NVIDIA/garak |
| **GitHub** | https://github.com/NVIDIA/garak |
| **Stars** | ~7,400 |
| **License** | Apache 2.0 |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Slowing |
| **Maturity** | Production |

## What It Does
Garak est un scanner de vulnérabilités LLM par NVIDIA. Il fournit une large bibliothèque d'attaques automatisées pour tester les hallucinations, la toxicité, le data leakage, le prompt injection, et d'autres vulnérabilités.

## Key Features
- **Large bibliothèque d'attaques**: Probes pour de nombreuses vulnérabilités
- **Framework extensible**: Créer ses propres probes
- **NVIDIA-backed**: Recherche NVIDIA
- **Multi-modèle**: Teste différents LLMs
- **Apache 2.0**: Licence permissive

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 3 | Bon mais ralenti |
| **Security** | 4 | Apache 2.0, NVIDIA |
| **Scalability** | 3 | CLI-based |
| **Support/Community** | 3 | 7.4k stars, mais **ralenti** |
| **Documentation** | 3 | Docs existantes |
| **Integration Ease** | 3 | CLI, Python |

## Use Cases
1. **Vulnerability scanning** — Scanner les vulnérabilités d'un LLM
2. **Model comparison** — Comparer la sécurité de différents modèles

## Getting Started
```bash
pip install garak
garak --model_type openai --model_name gpt-4 --probes all
```

## Strengths
- Large bibliothèque d'attaques
- NVIDIA-backed
- Apache 2.0

## Limitations
- **Activité ralentie** (dernier commit déc 2024)
- CLI uniquement (pas d'UI)
- Documentation parfois incomplète

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Promptfoo | **Plus actif**, UI, OWASP intégré |
| PyRIT | Microsoft, plus sophistiqué |

## References
- https://github.com/NVIDIA/garak
