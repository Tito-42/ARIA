# MedicalGPT

> Complete pipeline for training custom medical LLMs using ChatGPT-style RLHF methodology

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 15_domain_specific / healthcare |
| **URL** | https://github.com/shibing624/MedicalGPT |
| **GitHub** | https://github.com/shibing624/MedicalGPT |
| **Stars** | ~5,200 |
| **License** | Apache 2.0 |
| **Pricing** | Free / Open Source |
| **Last Verified** | 2026-04-02 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
MedicalGPT is a comprehensive training pipeline for building custom medical language models following the ChatGPT methodology. It supports the full training lifecycle: incremental pretraining on medical corpora, supervised fine-tuning (SFT), RLHF with PPO, and modern alignment techniques including DPO, ORPO, and GRPO (added in v2.4, April 2025).

The project is built on 2.4 million Chinese medical Q&A examples and supports a broad set of base models including Llama, Qwen, Baichuan, and ChatGLM. Beyond training, it includes a ChatPDF-style RAG module for question-answering on patient records and medical documents, making it a near-complete platform for custom medical AI deployment.

While the primary training corpus is in Chinese (reflecting its origins in the Chinese medical AI research community), the pipeline architecture is fully generalizable to English or multilingual medical datasets by substituting the training data.

## Key Features
- Full training pipeline: pretraining, SFT, RLHF/PPO, DPO, ORPO, GRPO
- Supports Llama, Qwen, Baichuan, ChatGLM, and other base models
- 2.4M Chinese medical Q&A training examples included
- RAG module (ChatPDF) for Q&A on patient records and medical PDFs
- Parameter-efficient fine-tuning via LoRA and QLoRA
- Gradio web interface for inference and demonstration
- Multi-GPU training with DeepSpeed integration

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Used in real medical applications in China; Apache 2.0 commercial use allowed |
| **Security** | 3 | Training pipeline only; inference deployment security is user responsibility |
| **Scalability** | 4 | DeepSpeed multi-GPU support; LoRA reduces hardware requirements significantly |
| **Support/Community** | 4 | 5.2k stars, active issues, Chinese community primarily |
| **Documentation** | 4 | Detailed README with training commands; English documentation could be improved |
| **Integration Ease** | 3 | Requires ML engineering expertise; not a no-code solution |

## Use Cases
1. **Custom clinical chatbot**: Fine-tune a medical LLM on your institution's internal clinical guidelines, drug formularies, and protocols for staff Q&A
2. **Patient-facing Q&A**: Build a medical information assistant trained on domain-specific data with RLHF alignment for safety
3. **Medical RAG over patient records**: Use the ChatPDF module to enable doctors to query patient history documents in natural language
4. **Chinese medical AI**: Ready-to-use solution for Chinese healthcare applications with 2.4M examples included

## Getting Started
```bash
git clone https://github.com/shibing624/MedicalGPT
cd MedicalGPT
pip install -r requirements.txt

# Step 1: Supervised Fine-Tuning with LoRA
python supervised_finetuning.py \
  --model_name_or_path Qwen/Qwen2.5-7B \
  --train_file_dir data/finetune \
  --output_dir outputs/sft \
  --num_train_epochs 3 \
  --per_device_train_batch_size 4 \
  --use_peft True \
  --lora_rank 8

# Step 2: DPO alignment
python dpo_training.py \
  --model_name_or_path outputs/sft \
  --train_file_dir data/dpo \
  --output_dir outputs/dpo
```

## Architecture / How It Works
MedicalGPT implements the 4-stage ChatGPT training recipe applied to the medical domain: (1) Continued pretraining on medical corpora to inject domain knowledge, (2) SFT on medical Q&A pairs to train instruction following, (3) Reward model training on human preference data, (4) Alignment via PPO, DPO, or the newer GRPO. Each stage builds on the previous. The LoRA integration makes each stage feasible on a single A100 or even consumer GPUs for smaller models.

## Strengths
- Most comprehensive open-source pipeline for end-to-end medical LLM creation
- Supports modern alignment methods (GRPO added 2025) not found in older pipelines
- Practical LoRA integration reduces compute requirements significantly
- Apache 2.0 allows commercial deployment

## Limitations
- Primary training data is in Chinese; English medical deployment requires sourcing separate datasets
- Not a pretrained model you can use directly; requires training infrastructure and ML expertise
- Medical accuracy validation is the user's responsibility; no built-in clinical benchmarking
- Last update April 2025; may lag behind the latest base models

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Meditron (EPFL) | Pretrained medical LLM ready to use; less flexibility for customization |
| BioMistral | Multilingual pretrained medical model; no training pipeline included |
| LLaMA-Factory | General fine-tuning framework; supports medical but not domain-specialized |
| Axolotl | General SFT/RLHF framework; more flexible but less medically focused |

## References
- https://github.com/shibing624/MedicalGPT
- https://huggingface.co/shibing624 (model releases)
- GRPO paper: https://arxiv.org/abs/2402.03300

## Notes
Best suited for organizations that want to build a highly customized medical LLM on proprietary data. For a faster path to a working medical chatbot, consider starting with a pretrained model like BioMistral or Meditron and adding a RAG layer rather than training from scratch.
