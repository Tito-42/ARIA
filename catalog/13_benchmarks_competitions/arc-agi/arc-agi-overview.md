# ARC-AGI (Abstraction and Reasoning Corpus)

> Benchmark mesurant l'intelligence fluide et le raisonnement abstrait - le test d'AGI de référence

## Metadata
| Field | Value |
|-------|-------|
| **Platform** | Kaggle / ARC Prize |
| **URL** | https://arcprize.org |
| **GitHub** | https://github.com/fchollet/ARC-AGI |
| **Stars** | 4,700 |
| **Year** | 2019 (v1), 2025 (v2) |
| **Prize** | $1M+ (ARC Prize) |
| **Status** | Active |

## Problem Description
ARC-AGI présente des puzzles visuels sur grille où les systèmes doivent inférer des règles de transformation à partir de quelques exemples et les appliquer à de nouveaux inputs. Les grilles sont des matrices rectangulaires d'entiers 0-9 (couleurs), jusqu'à 30x30 cellules. Créé par François Chollet (créateur de Keras) pour mesurer l'intelligence fluide, pas la mémorisation.

### ARC-AGI-1 (Original)
- 400 tâches d'entraînement + 400 d'évaluation
- License: Apache 2.0

### ARC-AGI-2 (2025)
- **1,000 tâches** d'entraînement + **120 d'évaluation**
- Performance humaine moyenne : **66%** sur l'évaluation
- 2 essais autorisés par input de test
- GitHub: https://github.com/arcprize/arc-agi-2

## Winning Approaches

### ARC Prize 2024 - 1st Place: "The Architects" (da-fr)
- **Score**: 53.5 sur le test set caché
- **Solution URL**: https://github.com/da-fr/arc-prize-2024 (189 stars)
- **Key Technique**: Fine-tuned **Mistral-NeMo-Minitron-8B** avec LoRA + Test-Time Training (TTT) + DFS inference + data augmentation + ensemble selection
- **Code Available**: Oui (avec paper détaillé)
- **Infrastructure**: Single NVIDIA H100 GPU

### ARC Prize 2024 - Silver Medal: BillyYang-creator
- **Solution URL**: https://github.com/BillyYang-creator/arc-prize-2024
- **Key Technique**: DSL symbolique en C++ avec heuristic search, sans neural networks
- **Code Available**: Oui

### ARC Prize 2025 - 1st Place: NVARC (NVIDIA Kaggle Grandmasters)
- **Score**: Top 1
- **Solution URL**: https://github.com/1ytic/NVARC (104 stars)
- **Team**: Ivan Sorokin & Jean-François Puget (NVIDIA)
- **Key Technique**: 3 composants - (1) Synthetic data generation (103K puzzles, 3.2M variants), (2) Fine-tuned **Qwen3 4B** avec Unsloth Flash LoRA, (3) Tiny Recursive Models (TRM)
- **Code Available**: Oui (avec paper)

### Autres approches notables
| Projet | Stars | Approche |
|--------|-------|----------|
| verantyx-v6 | 8 | Hybride: 30+ solvers + Claude Sonnet 4.5 program synthesis (84% training) |
| ARC-GEN (Google) | 41 | Générateur procédural de benchmarks |
| arc-dataset-collection | 86 | Collection de datasets ARC |
| ARC-Interactive-History | 117 | Enregistrements d'humains résolvant ARC |

## Key Takeaways for Enterprise
- **Hybride neural + symbolique** : les meilleures solutions combinent LLMs fine-tunés + raisonnement symbolique/DSL
- **Test-Time Training (TTT)** : technique clé - adapter le modèle aux exemples de test à la volée
- **Small models win** : Mistral 8B et Qwen 4B battent les gros modèles via fine-tuning spécialisé
- **Synthetic data** : génération massive de données synthétiques (3.2M variants pour NVARC)
- **Le benchmark n'est PAS résolu** : loin de la performance humaine (66%), l'AGI reste un défi

## Relevant Tools/Libraries Used
- Unsloth (fine-tuning rapide) → voir catalog/06_finetuning_training/
- LoRA/QLoRA (adaptation légère) → voir catalog/06_finetuning_training/
- Mistral-NeMo, Qwen3 → voir catalog/14_open_source_llms/

## References
- [ARC Prize](https://arcprize.org)
- [Paper original: "On the Measure of Intelligence"](https://arxiv.org/abs/1911.01547)
- [ARC-AGI-2 Technical Report](http://arcprize.org/blog/arc-agi-2-technical-report)
- [Solution "The Architects"](https://github.com/da-fr/arc-prize-2024)
- [Solution NVARC](https://github.com/1ytic/NVARC)
