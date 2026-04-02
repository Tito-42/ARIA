# Reflection / Self-Critique Pattern

## Problem
LLM agents produce outputs that may contain errors, hallucinations, or suboptimal responses on the first attempt. Without a mechanism for self-evaluation, agents cannot improve their own outputs or catch mistakes before presenting results to users.

## Solution
The Reflection pattern has an agent generate an initial output, then critique its own work (or have a separate critic agent evaluate it), and iterate to produce an improved version. This can involve explicit self-evaluation prompts, separate critic agents, or structured evaluation rubrics.

## Architecture Diagram
```
User Query
    |
    v
[Generator] --> Initial Output
    |
    v
[Reflector/Critic] --> Evaluation + Feedback
    |                    "The response misses X, and Y is incorrect"
    v
[Generator] --> Revised Output (incorporating feedback)
    |
    v
[Reflector/Critic] --> Evaluation
    |                    "Output is now satisfactory"
    v
Final Output
```

### Variants:
- **Self-Reflection**: Same agent generates and critiques
- **Separate Critic**: Different agent (possibly different model) evaluates
- **Rubric-Based**: Evaluation against structured criteria
- **Chain-of-Verification**: Agent generates verification questions, then answers them

## When to Use
- Quality-critical outputs (reports, code, analysis)
- Tasks where accuracy is more important than speed
- Complex reasoning where first-pass errors are common
- Code generation (generate -> test -> fix cycle)

## When NOT to Use
- Latency-critical applications (adds 2-3x LLM calls)
- Simple factual queries
- Tasks where the cost of iteration exceeds the value of improvement
- When evaluation criteria are unclear or subjective

## Implementation with Recommended Tools
| Component | Recommended Tool | Alternative |
|-----------|-----------------|-------------|
| Generation | Any LLM via LangGraph/PydanticAI | Direct API calls |
| Reflection | LangGraph (conditional loop) | Custom Python loop |
| Structured Eval | PydanticAI (typed evaluation) | DSPy (optimized eval) |
| Testing (code) | Smolagents (sandbox) | Docker execution |

## Reference Implementations
- LangGraph Reflection tutorial: https://langchain-ai.github.io/langgraph/tutorials/reflection/
- DSPy self-improving agents: https://dspy.ai
- Reflexion paper implementation: https://arxiv.org/abs/2303.11366

## Enterprise Considerations
- **Cost**: 2-3x token usage per query; budget accordingly
- **Quality**: Significant quality improvement for complex tasks (often 20-40% better)
- **Latency**: Not suitable for real-time applications
- **Observability**: Track iteration count and quality improvement per iteration

## References
- https://arxiv.org/abs/2303.11366 (Reflexion paper)
- https://arxiv.org/abs/2310.01798 (Self-Refine paper)
- https://langchain-ai.github.io/langgraph/concepts/reflection/
