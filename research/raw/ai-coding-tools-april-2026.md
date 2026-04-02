# AI Code Generation & Development Tools - Comprehensive Research
> Research date: 2026-04-01 | Sources: GitHub repositories, product pages, awesome-lists

---

## TIER 1: Major AI Code Editors & IDEs

### 1. Cursor
| Field | Value |
|-------|-------|
| **URL** | https://cursor.com |
| **GitHub** | https://github.com/getcursor/cursor (issue tracker only) |
| **Stars** | 32.6k |
| **License** | Proprietary (commercial product) |
| **Pricing** | Free (limited) / Pro $20/mo / Business $40/mo |
| **Status** | Active |
| **Maturity** | Production |

**Description:** AI-first code editor built as a VS Code fork. Features include Tab (intelligent autocomplete), Chat (conversational coding), Agent mode (multi-file autonomous coding), Composer (multi-file generation), and 30+ partner plugins. Cloud-based agents for background task execution.

**Key Features:**
- AI-powered Tab completion with multi-line predictions
- Agent mode for autonomous multi-file editing
- Composer for generating/editing across multiple files simultaneously
- Chat with codebase context (@codebase, @file, @folder references)
- Background cloud agents for long-running tasks
- Built on VS Code (full extension compatibility)
- Multi-model support (Claude, GPT-4, Gemini, etc.)
- 30+ partner plugins ecosystem

---

### 2. GitHub Copilot
| Field | Value |
|-------|-------|
| **URL** | https://github.com/features/copilot |
| **GitHub** | Integrated into github.com |
| **Stars** | N/A (proprietary service) |
| **License** | Proprietary |
| **Pricing** | Free (2k completions + 50 chats/mo) / Pro $20/mo / Pro+ $30/mo / Business $30/user/mo / Enterprise $39/user/mo |
| **Status** | Active |
| **Maturity** | Enterprise |

**Description:** GitHub's AI pair programmer integrated across the development lifecycle. Provides inline code suggestions, chat, code review, agent mode, and Copilot Spaces for organizing project context. Supports models from OpenAI, Anthropic (Claude Opus 4.6), and Google (Gemini).

**Key Features:**
- Agent Mode: analyzes code, proposes edits, runs tests, validates results across files
- Copilot Spaces: shared project context (code, docs, notes) as source of truth
- Code Review: automated PR review integrated in GitHub
- Edit Suggestions: ripple-effect detection across projects
- Multi-model selection (Anthropic Claude Opus 4.6, OpenAI GPT, Google Gemini)
- IDE support: VS Code, JetBrains, Visual Studio, Vim/Neovim, GitHub CLI
- Copilot coding agent for Pro/Business/Enterprise plans
- CLI access included in free tier
- 75% higher developer satisfaction, 55% more productive (reported)

---

### 3. Windsurf (by Codeium)
| Field | Value |
|-------|-------|
| **URL** | https://windsurf.com |
| **GitHub** | No public repo (proprietary) |
| **Stars** | N/A |
| **License** | Proprietary |
| **Pricing** | Free tier / Pro ~$15/mo (estimated) |
| **Status** | Active |
| **Maturity** | Production |

**Description:** Agentic IDE from Codeium (acquired by Google/OpenAI competitor) with Cascade -- a multi-step coding agent that maintains context across complex workflows. Features real-time AI assistance, deep codebase understanding, and agentic coding capabilities.

**Key Features:**
- Cascade: multi-step agentic coding with deep context
- Real-time AI code assistance and completion
- Agentic IDE design (not just autocomplete)
- Codebase-wide understanding and navigation
- Available as standalone editor and VS Code extension

---

### 4. Zed
| Field | Value |
|-------|-------|
| **URL** | https://zed.dev |
| **GitHub** | https://github.com/zed-industries/zed |
| **Stars** | 78.3k |
| **License** | Multi-licensed (AGPL / Apache / GPL-3.0) |
| **Pricing** | Free (open source) |
| **Status** | Active |
| **Maturity** | Production |

**Description:** High-performance multiplayer code editor built in Rust by the creators of Atom and Tree-sitter. Integrates AI agent capabilities, Copilot support, and real-time collaboration. Cross-platform (macOS, Linux, Windows).

**Key Features:**
- Blazing fast performance (Rust-native)
- Multiplayer real-time collaboration
- AI agent integration (Copilot, model selection)
- Code review with AI-assisted suggestions
- Extension ecosystem
- 36,592+ commits, very active development

---

### 5. Amazon Kiro
| Field | Value |
|-------|-------|
| **URL** | https://kiro.dev |
| **GitHub** | N/A |
| **Stars** | N/A |
| **License** | Proprietary |
| **Pricing** | Free tier available with AWS integration |
| **Status** | Active |
| **Maturity** | Production |

**Description:** Amazon's spec-driven AI development IDE with deep AWS integration. Emphasizes specification-first development where AI generates code from structured requirements documents.

