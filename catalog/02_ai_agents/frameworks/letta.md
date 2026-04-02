# Letta (formerly MemGPT)

> Platform for building stateful AI agents with advanced memory capabilities that learn and improve over time.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 02 - AI Agents |
| **URL** | https://letta.com |
| **GitHub** | https://github.com/cpacker/MemGPT |
| **Stars** | 21,800 |
| **License** | Apache 2.0 |
| **Pricing** | Free (OSS) / Letta Cloud (paid) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Letta (formerly MemGPT) is a platform for building stateful AI agents with advanced memory capabilities. It pioneered the concept of "memory management as an operating system" -- agents that actively manage their own context window, moving information between short-term and long-term memory like a virtual memory system in an OS.

The platform offers both Letta Code (run agents locally in your terminal, similar to Claude Code) and Letta API (build agents into applications with Python/TypeScript SDKs). Agents support skills, subagents, and pre-built memory and continual learning components.

## Key Features
- **Self-managed memory**: Agents actively manage their own context window
- **Letta Code**: Local terminal-based agent development (Node.js 18+)
- **Letta API**: Python and TypeScript SDKs for application integration
- **Skills and subagents**: Modular agent capabilities
- **Continual learning**: Agents improve over time through memory accumulation
- **Model-agnostic**: Works with various LLM providers

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | v0.16.7; active development; cloud offering |
| **Security** | 3 | Standard security; less enterprise-focused |
| **Scalability** | 3 | API-based; scales through application architecture |
| **Support/Community** | 4 | 21.8K stars; active Discord; 100+ contributors |
| **Documentation** | 4 | docs.letta.com; quickstart guides |
| **Integration Ease** | 4 | CLI and SDK options; Python and TypeScript |

## Use Cases
1. **Long-running agents** - Agents that maintain context across many interactions
2. **Personal assistants** - AI that learns and remembers user preferences
3. **Research agents** - Agents that accumulate knowledge over time
4. **Conversational AI** - Chatbots with genuine long-term memory

## Getting Started
```bash
# CLI
npm install -g @letta-ai/letta-code
# Python SDK
pip install letta-client
```

## Strengths
- Pioneered self-managed agent memory (MemGPT paper)
- Both CLI and API interfaces for flexibility
- Continual learning is a unique differentiator
- Active open-source community
- Academic foundation with published research

## Limitations
- Rebranding from MemGPT may cause confusion
- Memory management adds computational overhead
- Less mature than dedicated agent frameworks for orchestration
- Pre-1.0 (v0.16.x); API may change

## References
- https://letta.com
- https://docs.letta.com
- https://github.com/cpacker/MemGPT
- https://arxiv.org/abs/2310.08560 (MemGPT paper)

## Notes
Letta/MemGPT's contribution to the agent space is the insight that agents should actively manage their own memory, not just passively accumulate it. This "OS-level memory management" approach is more sophisticated than simple key-value memory stores. For agents that need to operate over long time horizons with genuine learning, Letta is the most research-grounded option.
