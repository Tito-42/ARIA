# MetaGPT

> Multi-agent framework that simulates a software company with SOP-driven agent collaboration for code generation and project planning.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 02 - AI Agents |
| **URL** | https://www.deepwisdom.ai |
| **GitHub** | https://github.com/geekan/MetaGPT |
| **Stars** | 66,500 |
| **License** | MIT |
| **Pricing** | Free (OSS) / MGX (commercial product) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
MetaGPT is a multi-agent framework that simulates a software company by assigning different roles (product manager, architect, project manager, engineer) to AI agents that collaborate through Standard Operating Procedures (SOPs). Given a one-line requirement, MetaGPT produces user stories, competitive analysis, requirements documents, data structures, APIs, and actual code.

The framework embodies the philosophy "Code = SOP(Team)" -- materializing standard operating procedures as executable multi-agent workflows. It includes a Data Interpreter for code writing and data analysis, and supports multiple reasoning strategies including ReAct, Chain-of-Thought, Tree-of-Thought, and Reflection patterns.

MetaGPT also spawned MGX (MetaGPT X), a commercial product described as "the world's first AI agent development team," which ranked #1 Product of the Week on Product Hunt in March 2025.

## Key Features
- **SOP-driven collaboration**: Agents follow standard operating procedures
- **Software company simulation**: Product manager, architect, engineer, QA roles
- **One-line to full project**: From a single requirement to complete documentation and code
- **Data Interpreter**: Built-in code writing and data analysis agent
- **Multiple reasoning strategies**: ReAct, CoT, ToT, Reflection
- **Skill Manager**: Incremental learning for agents
- **Role-based memory**: Long-term and short-term memory per agent
- **Academic research**: AFlow paper accepted at ICLR 2025 (top 1.8%)

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 3 | Great for prototyping; MGX for production use |
| **Security** | 3 | Code execution capabilities require oversight |
| **Scalability** | 3 | SOP approach scales for defined workflows |
| **Support/Community** | 5 | 66.5K stars; very active community; academic backing |
| **Documentation** | 4 | Good docs; multiple tutorials and papers |
| **Integration Ease** | 3 | Requires Python 3.9+; Node.js; more complex setup |

## Use Cases
1. **Software project generation** - From requirements to complete codebase
2. **Research and analysis** - Multi-agent research with structured output
3. **Data analysis** - Data Interpreter for automated data science workflows
4. **Education** - Learning about multi-agent SOP-driven collaboration

## Getting Started
```bash
pip install metagpt
```

## Strengths
- Unique SOP-driven approach maps directly to business processes
- Produces comprehensive artifacts (docs, code, tests) from simple inputs
- Strong academic foundation with published research
- Very large community (66.5K stars)
- Commercial product (MGX) validates production viability

## Limitations
- Complex setup with Node.js dependency
- SOP approach is rigid; less flexible than general agent frameworks
- Best for software development workflows; less general-purpose
- High token consumption for full project generation
- Python 3.9-3.11 requirement (not yet supporting 3.12+)

## Alternatives
| Tool | Key Difference |
|------|---------------|
| CrewAI | More general-purpose; flexible roles; lighter weight |
| AutoGen | Conversation-based; more general multi-agent patterns |
| LangGraph | Graph-based orchestration; more control |
| AutoGPT | Platform approach; marketplace; less SOP-driven |

## References
- https://github.com/geekan/MetaGPT
- https://docs.deepwisdom.ai
- https://arxiv.org/abs/2308.00352 (MetaGPT paper)

## Notes
MetaGPT's SOP-driven approach is innovative and produces impressive results for software development tasks. However, its specialization is also its limitation -- teams looking for general-purpose multi-agent frameworks may find CrewAI or AutoGen more flexible. The AFlow research (ICLR 2025) demonstrates the team's commitment to advancing the state of the art in automated workflow optimization.