**Key Features:**
- Spec-driven development workflow
- Deep AWS service integration
- AI-powered code generation from specifications
- Cloud-first development environment

---

### 6. Google Antigravity
| Field | Value |
|-------|-------|
| **URL** | https://antigravity.google |
| **GitHub** | N/A |
| **Stars** | N/A |
| **License** | Proprietary (Free) |
| **Pricing** | Free multi-agent orchestration platform |
| **Status** | Active (New - late 2025/early 2026) |
| **Maturity** | Beta/Production |

**Description:** Google's free multi-agent orchestration AI coding platform. Emerged as a major competitor in the AI IDE space.

---

## TIER 2: Terminal-Based AI Coding Agents

### 7. Claude Code (by Anthropic)
| Field | Value |
|-------|-------|
| **URL** | https://code.claude.com |
| **GitHub** | https://github.com/anthropics/claude-code |
| **Stars** | 95.1k |
| **License** | MIT |
| **Pricing** | Included with Claude Pro/Team/Enterprise subscriptions |
| **Status** | Active |
| **Maturity** | Production |

**Description:** Anthropic's agentic coding tool that lives in the terminal, understands codebases, and helps code faster through natural language. Handles routine tasks, explains complex code, manages git workflows. Works in terminal, IDE, or via @claude on GitHub.

**Key Features:**
- Terminal-based agentic coding with natural language
- Full codebase understanding and navigation
- Git workflow automation (commits, PRs, branches)
- IDE integration (VS Code, JetBrains)
- GitHub integration (@claude mentions)
- Plugin/extension ecosystem
- MCP (Model Context Protocol) support
- Multi-platform: macOS, Linux, Windows
- Installation via curl, Homebrew, WinGet, or npm

**Installation:**
```bash
# macOS/Linux
curl -fsSL https://claude.ai/install.sh | bash
# Windows
irm https://claude.ai/install.ps1 | iex
# Homebrew
brew install --cask claude-code
# WinGet
winget install Anthropic.ClaudeCode
```

---

### 8. OpenAI Codex CLI
| Field | Value |
|-------|-------|
| **URL** | https://github.com/openai/codex |
| **GitHub** | https://github.com/openai/codex |
| **Stars** | 70.8k |
| **License** | Apache-2.0 |
| **Pricing** | Included with ChatGPT Plus/Pro/Team/Enterprise |
| **Status** | Active |
| **Maturity** | Production |

**Description:** OpenAI's lightweight terminal coding agent. Runs locally, integrates with ChatGPT plans. Built primarily in Rust (94.7%) for performance. Supports integration with VS Code, Cursor, and Windsurf.

**Key Features:**
- Local-first terminal agent
- Rust-based for high performance
- Multi-platform (macOS, Linux)
- ChatGPT plan integration (Plus, Pro, Team, Enterprise)
- IDE integration support
- Latest version: v0.118.0 (March 2026)
- 4,981 commits, very active development

---

### 9. Gemini CLI (by Google)
| Field | Value |
|-------|-------|
| **URL** | https://github.com/google-gemini/gemini-cli |
| **GitHub** | https://github.com/google-gemini/gemini-cli |
| **Stars** | 99.8k |
| **License** | Apache 2.0 |
| **Pricing** | Free (60 req/min, 1000 req/day with Google account) |
| **Status** | Active |
| **Maturity** | Production |

**Description:** Google's open-source terminal AI agent bringing Gemini directly into the terminal. Offers generous free tier, 1M token context window, built-in tools, and MCP extensibility. The most starred AI coding CLI tool.

**Key Features:**
- Generous free tier (60 req/min, 1000 req/day)
- Gemini 3 models with 1M token context window
- Built-in tools: Google Search, file ops, shell commands, web fetch
- MCP (Model Context Protocol) support
- Conversation checkpointing (save/resume)
- GitHub Actions integration
- Multimodal: PDFs, images, sketches
- Multiple auth: Google OAuth, API keys, Vertex AI
- Release channels: Stable (weekly), Preview, Nightly

---

### 10. Aider
| Field | Value |
|-------|-------|
| **URL** | https://aider.chat |
| **GitHub** | https://github.com/paul-gauthier/aider |
| **Stars** | 42.6k |
| **License** | Apache-2.0 |
| **Pricing** | Free (open source, BYOK for LLM APIs) |
| **Status** | Active |
| **Maturity** | Production |

**Description:** AI pair programming tool in the terminal. Git-first approach with automatic commits. Supports cloud and local LLMs. Works across 100+ programming languages. Top 20 app on OpenRouter. 88% of its own code written by Aider itself.

**Key Features:**
- Git-first with automatic commits and sensible messages
- 100+ programming language support
- Cloud & local LLM support (Claude 3.7 Sonnet, DeepSeek, GPT-4o, o1, o3-mini)
- Automatic codebase mapping for large projects
- IDE integration via code comments
- Image and web page attachment support
- Voice-to-code functionality
- Automated linting, testing, and error fixing
- 5.7M+ PyPI installations, 15B tokens/week
- Latest: v0.86.0 (August 2025)

