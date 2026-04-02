# Gemini CLI

> Agent IA terminal open source de Google avec tier gratuit généreux et contexte 1M tokens

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 01_code_generation |
| **URL** | https://github.com/google-gemini/gemini-cli |
| **GitHub** | https://github.com/google-gemini/gemini-cli |
| **Stars** | 99,800 |
| **License** | Apache 2.0 |
| **Pricing** | Free (60 req/min, 1000 req/day avec compte Google) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Gemini CLI est l'agent terminal IA open source de Google qui amène Gemini directement dans le terminal. Avec un tier gratuit très généreux (60 requêtes/min, 1000/jour), une fenêtre de contexte de 1M tokens et le support MCP, c'est devenu le CLI IA le plus étoilé sur GitHub (99.8K stars).

Il supporte les fichiers multimodaux (PDFs, images, sketches), s'intègre avec GitHub Actions, et offre des outils intégrés comme Google Search, opérations fichiers et shell.

## Key Features
- **Tier gratuit massif** : 60 req/min, 1000 req/day avec simple compte Google
- **Contexte 1M tokens** : via Gemini 3 models
- **Outils intégrés** : Google Search, file ops, shell commands, web fetch
- **MCP support** : extensibilité via Model Context Protocol
- **Checkpointing** : sauvegarde/reprise de conversations
- **GitHub Actions** : intégration CI/CD native
- **Multimodal** : PDFs, images, sketches
- **Multi-auth** : Google OAuth, API keys, Vertex AI
- **Release channels** : Stable (hebdo), Preview, Nightly

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | 99.8K stars, Google-backed, stable releases hebdo |
| **Security** | 4 | Google OAuth, Vertex AI enterprise auth |
| **Scalability** | 4 | Rate limits généreux, Vertex AI pour enterprise |
| **Support/Community** | 5 | Google backing + communauté massive |
| **Documentation** | 4 | README détaillé, docs Google AI |
| **Integration Ease** | 5 | npm install, MCP, GitHub Actions |

## Use Cases
1. **Développement quotidien** : coding assisté gratuit dans le terminal
2. **Analyse de gros projets** : contexte 1M tokens pour comprendre de larges codebases
3. **CI/CD** : intégration GitHub Actions pour review automatique
4. **Prototypage** : génération rapide de code multimodal (depuis sketches/images)

## Getting Started
```bash
npm install -g @anthropic-ai/gemini-cli
# ou
npx @anthropic-ai/gemini-cli
```

## Strengths
- Le plus étoilé des CLI IA (99.8K)
- Tier gratuit le plus généreux du marché
- Apache 2.0 (vrai open source)
- Contexte 1M tokens
- MCP support pour extensibilité

## Limitations
- Lié à l'écosystème Google/Gemini uniquement
- Pas d'Agent Teams comme Claude Code
- Hooks system moins mature
- Pas de desktop app native

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Claude Code | Écosystème plus riche (agent teams, hooks, skills) |
| OpenAI Codex CLI | Rust-based, écosystème OpenAI |
| Aider | Multi-model, git-first, plus ancien et éprouvé |

## References
- [GitHub](https://github.com/google-gemini/gemini-cli)
- [Google AI Developer docs](https://ai.google.dev)
