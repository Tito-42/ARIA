# Modal

> Serverless cloud platform for running GPU and CPU workloads with a Python-native interface, instant cold starts, and pay-per-second billing.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 18_ai_infrastructure |
| **URL** | https://modal.com |
| **GitHub** | https://github.com/modal-labs |
| **Stars** | ~3,500 (modal-client + examples) |
| **License** | Proprietary (platform) / Apache 2.0 (client SDK) |
| **Pricing** | Pay-per-second: A100 ~$2.78/hr / H100 ~$4.78/hr / CPU from $0.016/hr / Free $30/mo credits |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Modal is a serverless cloud platform designed for data and ML teams. It provides a Python-native way to run compute-intensive workloads on GPU or CPU without managing infrastructure. Developers write Python functions decorated with Modal annotations, and Modal handles provisioning containers, GPUs, scaling, and scheduling.

Modal's key differentiator is its developer experience: there is no Dockerfile to write, no YAML to configure, and no infrastructure to manage. You define your environment (pip packages, system packages, model downloads) in Python code, and Modal builds and caches containers automatically. This makes Modal particularly popular for AI inference serving, batch processing, fine-tuning, and data engineering.

## Key Features
- **Python-native**: Define infrastructure in Python code (no YAML/Docker)
- **Serverless GPU**: A10G, A100, H100 GPUs with auto-scaling
- **Instant cold starts**: Fast container provisioning (<1 second warm starts)
- **Container caching**: Build once, reuse cached layers
- **Web endpoints**: Deploy functions as HTTP endpoints
- **Cron scheduling**: Run functions on schedules
- **Volumes**: Persistent and ephemeral storage
- **Secrets management**: Secure credential storage
- **GPU memory management**: Dynamic GPU memory allocation
- **Batch processing**: Map functions over large datasets
- **Parallel execution**: Fan-out across many containers

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Growing enterprise adoption; reliable platform |
| **Security** | 4 | Container isolation; secrets management; SOC 2 |
| **Scalability** | 5 | Auto-scales to thousands of containers |
| **Support/Community** | 4 | Active Slack; responsive support team |
| **Documentation** | 5 | Excellent docs; many examples |
| **Integration Ease** | 5 | Python-native; minimal boilerplate |

## Use Cases
1. **Model inference serving** - Deploy LLMs and models as serverless endpoints
2. **Batch processing** - Process large datasets with GPU acceleration
3. **Fine-tuning** - Fine-tune models with pay-per-second billing
4. **Data pipelines** - GPU-accelerated ETL and data processing
5. **Research experiments** - Quick GPU access for experiments

## Getting Started
```python
# Install
pip install modal

# Setup
modal setup

# Example: GPU function
import modal
app = modal.App("example")

@app.function(gpu="A100")
def inference(prompt: str):
    # GPU function runs on A100 in the cloud
    from transformers import pipeline
    pipe = pipeline("text-generation", model="meta-llama/...")
    return pipe(prompt)

# Deploy
# modal deploy app.py
```

## Strengths
- Best developer experience for serverless GPU
- Python-native (no Docker/YAML needed)
- Fast iteration cycle (seconds to deploy)
- Pay-per-second (no idle costs)
- Excellent documentation and examples

## Limitations
- Python-only (no other languages)
- Platform lock-in (Modal-specific decorators)
- Pricing is higher than raw GPU rental
- Limited regions
- Less suitable for long-running training (hours/days)

## Alternatives
| Tool | Key Difference |
|------|---------------|
| RunPod | Raw GPUs; cheaper; more control; Docker-based |
| Replicate | Model-focused; simpler API; less flexible |
| Together AI | Inference-only; pre-hosted models |
| AWS Lambda | General serverless; no GPU support |
| Ray Serve | Open source; self-hosted; more complex |

## References
- https://modal.com
- https://modal.com/docs
- https://github.com/modal-labs/modal-examples