---

### 11. Crush (by Charm, successor to OpenCode)
| Field | Value |
|-------|-------|
| **URL** | https://github.com/charmbracelet/crush |
| **GitHub** | https://github.com/charmbracelet/crush |
| **Stars** | 22.3k |
| **License** | See LICENSE.md |
| **Pricing** | Free (open source, BYOK) |
| **Status** | Active |
| **Maturity** | Production |

**Description:** "Glamorous agentic coding assistant for the terminal" by Charm (creators of Bubble Tea TUI framework). Successor to OpenCode (archived at 11.7k stars). Enterprise-ready, built on the Charm ecosystem supporting 25,000+ applications. Cross-platform including Android, FreeBSD, and OpenBSD.

**Key Features:**
- Multi-model support with mid-session switching
- Session-based architecture with multiple work contexts
- LSP (Language Server Protocol) integration
- MCP server support (stdio, HTTP, SSE)
- Cross-platform: macOS, Linux, Windows, Android, FreeBSD, OpenBSD, NetBSD
- Agent Skills standard support
- Enterprise-ready via Charm ecosystem
- Install via Homebrew, NPM, Debian/RPM, Go, binary downloads

---

### 12. Plandex
| Field | Value |
|-------|-------|
| **URL** | https://plandex.ai |
| **GitHub** | https://github.com/plandex-ai/plandex |
| **Stars** | 15.2k |
| **License** | MIT |
| **Pricing** | Free (open source, BYOK) |
| **Status** | Active |
| **Maturity** | Production |

**Description:** Terminal-based AI development platform for large coding tasks spanning many steps and dozens of files. Handles up to 2M tokens of context. Features sandbox environment for reviewing changes before applying.

**Key Features:**
- 2M token context capacity
- Tree-sitter project mapping (30+ languages)
- Full autonomy mode with configurable control levels
- Multi-model: Claude, GPT-4, Google, open-source models
- Automated terminal + browser debugging (Chrome)
- Built-in branching, commit generation, Git integration
- Sandbox: cumulative diff review before applying
- Written in Go (93.4%)
- Latest: cli/v2.2.1 (July 2025)

---

## TIER 3: VS Code Extensions & IDE Plugins

### 13. Cline (formerly Claude Dev)
| Field | Value |
|-------|-------|
| **URL** | https://cline.bot |
| **GitHub** | https://github.com/cline/cline |
| **Stars** | 59.7k |
| **License** | Apache 2.0 |
| **Pricing** | Free (open source, BYOK for API costs) |
| **Status** | Active |
| **Maturity** | Production |

**Description:** Autonomous coding agent integrated into VS Code. Can create/edit files, execute terminal commands, use a browser, and extend via MCP. Originally "Claude Dev", now supports multiple AI providers.

**Key Features:**
- Multi-API: OpenRouter, Anthropic, OpenAI, Google Gemini, AWS Bedrock, Azure, GCP Vertex, Cerebras, Groq
- Terminal command execution with VS Code shell integration
- File creation/editing with diff previews
- Browser automation with screenshot + console log capture
- Custom MCP tool creation
- Context: @url, @problems, @file, @folder commands
- Workspace checkpoints for comparing/restoring states
- Token and API cost tracking
- 5,042 commits, very active development

---

### 14. Roo Code
| Field | Value |
|-------|-------|
| **URL** | https://roocode.com |
| **GitHub** | https://github.com/RooVetGit/Roo-Code |
| **Stars** | 22.9k |
| **License** | Apache 2.0 |
| **Pricing** | Free (open source, BYOK) |
| **Status** | Active |
| **Maturity** | Production |

**Description:** AI-powered VS Code extension providing autonomous development agents with multiple specialized modes. Features Boomerang task automation for orchestrating complex multi-step workflows.

**Key Features:**
- Multiple modes: Code, Architect, Ask, Debug, Custom
- Boomerang task automation
- MCP Server integration
- Support for latest models (GPT-5.4, GPT-5.3 added in v3.51.0)
- Skills as slash commands
- 17+ language localizations
- 7,037 commits, active development
- Latest: v3.51.1 (March 2026)

---

### 15. Continue.dev
| Field | Value |
|-------|-------|
| **URL** | https://continue.dev |
| **GitHub** | https://github.com/continuedev/continue |
| **Stars** | 32.2k |
| **License** | Apache 2.0 |
| **Pricing** | Free (open source) |
| **Status** | Active |
| **Maturity** | Production |

**Description:** Open-source AI code assistant with a focus on source-controlled AI checks enforceable in CI. Runs AI agents on PRs as GitHub status checks. Each agent defined as markdown files in `.continue/checks/`. Supports VS Code and JetBrains.

