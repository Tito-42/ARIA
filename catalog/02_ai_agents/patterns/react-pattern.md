# ReAct (Reasoning + Acting)

## Problem
LLMs need to interleave reasoning about a problem with taking actions (tool calls) to gather information or affect the environment. Pure reasoning without action leads to hallucination; pure action without reasoning leads to inefficient tool use.

## Solution
The ReAct pattern interleaves Thought (reasoning about what to do), Action (executing a tool or API call), and Observation (processing the result) in a loop until the task is complete. The LLM generates a thought explaining its reasoning, then chooses an action, observes the result, and repeats.

## Architecture Diagram
```
User Query
    |
    v
[Thought] -- "I need to find X. Let me search for it."
    |
    v
[Action] -- tool_call: search("X")
    |
    v
[Observation] -- "Search returned: ..."
    |
    v
[Thought] -- "Now I have X. I need to calculate Y."
    |
    v
[Action] -- tool_call: calculate(Y)
    |
    v
[Observation] -- "Result: ..."
    |
    v
[Thought] -- "I now have enough information to answer."
    |
    v
[Final Answer]
```

## When to Use
- Tasks requiring information gathering from external sources
- Multi-step reasoning where intermediate results inform next steps
- Tool-augmented question answering
- Any task where the agent needs to "think before acting"

## When NOT to Use
- Simple, single-step tasks (overhead not justified)
- Tasks where all information is already in the prompt
- Real-time applications where latency is critical (each step adds latency)
- Tasks where tool access is not needed

## Implementation with Recommended Tools
| Component | Recommended Tool | Alternative |
|-----------|-----------------|-------------|
| ReAct Loop | LangGraph | OpenAI Agents SDK, PydanticAI |
| Tool Execution | MCP Servers / Composio | Custom function tools |
| LLM Provider | Any (GPT-4o, Claude, Gemini) | LiteLLM for multi-provider |
| Tracing | LangSmith / AgentOps | Logfire (PydanticAI) |

## Reference Implementations
- LangGraph ReAct agent: https://langchain-ai.github.io/langgraph/how-tos/create-react-agent/
- Dify ReAct agent: Built-in agent type in Dify platform
- Original paper: "ReAct: Synergizing Reasoning and Acting in Language Models" (Yao et al., 2023)

## Enterprise Considerations
- **Cost**: Each thought-action-observation cycle consumes tokens; monitor costs
- **Latency**: Multiple LLM calls per query; not suitable for sub-second response requirements
- **Reliability**: Agents may loop or get stuck; implement max-step limits
- **Observability**: Trace each step for debugging; LangSmith or similar is essential

## References
- https://arxiv.org/abs/2210.03629 (ReAct paper)
- https://langchain-ai.github.io/langgraph/concepts/react-agent/
- https://www.deeplearning.ai/short-courses/ai-agents-in-langgraph/
