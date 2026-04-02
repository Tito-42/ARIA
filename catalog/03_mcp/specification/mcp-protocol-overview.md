# Model Context Protocol (MCP)

> Standard ouvert pour connecter les applications IA aux systèmes externes - le "USB-C de l'IA"

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 03_mcp |
| **URL** | https://modelcontextprotocol.io |
| **GitHub** | https://github.com/modelcontextprotocol/modelcontextprotocol |
| **Stars** | 7,678 (spec) / 82,700 (servers) |
| **License** | MIT |
| **Pricing** | Free (open source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
MCP (Model Context Protocol) est un standard ouvert créé par Anthropic pour connecter les applications IA aux sources de données, outils et workflows externes. Il standardise la façon dont les LLMs interagissent avec le monde extérieur, de la même manière qu'USB-C standardise les connexions physiques.

Adopté massivement par l'industrie : Claude, ChatGPT, VS Code, Cursor, JetBrains et des centaines d'autres applications supportent MCP.

## Key Features
- **Architecture Client-Server** : MCP Host (app IA) → MCP Client → MCP Server
- **Protocole JSON-RPC 2.0** : couche data standardisée
- **Transports** : Stdio (local) et Streamable HTTP (remote, avec SSE)
- **3 primitives serveur** : Tools (fonctions), Resources (données), Prompts (templates)
- **Primitives client** : Sampling (completions LLM), Elicitation (input utilisateur), Logging
- **Tasks** (experimental) : wrappers d'exécution durable
- **SDKs officiels** : Python, TypeScript, C#, Go, Java, Kotlin, PHP, Ruby

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | Standard adopté par tous les majeurs (Claude, ChatGPT, VS Code) |
| **Security** | 4 | Système de permissions, mais dépend de l'implémentation serveur |
| **Scalability** | 5 | HTTP transport pour déploiement distribué, multi-serveurs |
| **Support/Community** | 5 | Anthropic + Microsoft + Google + JetBrains + communauté massive |
| **Documentation** | 5 | modelcontextprotocol.io - docs exhaustives |
| **Integration Ease** | 5 | SDKs dans 8 langages, inspector visuel, centaines de serveurs prêts |

## Use Cases
1. **Connecter IA aux bases de données** : PostgreSQL, MongoDB, Redis via MCP
2. **Intégration outils dev** : GitHub, GitLab, Jira, Linear
3. **Browser automation** : Playwright, Puppeteer via MCP
4. **Communication** : Slack, Discord, Telegram, email
5. **Données entreprise** : Salesforce, SharePoint, Google Drive
6. **Monitoring** : Grafana, Sentry, DataDog

## SDKs Officiels

| SDK | GitHub | Stars | Collaborateur |
|-----|--------|-------|---------------|
| Python SDK | modelcontextprotocol/python-sdk | 22,445 | - |
| TypeScript SDK | modelcontextprotocol/typescript-sdk | 12,065 | - |
| Go SDK | modelcontextprotocol/go-sdk | 4,272 | Google |
| C# SDK | modelcontextprotocol/csharp-sdk | 4,159 | Microsoft |
| Java SDK | modelcontextprotocol/java-sdk | 3,323 | Spring AI |
| PHP SDK | modelcontextprotocol/php-sdk | 1,429 | PHP Foundation |
| Kotlin SDK | modelcontextprotocol/kotlin-sdk | 1,318 | JetBrains |
| Ruby SDK | modelcontextprotocol/ruby-sdk | 758 | - |

## Serveurs de Référence (Actifs)

| Serveur | Description |
|---------|-------------|
| Everything | Serveur de test/référence |
| Fetch | Récupération de contenu web |
| Filesystem | Opérations fichiers |
| Git | Opérations repository |
| Memory | Knowledge graph persistant |
| Sequential Thinking | Raisonnement structuré |
| Time | Fuseaux horaires |

## Getting Started
```bash
# Installer le SDK Python
pip install mcp

# Créer un serveur MCP minimal
cat > server.py << 'EOF'
from mcp.server import Server
from mcp.server.stdio import stdio_server

app = Server("my-server")

@app.tool()
async def hello(name: str) -> str:
    """Say hello to someone"""
    return f"Hello, {name}!"

async def main():
    async with stdio_server() as (read, write):
        await app.run(read, write)

if __name__ == "__main__":
    import asyncio
    asyncio.run(main())
EOF

# Tester avec MCP Inspector
npx @modelcontextprotocol/inspector
```

## Architecture / How It Works
```
┌──────────────────────────────────────────────┐
│                MCP Host                       │
│  (Claude Code / ChatGPT / VS Code / Custom)  │
│                                               │
│  ┌─────────┐  ┌─────────┐  ┌─────────┐      │
│  │ Client 1│  │ Client 2│  │ Client N│      │
│  └────┬────┘  └────┬────┘  └────┬────┘      │
└───────┼────────────┼────────────┼────────────┘
        │            │            │
   ┌────▼────┐  ┌────▼────┐  ┌────▼────┐
   │Server A │  │Server B │  │Server C │
   │(GitHub) │  │(Postgres)│ │(Slack)  │
   └─────────┘  └─────────┘  └─────────┘
```

## Strengths
- Standard universel adopté par toute l'industrie IA
- SDKs dans 8 langages avec collaborateurs majeurs
- 82,700 stars sur le repo servers (adoption massive)
- Communauté de centaines de serveurs communautaires
- MCP Inspector pour debugging visuel

## Limitations
- Sécurité dépendante de chaque implémentation serveur
- Pas de mécanisme d'authentification standardisé (en cours)
- Overhead réseau pour les transports HTTP
- Complexité accrue vs appels d'API directs

## Alternatives
| Tool | Key Difference |
|------|---------------|
| OpenAI Function Calling | Propriétaire OpenAI, pas de standard ouvert |
| LangChain Tools | Spécifique à LangChain, pas interopérable |
| Tool Use natif | Intégré aux API mais pas standardisé |

## References
- [Site officiel](https://modelcontextprotocol.io)
- [Spécification GitHub](https://github.com/modelcontextprotocol/modelcontextprotocol)
- [Serveurs de référence](https://github.com/modelcontextprotocol/servers)
- [MCP Inspector](https://github.com/modelcontextprotocol/inspector)
- [Awesome MCP Servers](https://github.com/wong2/awesome-mcp-servers)
- [Guide de construction](https://modelcontextprotocol.io/docs/develop/build-server)

## Notes
- Le repo awesome-mcp-servers (3,800 stars) référence des centaines de serveurs communautaires
- Organisation GitHub MCP : 39 repos au total
- Spec version actuelle : 2025-06-18
- Anthropic, Microsoft, Google, JetBrains, PHP Foundation sont tous contributeurs officiels