**Key Features:**
- AI-powered code review agents on every PR
- Source-controlled check definitions (markdown files)
- GitHub status check integration (green/red with suggested diffs)
- Open-source CLI tool (`cn` command)
- Security reviews, code quality checks, custom validations
- VS Code extension + JetBrains plugin
- Multi-platform (macOS, Linux, Windows)
- Latest: v1.2.22-vscode (March 27, 2026)
- 21,488 commits, 4.3k forks

---

### 16. Amazon Q Developer
| Field | Value |
|-------|-------|
| **URL** | https://aws.amazon.com/q/developer/ |
| **GitHub** | https://github.com/aws/aws-toolkit-vscode |
| **Stars** | 2,000+ (VS Code extension repo) |
| **License** | Apache 2.0 |
| **Pricing** | Free tier / Pro included with AWS subscriptions |
| **Status** | Active |
| **Maturity** | Enterprise |

**Description:** AWS's generative AI assistant for software development. Inline code suggestions, chat-based code generation, security vulnerability analysis, and Java application modernization. Deep AWS service integration.

**Key Features:**
- Inline code suggestions as you type
- Chat-based code generation and explanation
- Security scanning and vulnerability remediation
- Java application modernization
- Deep AWS service integration
- Available as VS Code extension and CLI
- 14,055+ commits, 427 releases

---

### 17. Tabby
| Field | Value |
|-------|-------|
| **URL** | https://tabby.tabbyml.com |
| **GitHub** | https://github.com/TabbyML/tabby |
| **Stars** | 33.3k |
| **License** | Open source (see repo) |
| **Pricing** | Free (self-hosted) |
| **Status** | Active |
| **Maturity** | Production |

**Description:** Open-source, self-hosted alternative to GitHub Copilot. Provides AI-powered code completion without requiring external cloud services or databases. Supports consumer-grade GPUs.

**Key Features:**
- Fully self-hosted, no cloud dependency
- No database required
- OpenAPI interface for infrastructure integration
- Consumer-grade GPU compatible
- Chat and answer engine
- Code browser with repository context
- GitLab Merge Request indexing (v0.30.0+)
- Written in Rust (92.9%)
- Latest: v0.32.0 (January 2026)

---

## TIER 4: Autonomous AI Software Engineers

### 18. Devin (by Cognition)
| Field | Value |
|-------|-------|
| **URL** | https://devin.ai |
| **GitHub** | N/A (proprietary) |
| **Stars** | N/A |
| **License** | Proprietary |
| **Pricing** | Team plan (contact sales) / Enterprise |
| **Status** | Active |
| **Maturity** | Production |

**Description:** Autonomous AI software engineer by Cognition Labs. Features integrated IDE, sandbox environment, browser, and terminal. Can plan, code, debug, and deploy independently. One of the first "AI software engineer" products.

**Key Features:**
- Fully autonomous software engineering
- Integrated IDE + sandbox + browser + terminal
- Planning, coding, debugging, and deployment
- Slack integration for task assignment
- Session-based work with persistent context

---

### 19. OpenHands (formerly OpenDevin)
| Field | Value |
|-------|-------|
| **URL** | https://www.all-hands.dev |
| **GitHub** | https://github.com/All-Hands-AI/OpenHands |
| **Stars** | 70.3k |
| **License** | MIT (enterprise directory: source-available) |
| **Pricing** | Free (open source) / Enterprise self-hosted |
| **Status** | Active |
| **Maturity** | Production/Enterprise |

**Description:** AI-driven development platform for autonomous software agents. Multiple interfaces: CLI, local GUI with React, cloud deployment with Slack/Jira/Linear integration. Enterprise option via Kubernetes. SWE-Bench score of 77.6.

**Key Features:**
- Software Agent SDK (composable Python library)
- CLI supporting Claude, GPT, and other LLMs
- Local GUI with REST API + React interface
- Cloud deployment with Slack, Jira, Linear integrations
- Enterprise self-hosted via Kubernetes
- Multi-user with RBAC and collaboration
- SWE-Bench: 77.6 (top performer)
- Used by TikTok, VMware, Amazon, Netflix, Apple, NVIDIA, Google
- Latest: v1.6.0 (March 30, 2026)

---

### 20. Goose (by Block)
| Field | Value |
|-------|-------|
| **URL** | https://block.github.io/goose |
| **GitHub** | https://github.com/block/goose |
| **Stars** | 33.9k |
| **License** | Apache-2.0 |
| **Pricing** | Free (open source, BYOK) |
| **Status** | Active |
| **Maturity** | Production |

**Description:** Local, extensible, open-source AI agent by Block (Square/Cash App) that automates engineering tasks. Goes beyond suggestions to autonomous execution of development workflows. Desktop app and CLI. Written primarily in Rust.

**Key Features:**
- Autonomous task execution across dev workflows
- Multi-LLM support with configurable model selection
- MCP server integration for extensibility
- Desktop application + CLI interfaces
- Code generation, testing, debugging
- External API interaction
- Cost optimization through multi-model config
- Rust-based (58.2%) + TypeScript (34.2%)
- Latest: v1.29.0 (March 31, 2026)
- 125 releases, 4,052 commits

