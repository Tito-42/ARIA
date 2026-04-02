# MedSAM

> Segment Anything Model adapted for interactive medical image segmentation

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 15_domain_specific / healthcare |
| **URL** | https://github.com/bowang-lab/MedSAM |
| **GitHub** | https://github.com/bowang-lab/MedSAM |
| **Stars** | ~4,200 |
| **License** | Apache 2.0 |
| **Pricing** | Free / Open Source |
| **Last Verified** | 2026-04-02 |
| **Status** | Maintained |
| **Maturity** | Beta |

## What It Does
MedSAM is a fine-tuned version of Meta's Segment Anything Model (SAM) specifically trained and validated on medical images. While SAM is a powerful general-purpose segmentation model, it performs poorly on medical imaging modalities (CT, MRI, ultrasound) due to the domain gap between natural photographs and medical scans. MedSAM addresses this by training SAM on over 1.5 million medical image-mask pairs across 11 medical imaging modalities.

The model supports interactive segmentation via bounding box prompts: the user draws a box around the structure of interest, and MedSAM segments it precisely. This makes it suitable for semi-automated annotation workflows and clinical decision support. A LiteMedSAM variant provides 10x faster inference for resource-constrained environments.

The project includes a 3D Slicer plugin, which is the standard open-source medical image viewer used in hospitals and research institutions, facilitating clinical adoption without requiring custom UI development.

## Key Features
- Fine-tuned on 1.5M+ medical image-mask pairs across CT, MRI, ultrasound, X-ray, dermoscopy, and endoscopy
- Interactive bounding-box segmentation of anatomical structures
- LiteMedSAM: lightweight variant with 10x faster inference
- 3D Slicer plugin for clinical integration (no custom UI needed)
- CLI, Jupyter notebook, and PyQt5 GUI interfaces
- Automatic windowing adjustment for CT/MRI density ranges
- Support for 2D slices and 3D volumes

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 3 | Research-grade; last commit Sept 2024; needs validation for clinical use |
| **Security** | 3 | Apache 2.0; clinical data security is deployment responsibility |
| **Scalability** | 3 | Single-model inference; no built-in batch processing pipeline |
| **Support/Community** | 4 | Active paper citations; community contributions; 3D Slicer ecosystem |
| **Documentation** | 4 | Good README, tutorial notebooks, paper with methodology |
| **Integration Ease** | 4 | 3D Slicer plugin simplifies clinical integration; Python API also available |

## Use Cases
1. **Annotation acceleration**: Semi-automated annotation of medical images to build training datasets, reducing labeling time by 3-5x compared to manual drawing
2. **Tumor delineation**: Interactive segmentation of lesions in CT/MRI for radiotherapy planning with radiologist validation
3. **Research pipelines**: Rapid prototyping of segmentation experiments without training a dedicated model from scratch
4. **Clinical decision support**: Bounding-box-driven organ and structure identification for radiologist workflow augmentation

## Getting Started
```bash
git clone https://github.com/bowang-lab/MedSAM
cd MedSAM
pip install -e .

# Download checkpoint
wget https://dl.fbaipublicfiles.com/segment_anything/sam_vit_b_01ec64.pth

# Run inference on a CT slice
python MedSAM_Inference.py \
  -i image.nii.gz \
  -o output/ \
  --box "[50, 60, 200, 250]"
```

## Architecture / How It Works
MedSAM builds on SAM's Vision Transformer (ViT) backbone. The image encoder (ViT-B) processes the medical image into embeddings, the prompt encoder converts the bounding box into positional embeddings, and the mask decoder produces the segmentation mask. MedSAM fine-tunes the entire model on medical data while preserving the interactive prompting interface. LiteMedSAM replaces the heavy ViT-B encoder with a lightweight TinyViT for embedded/edge use.

## Strengths
- Directly leverages Meta's SAM architecture without having to design a custom segmentation network
- 3D Slicer plugin provides immediate integration into existing clinical radiology workflows
- LiteMedSAM enables deployment on modest hardware
- No model training required for new modalities if within the training distribution

## Limitations
- Last major update September 2024; development pace has slowed
- Bounding box prompting requires human interaction; not fully autonomous
- Performance degrades on rare modalities not well-represented in training data
- Not FDA/CE-MDR cleared; requires institutional validation before clinical use

## Alternatives
| Tool | Key Difference |
|------|---------------|
| MONAI | Full training framework; not limited to segmentation; requires training data |
| SAM 2 (Meta) | General SAM for video and images; not fine-tuned for medical data |
| nnU-Net | Automated training pipeline; superior accuracy when enough training data available |
| TotalSegmentator | Fully automated (no user prompt) CT segmentation of 100+ structures |

## References
- https://github.com/bowang-lab/MedSAM
- Ma et al., "Segment Anything in Medical Images", Nature Communications 2024
- https://slicer.org/ (3D Slicer, the clinical viewer)
- LiteMedSAM paper: https://arxiv.org/abs/2403.08905

## Notes
MedSAM is best used as an annotation acceleration tool or for research prototyping. For production clinical segmentation of specific structures (e.g., prostate, liver, kidneys), TotalSegmentator or a specialized MONAI model trained on institutional data will deliver better accuracy. The 3D Slicer plugin is the fastest path to a clinical pilot.
