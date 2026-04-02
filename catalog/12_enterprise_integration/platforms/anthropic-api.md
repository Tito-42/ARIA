# Anthropic API & SDKs

> API de Claude pour intégrer l'IA dans les applications enterprise

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 12_enterprise_integration |
| **URL** | https://docs.anthropic.com |
| **GitHub** | https://github.com/anthropics/anthropic-sdk-python |
| **Stars** | 3,075 (Python) / 1,789 (TypeScript) |
| **License** | MIT (SDKs) |
| **Pricing** | Paid (pay-per-token) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Enterprise |

## What It Does
L'API Anthropic permet d'intégrer les modèles Claude (Opus 4.6, Sonnet 4.6, Haiku 4.5) dans n'importe quelle application. Les SDKs officiels sont disponibles en Python, TypeScript, Ruby, C# et PHP. L'API supporte le chat, tool use, vision multimodale, extended thinking, streaming, batch processing et prompt caching.

## Key Features
- **Messages API** : interface conversationnelle principale
- **Tool Use / Function Calling** : appels de fonctions structurés
- **Extended Thinking** : raisonnement approfondi visible
- **Vision** : analyse d'images et documents
- **Streaming** : réponses en temps réel
- **Batch API** : traitement en masse à coût réduit
- **Prompt Caching** : réutilisation de contextes pour économiser des tokens
- **Modèles** : claude-opus-4-6, claude-sonnet-4-6, claude-haiku-4-5

## SDKs Officiels

| SDK | GitHub | Stars | Version |
|-----|--------|-------|---------|
| Python | anthropics/anthropic-sdk-python | 3,075 | v0.87.0 |
| TypeScript | anthropics/anthropic-sdk-typescript | 1,789 | v0.81.0 |
| Ruby | anthropics/anthropic-sdk-ruby | 312 | - |
| C# | anthropics/anthropic-sdk-csharp | 215 | - |
| PHP | anthropics/anthropic-sdk-php | 130 | - |

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | Utilisé par 46,900+ projets (Python SDK seul) |
| **Security** | 5 | SOC2, HIPAA eligible, enterprise agreements |
| **Scalability** | 5 | Rate limits enterprise, batch API, prompt caching |
| **Support/Community** | 5 | Support enterprise dédié + documentation exhaustive |
| **Documentation** | 5 | docs.anthropic.com - excellente |
| **Integration Ease** | 5 | SDKs natifs dans 5 langages, REST API standard |

## Use Cases
1. **Chatbots enterprise** : assistants conversationnels avec tool use
2. **Document processing** : extraction, résumé, classification
3. **Code generation** : intégration dans les IDEs et pipelines
4. **Data analysis** : analyse de données avec extended thinking
5. **Content moderation** : filtrage et classification de contenu

## Getting Started
```bash
# Python
pip install anthropic

# TypeScript
npm install @anthropic-ai/sdk
```

```python
import anthropic

client = anthropic.Anthropic()
message = client.messages.create(
    model="claude-sonnet-4-6-20250514",
    max_tokens=1024,
    messages=[{"role": "user", "content": "Hello, Claude!"}]
)
print(message.content[0].text)
```

## Strengths
- Modèles Claude parmi les plus performants du marché
- Extended thinking unique (raisonnement visible)
- SDKs MIT license
- Prompt caching pour optimisation des coûts
- Batch API pour traitement en masse

## Limitations
- Pas de modèle open source (API only)
- Coûts tokens peuvent être élevés pour gros volumes
- Rate limits sur les plans non-enterprise

## Alternatives
| Tool | Key Difference |
|------|---------------|
| OpenAI API | GPT-4o, plus de modèles spécialisés, prix similaires |
| Google Vertex AI | Gemini, intégration GCP native |
| AWS Bedrock | Multi-model (Claude inclus), intégration AWS |
| Azure OpenAI | GPT via Azure, compliance enterprise |

## References
- [Documentation API](https://docs.anthropic.com)
- [Claude Cookbooks](https://github.com/anthropics/claude-cookbooks) - 36,900 stars
- [Courses](https://github.com/anthropics/courses) - 20,100 stars
- [Prompt Engineering Tutorial](https://github.com/anthropics/prompt-eng-interactive-tutorial) - 34,300 stars
- [Claude Quickstarts](https://github.com/anthropics/claude-quickstarts) - 15,800 stars

## Notes
- Anthropic a 78 repos GitHub au total
- Financial Services Plugins (7,146 stars) : suite de plugins pour investissement, equity research, private equity, wealth management - inclut 41 skills, 38 commands, 11 intégrations MCP
- Claude Code Action (6,791 stars) : GitHub Action pour intégrer Claude dans les PRs
