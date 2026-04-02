# OpenAI Agents SDK

> Lightweight yet powerful framework for building multi-agent workflows with handoffs, guardrails, and tracing.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 02 - AI Agents |
| **URL** | https://openai.github.io/openai-agents-python/ |
| **GitHub** | https://github.com/openai/openai-agents-python |
| **Stars** | 20,500 |
| **License** | MIT |
| **Pricing** | Free (OSS); requires OpenAI API or compatible LLM |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
The OpenAI Agents SDK (formerly known as "Swarm") is a lightweight framework for building multi-agent workflows. It provides a minimal but complete set of primitives: Agents (LLMs with instructions, tools, and guardrails), Handoffs (agent-to-agent delegation), Guardrails (input/output validation), and Tracing (execution visualization).

Despite originating from OpenAI, the SDK supports 100+ LLMs beyond OpenAI's own models, making it provider-agnostic. The framework emphasizes simplicity -- agents are defined with just a few lines of code, and multi-agent coordination happens through explicit handoff mechanisms rather than complex orchestration.

The SDK has rapidly grown to be used by 4,800+ projects since its release, offering features like session management, human-in-the-loop, and voice agent support with gpt-realtime models.

## Key Features
- **Agents**: LLMs configured with instructions, tools, guardrails, and handoff capabilities
- **Handoffs**: Explicit agent-to-agent delegation for task routing
- **Guardrails**: Input/output validation and safety checks
- **Tracing & debugging**: Built-in agent run visualization and optimization
- **Human-in-the-loop**: Built-in mechanisms for human involvement
- **Session management**: Automatic conversation history tracking
- **Voice agents**: Real-time voice support with gpt-realtime-1.5
- **MCP support**: Model Context Protocol tool integration
- **100+ LLM support**: Not limited to OpenAI models
- **Hosted tools**: Pre-built tools (web search, file search, computer use)

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Actively versioned (v0.13.4); still pre-1.0 |
| **Security** | 4 | Guardrails built-in; OpenAI's security practices |
| **Scalability** | 3 | Lightweight but no built-in distributed execution |
| **Support/Community** | 4 | OpenAI-backed; growing community; 4.8K dependent projects |
| **Documentation** | 4 | Clear docs and examples; growing tutorial ecosystem |
| **Integration Ease** | 5 | Extremely simple API; minimal boilerplate |

## Use Cases
1. **Customer service routing** - Triage agent hands off to specialized agents based on query type
2. **Multi-step workflows** - Chain of agents each handling a specific step
3. **Voice assistants** - Real-time voice agents with tool access
4. **Content moderation** - Guardrails for validating agent inputs and outputs

## Getting Started
```bash
pip install openai-agents
```
```python
from agents import Agent, Runner

agent = Agent(name="Assistant", instructions="You are a helpful assistant.")
result = Runner.run_sync(agent, "Hello!")
print(result.final_output)
```

## Architecture / How It Works
```
Agent A (Triage)
  |-- Instructions: "Route queries..."
  |-- Tools: [classify_query]
  |-- Handoffs: [Agent B, Agent C]
      |
      |--> Agent B (Sales)        Agent C (Support)
           |-- Tools: [lookup]     |-- Tools: [search_kb]
           |-- Guardrails: [...]   |-- Guardrails: [...]
```
The framework uses a simple loop: Agent receives input -> calls tools or hands off -> returns output. Handoffs transfer conversation context between agents. Guardrails validate inputs/outputs at each step.

## Strengths
- Extremely lightweight and simple API -- fastest to prototype
- Handoff mechanism is elegant and intuitive for multi-agent routing
- Built-in guardrails address safety concerns
- Provider-agnostic despite the OpenAI name
- Voice agent support is unique among agent frameworks
- Tracing built-in from day one

## Limitations
- Still pre-1.0 (v0.13.x); API may evolve
- Less sophisticated orchestration than LangGraph or CrewAI
- No built-in persistent state management or durable execution
- Limited memory/context management compared to full-featured frameworks
- Handoff model is simpler but less flexible than graph-based approaches

## Alternatives
| Tool | Key Difference |
|------|---------------|
| LangGraph | More powerful orchestration; stateful; steeper learning curve |
| CrewAI | Role-based teams; more structured collaboration |
| PydanticAI | Type-safe; Pydantic-native; similar simplicity |
| Anthropic Agent SDK | Claude-native; code execution focus |

## References
- https://openai.github.io/openai-agents-python/
- https://github.com/openai/openai-agents-python
- https://platform.openai.com/docs/guides/agents

## Notes
The Agents SDK represents OpenAI's philosophy that agent frameworks should be minimal and opinionated about the right primitives rather than feature-heavy. The "Swarm" experimental predecessor introduced the handoff concept, which the Agents SDK productionized. For teams wanting the simplest possible multi-agent setup, this is the go-to choice. The voice agent capability is a unique differentiator for real-time applications.
