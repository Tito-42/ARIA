# Vast.ai

> Decentralized GPU marketplace connecting GPU owners with renters, offering the lowest prices for AI compute through a peer-to-peer model.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 18_ai_infrastructure |
| **URL** | https://vast.ai |
| **GitHub** | https://github.com/vast-ai |
| **Stars** | N/A (marketplace platform) |
| **License** | Proprietary (platform) |
| **Pricing** | Marketplace pricing: RTX 3090 ~$0.20/hr / A100 ~$0.90/hr / H100 ~$2.50/hr (varies) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Vast.ai is a decentralized GPU marketplace that connects GPU owners (hosts) with users who need compute power. It operates on a peer-to-peer model where anyone with spare GPU capacity can list their hardware, and users can rent it at market-driven prices. This marketplace approach typically yields the lowest GPU prices available, often 3-5x cheaper than major cloud providers.

The platform supports on-demand and interruptible instances, Docker-based workloads, and a search/filter system for finding GPUs by specs, price, reliability rating, and location. Vast.ai is popular for training, fine-tuning, and batch inference workloads where cost is the primary concern and some variability in reliability is acceptable.

## Key Features
- **GPU marketplace**: Peer-to-peer GPU rental
- **Lowest prices**: Market-driven pricing; often cheapest available
- **Hardware variety**: From RTX 3090 to H100; multi-GPU configurations
- **Docker-based**: Run any Docker container
- **Reliability ratings**: Host reliability scores and uptime history
- **DLPerf scoring**: Performance benchmarks for each listing
- **On-demand and interruptible**: Choose reliability vs price
- **CLI and API**: Programmatic instance management
- **Search/filter**: Find GPUs by specs, price, location, reliability
- **Jupyter/SSH**: Direct access to instances

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 3 | Good for dev/training; less for production serving |
| **Security** | 2 | Shared hardware from unknown hosts; limited controls |
| **Scalability** | 4 | Large marketplace; many available GPUs |
| **Support/Community** | 3 | Discord; community support |
| **Documentation** | 3 | Basic docs; CLI reference |
| **Integration Ease** | 3 | CLI/API; Docker-based |

## Use Cases
1. **Budget training** - Fine-tune models at lowest possible cost
2. **Batch processing** - Large-scale inference on cheap GPUs
3. **Experimentation** - Try different GPU types cheaply
4. **Image generation** - Stable Diffusion and similar on cheap GPUs
5. **Research** - Academic teams with limited budgets

## Getting Started
```bash
# Install CLI
pip install vastai

# Search for instances
vastai search offers 'gpu_name=RTX_4090 num_gpus=1 dph<0.50'

# Create instance
vastai create instance <OFFER_ID> --image pytorch/pytorch:latest

# SSH into instance
vastai ssh-url <INSTANCE_ID>
```

## Strengths
- Lowest GPU prices available (marketplace competition)
- Wide hardware variety (consumer to enterprise GPUs)
- Good for cost-sensitive training and batch workloads
- Reliability ratings help choose stable hosts
- CLI for automation

## Limitations
- Security concerns (shared/unknown hardware hosts)
- Reliability varies by host (instances can be interrupted)
- Not suitable for production serving
- Limited compliance and enterprise features
- No SLA guarantees
- Network speeds vary by host

## Alternatives
| Tool | Key Difference |
|------|---------------|
| RunPod | More reliable; managed platform; slightly pricier |
| Lambda Labs | Enterprise-focused; dedicated hardware |
| Modal | Serverless; Python-native; managed |
| AWS/GCP/Azure | Enterprise-grade; much more expensive |

## References
- https://vast.ai
- https://vast.ai/docs
