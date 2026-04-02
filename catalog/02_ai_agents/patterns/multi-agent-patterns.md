# Multi-Agent Patterns

## Problem
Complex tasks often exceed what a single agent can handle effectively. Different aspects of a task may require different expertise, tools, or perspectives. Single agents also suffer from context window limitations and lack of specialization.

## Solution
Multi-agent patterns distribute work across multiple specialized agents that collaborate through various coordination mechanisms. The main patterns are: Supervisor, Hierarchical, Debate, Swarm/Handoff, and Pipeline.

## Architecture Diagram

### Pattern 1: Supervisor
```
User Query --> [Supervisor Agent]
                    |
         ---------------------
         |         |         |
    [Agent A]  [Agent B]  [Agent C]
    (Research) (Analysis) (Writing)
         |         |         |
         ---------------------
                    |
              [Supervisor] --> Final Output
```
The Supervisor receives tasks, delegates to specialized agents, collects results, and synthesizes the final output. Used by: LangGraph, CrewAI (hierarchical process).

### Pattern 2: Handoff / Swarm
```
User Query --> [Triage Agent]
                    |
              [Decision: Route to...]
              /            \
    [Sales Agent]    [Support Agent]
         |                |
    [Handoff to...]  [Handoff to...]
         |                |
    [Billing Agent]  [Escalation Agent]
```
Agents hand off conversations to other agents based on context. The conversation follows the user's needs. Used by: OpenAI Agents SDK, LangGraph.

### Pattern 3: Debate / Critique
```
User Query --> [Generator Agent] --> Draft Response
                                         |
                                    [Critic Agent] --> Feedback
                                         |
                                    [Generator Agent] --> Revised Response
                                         |
                                    [Critic Agent] --> Approved / More Feedback
                                         |
                                    Final Output
```
One agent generates, another critiques, iterating until quality is satisfactory. Used by: AutoGen, custom LangGraph flows.

### Pattern 4: Pipeline / Sequential
```
User Query --> [Agent 1: Research] --> [Agent 2: Analyze] --> [Agent 3: Write] --> Final Output
```
Agents execute in sequence, each building on the previous agent's output. Used by: CrewAI (sequential process), LangGraph.

### Pattern 5: Hierarchical / Tree
```
[Manager Agent]
    |
    |-- [Team Lead A]
    |       |-- [Worker A1]
    |       |-- [Worker A2]
    |
    |-- [Team Lead B]
            |-- [Worker B1]
            |-- [Worker B2]
```
Multi-level hierarchy with delegation at each level. Used by: CrewAI, MetaGPT, Google ADK.

## When to Use
- Tasks requiring diverse expertise (research + analysis + writing)
- Large tasks that benefit from parallel execution
- Quality-critical tasks where debate/critique improves output
- Customer-facing scenarios where routing to specialists improves UX
- Complex workflows with clear separation of concerns

## When NOT to Use
- Simple tasks where single-agent is sufficient (over-engineering)
- Latency-critical applications (multi-agent adds overhead)
- When agent communication costs exceed the benefit of specialization
- Tightly coupled tasks where splitting increases complexity

## Implementation with Recommended Tools
| Pattern | Recommended Tool | Alternative |
|---------|-----------------|-------------|
| Supervisor | LangGraph | CrewAI (hierarchical), Google ADK |
| Handoff / Swarm | OpenAI Agents SDK | LangGraph, custom routing |
| Debate / Critique | AutoGen | LangGraph, custom |
| Pipeline / Sequential | CrewAI (sequential) | LangGraph, Haystack |
| Hierarchical / Tree | CrewAI | MetaGPT, Google ADK |

## Reference Implementations
- LangGraph multi-agent: https://langchain-ai.github.io/langgraph/tutorials/multi_agent/
- CrewAI multi-agent: https://docs.crewai.com
- OpenAI Agents SDK handoffs: https://openai.github.io/openai-agents-python/
- AutoGen group chat: https://microsoft.github.io/autogen/
- MetaGPT SOP: https://github.com/geekan/MetaGPT

## Enterprise Considerations
- **Cost**: Multiple agents = multiple LLM calls; budget carefully
- **Latency**: Parallel patterns reduce wall-clock time vs. sequential
- **Debugging**: Multi-agent systems are harder to debug; invest in observability (LangSmith, AgentOps)
- **Failure modes**: Agent communication failures, infinite loops, conflicting outputs
- **Governance**: Human-in-the-loop is more important with multiple autonomous agents
- **Testing**: Test individual agents AND their interactions; emergent behavior can be surprising

## References
- https://arxiv.org/abs/2308.08155 (AutoGen paper - multi-agent conversations)
- https://arxiv.org/abs/2308.00352 (MetaGPT paper - SOP-driven multi-agent)
- https://langchain-ai.github.io/langgraph/concepts/multi_agent/
- https://www.deeplearning.ai/short-courses/multi-ai-agent-systems-with-crewai/
- https://www.deeplearning.ai/short-courses/ai-agentic-design-patterns-with-autogen/
