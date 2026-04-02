# Ray / Ray Serve

> Framework de computing distribué par Anyscale — Ray Serve pour model serving, Ray Train pour distributed training.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 10 - Data Science & MLOps / Distributed Computing |
| **URL** | https://ray.io |
| **GitHub** | https://github.com/ray-project/ray |
| **Stars** | ~41,900 |
| **License** | Apache 2.0 |
| **Pricing** | Free (OSS) / Anyscale Platform (Paid) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Enterprise |

## What It Does
Ray est un framework de computing distribué universel par Anyscale, avec plus de 26k+ dependents et 41.9k stars. Il permet de distribuer n'importe quel code Python sur un cluster avec un décorateur `@ray.remote`.

Ray inclut des bibliothèques spécialisées : Ray Serve (model serving), Ray Train (distributed training), Ray Tune (hyperparameter tuning), Ray Data (distributed data processing). C'est l'infrastructure derrière de nombreuses plateformes ML/AI d'entreprise.

## Key Features
- **Ray Core**: Computing distribué universel avec `@ray.remote`
- **Ray Serve**: Model serving avec auto-scaling et multi-model
- **Ray Train**: Training distribué PyTorch/TensorFlow/HuggingFace
- **Ray Tune**: Hyperparameter tuning distribué
- **Ray Data**: Processing distribué de datasets
- **Anyscale**: Plateforme managée

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | Enterprise-grade, 26k+ dependents |
| **Security** | 4 | Self-hosted, Apache 2.0, Anyscale managed |
| **Scalability** | 5 | Conçu pour le distribué, scaling massif |
| **Support/Community** | 5 | 41.9k stars, Anyscale backing, communauté massive |
| **Documentation** | 4 | Docs complètes, exemples nombreux |
| **Integration Ease** | 3 | Puissant mais courbe d'apprentissage |

## Use Cases
1. **Distributed training** — Training PyTorch/HuggingFace distribué multi-GPU
2. **Model serving** — Serving multi-modèle avec auto-scaling via Ray Serve
3. **Data processing** — Traitement distribué de gros datasets

## Getting Started
```python
import ray
from ray import serve

ray.init()

@serve.deployment
class MyModel:
    def __init__(self):
        self.model = load_model()
    
    def __call__(self, request):
        return self.model.predict(request.json())

app = MyModel.bind()
serve.run(app)
```

## Architecture / How It Works
Ray utilise un runtime distribué avec un head node (GCS, scheduler) et des worker nodes. Les tâches (`@ray.remote`) sont distribuées automatiquement sur les workers disponibles. Ray Serve ajoute une couche HTTP avec load balancing et auto-scaling. Ray Train orchestre le training distribué avec intégration DeepSpeed, FSDP.

## Strengths
- Framework distribué le plus polyvalent
- Écosystème complet (serve, train, tune, data)
- 41.9k stars, 26k+ dependents
- Anyscale pour managed deployment

## Limitations
- Complexe à opérer en self-hosted
- Overhead significatif pour des tâches simples
- Debugging distribué non trivial

## Alternatives
| Tool | Key Difference |
|------|---------------|
| vLLM | Spécialisé LLM serving, plus simple |
| Dask | Distribué Python, plus simple, moins ML-focused |
| Spark | Big Data oriented, JVM-based |

## References
- https://docs.ray.io
- https://github.com/ray-project/ray
- https://anyscale.com

## Notes
Ray v2.54.1 courante. Ray est l'infrastructure de choix quand on a besoin de distribuer du compute ML. Pour du LLM serving pur, vLLM est plus optimisé. Pour de l'orchestration simple, Airflow/Prefect sont plus adaptés.