---

### 21. SWE-agent
| Field | Value |
|-------|-------|
| **URL** | https://swe-agent.com |
| **GitHub** | https://github.com/SWE-agent/SWE-agent |
| **Stars** | 18.9k |
| **License** | MIT |
| **Pricing** | Free (open source) |
| **Status** | Active |
| **Maturity** | Production/Research |

**Description:** Autonomous software engineering tool enabling LLMs to automatically fix GitHub issues, identify cybersecurity vulnerabilities, and solve competitive coding challenges. State-of-the-art on SWE-bench among open-source tools.

**Key Features:**
- State-of-the-art SWE-bench performance (open source)
- Automatic GitHub issue fixing
- Cybersecurity vulnerability identification (EnIGMA mode)
- Single YAML configuration
- Multi-LLM: GPT-4o, Claude Sonnet 4
- Research-focused, hackable architecture
- mini-SWE-agent available as simpler alternative
- Latest: v1.1.0 (May 2025)

---

## TIER 5: AI Full-Stack App Builders

### 22. bolt.new (by StackBlitz)
| Field | Value |
|-------|-------|
| **URL** | https://bolt.new |
| **GitHub** | https://github.com/stackblitz/bolt.new |
| **Stars** | 16.3k |
| **License** | MIT |
| **Pricing** | Freemium (hosted service) |
| **Status** | Active |
| **Maturity** | Production |

**Description:** AI-powered web development agent for building, running, editing, and deploying full-stack applications directly in the browser. Uses StackBlitz WebContainers -- no local setup required.

**Key Features:**
- Full-stack browser development (no local setup)
- StackBlitz WebContainers integration
- AI controls filesystem, Node.js server, package manager, terminal
- Production deployment from chat interface
- Project sharing via URL
- JavaScript framework support
- TypeScript-based (89.9%)

---

### 23. bolt.diy (Open Source bolt.new)
| Field | Value |
|-------|-------|
| **URL** | https://github.com/stackblitz-labs/bolt.diy |
| **GitHub** | https://github.com/stackblitz-labs/bolt.diy |
| **Stars** | 19.2k |
| **License** | Open source |
| **Pricing** | Free (BYOK for LLM APIs) |
| **Status** | Active |
| **Maturity** | Production |

**Description:** Open-source version of bolt.new allowing use of any LLM provider. Prompt, run, edit, and deploy full-stack web applications. Available as Electron desktop app.

**Key Features:**
- 19+ AI Provider integrations (OpenAI, Anthropic, Google, Groq, xAI, DeepSeek, Mistral, etc.)
- Electron desktop application
- Advanced deployment (Netlify, Vercel, GitHub Pages)
- Integrated terminal and version history
- File locking and diff view
- Git integration with clone/deploy
- MCP support
- Supabase database integration
- Voice prompting
- 1,629 commits

---

### 24. Lovable (formerly GPT Engineer)
| Field | Value |
|-------|-------|
| **URL** | https://lovable.dev |
| **GitHub** | N/A (proprietary service) |
| **Stars** | N/A |
| **License** | Proprietary |
| **Pricing** | Freemium |
| **Status** | Active |
| **Maturity** | Production |

**Description:** "Idea to app in seconds." Browser-based AI app builder that generates full-stack applications from single prompts. Formerly known as GPT Engineer. Positioned as a "superhuman full stack engineer."

**Key Features:**
- Single-prompt app generation
- Browser-based development and deployment
- Full-stack application building
- Natural language to working application
- Rapid prototyping and MVP creation

---

### 25. Replit Agent
| Field | Value |
|-------|-------|
| **URL** | https://replit.com |
| **GitHub** | N/A (proprietary) |
| **Stars** | N/A |
| **License** | Proprietary |
| **Pricing** | Free tier / Replit Core ~$25/mo |
| **Status** | Active |
| **Maturity** | Production |

**Description:** Agent-driven development platform in Replit's cloud IDE. Advanced AI agent capable of building complete applications, managing deployments, and handling full development workflows in the browser.

**Key Features:**
- Browser-based cloud development environment
- AI agent for complete application building
- Automatic deployment and hosting
- Collaborative multiplayer editing
- Database provisioning
- Mobile app support

---

### 26. v0 by Vercel
| Field | Value |
|-------|-------|
| **URL** | https://v0.dev |
| **GitHub** | N/A (proprietary) |
| **Stars** | N/A |
| **License** | Proprietary |
| **Pricing** | Freemium |
| **Status** | Active |
| **Maturity** | Production |

**Description:** Vercel's AI-powered tool for generating Next.js production applications and UI components from text prompts. Specializes in React/Next.js with Tailwind CSS and shadcn/ui.

