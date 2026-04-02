# Mergekit

> Toolkit pour fusionner des LLMs avec des méthodes SLERP, TIES, DARE, linear et task arithmetic

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 06_finetuning_training |
| **URL** | https://github.com/arcee-ai/mergekit |
| **GitHub** | https://github.com/arcee-ai/mergekit |
| **Stars** | 6,900 |
| **License** | LGPL v3 |
| **Pricing** | Free / Open Source |
| **Last Verified** | 2026-04-01 |
| **Status** | Maintained |
| **Maturity** | Production |

## What It Does
Mergekit est un toolkit développé par Arcee AI spécialisé dans la fusion (merging) de modèles de langage. Plutôt que de fine-tuner un modèle from scratch, la fusion permet de combiner les capacités de plusieurs modèles spécialisés en un seul modèle plus capable. Cette approche est souvent moins coûteuse en compute et peut donner d'excellents résultats.

Le toolkit implémente plusieurs méthodes de fusion : SLERP (interpolation sphérique), TIES (réduction des conflits entre paramètres), DARE (élagage des paramètres delta), linear (combinaison linéaire simple) et task arithmetic (addition de vecteurs de tâches). Chaque méthode a ses forces selon le type de modèles à fusionner.

Mergekit est unique dans son segment : il n'existe pratiquement pas d'alternative comparable en termes de richesse des méthodes de fusion. Il est massivement utilisé par la communauté Hugging Face pour créer des modèles merged qui se retrouvent régulièrement en tête des leaderboards.

## Key Features
- **SLERP** : Spherical Linear Interpolation pour interpoler entre deux modèles
- **TIES** : Trimming, Elect Sign & Merge - réduit les conflits entre paramètres
- **DARE** : Drop And REscale - élagage des delta paramètres avant fusion
- **Linear** : combinaison linéaire pondérée de plusieurs modèles
- **Task Arithmetic** : addition de vecteurs de tâches pour multi-task
- **Passthrough** : copier des couches entre modèles
- **YAML config** : configuration déclarative des fusions
- **CPU merging** : fusion sur CPU pour modèles dépassant la VRAM
- **LoRA merge** : fusion d'adaptateurs LoRA avec des modèles base

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 3 | Utilisé en production mais résultats peuvent varier, licence LGPL |
| **Security** | 3 | Projet Arcee AI, LGPL peut créer des contraintes légales |
| **Scalability** | 3 | CPU merging disponible, mais pas conçu pour du batch merging |
| **Support/Community** | 3 | Communauté active mais projet Arcee AI commercial |
| **Documentation** | 3 | Documentation suffisante mais pas exhaustive |
| **Integration Ease** | 4 | Configuration YAML intuitive, CLI simple |

## Use Cases
1. **Fusion de spécialistes** : combiner un modèle bon en code avec un bon en raisonnement
2. **Éviter le fine-tuning coûteux** : merger deux modèles LoRA fine-tunés pour obtenir une capacité combinée
3. **Modèles francophones** : merger un modèle anglophone avec un modèle francophone
4. **Task Arithmetic** : additionner des capacités spécifiques (mathématiques, fiction, etc.)
5. **Expérimentation communauté** : créer des modèles merged originaux à publier sur HuggingFace Hub

## Getting Started
```bash
# Installation
pip install mergekit

# Config minimale YAML (merge_config.yaml)
# SLERP entre deux modèles
merge_method: slerp
base_model: meta-llama/Llama-3-8B
models:
  - model: model-a-finetuned
    parameters:
      t: 0.5
  - model: model-b-finetuned
    parameters:
      t: 0.5
dtype: bfloat16

# Lancement fusion
mergekit-yaml merge_config.yaml ./output-merged-model

# TIES merge (plusieurs modèles)
merge_method: ties
base_model: meta-llama/Llama-3-8B
models:
  - model: specialist-code
    parameters: {weight: 0.4, density: 0.5}
  - model: specialist-math
    parameters: {weight: 0.4, density: 0.5}
  - model: generalist
    parameters: {weight: 0.2}
```

## Architecture / How It Works
```
Mergekit - Méthodes de Fusion
                      Base Model
                          │
         ┌────────────────┼────────────────┐
         │                │                │
    Model A           Model B           Model C
    (ΔW_A)            (ΔW_B)            (ΔW_C)
         │                │                │
         └────────────────┼────────────────┘
                          │
              ┌───────────▼───────────┐
              │   Méthode de Fusion   │
              │                       │
              │  SLERP: interpolation │
              │  TIES:  élague conflits│
              │  DARE:  élague deltas │
              │  Linear: α*A + β*B    │
              └───────────┬───────────┘
                          │
                   Merged Model
```

## Strengths
- Unique dans sa catégorie pour la richesse des méthodes de fusion
- Massivement utilisé par la communauté HuggingFace
- Fusion CPU permet de merger des modèles qui ne tiennent pas en VRAM
- Configuration YAML intuitive
- Alternative peu coûteuse au fine-tuning pour certains cas d'usage

## Limitations
- Licence LGPL v3 peut créer des contraintes légales pour usage commercial
- Résultats variables et imprévisibles selon les modèles fusionnés
- Pas de garantie que la fusion améliorera les deux capacités simultanément
- Activité modérée (mars 2025), moins de mises à jour récentes
- Moins adapté si les modèles de base sont trop différents architecturalement

## Alternatives
| Tool | Key Difference |
|------|---------------|
| LM-Cocktail (BAAI) | Alternative plus légère pour fusion linéaire |
| Model Merging (HF) | API HuggingFace native, moins de méthodes |
| {TODO} | Pas vraiment de concurrent direct avec autant de méthodes |

## References
- [GitHub Repository](https://github.com/arcee-ai/mergekit)
- [Documentation](https://github.com/arcee-ai/mergekit/blob/main/README.md)
- [Paper TIES](https://arxiv.org/abs/2306.01708)
- [Paper DARE](https://arxiv.org/abs/2311.03099)
- [Arcee AI](https://www.arcee.ai)

## Notes
- Activité modérée depuis mars 2025, mais outil stable et fonctionnel
- La licence LGPL v3 doit être vérifiée pour les déploiements commerciaux
- Les modèles merged du Hub HuggingFace (souvent en tête des leaderboards) sont fréquemment créés avec mergekit
- Arcee AI construit des produits commerciaux autour de mergekit
