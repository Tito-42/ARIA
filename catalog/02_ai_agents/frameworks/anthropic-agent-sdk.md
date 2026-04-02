# Anthropic Claude Agent SDK

> Official SDK for building AI agents powered by Claude with bidirectional conversations, custom tools, hooks, and MCP integration.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 02 - AI Agents |
| **URL** | https://platform.claude.com/docs/en/agent-sdk/python |
| **GitHub** | https://github.com/anthropics/claude-agent-sdk-python |
| **Stars** | 6,000 |
| **License** | MIT |
| **Pricing** | Free (OSS); requires Claude API access |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Beta/Production |

## What It Does
The Claude Agent SDK is Anthropic's official Python SDK for building AI agents powered by Claude. It provides a programmatic interface to Claude Code's agentic capabilities, enabling developers to build agents that can read/write files, execute bash commands, use custom tools, and orchestrate complex workflows -- all with Claude as the reasoning engine.

The SDK offers two main interfaces: a simple `query()` function for one-shot agent tasks, and `ClaudeSDKClient` for interactive, bidirectional conversations with full control over agent behavior. A key innovation is **in-process MCP servers** -- custom tools that run directly in the Python process without subprocess overhead, making tool integration simpler and faster.

The SDK also provides a powerful **hooks system** for intercepting and controlling agent behavior (e.g., blocking dangerous commands, requiring approval for file writes), making it suitable for production deployments where safety and control are critical.

## Key Features
- **Simple query interface**: One-line agent invocations with `query(prompt="...")`
- **Interactive conversations**: Bidirectional communication via `ClaudeSDKClient`
- **In-process MCP servers**: Custom tools running directly in Python (no subprocess overhead)
- **Hooks system**: Pre/post tool-use interception for safety and control
- **Full Claude Code toolset**: Read, Write, Edit, Bash, and all Claude Code tools
- **Permission controls**: `allowed_tools` and `disallowed_tools` for fine-grained access
- **Mixed MCP support**: Combine in-process SDK servers with external MCP servers
- **Streaming**: Real-time streaming of agent responses and actions
- **Working directory control**: Scope agent file operations to specific directories
- **Comprehensive error handling**: Typed exceptions for all failure modes

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 3 | Relatively new; rapidly maturing; Claude Code backend is production-proven |
| **Security** | 5 | Hooks for command interception; permission controls; Anthropic's safety focus |
| **Scalability** | 3 | Single-agent focused; orchestrate multiple via application code |
| **Support/Community** | 4 | Anthropic-backed; growing ecosystem; Claude Code has 95K stars |
| **Documentation** | 4 | Good SDK docs and examples; Claude Code docs are comprehensive |
| **Integration Ease** | 5 | `pip install claude-agent-sdk`; auto-bundles Claude Code CLI |

## Use Cases
1. **Automated code generation** - Build agents that write, test, and iterate on code
2. **CI/CD automation** - Agents that review PRs, fix issues, and manage deployments
3. **Data processing** - Agents that read files, transform data, and write results
4. **Custom development tools** - IDE integrations and developer productivity agents

## Getting Started
```bash
pip install claude-agent-sdk
```
```python
import anyio
from claude_agent_sdk import query

async def main():
    async for message in query(prompt="Create a Python hello world script"):
        print(message)

anyio.run(main)
```

## Architecture / How It Works
```
Your Python Application
  |-- claude_agent_sdk
       |-- ClaudeSDKClient (interactive) / query() (one-shot)
            |-- Claude Code CLI (bundled)
                 |-- Claude API (reasoning)
                 |-- Tools: Read, Write, Edit, Bash, ...
                 |-- Custom MCP Servers (in-process or external)
                 |-- Hooks: PreToolUse, PostToolUse
```
The SDK wraps the Claude Code CLI, providing a Python API over its agentic capabilities. Custom tools are registered as MCP servers (either in-process for performance or external for isolation). Hooks intercept tool calls for safety validation.

## Strengths
- Direct access to Claude's best-in-class reasoning for agent tasks
- In-process MCP servers eliminate subprocess overhead and simplify deployment
- Hooks system provides production-grade safety controls
- Auto-bundles Claude Code CLI -- no separate installation needed
- Type-safe with comprehensive error types
- Benefits from Claude Code's massive ecosystem (95K stars)

## Limitations
- Claude-only: tied to Anthropic's models (no model-agnostic support)
- Relatively new SDK; smaller community compared to LangChain/CrewAI
- Single-agent focused; no built-in multi-agent orchestration
- Depends on Claude Code CLI as backend -- adds a layer of complexity
- Pre-1.0 API; may evolve

## Alternatives
| Tool | Key Difference |
|------|---------------|
| OpenAI Agents SDK | OpenAI-native; multi-agent handoffs; provider-agnostic |
| LangGraph | Framework-agnostic; graph-based orchestration; more features |
| PydanticAI | Model-agnostic; type-safe; different architecture |
| CrewAI | Multi-agent teams; role-based; provider-agnostic |

## References
- https://platform.claude.com/docs/en/agent-sdk/python
- https://github.com/anthropics/claude-agent-sdk-python
- https://code.claude.com/docs/en/overview
- https://github.com/anthropics/claude-code

## Notes
The Claude Agent SDK represents Anthropic's approach to agent building: leverage Claude Code's proven agentic capabilities through a clean Python API. The hooks system is particularly notable for enterprise use cases where agent actions must be auditable and controllable. For teams already using Claude and wanting tight integration with Claude's capabilities, this is the most direct path. For multi-model or multi-agent needs, consider combining with a framework like LangGraph.