**Key Features:**
- Next.js production app generation
- React component generation from text/images
- shadcn/ui + Tailwind CSS integration
- Real-time preview
- One-click Vercel deployment
- Chat-based iterative refinement

---

### 27. Firebase Studio (by Google)
| Field | Value |
|-------|-------|
| **URL** | https://studio.firebase.google.com |
| **GitHub** | N/A |
| **Stars** | N/A |
| **License** | Proprietary (Free) |
| **Pricing** | Free with Google Cloud |
| **Status** | Active (New - 2025/2026) |
| **Maturity** | Production |

**Description:** Google's full-stack AI development environment. Cloud-based IDE with AI assistance, integrated with Firebase services for backend, hosting, and database.

---

## TIER 6: Code Review & PR Agents

### 28. Qodo PR Agent (formerly CodiumAI)
| Field | Value |
|-------|-------|
| **URL** | https://www.qodo.ai |
| **GitHub** | https://github.com/Codium-ai/pr-agent |
| **Stars** | 10.7k |
| **License** | AGPL-3.0 |
| **Pricing** | Free (open source) / Qodo Pro (paid) |
| **Status** | Active |
| **Maturity** | Production |

**Description:** The original open-source PR reviewer. AI-powered code review agent supporting GitHub, GitLab, Bitbucket, Azure DevOps, and Gitea. Commands: /review, /describe, /improve, /ask.

**Key Features:**
- Automated PR review with slash commands
- Multi-platform: GitHub, GitLab, Bitbucket, Azure DevOps, Gitea
- Multiple deployment: CLI, GitHub Actions, Docker, webhooks
- Multi-model: OpenAI GPT, Claude, Deepseek
- PR compression for any size
- RAG context enrichment
- Latest: v0.33 (March 29, 2026)
- 4,894 commits, 209 contributors

---

## TIER 7: Multi-Agent Orchestration & Infrastructure

### 29. Superset
| Field | Value |
|-------|-------|
| **URL** | https://github.com/superset-sh/superset |
| **GitHub** | https://github.com/superset-sh/superset |
| **Stars** | 8.4k |
| **License** | Elastic License 2.0 |
| **Pricing** | Free (open source) |
| **Status** | Active (New - 2026) |
| **Maturity** | Beta/Production |

**Description:** Desktop code editor for orchestrating multiple CLI-based coding agents in parallel. "Orchestrate swarms of Claude Code, Codex, and more." Each task runs in isolated git worktree branches.

**Key Features:**
- Parallel execution of 10+ coding agents simultaneously
- Git worktree isolation per task
- Agent monitoring with notifications
- Built-in diff viewer for reviewing changes
- IDE integration (one-click open)
- Workspace presets for environment setup
- Supports: Claude Code, Cursor Agent, Copilot, Codex CLI, Gemini CLI
- Electron + React + TailwindCSS

---

### 30. Suna (by Kortix)
| Field | Value |
|-------|-------|
| **URL** | https://github.com/kortix-ai/suna |
| **GitHub** | https://github.com/kortix-ai/suna |
| **Stars** | 19.6k |
| **License** | Open source |
| **Pricing** | Free (self-hosted) |
| **Status** | Active |
| **Maturity** | Production |

**Description:** Comprehensive platform for creating autonomous AI agents. Features browser automation, file management, web intelligence, system operations, and API integrations. Agents run in isolated Docker environments.

**Key Features:**
- Browser automation (navigation, data extraction, forms)
- File management (documents, spreadsheets, format conversion)
- Web crawling and intelligence synthesis
- System operations and DevOps automation
- API integrations across platforms
- Agent builder for configuration/deployment
- Isolated Docker runtime with security sandboxing
- Supabase backend (auth, storage, real-time)
- 6,260 commits

---

## TIER 8: Additional Notable Tools

### 31. GPT Pilot (by Pythagora) - ARCHIVED
| Field | Value |
|-------|-------|
| **GitHub** | https://github.com/Pythagora-io/gpt-pilot |
| **Stars** | 33.8k |
| **License** | See LICENSE |
| **Status** | Archived (no longer maintained, redirected to Pythagora.ai) |

**Description:** Was the first "real AI developer companion" with multi-agent architecture. Featured specialized agents (Spec Writer, Architect, Tech Lead, Developer, Reviewer, Debugger, Tech Writer). Now maintained as Pythagora.ai commercial product.

---

### 32. Aide (by nicepkg) - VS Code Extension
| Field | Value |
|-------|-------|
| **GitHub** | https://github.com/nicepkg/aide |
| **Stars** | 2.7k |
| **License** | MIT |
| **Pricing** | Free |
| **Status** | Active |
| **Maturity** | Production |

**Description:** VS Code extension for AI-enhanced development. One-click comments, code conversion, UI-to-code, and AI batch processing.

---

### 33. Aide (by CodeStory) - AI-Native IDE - ARCHIVED
| Field | Value |
|-------|-------|
| **GitHub** | https://github.com/codestoryai/aide |
| **Stars** | 2.2k |
| **License** | AGPL-3.0 |
| **Status** | Archived (February 2025) |

