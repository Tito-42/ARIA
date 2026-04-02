# LM Evaluation Harness

> Framework d'évaluation standardisé pour LLMs avec 200+ benchmarks, standard pour Open LLM Leaderboard

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 06_finetuning_training |
| **URL** | https://github.com/EleutherAI/lm-evaluation-harness |
| **GitHub** | https://github.com/EleutherAI/lm-evaluation-harness |
| **Stars** | 12,000 |
| **License** | MIT |
| **Pricing** | Free / Open Source |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
LM Evaluation Harness est un framework d'évaluation développé par EleutherAI permettant de mesurer les performances des LLMs sur plus de 200 benchmarks standardisés. C'est l'infrastructure qui propulse le HuggingFace Open LLM Leaderboard, ce qui en fait le standard de facto pour l'évaluation comparative des modèles open source.

Le framework s'appuie sur une architecture de tâches modulaire où chaque benchmark est défini comme une tâche YAML indépendante. Il supporte les modèles HuggingFace, OpenAI API, Anthropic API, les modèles GGUF (via llama.cpp) et d'autres backends, permettant une comparaison uniforme entre modèles open source et propriétaires.

En tant que standard pour le Open LLM Leaderboard et nombreuses publications académiques, les résultats obtenus avec LM Evaluation Harness sont reconnus et reproductibles, ce qui en fait un outil incontournable pour toute équipe sérieuse d'évaluation LLM.

## Key Features
- **200+ benchmarks** : MMLU, HellaSwag, ARC, TruthfulQA, GSM8K, HumanEval, et bien plus
- **Multi-backend** : HuggingFace, OpenAI API, Anthropic, GGUF (llama.cpp), vLLM
- **Tâches YAML** : définition de nouveaux benchmarks sans code Python
- **Few-shot configurable** : 0-shot à N-shot pour chaque tâche
- **Batch evaluation** : évaluation efficace par batch
- **Résultats JSON** : output structuré pour analyse et comparaison
- **Filtres et transformations** : preprocessing des données configurable
- **Génération de texte et log-likelihood** : deux modes d'évaluation
- **Intégration W&B / MLflow** : logging des résultats

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Standard pour évaluation, stable, utilisé par HuggingFace |
| **Security** | 4 | Outil local, pas de surface réseau, MIT license permissive |
| **Scalability** | 3 | Peut être lent sur gros modèles, optimisation via batch size |
| **Support/Community** | 4 | Communauté EleutherAI active, issues répondues |
| **Documentation** | 4 | Documentation claire, nombreux exemples |
| **Integration Ease** | 4 | CLI simple, API Python, compatible HuggingFace Hub |

## Use Cases
1. **Évaluation post-fine-tuning** : mesurer l'impact d'un fine-tuning sur les benchmarks standards
2. **Comparaison de modèles** : comparer différents modèles de manière reproductible
3. **Soumission Open LLM Leaderboard** : préparer les résultats pour le leaderboard HuggingFace
4. **Régression testing** : vérifier qu'une mise à jour du modèle ne dégrade pas les performances
5. **Évaluation modèles propriétaires** : benchmarker via API OpenAI/Anthropic avec les mêmes métriques

## Getting Started
```bash
# Installation
pip install lm-eval

# Évaluation basique sur MMLU
lm_eval --model hf \
    --model_args pretrained=meta-llama/Llama-3-8B \
    --tasks mmlu \
    --device cuda:0 \
    --batch_size 8

# Suite de benchmarks standard (style leaderboard)
lm_eval --model hf \
    --model_args pretrained=my-finetuned-model \
    --tasks arc_challenge,hellaswag,mmlu,truthfulqa_mc2,winogrande,gsm8k \
    --num_fewshot 25,10,5,0,5,5 \
    --output_path results/

# Avec vLLM pour accélération
lm_eval --model vllm \
    --model_args pretrained=my-model,dtype=bfloat16 \
    --tasks mmlu
```

## Architecture / How It Works
```
LM Evaluation Harness Architecture
├── Task Registry
│   ├── 200+ tâches YAML    →  Définition benchmarks
│   ├── Groupes de tâches   →  mmlu, leaderboard, etc.
│   └── Custom tasks        →  Ajout de nouveaux benchmarks
├── Model Backends
│   ├── HuggingFace (local) →  transformers AutoModel
│   ├── vLLM               →  Inférence accélérée
│   ├── OpenAI API          →  GPT-4, etc.
│   ├── Anthropic API       →  Claude, etc.
│   └── GGUF (llama.cpp)   →  Modèles quantifiés
├── Evaluation Engine
│   ├── Log-likelihood      →  Multiple choice tasks
│   └── Generation          →  Open-ended tasks
└── Output
    ├── JSON results        →  Métriques détaillées
    └── Summary table       →  Vue comparative
```

## Strengths
- Standard de facto pour l'évaluation comparative LLM (Open LLM Leaderboard)
- Résultats reproductibles et comparables entre équipes
- Large couverture de benchmarks couvrant tous les aspects des LLMs
- Support multi-backend pour évaluer aussi bien les modèles open source que propriétaires
- Licence MIT très permissive

## Limitations
- Peut être très lent sur de gros modèles sans accélération (vLLM recommandé)
- Certains benchmarks peuvent être contaminés (données d'entraînement du modèle)
- Configuration parfois complexe pour les tâches peu standard
- Ne couvre pas tous les aspects (ex : évaluation subjective de la qualité)

## Alternatives
| Tool | Key Difference |
|------|---------------|
| HELM (Stanford) | Suite d'évaluation alternative plus large mais plus lente |
| BIG-bench | Benchmark Google DeepMind, plus de tâches spécialisées |
| Evals (OpenAI) | Framework OpenAI, moins standard pour modèles open source |
| lighteval (HF) | Alternative HuggingFace, plus légère et plus rapide |

## References
- [GitHub Repository](https://github.com/EleutherAI/lm-evaluation-harness)
- [Documentation](https://github.com/EleutherAI/lm-evaluation-harness/blob/main/docs/README.md)
- [Open LLM Leaderboard](https://huggingface.co/spaces/HuggingFaceH4/open_llm_leaderboard)
- [Paper original](https://arxiv.org/abs/2110.08207)

## Notes
- Dernière mise à jour active : décembre 2025
- Utilisé directement par HuggingFace pour le Open LLM Leaderboard
- La tâche `leaderboard` regroupe les benchmarks standards du leaderboard
- Pour les modèles très larges, utiliser `--model vllm` pour l'accélération
