# AutoGen (Microsoft)

> Multi-agent conversation framework for building AI applications with conversational agents that can collaborate and execute code.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 02 - AI Agents |
| **URL** | https://microsoft.github.io/autogen/ |
| **GitHub** | https://github.com/microsoft/autogen |
| **Stars** | 56,500 |
| **License** | MIT (code) / CC-BY-4.0 (docs) |
| **Pricing** | Free (OSS) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active (maintenance + transition to Microsoft Agent Framework) |
| **Maturity** | Production |

## What It Does
AutoGen is Microsoft's open-source framework for building multi-agent AI applications where agents engage in conversations to solve tasks. Unlike role-based frameworks (CrewAI) or graph-based ones (LangGraph), AutoGen models agent collaboration as structured conversations -- agents send messages, respond, and negotiate solutions through dialogue.

The framework operates across three abstraction layers: **Core API** (message passing, event-driven agents, distributed runtime), **AgentChat API** (rapid prototyping with common multi-agent patterns), and **Extensions API** (LLM integrations, code execution). AutoGen supports both fully autonomous and human-in-the-loop workflows.

**Important note (2026):** Microsoft has announced the "Microsoft Agent Framework" as the successor direction, while AutoGen continues receiving maintenance, bug fixes, and security patches. New users should evaluate both options.

## Key Features
- **Conversational agents**: Agents collaborate through structured multi-turn conversations
- **Code execution**: Built-in Docker-based code execution for agents that write and run code
- **Group chat**: Multi-agent group conversations with configurable speaking order
- **AgentChat API**: High-level patterns for common multi-agent scenarios
- **Distributed runtime**: Core API supports distributed agent deployment (Python and .NET)
- **AutoGen Studio**: No-code GUI for building and testing agent workflows
- **AutoGen Bench**: Performance evaluation and benchmarking suite
- **Nested conversations**: Agents can spawn sub-conversations for complex tasks
- **Customizable reply functions**: Fine-grained control over agent response logic

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Mature framework; used widely; transition period creates uncertainty |
| **Security** | 4 | Docker-based code execution; Microsoft backing |
| **Scalability** | 4 | Distributed runtime support; .NET support for enterprise |
| **Support/Community** | 5 | Microsoft-backed; weekly office hours; large Discord; active development |
| **Documentation** | 4 | Good docs; migration guides from v0.2; research papers |
| **Integration Ease** | 4 | Simple API for basic use; complexity grows with advanced patterns |

## Use Cases
1. **Code generation and debugging** - Agents that write, execute, and fix code collaboratively
2. **Research and analysis** - Multi-agent conversations to explore and synthesize information
3. **Task automation** - Orchestrating complex workflows through agent conversations
4. **Conversational AI** - Building sophisticated multi-party dialogue systems

## Getting Started
```bash
pip install -U "autogen-agentchat" "autogen-ext[openai]"
```

## Architecture / How It Works
```
Core API (Low-level)
  |-- Message passing between agents
  |-- Event-driven architecture
  |-- Distributed runtime (Python + .NET)

AgentChat API (High-level)
  |-- AssistantAgent, UserProxyAgent
  |-- GroupChat, GroupChatManager
  |-- Sequential / Dynamic speaking order

Extensions API
  |-- OpenAI, AzureOpenAI integrations
  |-- Code execution (Docker)
  |-- Tool registration
```

## Strengths
- Conversation-based paradigm is intuitive for many use cases
- Built-in code execution is a strong differentiator
- Microsoft backing provides long-term viability and enterprise trust
- Three-layer architecture serves both beginners and advanced users
- AutoGen Studio provides no-code access for non-developers
- Strong research foundation (originated from Microsoft Research)

## Limitations
- Transition to "Microsoft Agent Framework" creates uncertainty about long-term direction
- Conversation-based paradigm can be less efficient than graph-based approaches for structured workflows
- Agent behavior in group chats can be difficult to control precisely
- Migration from v0.2 to current API required significant refactoring
- Heavier framework compared to lightweight alternatives

## Alternatives
| Tool | Key Difference |
|------|---------------|
| CrewAI | Role-based vs. conversation-based; simpler to start |
| LangGraph | Graph-based; more precise control over agent flow |
| AG2 | Community fork of AutoGen with independent governance |
| OpenAI Agents SDK | Lighter weight; handoff-based; fewer features |

## References
- https://microsoft.github.io/autogen/
- https://github.com/microsoft/autogen
- https://www.deeplearning.ai/short-courses/ai-agentic-design-patterns-with-autogen/
- https://arxiv.org/abs/2308.08155 (AutoGen paper)

## Notes
AutoGen pioneered the multi-agent conversation paradigm and remains one of the most-starred agent frameworks (56.5K). However, the 2026 transition to "Microsoft Agent Framework" signals a strategic shift. Teams choosing AutoGen should monitor the migration path. The community fork **AG2** (see separate entry) offers an alternative with independent governance for those concerned about Microsoft's direction.
