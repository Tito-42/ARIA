# Mistral / Mixtral / Mistral Small 4

> European open-weight LLMs from Mistral AI, including dense and MoE architectures

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 14 - Open Source LLMs |
| **URL** | https://mistral.ai/ |
| **GitHub** | https://github.com/mistralai/mistral-inference |
| **Stars** | ~10.8k |
| **License** | Apache 2.0 (some models), MNPL/MRL (others, non-commercial) |
| **Pricing** | Free / Open Weights |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Mistral AI is a French AI company producing a wide range of open-weight language models. Their lineup spans from lightweight 7B models to massive 675B parameter models, including both dense and Mixture-of-Experts (MoE) architectures. Mistral is the leading European AI model provider and is known for strong multilingual performance, particularly in European languages.

The company has expanded beyond text LLMs into code-specialized models (Codestral, Devstral), math models (Mathstral), speech models (Voxtral), and agentic models (Magistral). Their models are widely used in production and available through major cloud providers.

## Model Family (Current as of March 2026)

### Flagship Models
| Model | Parameters | Type | Notes |
|-------|-----------|------|-------|
| Mistral Large 3 | 675B | Dense | Frontier model, NVFP4 quantized available |
| Mistral Small 4 | 119B | Dense | Latest general-purpose model (March 2026) |
| Magistral Small | 24B | Dense | General purpose (Sep 2025) |
| Mistral Nemo | 12B | Dense | Compact general-purpose |

### Code/Agent Models
| Model | Parameters | Type | Notes |
|-------|-----------|------|-------|
| Devstral 2 (123B) | 125B | Code/Agentic | Dec 2025 |
| Devstral Small 2 (24B) | 24B | Code/Agentic | Dec 2025 |
| Codestral | 22B | Code | Fill-in-the-middle support |

### Specialized Models
| Model | Parameters | Type | Notes |
|-------|-----------|------|-------|
| Voxtral 4B TTS | 4B | Text-to-Speech | March 2026 |
| Voxtral Mini 4B | 4B | Speech Recognition | Feb 2026 |
| Leanstral | N/A | Optimized LLM | March 2026 |
| Mathstral | 7B | Math-focused | Specialized |
| Pixtral Large | N/A | Multimodal | Vision-language |
| Pixtral 12B | 12B | Multimodal | Compact vision-language |

### Legacy MoE Models
| Model | Parameters | Type |
|-------|-----------|------|
| Mixtral 8x22B | 141B total / ~39B active | MoE |
| Mixtral 8x7B | 46.7B total / ~12.9B active | MoE |

## Key Features
- European AI sovereignty (French company, EU compliant)
- Wide range of model sizes (4B to 675B)
- Strong multilingual performance (especially European languages)
- Code-specialized models (Codestral, Devstral)
- Multimodal vision (Pixtral) and speech (Voxtral) models
- Function calling capabilities
- Fill-in-the-middle (FIM) code completion
- CLI and Python API inference tools
- Docker containerization support
- Available on all major cloud providers

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | Widely deployed in enterprise |
| **Security** | 5 | European company, EU AI Act compliant |
| **Scalability** | 5 | Models for every scale |
| **Support/Community** | 4 | Active community, commercial support available |
| **Documentation** | 4 | Good docs, API references |
| **Integration Ease** | 5 | All major frameworks, cloud providers |

## Use Cases
1. **European enterprise AI** - EU data sovereignty requirements
2. **Code generation** - Codestral/Devstral for development
3. **Multilingual applications** - Strong European language support
4. **Speech AI** - Voxtral for TTS and ASR
5. **Multimodal** - Pixtral for vision-language tasks

## Getting Started
```bash
# Via Ollama
ollama run mistral
ollama run mixtral

# Via pip
pip install mistral-inference
mistral-chat /path/to/model --instruct
```

## Strengths
- European data sovereignty and regulatory compliance
- Comprehensive model lineup covering all modalities
- Strong code models (Codestral, Devstral)
- Apache 2.0 license on several key models
- Rapid innovation pace (new models monthly)

## Limitations
- Some models use restrictive licenses (MNPL, MRL)
- Largest models (675B) require enterprise compute
- Less community adoption than Llama/DeepSeek for some use cases
- MoE models (Mixtral) are being superseded by dense models

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Llama 4 | Larger community, native multimodal MoE |
| DeepSeek V3 | Stronger reasoning, MIT license |
| Qwen 3 | More size options, stronger Asian language support |
| Gemma 3 | Google backing, simpler licensing |

## References
- [Mistral AI Documentation](https://docs.mistral.ai/)
- [Mistral Inference GitHub](https://github.com/mistralai/mistral-inference)
- [HuggingFace - Mistral AI](https://huggingface.co/mistralai)
- [Mistral AI Blog](https://mistral.ai/news/)
