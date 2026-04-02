# AG2 (formerly AutoGen)

> Community-governed fork of AutoGen with independent governance, multi-agent conversation patterns, and active development toward v1.0.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 02 - AI Agents |
| **URL** | https://ag2.ai |
| **GitHub** | https://github.com/ag2ai/ag2 |
| **Stars** | 4,300 |
| **License** | Apache 2.0 |
| **Pricing** | Free (OSS) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active (transitioning to v1.0) |
| **Maturity** | Beta |

## What It Does
AG2 is the community-governed continuation of AutoGen, established in November 2024 when a new organization (AG2AI) was created for open governance independent of Microsoft. It retains AutoGen's core multi-agent conversation framework while pursuing independent development toward a v1.0 release.

The framework supports conversable agents capable of interacting through various patterns: swarms, group chats, nested chats, and sequential conversations. It maintains backward compatibility with AutoGen's API while introducing a beta framework (autogen.beta) that will become the official API at v1.0.

AG2 exists for teams that want an AutoGen-compatible framework with community governance and without Microsoft corporate direction. The current framework is being "tidied up through deprecations" with the beta framework being actively developed.

## Key Features
- **Conversable agents**: Agents interact through multi-turn conversations
- **Multiple conversation patterns**: Swarms, group chats, nested chats, sequential chats
- **Structured outputs**: Type-safe agent responses
- **RAG support**: Retrieval-augmented generation built-in
- **Code execution**: Agents can write and execute code
- **Custom orchestration**: Registered reply methods for fine-grained control
- **Human-in-the-loop**: Support for autonomous and supervised workflows
- **AutoGen compatibility**: Migration path from AutoGen v0.2
- **Open governance**: Community-driven development independent of Microsoft

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 3 | In transition to v1.0; current framework entering maintenance |
| **Security** | 3 | Docker-based code execution; less enterprise tooling than AutoGen |
| **Scalability** | 3 | Inherits AutoGen's architecture; less enterprise infrastructure |
| **Support/Community** | 3 | Growing independent community; DeepLearning.ai course exists |
| **Documentation** | 3 | Docs exist but transition creates confusion between old/new API |
| **Integration Ease** | 4 | Compatible with AutoGen patterns; `pip install ag2` |

## Use Cases
1. **AutoGen migration** - Teams wanting to continue with AutoGen patterns under open governance
2. **Multi-agent conversations** - Complex dialogue-based agent collaboration
3. **Code generation** - Agents that write, execute, and debug code together
4. **Research prototyping** - Experimental multi-agent patterns

## Getting Started
```bash
pip install ag2
```

## Strengths
- Open governance ensures community-driven development
- AutoGen compatibility provides migration path
- Multiple conversation patterns are well-tested
- Active development toward v1.0 with clear roadmap
- Apache 2.0 license (vs. AutoGen's MIT + CC-BY-4.0)

## Limitations
- Smaller community than AutoGen (4.3K vs. 56.5K stars)
- Transition period creates API uncertainty
- Less corporate backing than Microsoft AutoGen
- Beta framework not yet stable
- Risk of fragmentation between AG2 and Microsoft's Agent Framework

## Alternatives
| Tool | Key Difference |
|------|---------------|
| AutoGen (Microsoft) | Original project; more stars; Microsoft backing; but transitioning |
| CrewAI | Role-based; simpler; more mature for production |
| LangGraph | Graph-based; more precise control |
| OpenAI Agents SDK | Simpler; handoff-based |

## References
- https://ag2.ai
- https://github.com/ag2ai/ag2
- https://www.deeplearning.ai/short-courses/ai-agentic-design-patterns-with-autogen/

## Notes
AG2 is in a critical transition period. Teams should evaluate whether the open governance model and Apache 2.0 license justify the smaller community and transition risks compared to staying with Microsoft's AutoGen or switching to a more established framework. The v1.0 release will be the key milestone to watch.
