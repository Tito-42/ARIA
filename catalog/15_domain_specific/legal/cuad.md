# CUAD

> Professional legal contract understanding dataset with 500 annotated contracts and 41 clause types

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 15_domain_specific / legal |
| **URL** | https://www.atticusprojectai.org/cuad |
| **GitHub** | https://github.com/TheAtticusProject/cuad |
| **Stars** | ~400 |
| **License** | CC BY 4.0 |
| **Pricing** | Free / Open Source |
| **Last Verified** | 2026-04-02 |
| **Status** | Maintained |
| **Maturity** | Production |

## What It Does
CUAD (Contract Understanding Atticus Dataset) is the industry-standard dataset for training and evaluating AI models that analyze legal contracts. Created by The Atticus Project, it contains 500 commercial contracts annotated by practicing attorneys with 13,000+ labeled examples covering 41 types of important legal clauses.

The dataset was designed to solve a real bottleneck in legal practice: contracts contain critical clauses that need to be identified during due diligence, M&A review, and contract management, but manual review is slow and expensive. CUAD provides a rigorous training foundation for building models that automatically identify and extract these clauses, including high-stakes provisions around termination rights, IP ownership, liability caps, change of control, and non-compete clauses.

Published at NeurIPS 2021, CUAD set the standard for contract AI evaluation and remains the foundation dataset for tools like LexisNexis Contract Analyzer and many legal tech startups. The CC BY 4.0 license explicitly permits commercial use, making it suitable for proprietary product development.

## Key Features
- 500 commercial contracts from SEC EDGAR (real-world, professionally executed contracts)
- 13,000+ labeled examples across 41 clause categories
- Annotated by practicing attorneys, not crowdsourced
- 41 clause types include: Governing Law, Termination for Convenience, Indemnification, IP Ownership, Change of Control, Non-Compete, Liquidated Damages, Limitation of Liability, and more
- QA extractive format: model must locate the exact span in the contract text
- Compatible with Hugging Face Datasets and standard QA fine-tuning pipelines
- Companion leaderboard for model comparison

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | NeurIPS 2021 reference dataset; used by multiple commercial legal AI products |
| **Security** | 5 | Public dataset from SEC EDGAR; no PII; CC BY 4.0 |
| **Scalability** | 5 | Static dataset; scales trivially for training/evaluation |
| **Support/Community** | 4 | Atticus Project, active legal tech community, cited in 500+ papers |
| **Documentation** | 4 | Paper + GitHub + Hugging Face dataset card |
| **Integration Ease** | 5 | Standard Hugging Face Datasets API; drop-in for any QA fine-tuning pipeline |

## Use Cases
1. **Contract clause extraction**: Fine-tuning a model to automatically identify and extract specific clause types from uploaded contracts for contract management platforms
2. **Due diligence acceleration**: Building a tool that flags high-risk clauses (unlimited liability, onerous IP assignment) during M&A or vendor contract review
3. **Contract compliance monitoring**: Automated monitoring of contract databases to surface contracts with expiring notice periods or problematic provisions
4. **Legal AI product development**: Using CUAD as the fine-tuning dataset for a commercial contract review product (CC BY 4.0 explicitly permits this)

## Getting Started
```python
from datasets import load_dataset
from transformers import pipeline

# Load CUAD from Hugging Face
dataset = load_dataset("theatticusproject/cuad")
print(dataset["train"][0])
# {'id': '...', 'title': 'Agreement', 'context': 'This Agreement...', 
#  'question': 'Highlight the parts about Governing Law', 'answers': {...}}

# Fine-tune a QA model on CUAD
from transformers import AutoModelForQuestionAnswering, TrainingArguments, Trainer

model = AutoModelForQuestionAnswering.from_pretrained("nlpaueb/legal-bert-base-uncased")
# ... standard QA fine-tuning setup

# Or use a pre-trained CUAD model
cuad_model = pipeline("question-answering", model="theatticusproject/cuad-electra-large")
result = cuad_model(
    question="What is the governing law for this agreement?",
    context=contract_text
)
```

## Architecture / How It Works
CUAD frames contract understanding as an extractive question answering (QA) task. For each of the 41 clause types, a natural language question is defined (e.g., "Does the contract have a change of control clause?"). The model receives the full contract text as context and must either return the exact passage that answers the question or indicate the answer is not present. This extractive QA approach grounds the model's output in the actual contract text rather than allowing hallucination. Models are evaluated on F1 score and exact match on the answer spans.

## Strengths
- Annotated by real attorneys, not crowdsourced, ensuring high annotation quality
- 41 clause types cover the most commercially important contract provisions
- CC BY 4.0 enables commercial product development without licensing fees
- NeurIPS 2021 pedigree ensures rigorous validation and peer review
- Used as foundation by multiple commercial legal AI products (validates quality)

## Limitations
- English only; no coverage of non-English or civil law jurisdictions
- 500 contracts from SEC EDGAR skews toward US public company contracts; may not generalize to SMB contracts or international agreements
- Extractive QA only; cannot generate redline suggestions or summarize implications
- Does not cover non-disclosure agreements (NDAs), employment contracts, or consumer contracts well
- Last major dataset update was 2021; no new contract types added since

## Alternatives
| Tool | Key Difference |
|------|---------------|
| ContractNLI | Natural language inference on contracts; different task formulation |
| MAUD (M&A contracts) | Specialized for M&A agreement analysis; complements CUAD |
| LegalBench (contract tasks) | Broader legal reasoning; includes contract understanding as a subset |
| EDGAR contracts raw | Raw SEC contracts without annotations; requires custom annotation |

## References
- https://www.atticusprojectai.org/cuad
- https://github.com/TheAtticusProject/cuad
- https://huggingface.co/datasets/theatticusproject/cuad
- Hendrycks et al., "CUAD: An Expert-Annotated NLP Dataset for Legal Contract Review", NeurIPS 2021, arXiv:2103.06268

## Notes
CUAD is the essential starting point for any contract AI product. Its commercial-permissive CC BY 4.0 license and professional annotation quality make it the foundation of choice. For EU law coverage, supplement with ContractNLI and GDPR-specific datasets. For M&A-specific analysis, consider MAUD (Merger Agreement Understanding Dataset) which extends CUAD's approach to acquisition agreements specifically.