**Description:** Was an open-source AI-native IDE (VS Code fork). Featured proactive AI agents, inline editing, AST navigation. No longer maintained.

---

### 34. smolagents (by HuggingFace)
| Field | Value |
|-------|-------|
| **GitHub** | https://github.com/huggingface/smolagents |
| **Stars** | 26.4k |
| **License** | Apache-2.0 |
| **Pricing** | Free (open source) |
| **Status** | Active |
| **Maturity** | Production |

**Description:** Lightweight Python library for building AI agents that write actions as executable code. Core agent logic ~1,000 lines. LLM-agnostic supporting 100+ providers via LiteLLM. Sandbox support via E2B, Docker, WASM.

---

### 35. GPTScript
| Field | Value |
|-------|-------|
| **GitHub** | https://github.com/gptscript-ai/gptscript |
| **Stars** | 3.3k |
| **License** | Apache 2.0 |
| **Pricing** | Free |
| **Status** | Active |

**Description:** Framework for LLMs to interact with systems via prompt-based scripts. Chat with CLI tools, OpenAPI endpoints, local files. Written in Go.

---

## NEW TOOLS (Late 2025 / Early 2026)

### 36. Manus
| **URL** | https://manus.im |
**Description:** End-to-end project automation agent. Handles complete project workflows from planning to delivery.

### 37. Emergent
| **URL** | https://emergent.sh |
**Description:** Multi-agent autonomous app builder. Uses multiple AI agents collaborating to build applications.

### 38. Tempo
| **URL** | https://tempo.new |
**Description:** React development platform with visual IDE and Figma integration. AI-assisted React component building.

### 39. Dyad
| **URL** | https://dyad.sh |
**Description:** Free, open-source desktop app builder supporting local models via Ollama. Privacy-focused local development.

### 40. Agent Deck
| **GitHub** | https://github.com/asheshgoplani/agent-deck |
| **Stars** | 1.8k |
**Description:** Terminal session manager for AI coding agents. One TUI for Claude Code, Gemini CLI, OpenCode, Codex, and more.

### 41. JunieAI (by JetBrains)
**Description:** JetBrains' intelligent AI planner integrated into JetBrains IDEs. Specification-driven development with deep IDE integration.

### 42. Rovo Dev (by Atlassian)
**Description:** Atlassian's terminal AI agent for development workflows. Integrates with Jira and Atlassian ecosystem.

### 43. Command.new
| **URL** | https://command.new |
**Description:** AI agents, apps, and APIs generated from prompts. Browser-based full-stack development platform.

---

## COMPARISON: Top Terminal AI Coding Agents (April 2026)

| Dimension | Claude Code | Codex CLI | Gemini CLI | Aider | Crush | Goose |
|-----------|-------------|-----------|------------|-------|-------|-------|
| **GitHub Stars** | 95.1k | 70.8k | 99.8k | 42.6k | 22.3k | 33.9k |
| **License** | MIT | Apache-2.0 | Apache 2.0 | Apache-2.0 | See repo | Apache-2.0 |
| **Pricing** | Claude sub | ChatGPT sub | Free | Free (BYOK) | Free (BYOK) | Free (BYOK) |
| **Primary Lang** | Shell/Python/TS | Rust | (not specified) | Python | Go/TS | Rust/TS |
| **MCP Support** | Yes | Unknown | Yes | No | Yes | Yes |
| **Multi-Model** | Claude only | OpenAI only | Gemini only | Yes (any) | Yes (any) | Yes (any) |
| **Git Integration** | Deep | Basic | Basic | Deep | Session-based | Basic |
| **IDE Integration** | VS Code, JetBrains | VS Code, Cursor | GitHub Actions | Via comments | Terminal-only | Desktop + CLI |
| **Best For** | Anthropic users | OpenAI users | Google users | BYOK flexibility | Beautiful TUI | Block ecosystem |

## COMPARISON: Top AI Code Editors (April 2026)

| Dimension | Cursor | Windsurf | Zed | VS Code + Copilot |
|-----------|--------|----------|-----|-------------------|
| **Stars** | 32.6k | N/A | 78.3k | N/A |
| **License** | Proprietary | Proprietary | AGPL/Apache | Proprietary |
| **Pricing** | Free/Pro $20 | Free/Pro ~$15 | Free | Free/Pro $20 |
| **Base** | VS Code fork | Proprietary | Rust-native | VS Code |
| **Agent Mode** | Yes (Composer) | Yes (Cascade) | Yes | Yes |
| **Multi-Model** | Yes | Yes | Limited | Yes |
| **Performance** | Good | Good | Excellent | Good |
| **Extensions** | VS Code compat | Limited | Own ecosystem | Full VS Code |
| **Best For** | AI-first dev | Agentic workflows | Performance | Ecosystem |

## COMPARISON: AI App Builders (April 2026)

