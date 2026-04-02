# SkyPilot

> Framework multi-cloud pour ML — optimise les coûts via spot instances avec 3-6x d'économies.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 10 - Data Science & MLOps / Infrastructure |
| **URL** | https://skypilot.readthedocs.io |
| **GitHub** | https://github.com/skypilot-org/skypilot |
| **Stars** | ~9,700 |
| **License** | Apache 2.0 |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
SkyPilot est un framework qui abstrait le multi-cloud pour les workloads ML/AI. Il résout le problème du coût GPU en trouvant automatiquement les instances les moins chères sur AWS, GCP, Azure, Lambda, et d'autres providers, avec un focus sur les spot instances qui offrent 3-6x d'économies.

SkyPilot gère automatiquement le failover, le checkpointing, et la migration entre clouds quand les spot instances sont préemptées.

## Key Features
- **Multi-cloud automatique**: AWS, GCP, Azure, Lambda, OCI, etc.
- **Spot instances**: 3-6x cost savings avec auto-recovery
- **Auto-failover**: Migration automatique en cas de préemption
- **Job queue**: Queue de jobs avec priorités
- **Managed spot**: Checkpointing et restart automatiques
- **CLI simple**: `sky launch` pour démarrer

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Production, UC Berkeley research group |
| **Security** | 4 | Vos clouds, vos credentials, Apache 2.0 |
| **Scalability** | 4 | Multi-cloud, multi-région, spot scaling |
| **Support/Community** | 3 | 9.7k stars, communauté active |
| **Documentation** | 4 | Docs claires, exemples ML |
| **Integration Ease** | 4 | CLI simple, YAML config |

## Use Cases
1. **Training ML cost-optimized** — Entraîner des modèles sur spot instances multi-cloud
2. **GPU cluster management** — Gérer des clusters GPU sans vendor lock-in
3. **Batch inference** — Exécuter des batch jobs sur le cloud le moins cher

## Getting Started
```bash
pip install skypilot[aws,gcp]

# Lancer un job
sky launch -c my-cluster --gpus A100:4 -- python train.py

# Ou via YAML
sky launch task.yaml
```

## Architecture / How It Works
SkyPilot utilise un optimizer qui compare les prix GPU en temps réel sur tous les clouds configurés et choisit l'option la moins chère. Pour les spot instances, il gère le checkpointing et le failover automatiquement. Le controller SkyPilot orchestre les clusters et les jobs queue.

## Strengths
- 3-6x cost savings sur GPU via spot
- Multi-cloud sans vendor lock-in
- Auto-failover et recovery
- CLI simple

## Limitations
- Dépend des cloud providers (credentials setup)
- Spot instances pas adaptées à tous les workloads (serving temps réel)
- Nécessite du checkpointing dans le code de training

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Ray | Computing distribué plus généraliste |
| Anyscale | Ray managed, plus intégré |
| Terraform | Infrastructure as code, pas ML-specific |

## References
- https://skypilot.readthedocs.io
- https://github.com/skypilot-org/skypilot

## Notes
SkyPilot v0.12.0 courant. Excellent pour réduire les coûts de training ML. Se combine bien avec Ray pour le distributed training et vLLM pour le serving.
