# Chemprop

> Message Passing Neural Networks for molecular property prediction

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 15_domain_specific / healthcare |
| **URL** | https://chemprop.readthedocs.io |
| **GitHub** | https://github.com/chemprop/chemprop |
| **Stars** | ~2,300 |
| **License** | MIT |
| **Pricing** | Free / Open Source |
| **Last Verified** | 2026-04-02 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Chemprop is the leading implementation of Message Passing Neural Networks (MPNN) for molecular property prediction in cheminformatics. It treats molecules as graphs where atoms are nodes and bonds are edges, and learns to predict chemical properties by aggregating information through iterative message passing over this molecular graph. This approach consistently outperforms traditional fingerprint-based methods on most QSAR benchmarks.

Chemprop achieved real-world validation in one of its most cited applications: it was used by MIT researchers to discover Halicin, a novel antibiotic with activity against drug-resistant bacteria, published in Cell (2020). This demonstrated that Chemprop-class models can power genuine drug discovery campaigns. The tool also powers ADMET-AI, a widely used ADMET prediction platform.

Version 2.2.3 (March 2026) is actively maintained by the Coley Group at MIT, making it one of the most current open-source cheminformatics tools available.

## Key Features
- D-MPNN (Directed MPNN) architecture for molecular graph learning
- Multi-task learning for simultaneous prediction of multiple properties
- Uncertainty quantification (ensembles, evidential learning, conformal prediction)
- Atomic and bond-level interpretability via attention weights
- Reaction property prediction beyond individual molecules
- CLI and Python API interfaces
- Hyperparameter optimization via Optuna
- Support for RDKit molecular featurization
- Transfer learning and fine-tuning on custom datasets

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | v2.2.3 March 2026; MIT license; used in published drug discovery campaigns |
| **Security** | 4 | MIT, fully local, no data leaves the environment |
| **Scalability** | 4 | Multi-GPU training; handles millions of molecule predictions |
| **Support/Community** | 4 | MIT Coley Group backing, active GitHub, cited in 1000+ papers |
| **Documentation** | 5 | Comprehensive ReadTheDocs, tutorials, example datasets |
| **Integration Ease** | 4 | Clean CLI and Python API; SMILES input; easy to integrate in pipelines |

## Use Cases
1. **ADMET property prediction**: Predicting bioavailability, solubility, hERG toxicity, and other ADMET properties for compound triage in lead optimization
2. **Virtual screening scoring**: Ranking millions of candidate molecules from a virtual library by predicted activity against a target
3. **Reaction prediction**: Predicting outcomes and selectivity of chemical reactions
4. **Antibiotic discovery**: Screening large chemical databases for novel antibiotics (as demonstrated with Halicin)

## Getting Started
```bash
pip install chemprop

# Train a model on a custom SMILES+property CSV
chemprop train \
  --data_path data/train.csv \
  --smiles_columns smiles \
  --target_columns activity \
  --save_dir checkpoints/

# Predict on new molecules
chemprop predict \
  --test_path data/test.csv \
  --model_path checkpoints/ \
  --preds_path predictions.csv
```

## Architecture / How It Works
Chemprop builds a directed molecular graph from a SMILES string (each bond becomes two directed edges). At each message passing step, each atom aggregates information from its neighboring bonds and atoms. After K steps (typically 3), atom representations are summed to form a molecular fingerprint. A feed-forward network then maps this fingerprint to the predicted property. The D-MPNN formulation (directed, bond-based messages) was shown to outperform atom-based approaches on benchmark datasets.

## Strengths
- Validated in real drug discovery (Halicin antibiotic discovery, Cell 2020)
- Most accurate MPNN implementation with well-tuned defaults
- Uncertainty quantification built-in (essential for active learning campaigns)
- Actively maintained by MIT; March 2026 release is highly current
- MIT license for unrestricted commercial use

## Limitations
- Deep learning approach requires more data than classical ML methods (typically >1000 examples)
- Interpretability is limited compared to tree-based methods despite attention weights
- 3D structural information (pharmacophores, docking poses) is not natively handled
- Slower to train than XGBoost on small datasets

## Alternatives
| Tool | Key Difference |
|------|---------------|
| DeepChem | Broader toolchain with 200+ datasets; less focused than Chemprop |
| MolBERT / ChemBERTa | Transformer-based; better transfer learning on small datasets |
| XGBoost + ECFP | Faster, more interpretable; better on very small datasets (<500 molecules) |
| GraphSAGE / MPNN (PyG) | General graph DL; requires more custom code for molecular tasks |

## References
- https://chemprop.readthedocs.io/
- https://github.com/chemprop/chemprop
- Stokes et al., "A Deep Learning Approach to Antibiotic Discovery", Cell 2020 (Halicin paper)
- Yang et al., "Analyzing Learned Molecular Representations for Property Prediction", JCIM 2019
- ADMET-AI: https://github.com/swansonk14/admet_ai

## Notes
Chemprop is the go-to tool for serious QSAR modeling in pharma. Its combination of MPNN accuracy, uncertainty quantification, and MIT license makes it suitable for production drug discovery pipelines. For small datasets (<500 molecules), complement with a classical XGBoost+ECFP model as a baseline. The fact that it is updated to March 2026 signals strong ongoing maintenance commitment.
