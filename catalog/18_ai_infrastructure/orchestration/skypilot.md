# SkyPilot

> Open-source framework for running AI workloads on any cloud (AWS, GCP, Azure, Lambda, RunPod, etc.) with automatic cost optimization and multi-cloud orchestration.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 18_ai_infrastructure |
| **URL** | https://skypilot.readthedocs.io |
| **GitHub** | https://github.com/skypilot-org/skypilot |
| **Stars** | ~8,500 |
| **License** | Apache 2.0 |
| **Pricing** | Free (OSS) -- you pay cloud provider costs |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
SkyPilot is an open-source framework that enables running AI and batch workloads on any cloud provider with automatic cost optimization. It abstracts away cloud-specific differences, allowing users to write workloads once and run them on AWS, GCP, Azure, Lambda Labs, RunPod, Kubernetes, or other providers based on cost, availability, and performance requirements.

SkyPilot's optimizer automatically selects the cheapest cloud/region/instance type for a given workload, handles spot instance preemption and recovery, and can migrate workloads between clouds. This is particularly valuable for AI workloads where GPU prices vary 3-10x across providers and regions. UC Berkeley developed SkyPilot, and it has been adopted by research labs and companies running large-scale AI workloads.

## Key Features
- **Multi-cloud**: AWS, GCP, Azure, Lambda, RunPod, OCI, Kubernetes
- **Cost optimizer**: Automatically picks cheapest cloud/region/instance
- **Spot instances**: Automatic spot/preemptible management with recovery
- **Managed jobs**: Long-running jobs with auto-recovery from preemption
- **Sky Serve**: Model serving across clouds with auto-scaling
- **Storage mounting**: Unified cloud storage access
- **Docker support**: Run any Docker container
- **CLI interface**: Simple `sky launch` commands
- **YAML spec**: Declarative workload specification
- **Cluster management**: Automatic provisioning and teardown

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Used by research labs and companies |
| **Security** | 4 | Uses your own cloud accounts; no middleman |
| **Scalability** | 5 | Multi-cloud; arbitrage across providers |
| **Support/Community** | 4 | 8.5K stars; UC Berkeley backing |
| **Documentation** | 4 | Good docs; many examples |
| **Integration Ease** | 4 | Simple CLI; YAML-based |

## Use Cases
1. **Cost-optimized training** - Train on cheapest available GPUs across clouds
2. **Spot instance management** - Auto-recover from preemption across clouds
3. **Multi-cloud inference** - Serve models across regions/clouds for reliability
4. **GPU availability** - Find available GPUs when one cloud is sold out
5. **Cloud migration** - Easily move workloads between cloud providers

## Getting Started
```bash
# Install
pip install skypilot[aws,gcp,azure]

# Launch a GPU job
sky launch -c mycluster --gpus A100:1 -- python train.py

# Or use YAML
sky launch task.yaml

# Check status
sky status
```

## Strengths
- Massive cost savings through multi-cloud optimization
- Spot instance management is production-grade
- No vendor lock-in (your cloud accounts, open source)
- UC Berkeley research credibility
- Supports diverse cloud providers including GPU-specific ones

## Limitations
- Requires cloud account setup for each provider
- Additional abstraction layer adds complexity
- Not as polished as managed platforms (Modal, etc.)
- Best for batch/training; less for real-time serving
- Cloud credential management across providers

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Modal | Serverless; simpler DX; single provider |
| Terraform | General IaC; no AI-specific optimization |
| Kubernetes | Container orchestration; no cost optimization |
| RunPod | Single provider; simpler; managed |
| Anyscale | Managed Ray; more features; enterprise |

## References
- https://skypilot.readthedocs.io
- https://github.com/skypilot-org/skypilot
