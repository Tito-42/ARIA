# Anthropic Skills (Agent Skills)

> Standard pour équiper les agents Claude de capacités spécialisées - le repo Anthropic le plus populaire (108K stars)

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 01_code_generation |
| **URL** | https://agentskills.io |
| **GitHub** | https://github.com/anthropics/skills |
| **Stars** | 108,000 |
| **License** | Apache 2.0 (skills) / Source-available (document skills) |
| **Pricing** | Free (open source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Agent Skills est un standard ouvert pour équiper les agents Claude de capacités spécialisées. Les skills sont des dossiers autonomes contenant des instructions et ressources que Claude charge dynamiquement selon le contexte. C'est le repo le plus populaire d'Anthropic avec 108K stars.

Les skills couvrent le design créatif, le développement technique, la communication enterprise, et le traitement de documents (DOCX, PDF, PPTX, XLSX).

## Key Features
- **Creative & Design** : skills pour design, UI/UX, création visuelle
- **Development & Technical** : skills de développement, debugging, architecture
- **Enterprise & Communication** : skills business, communication, reporting
- **Document Skills** : DOCX, PDF, PPTX, XLSX - lecture, création, modification
- **Auto-chargement** : Claude détecte et charge les skills pertinentes automatiquement
- **Extensible** : créer ses propres skills custom

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | 108K stars, utilisé massivement |
| **Security** | 4 | Skills en lecture seule, pas d'exécution arbitraire |
| **Scalability** | 5 | Skills modulaires, chargeables à la demande |
| **Support/Community** | 5 | Anthropic officiel + communauté massive |
| **Documentation** | 4 | agentskills.io + README détaillé |
| **Integration Ease** | 5 | Drop-in avec Claude Code, aucune config requise |

## Use Cases
1. **Document processing** : génération et modification de documents Office
2. **Custom workflows** : skills métier spécialisées pour chaque département
3. **Onboarding** : skills de formation et documentation interactive
4. **Reporting** : génération automatique de rapports structurés

## Getting Started
```bash
# Les skills sont automatiquement disponibles dans Claude Code
# Pour créer une skill custom :
mkdir -p .claude/skills/my-skill
echo "Instructions pour la skill..." > .claude/skills/my-skill/instructions.md
```

## Strengths
- Repo Anthropic le plus populaire au monde
- Standard ouvert (Apache 2.0)
- Intégration transparente avec Claude Code
- Extensible avec des skills custom

## Limitations
- Spécifique à l'écosystème Claude
- Document skills sous licence source-available (pas Apache)
- Skills limitées aux instructions textuelles (pas de code exécutable)

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Custom Prompts | Plus simple mais moins structuré |
| MCP Servers | Plus puissant (exécution de code) mais plus complexe |
| LangChain Tools | Multi-model mais moins intégré |

## References
- [agentskills.io](https://agentskills.io)
- [GitHub](https://github.com/anthropics/skills)
