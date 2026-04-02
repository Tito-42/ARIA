# Command R / R+ (Cohere)

> RAG-optimized open-weight models with built-in grounded generation and tool use

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 14 - Open Source LLMs |
| **URL** | https://cohere.com/ |
| **GitHub** | https://github.com/cohere-ai/cohere-toolkit |
| **Stars** | ~3.2k (toolkit) |
| **License** | CC-BY-NC 4.0 (open weights, non-commercial); Commercial via Cohere API |
| **Pricing** | Free weights (non-commercial) / Commercial API |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Command R and Command R+ are Cohere's open-weight language models specifically optimized for Retrieval-Augmented Generation (RAG), tool use, and multi-step agentic reasoning. Unlike general-purpose LLMs, Command R models are designed from the ground up to work with external knowledge sources, producing grounded responses with inline citations.

Command R+ (104B parameters) is the flagship model, supporting 23 languages and featuring built-in capabilities for grounded generation with document citations, single-step and multi-step tool use, and code generation. The models are available as open weights on HuggingFace and commercially through the Cohere API.

## Model Variants

### Command R+ (08-2024)
| Spec | Value |
|------|-------|
| **Parameters** | 104B |
| **Context Length** | 128K tokens |
| **Architecture** | Auto-regressive Transformer with Grouped Query Attention |
| **Languages** | 23 (trained), 10 (evaluated) |
| **Training** | SFT + Preference Training |
| **License** | CC-BY-NC 4.0 |

### Command R (08-2024)
| Spec | Value |
|------|-------|
| **Parameters** | 35B |
| **Context Length** | 128K tokens |
| **Architecture** | Auto-regressive Transformer |
| **Languages** | 23 |
| **License** | CC-BY-NC 4.0 |

## Key Features
- **Grounded Generation (RAG)**: Built-in citation system with `<co: doc>` markup
  - Accurate mode: Full answer then grounding
  - Fast mode: Direct grounding with fewer tokens
- **Single-Step Tool Use**: Function calling with parameter selection
- **Multi-Step Tool Use (Agents)**: Iterative Action/Observation/Reflection cycles
- **Code Capabilities**: Optimized for code interaction
- **23-language support**: EN, FR, ES, IT, DE, PT, JA, KO, AR, ZH-CN, and more
- **`directly_answer` tool**: Allows model to abstain from tool use when appropriate

## Evaluated Languages
English, French, Spanish, Italian, German, Portuguese, Japanese, Korean, Arabic, Simplified Chinese

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | Enterprise-grade, used in production RAG systems |
| **Security** | 4 | Canadian company, strong compliance |
| **Scalability** | 4 | 35B and 104B models |
| **Support/Community** | 4 | Commercial support via Cohere |
| **Documentation** | 5 | Excellent RAG and tool-use docs |
| **Integration Ease** | 4 | HuggingFace, Cohere API, toolkit |

## Use Cases
1. **Enterprise RAG** - Grounded answers with citations from internal documents
2. **Agentic workflows** - Multi-step tool use for complex tasks
3. **Multilingual customer support** - 23-language capability
4. **Research assistants** - Citation-backed responses
5. **Code assistants** - Optimized code generation

## Getting Started
```python
from transformers import AutoTokenizer, AutoModelForCausalLM

model_id = "CohereForAI/c4ai-command-r-plus-08-2024"
tokenizer = AutoTokenizer.from_pretrained(model_id)
model = AutoModelForCausalLM.from_pretrained(model_id)

# Grounded generation with documents
documents = [
    {"title": "Doc Title", "text": "Document content here."}
]
conversation = [{"role": "user", "content": "Your question?"}]
prompt = tokenizer.apply_grounded_generation_template(
    conversation, documents=documents, citation_mode="accurate",
    tokenize=False, add_generation_prompt=True
)
```

## Strengths
- Best-in-class RAG capabilities with built-in citation
- Unique grounded generation template system
- Multi-step agentic tool use
- Strong multilingual support (23 languages)
- Enterprise toolkit for quick RAG app deployment

## Limitations
- CC-BY-NC license restricts commercial use without API
- 104B model requires significant compute
- Smaller community than Llama/Qwen/DeepSeek
- Fewer quantized variants available
- Less competitive on pure reasoning benchmarks

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Llama 4 | Larger community, multimodal, more permissive license |
| Qwen 3 | Better reasoning, wider size range |
| Mistral | European, more model variants |
| DeepSeek R1 | Superior reasoning, MIT license |

## References
- [Command R+ on HuggingFace](https://huggingface.co/CohereForAI/c4ai-command-r-plus-08-2024)
- [Cohere RAG Documentation](https://docs.cohere.com/docs/retrieval-augmented-generation-rag)
- [Cohere Toolkit GitHub](https://github.com/cohere-ai/cohere-toolkit)
- [Cohere Multi-Step Tool Use](https://docs.cohere.com/docs/multi-step-tool-use)
