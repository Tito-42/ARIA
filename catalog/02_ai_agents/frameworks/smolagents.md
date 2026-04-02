# Smolagents (Hugging Face)

> Lightweight agent framework where agents write Python code instead of JSON/text, fitting in ~1,000 lines of core code.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 02 - AI Agents |
| **URL** | https://huggingface.co/docs/smolagents |
| **GitHub** | https://github.com/huggingface/smolagents |
| **Stars** | 26,400 |
| **License** | Apache 2.0 |
| **Pricing** | Free (OSS) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Smolagents is Hugging Face's minimalist agent framework where agents express their actions as executable Python code rather than JSON tool calls or text descriptions. This "code agent" approach is more efficient (30% fewer steps than traditional tool-calling) and more expressive, since agents can use Python's full capabilities including loops, conditionals, and data structures.

The entire core agent logic fits in approximately 1,000 lines of code in a single `agents.py` file, making it one of the most readable and hackable agent frameworks available. Despite its minimalism, smolagents supports sandbox execution (E2B, Docker, WebAssembly, Modal, Blaxel), multi-modal inputs (text, vision, video, audio), and 100+ model providers via LiteLLM.

A key differentiator is the Hugging Face Hub integration: agents can be shared and imported directly from the Hub, enabling community-driven agent development.

## Key Features
- **Code agents**: Actions are Python code snippets, not JSON tool definitions
- **Minimal codebase**: Core logic in ~1,000 lines; highly readable and hackable
- **Sandbox execution**: E2B, Docker, WebAssembly, Modal, Blaxel sandboxing
- **Model-agnostic**: Local transformers, Ollama, OpenAI, Anthropic, 100+ via LiteLLM
- **Multi-modal**: Text, vision, video, and audio input support
- **Hub integration**: Share and import agents via Hugging Face Hub
- **30% fewer steps**: Code agents are more efficient than tool-calling agents
- **Open-source model support**: Benchmarks show DeepSeek-R1 competitive with closed models
- **Multi-agent**: Support for orchestrating multiple code agents

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 3 | Good for experimentation; sandbox execution adds safety |
| **Security** | 4 | Sandboxed code execution; multiple isolation options |
| **Scalability** | 3 | Lightweight but no built-in distributed execution |
| **Support/Community** | 5 | Hugging Face backing; 26K+ stars; active development |
| **Documentation** | 4 | Good docs on HF; examples and tutorials |
| **Integration Ease** | 5 | Minimal dependencies; familiar Hugging Face patterns |

## Use Cases
1. **Data analysis** - Code agents that write and execute data processing scripts
2. **Research automation** - Agents that search, download, and analyze research papers
3. **Open-source AI** - Building agents with open-source models via Hub integration
4. **Multi-modal tasks** - Processing images, video, and audio with code agents

## Getting Started
```bash
pip install smolagents
```
```python
from smolagents import CodeAgent, HfApiModel

agent = CodeAgent(tools=[], model=HfApiModel())
agent.run("What is 2**10?")
```

## Architecture / How It Works
```
User Query --> CodeAgent --> LLM generates Python code
                               |
                               v
                          Sandbox Execution (E2B/Docker/Wasm)
                               |
                               v
                          Result --> Agent decides: done or iterate
```
Instead of generating JSON tool calls, the LLM writes Python code that gets executed in a sandboxed environment. The agent iterates until it produces a satisfactory result. This approach leverages LLMs' strong code generation capabilities.

## Strengths
- Radical simplicity -- the entire framework is understandable in an afternoon
- Code agents are more expressive and efficient than tool-calling agents
- Excellent open-source model support through Hugging Face ecosystem
- Multiple sandbox options provide flexibility for security requirements
- Hub integration enables community sharing of agents
- Great for learning how agent frameworks work internally

## Limitations
- Code execution carries inherent security risks (mitigated by sandboxing)
- Less structured than role-based or graph-based frameworks
- No built-in memory, state management, or conversation history
- Smaller enterprise adoption compared to LangChain or CrewAI
- Less suited for complex multi-agent coordination patterns

## Alternatives
| Tool | Key Difference |
|------|---------------|
| LangChain | Full ecosystem; tool-calling based; more integrations |
| CrewAI | Role-based multi-agent; more structured |
| OpenAI Agents SDK | Handoff-based; lighter but no code execution |
| PydanticAI | Type-safe; structured outputs; different paradigm |

## References
- https://huggingface.co/docs/smolagents
- https://github.com/huggingface/smolagents
- https://huggingface.co/blog/smolagents

## Notes
Smolagents' code agent paradigm is a genuinely different approach that challenges the JSON tool-calling orthodoxy. The 30% efficiency improvement is significant for cost-sensitive applications. The framework is ideal for teams that want maximum transparency into agent behavior (code is inspectable) and are comfortable with sandboxed code execution. It pairs naturally with Hugging Face's open-source model ecosystem.
