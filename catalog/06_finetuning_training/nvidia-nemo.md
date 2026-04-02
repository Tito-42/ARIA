# NVIDIA NeMo

> Framework NVIDIA enterprise pour training, fine-tuning et déploiement de LLMs et modèles speech/vision à grande échelle

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 06_finetuning_training |
| **URL** | https://www.nvidia.com/en-us/ai-data-science/products/nemo/ |
| **GitHub** | https://github.com/NVIDIA/NeMo |
| **Stars** | 17,000 |
| **License** | Apache 2.0 |
| **Pricing** | Free / Open Source (NeMo Microservices payants) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Enterprise |

## What It Does
NVIDIA NeMo est un framework complet pour le développement de modèles d'IA à grande échelle, couvrant le cycle complet de training, fine-tuning, alignment et déploiement. Il est optimisé pour les GPU NVIDIA et s'intègre nativement avec Megatron-LM pour le parallelism avancé, ainsi qu'avec l'infrastructure NVIDIA (DGX, BCP, NGC).

NeMo est particulièrement adapté aux organisations qui veulent une solution enterprise-grade pour entraîner ou fine-tuner des modèles de très grande taille (70B, 180B, voire plus). Il supporte le pré-entraînement complet, le fine-tuning supervisé, RLHF, DPO et les modèles speech (ASR/TTS).

La version v2.7.2 (mars 2026) renforce le support des architectures transformer modernes et améliore l'intégration avec la NeMo Platform cloud de NVIDIA. C'est le choix privilégié des entreprises qui opèrent dans l'écosystème NVIDIA et ont besoin d'un support commercial officiel.

## Key Features
- **Megatron-LM integration** : tensor, pipeline et sequence parallelism pour modèles 100B+
- **NeMo Curator** : curation et filtrage de données à grande échelle
- **NeMo Aligner** : RLHF, DPO, SteerLM pour alignment
- **NeMo Guardrails** : contrôle comportemental des LLMs (séparé)
- **ASR/TTS** : modèles speech de classe mondiale (Conformer, FastPitch, HifiGAN)
- **Multi-modal** : vision-language models
- **Export TensorRT-LLM** : optimisation pour inférence NVIDIA
- **BCP support** : Base Command Platform pour clusters NVIDIA DGX
- **LoRA / P-Tuning** : méthodes PEFT intégrées

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | Framework enterprise NVIDIA, v2.7.2, SLA commercial disponible |
| **Security** | 4 | Projet NVIDIA officiel, maintenu activement, compliance enterprise |
| **Scalability** | 5 | Conçu pour clusters DGX massifs, Megatron pour modèles 1T+ |
| **Support/Community** | 4 | Support NVIDIA officiel disponible, communauté active |
| **Documentation** | 4 | Documentation complète, guides enterprise, tutoriels détaillés |
| **Integration Ease** | 3 | Fortement couplé à NVIDIA, courbe d'apprentissage significative |

## Use Cases
1. **Pre-training LLM enterprise** : entraîner un modèle propriétaire from scratch sur cluster NVIDIA DGX
2. **Fine-tuning modèles 70B+** : adapter des modèles très larges avec Megatron parallelism
3. **Pipeline speech complet** : ASR + NLP + TTS pour applications voice enterprise
4. **RLHF production** : alignment de LLMs à grande échelle via NeMo Aligner
5. **Déploiement optimisé NVIDIA** : exporter vers TensorRT-LLM pour inference optimale

## Getting Started
```bash
# Via Docker (recommandé)
docker pull nvcr.io/nvidia/nemo:24.12

# Ou pip (version allégée)
pip install nemo_toolkit['all']

# Fine-tuning SFT
python examples/nlp/language_modeling/tuning/megatron_gpt_sft.py \
    trainer.devices=8 \
    trainer.num_nodes=1 \
    model.restore_from_path=/path/to/model.nemo \
    model.data.train_ds.file_path=/path/to/train.jsonl

# Via NeMo Framework Launcher
python main.py \
    stages=[sft] \
    cluster_type=bcm \
    sft.model.restore_from_path=...
```

## Architecture / How It Works
```
NVIDIA NeMo Stack
├── NeMo Framework (Core)
│   ├── NeMo LLM           →  Language models training/fine-tuning
│   │   └── Megatron-LM    →  Tensor/Pipeline/Sequence parallelism
│   ├── NeMo ASR           →  Speech recognition (Conformer, etc.)
│   ├── NeMo TTS           →  Text-to-speech synthesis
│   └── NeMo Vision        →  Vision models
├── NeMo Tools
│   ├── NeMo Curator       →  Data curation at scale
│   ├── NeMo Aligner       →  RLHF/DPO alignment
│   └── NeMo Guardrails    →  Behavioral control
└── Infrastructure
    ├── BCP (Base Command Platform)
    ├── DGX Systems
    └── TensorRT-LLM (export)
```

## Strengths
- Solution enterprise-grade complète couvrant tout le lifecycle ML
- Optimisations NVIDIA de premier ordre pour performance GPU maximale
- Support Megatron-LM pour les modèles les plus larges du marché
- Pipeline speech (ASR/TTS) de classe mondiale intégré
- Support commercial NVIDIA disponible pour les entreprises

## Limitations
- Fortement couplé à l'écosystème NVIDIA (vendor lock-in potentiel)
- Courbe d'apprentissage significative, complexité élevée
- Moins adapté aux environnements multi-cloud ou non-NVIDIA
- Container Docker recommandé, setup environnement complexe

## Alternatives
| Tool | Key Difference |
|------|---------------|
| LLaMA-Factory | Plus accessible, multi-framework, moins enterprise mais plus agile |
| DeepSpeed | Microsoft, multi-hardware, moins spécialisé NVIDIA |
| Megatron-LM | Backend bas niveau de NeMo, ultra-spécialisé training distribué |
| Axolotl | Beaucoup plus simple, pas de support modèles 100B+ |

## References
- [Site officiel NeMo](https://www.nvidia.com/en-us/ai-data-science/products/nemo/)
- [GitHub Repository](https://github.com/NVIDIA/NeMo)
- [Documentation](https://docs.nvidia.com/nemo-framework/user-guide/latest/)
- [NGC Container](https://catalog.ngc.nvidia.com/orgs/nvidia/containers/nemo)
- [NeMo Aligner](https://github.com/NVIDIA/NeMo-Aligner)

## Notes
- Version v2.7.2 (mars 2026) améliore l'intégration avec NeMo Platform cloud
- Idéal pour les organisations déjà investies dans l'infrastructure NVIDIA DGX
- NeMo Guardrails est un projet séparé (https://github.com/NVIDIA/NeMo-Guardrails)
- Support PyTorch Lightning en interne pour la gestion du training
