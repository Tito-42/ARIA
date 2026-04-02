# ImageBind

> Meta FAIR's open-source model that learns a joint embedding space across six modalities — image, text, audio, depth, thermal, and IMU — enabling zero-shot cross-modal transfer.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 17 - multimodal / omnimodal |
| **URL** | https://imagebind.metademolab.com/ |
| **GitHub** | https://github.com/facebookresearch/ImageBind |
| **Stars** | 9 000 |
| **License** | CC BY-NC 4.0 (non-commercial) |
| **Pricing** | Free / Open Weights (non-commercial) |
| **Last Verified** | 2026-04-02 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
ImageBind is a foundation model from Meta FAIR that learns a single joint embedding space across six different modalities: images/video, text, audio, depth maps, thermal (infrared) images, and IMU (inertial measurement unit) data. The key insight is that images co-occur naturally with all other modalities — a street scene can have paired audio (traffic sounds), depth (stereo camera), and thermal data — and by using images as the binding modality, all six spaces can be aligned without requiring direct pairing between non-image modalities.

The result is remarkable: a text query can retrieve audio (describe a sound to find it), audio can retrieve images (a dog bark retrieves pictures of dogs), and depth maps can retrieve text descriptions, all in a unified embedding space. This enables zero-shot cross-modal transfer without any explicit training on those pairs.

Presented at CVPR 2023, ImageBind remains the only major open-source model covering six modalities including the physically-grounded ones (depth, thermal, IMU) that are critical for robotics, AR/VR, and industrial applications.

## Key Features
- Single joint embedding space across 6 modalities: image, text, audio, depth, thermal, IMU
- Zero-shot cross-modal retrieval (any modality → any modality)
- ImageBind-as-retriever: universal similarity search across modalities
- Emergent zero-shot cross-modal generation when combined with generation models
- PyTorch implementation with pre-trained weights
- Audio to image retrieval and image to audio retrieval
- Combined embedding arithmetic (text + audio → image retrieval)
- Used as audio encoder in Video-LLaMA

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 3 | Research model used in production as component; CC BY-NC limits commercial use |
| **Security** | 3 | CC BY-NC 4.0 prohibits commercial use without Meta licensing |
| **Scalability** | 4 | Efficient embedding inference; standard contrastive architecture |
| **Support/Community** | 4 | Meta FAIR backing, 9K stars, widely referenced in academic work |
| **Documentation** | 4 | Good README, demo notebook, CVPR paper |
| **Integration Ease** | 3 | PyTorch native; requires custom integration work for production use cases |

## Use Cases
1. **Cross-modal retrieval systems** - Search image databases by audio description, or find audio matching an image, for media archives and content platforms
2. **Robotics sensor fusion** - Align embeddings from cameras, depth sensors, thermal cameras, and IMU for robot perception
3. **AR/VR multimodal understanding** - Combine visual, audio, and spatial (depth/IMU) data for immersive environment understanding
4. **Audio-visual content analysis** - Find visual scenes matching audio clips (security footage, media production)
5. **Component in larger systems** - Used as audio encoder in Video-LLaMA, as part of larger omnimodal pipelines

## Getting Started
```bash
git clone https://github.com/facebookresearch/ImageBind
cd ImageBind
pip install -r requirements.txt

import data
import torch
from models import imagebind_model
from models.imagebind_model import ModalityType

model = imagebind_model.imagebind_huge(pretrained=True)
model.eval()
model.to("cuda")

inputs = {
    ModalityType.TEXT: data.load_and_transform_text(["A dog barking"], device="cuda"),
    ModalityType.AUDIO: data.load_and_transform_audio_data(["dog_bark.wav"], device="cuda"),
    ModalityType.VISION: data.load_and_transform_vision_data(["dog.jpg"], device="cuda"),
}
with torch.no_grad():
    embeddings = model(inputs)

print("Similarity TEXT-AUDIO:", torch.softmax(
    embeddings[ModalityType.TEXT] @ embeddings[ModalityType.AUDIO].T, dim=-1
))
```

## Architecture / How It Works
ImageBind uses a ViT-H/14 (Huge) vision transformer as the image encoder. Each non-image modality has its own encoder that is trained to align with the image embedding space using contrastive learning (InfoNCE loss). The training uses naturally co-occurring data pairs from the internet: image-text from web pages, image-audio from videos, image-depth from 3D datasets, image-thermal from thermal camera datasets, and image-IMU from egocentric video with IMU sensors. This binding approach means the non-image modalities can communicate with each other through the shared image space, even without direct training pairs.

## Strengths
- Only major open-source model covering depth, thermal, and IMU alongside text/image/audio
- Emergent cross-modal capabilities with no direct non-image modality pairing
- Clean PyTorch implementation, well-suited as a research building block
- Enables embedding arithmetic across modalities
- Widely adopted as a component in larger systems (Video-LLaMA, etc.)

## Limitations
- CC BY-NC 4.0 license prohibits commercial use — significant barrier for enterprise
- Not updated since 2023; newer models may offer better individual modality performance
- No instruction-following capability; pure embedding model
- Single embedding size for all modalities limits expressiveness for some tasks
- GPU required for efficient inference (model is ViT-H/14 scale)

## Alternatives
| Tool | Key Difference |
|------|---------------|
| CLIP | Text+image only; commercial license options; widely deployed |
| CLAP | Audio+text only; commercial-friendly; better audio retrieval |
| LanguageBind | Extends ImageBind approach; video-centric; newer |
| OpenCLIP | Open-source CLIP with Apache 2.0; text+image only |

## References
- https://imagebind.metademolab.com/
- https://github.com/facebookresearch/ImageBind
- https://arxiv.org/abs/2305.05665 (ImageBind CVPR 2023 paper)

## Notes
ImageBind is architecturally significant and remains the go-to reference for multi-modal embedding research covering physical sensors (depth, thermal, IMU). The CC BY-NC 4.0 license is the main commercial barrier. For commercial applications requiring cross-modal retrieval, consider combining specialized models (CLIP for image-text, CLAP for audio-text) unless the unique 6-modality or IMU/thermal capabilities are specifically needed.