| Dimension | bolt.new | bolt.diy | Lovable | v0 | Replit Agent |
|-----------|----------|----------|---------|-----|-------------|
| **Stars** | 16.3k | 19.2k | N/A | N/A | N/A |
| **License** | MIT | Open source | Proprietary | Proprietary | Proprietary |
| **Pricing** | Freemium | Free (BYOK) | Freemium | Freemium | Free/Core $25 |
| **Self-Host** | No | Yes | No | No | No |
| **LLM Choice** | Fixed | 19+ providers | Fixed | Fixed | Fixed |
| **Deploy** | StackBlitz | Netlify/Vercel/GH | Built-in | Vercel | Replit |
| **Best For** | Quick prototypes | BYOK flexibility | Non-technical | React/Next.js | Full IDE |

---

## STAR RANKINGS (GitHub Stars, April 2026)

1. **Gemini CLI** - 99.8k stars
2. **Claude Code** - 95.1k stars
3. **Zed** - 78.3k stars
4. **OpenAI Codex CLI** - 70.8k stars
5. **OpenHands** - 70.3k stars
6. **Cline** - 59.7k stars
7. **Aider** - 42.6k stars
8. **Goose** - 33.9k stars
9. **GPT Pilot** - 33.8k stars (archived)
10. **Tabby** - 33.3k stars
11. **Cursor** - 32.6k stars
12. **Continue.dev** - 32.2k stars
13. **smolagents** - 26.4k stars
14. **Roo Code** - 22.9k stars
15. **Crush** - 22.3k stars
16. **Suna** - 19.6k stars
17. **bolt.diy** - 19.2k stars
18. **SWE-agent** - 18.9k stars
19. **bolt.new** - 16.3k stars
20. **Plandex** - 15.2k stars

---

## KEY TRENDS (April 2026)

1. **Terminal agents dominate**: Claude Code, Codex CLI, Gemini CLI all near/above 70k stars. The "big three" each tied to their parent LLM provider.

2. **Multi-agent orchestration emerging**: Tools like Superset (8.4k stars) let developers run 10+ agents in parallel with git worktree isolation.

3. **MCP as standard protocol**: Model Context Protocol has become the de facto standard for extending AI coding tools. Supported by Claude Code, Gemini CLI, Cline, Roo Code, Crush, Goose, Continue, bolt.diy.

4. **BYOK (Bring Your Own Key) model**: Open-source tools like Aider, Crush, Roo Code, and bolt.diy let users choose any LLM provider, while vendor tools (Claude Code, Codex, Gemini CLI) lock to their own models.

5. **IDE convergence**: Cursor, Windsurf, and Zed compete as AI-first editors, while VS Code + extensions (Cline, Roo Code, Continue, Copilot) remain the dominant platform.

6. **Autonomous agents maturing**: Devin, OpenHands (SWE-Bench 77.6), and SWE-agent represent the frontier of fully autonomous coding. Enterprise adoption growing.

7. **App builders proliferate**: bolt.new/bolt.diy, Lovable, v0, Replit Agent, Firebase Studio, and newcomers like Manus, Emergent, and Tempo target non-developers and rapid prototyping.

8. **Free tiers expanding**: Gemini CLI offers 60 req/min free, GitHub Copilot has a free plan, Google Antigravity is free. Competition driving generous free offerings.

9. **Rust rising**: Codex CLI (94.7% Rust), Zed (97.6% Rust), Tabby (92.9% Rust), Goose (58.2% Rust) -- performance-critical tools increasingly built in Rust.

10. **"Vibe coding" culture**: The emergence of awesome-vibe-coding (3.8k stars), vibe-kanban, and vibe-log-cli signal a cultural shift toward AI-collaborative development as a mainstream practice.

---

## Sources & URLs
- https://github.com/anthropics/claude-code
- https://github.com/openai/codex
- https://github.com/google-gemini/gemini-cli
- https://github.com/paul-gauthier/aider
- https://github.com/cline/cline
- https://github.com/continuedev/continue
- https://github.com/getcursor/cursor
- https://github.com/features/copilot
- https://github.com/stackblitz/bolt.new
- https://github.com/stackblitz-labs/bolt.diy
- https://github.com/All-Hands-AI/OpenHands
- https://github.com/block/goose
- https://github.com/charmbracelet/crush
- https://github.com/zed-industries/zed
- https://github.com/RooVetGit/Roo-Code
- https://github.com/TabbyML/tabby
- https://github.com/plandex-ai/plandex
- https://github.com/SWE-agent/SWE-agent
- https://github.com/Codium-ai/pr-agent
- https://github.com/Pythagora-io/gpt-pilot
- https://github.com/kortix-ai/suna
- https://github.com/superset-sh/superset
- https://github.com/huggingface/smolagents
- https://github.com/filipecalegario/awesome-vibe-coding
- https://github.com/ai-for-developers/awesome-ai-coding-tools
- https://github.com/topics/ai-coding-assistant
