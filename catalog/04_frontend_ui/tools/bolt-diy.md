# Bolt.diy

> Open-source, community-driven fork of Bolt.new that allows self-hosting and supports multiple LLM providers including local models.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 04_frontend_ui |
| **URL** | https://github.com/stackblitz-labs/bolt.diy |
| **GitHub** | https://github.com/stackblitz-labs/bolt.diy |
| **Stars** | ~19,200 |
| **License** | MIT |
| **Pricing** | Free (OSS) -- BYO API keys |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Growth |

## What It Does
Bolt.diy (formerly oTToDev) is the open-source, community-driven fork of Bolt.new that enables developers to self-host the full-stack AI development environment. While Bolt.new is a hosted service, Bolt.diy allows running the same WebContainer-based AI coding experience on your own infrastructure with your own API keys.

The project has grown rapidly (19.2K stars) driven by demand for a self-hostable alternative to Bolt.new that supports multiple LLM providers. Users can plug in OpenAI, Anthropic, Google, Groq, Mistral, OpenRouter, or local models via Ollama, making it highly flexible for teams with specific model preferences or data sovereignty requirements.

## Key Features
- **Self-hostable**: Run on your own infrastructure
- **Multi-provider LLM support**: OpenAI, Anthropic, Google, Groq, Mistral, OpenRouter, Ollama
- **Local model support**: Use Ollama for fully offline AI coding
- **BYOK (Bring Your Own Key)**: Use your own API keys
- **Full Bolt.new experience**: WebContainers, live preview, terminal, file system
- **Docker support**: Easy deployment via Docker containers
- **Community-driven**: Active development with community contributions
- **Customizable**: Modify prompts, UI, and behavior
- **Multi-framework**: Same framework support as Bolt.new

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 3 | Community-maintained; fast-moving |
| **Security** | 4 | Self-hosted; data stays on-premises |
| **Scalability** | 3 | Self-managed infrastructure |
| **Support/Community** | 4 | 19.2K stars; active community |
| **Documentation** | 3 | Community docs; some gaps |
| **Integration Ease** | 3 | Requires Docker/setup; more complex than hosted |

## Use Cases
1. **Self-hosted AI coding** - Organizations needing data sovereignty
2. **Custom LLM integration** - Teams using specific/local models
3. **Air-gapped environments** - With Ollama for fully offline usage
4. **Cost optimization** - Use cheaper models or self-hosted LLMs
5. **Customized workflows** - Modified prompts and UI for specific teams

## Getting Started
```bash
# Clone and run with Docker
git clone https://github.com/stackblitz-labs/bolt.diy
cd bolt.diy
docker-compose up

# Or run locally
npm install
npm run dev
```

## Strengths
- Self-hostable -- full data sovereignty
- Multi-provider flexibility including local models
- Active community with rapid development
- MIT license -- no restrictions
- Cost control via BYO API keys

## Limitations
- Community-maintained (no commercial support)
- May lag behind Bolt.new features
- Requires self-hosting infrastructure
- Setup more complex than hosted alternatives
- Some features may be unstable in development

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Bolt.new | Hosted; no setup; StackBlitz supported |
| OpenHands | More code-agent focused; Python-based |
| Cline | VS Code extension; terminal-based |
| Aider | Terminal-based; Git-integrated |

## References
- https://github.com/stackblitz-labs/bolt.diy
