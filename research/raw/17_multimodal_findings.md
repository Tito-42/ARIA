# 17_multimodal — Research Findings
**Date**: 2026-04-02
**Sources**: GitHub repos, HuggingFace, web search, awesome-multimodal-LLMs list
**Chercheur**: Agent Researcher ARIA

---

## Synthese

La categorie 17_multimodal couvre les modeles et outils qui combinent plusieurs modalites (texte, image, audio, video, profondeur, etc.). En 2025-2026, c'est l'une des categories les plus actives : quasi tous les grands labs (Meta, Google, Microsoft, Alibaba, DeepSeek, ByteDance) publient des VLMs open-source competitifs. L'espace se divise en :
1. **Vision-Language Models (VLMs)** : comprendre/repondre a partir d'images
2. **Document AI** : extraire du contenu structure depuis PDFs/images de documents
3. **Video Understanding** : comprendre des videos et sequences temporelles
4. **Audio-Visual / Omnimodal** : combiner audio, image, texte et plus
5. **Multimodal RAG** : retrieval qui exploite les modalites visuelles
6. **World Models / Embodied AI** : modeles pour la robotique et la simulation

---

## 1. VISION-LANGUAGE MODELS (VLMs)

### 1.1 LLaVA / LLaVA-NeXT
- **URL**: https://github.com/haotian-liu/LLaVA
- **GitHub**: https://github.com/haotian-liu/LLaVA
- **Stars**: 24 600
- **Licence**: Apache 2.0
- **Source de decouverte**: GitHub trending + reference directe
- **Date de recherche**: 2026-04-02
- **Categorie suggeree**: 17_multimodal/vision-language
- **Modalites**: texte + image (video via LLaVA-NeXT)
- **Description**: Modele instruction-tuned combinant un encodeur vision fige (CLIP ViT) avec un LLM via un connecteur entraine. La serie LLaVA-NeXT (jan-mai 2024) ajoute support Llama-3, Qwen-1.5, video zero-shot et resolution x4.
- **Pourquoi c'est pertinent**: Reference de facto pour VLMs open-source ; base de nombreux autres projets (Video-LLaVA, LLaMA-VID, Mantis). Excelente documentation, support LoRA/4bit/8bit.

### 1.2 InternVL / InternVL3.5
- **URL**: https://github.com/OpenGVLab/InternVL
- **GitHub**: https://github.com/OpenGVLab/InternVL
- **Stars**: 9 900
- **Licence**: MIT (code) / modele sous license specifique
- **Source de decouverte**: Awesome-Multimodal-LLMs list + web
- **Date de recherche**: 2026-04-02
- **Categorie suggeree**: 17_multimodal/vision-language
- **Modalites**: texte + image + video
- **Description**: Serie de modeles multimodaux open-source de 1B a 241B parametres (MoE), presentee comme alternative open-source a GPT-4o. InternVL2.5-78B premier open-source a depasser 70% sur MMMU. InternVL3.5 241B-A28B est le flagship 2025.
- **Pourquoi c'est pertinent**: Performances SOTA open-source sur quasi tous les benchmarks multimodaux (MMMU, MMStar, MathVista). Tres actif, mis a jour regulierement.

### 1.3 Qwen2-VL / Qwen2.5-VL / Qwen3-VL
- **URL**: https://github.com/QwenLM/Qwen2-VL
- **GitHub**: https://github.com/QwenLM/Qwen2-VL (puis Qwen2.5-VL, redirige vers Qwen3-VL)
- **Stars**: 18 800 (repo Qwen2-VL/Qwen3-VL combine)
- **Licence**: Qwen License (commercial permis sous conditions)
- **Source de decouverte**: GitHub + HuggingFace trending
- **Date de recherche**: 2026-04-02
- **Categorie suggeree**: 17_multimodal/vision-language
- **Modalites**: texte + image (haute resolution) + video + documents
- **Description**: Serie VLM d'Alibaba Cloud (7B/72B). Qwen-VL original supporte bilingual EN/ZH, grounding bounding boxes, images jusqu'a millions de pixels. Qwen2.5-VL (jan 2025) ajoute comprehension video longue. Qwen3-VL (2026) est le nouveau flagship : "le plus puissant de la serie", avec reasoning spatial, video dynamics et capacites agentic.
- **Pourquoi c'est pertinent**: Meilleur VLM open-source dans sa gamme de taille pour les taches document/OCR/multilingual. Tres utilise en production.

### 1.4 MiniGPT-4 / MiniGPT-v2
- **URL**: https://github.com/Vision-CAIR/MiniGPT-4
- **GitHub**: https://github.com/Vision-CAIR/MiniGPT-4
- **Stars**: 25 800
- **Licence**: BSD 3-Clause
- **Source de decouverte**: GitHub search
- **Date de recherche**: 2026-04-02
- **Categorie suggeree**: 17_multimodal/vision-language
- **Modalites**: texte + image
- **Description**: Un des premiers VLMs open-source de haute qualite, combinant Llama 2/Vicuna avec BLIP-2. MiniGPT-v2 est une interface unifiee multi-taches vision-language. Bonne base pedagogique et de recherche.
- **Pourquoi c'est pertinent**: Tres cite academiquement (base de beaucoup de papiers). Toujours pertinent comme reference historique et pour le fine-tuning.

### 1.5 CogVLM / CogVLM2
- **URL**: https://github.com/THUDM/CogVLM
- **GitHub CogVLM**: https://github.com/THUDM/CogVLM (6 700 stars)
- **GitHub CogVLM2**: https://github.com/THUDM/CogVLM2 (2 400 stars)
- **Licence**: Apache 2.0 (code) + Meta Llama 3 license (modele)
- **Source de decouverte**: GitHub search
- **Date de recherche**: 2026-04-02
- **Categorie suggeree**: 17_multimodal/vision-language
- **Modalites**: texte + image (resolution 1344x1344) + video (CogVLM2)
- **Description**: VLM de Tsinghua (THUDM) avec 10B parametres vision. CogVLM2 base sur Llama3-8B, niveau GPT-4V, supporte 8K context, taches TextVQA/DocVQA/ChartQA. CogAgent (variant) specialise dans la comprehension d'interfaces GUI.
- **Pourquoi c'est pertinent**: CogAgent est particulierement interessant pour les agents UI/browser automation. CogVLM2 offre des performances GPT-4V a poids ouverts.

### 1.6 DeepSeek-VL2
- **URL**: https://github.com/deepseek-ai/DeepSeek-VL2
- **GitHub**: https://github.com/deepseek-ai/DeepSeek-VL2
- **Stars**: 5 300
- **Licence**: MIT (code) + DeepSeek Model License (commercial OK)
- **Source de decouverte**: GitHub search + communaute r/LocalLLaMA
- **Date de recherche**: 2026-04-02
- **Categorie suggeree**: 17_multimodal/vision-language
- **Modalites**: texte + image + documents
- **Description**: Serie VLM Mixture-of-Experts de DeepSeek en 3 tailles (Tiny 1B, Small 2.8B, standard 4.5B parametres actifs). Excellentes performances sur VQA, OCR, document analysis et visual grounding, avec des ressources computationnelles minimales.
- **Pourquoi c'est pertinent**: Tres efficace en termes de ratio performance/taille. Bonne option pour les deploiements contraints.

### 1.7 Janus / Janus-Pro
- **URL**: https://github.com/deepseek-ai/Janus
- **GitHub**: https://github.com/deepseek-ai/Janus
- **Stars**: 17 700
- **Licence**: MIT (code) + Model Agreement (modele)
- **Source de decouverte**: GitHub trending
- **Date de recherche**: 2026-04-02
- **Categorie suggeree**: 17_multimodal/vision-language
- **Modalites**: texte + image (comprehension ET generation)
- **Description**: Modele de DeepSeek qui decouple l'encodage visuel en deux chemins separes tout en maintenant un seul transformateur unifie. Supporte a la fois la comprehension d'images (VQA) et la generation d'images (text-to-image) dans le meme modele. Janus-Pro ameliore le training et le scaling.
- **Pourquoi c'est pertinent**: Approche unifiee comprehension+generation rare en open-source. Architecture innovante.

### 1.8 Florence-2
- **URL**: https://huggingface.co/microsoft/Florence-2-large
- **HuggingFace**: https://huggingface.co/microsoft/Florence-2-large
- **Stars HF**: 1 197 921 downloads/mois
- **Licence**: MIT
- **Source de decouverte**: HuggingFace trending
- **Date de recherche**: 2026-04-02
- **Categorie suggeree**: 17_multimodal/vision-language
- **Modalites**: texte + image
- **Description**: Modele de vision fondamental de Microsoft (0.23B-0.77B). Approche prompt-based pour une large gamme de taches vision: captioning, detection, OCR, dense region captioning, phrase grounding. Entraine sur FLD-5B (5.4B annotations, 126M images). Architecture seq2seq.
- **Pourquoi c'est pertinent**: Tres petit et tres versatile. +1.2M downloads/mois prouve l'adoption massive. Ideal pour fine-tuning sur taches specifiques.

### 1.9 Microsoft Phi-3 Vision
- **URL**: https://huggingface.co/microsoft/Phi-3-vision-128k-instruct
- **HuggingFace**: https://huggingface.co/microsoft/Phi-3-vision-128k-instruct
- **Downloads HF**: 94 235 /mois
- **Licence**: MIT
- **Source de decouverte**: HuggingFace
- **Date de recherche**: 2026-04-02
- **Categorie suggeree**: 17_multimodal/vision-language
- **Modalites**: texte + image
- **Description**: VLM leger de Microsoft (4.2B params, 128K context). Optimise pour les environnements contraints en memoire/calcul. Bonnes capacites OCR, comprehension de charts/tables, raisonnement vision-texte. Entraine sur 500B tokens vision+texte.
- **Pourquoi c'est pertinent**: Excellent ratio taille/performance pour edge deployment. 128K context est exceptionnel pour sa taille.

### 1.10 InternLM-XComposer2.5
- **URL**: https://github.com/InternLM/InternLM-XComposer
- **GitHub**: https://github.com/InternLM/InternLM-XComposer
- **Stars**: 2 900
- **Licence**: Apache 2.0
- **Source de decouverte**: GitHub search
- **Date de recherche**: 2026-04-02
- **Categorie suggeree**: 17_multimodal/vision-language
- **Modalites**: texte + image (ultra-haute resolution) + video (long-terme) + audio
- **Description**: Systeme multimodal de l'equipe InternLM pour interactions video longue duree et audio. XComposer2.5-OmniLive gere streaming video etendu, analyse video fine-grained, et dialogue multi-images/multi-tours.
- **Pourquoi c'est pertinent**: Capacites omnimodales (image+video+audio) avec InternLM comme backbone. Bonne option pour les applications streaming.

### 1.11 SmolVLM (HuggingFace)
- **URL**: https://github.com/huggingface/smollm
- **GitHub**: https://github.com/huggingface/smollm
- **Stars**: 3 700
- **Licence**: Apache 2.0
- **Source de decouverte**: HuggingFace
- **Date de recherche**: 2026-04-02
- **Categorie suggeree**: 17_multimodal/vision-language
- **Modalites**: texte + image (multi-images)
- **Description**: VLM ultra-leger de HuggingFace concu pour le on-device deployment. Supporte visual QA, description d'images, visual storytelling et conversations multi-images. Partie de la famille SmolLM d'HF.
- **Pourquoi c'est pertinent**: Reference pour VLMs sur appareil (edge/mobile). Tres bien documente et integre dans l'ecosysteme HF Transformers.

### 1.12 Ovis2.5 (AIDC-AI)
- **URL**: https://github.com/AIDC-AI/Ovis
- **GitHub**: https://github.com/AIDC-AI/Ovis
- **Stars**: 1 400
- **Licence**: Apache 2.0
- **Source de decouverte**: GitHub search
- **Date de recherche**: 2026-04-02
- **Categorie suggeree**: 17_multimodal/vision-language
- **Modalites**: texte + image + video (charts)
- **Description**: Architecture MLLM qui aligne structurellement les embeddings visuels et textuels. La serie Ovis2.5 ajoute perception visuelle en resolution native, raisonnement ameliore, et performances fortes sur les benchmarks multimodaux incluant l'analyse de charts et la comprehension video.
- **Pourquoi c'est pertinent**: Architecture originale avec alignement structurel des embeddings. Actif et en progression rapide.

---

## 2. DOCUMENT AI

### 2.1 Docling (IBM Research)
- **URL**: https://github.com/DS4SD/docling
- **GitHub**: https://github.com/DS4SD/docling
- **Stars**: 56 900
- **Licence**: MIT
- **Source de decouverte**: GitHub trending
- **Date de recherche**: 2026-04-02
- **Categorie suggeree**: 17_multimodal/document-ai
- **Modalites**: documents (PDF, DOCX, PPTX, XLSX, HTML, images, audio)
- **Description**: Outil de traitement documentaire d'IBM Research Zurich sous LF AI & Data Foundation. Parsing avance PDF (layout, tableaux, formules), representation documentaire unifiee, exports multiples, integrations natives avec LangChain/LlamaIndex/Haystack.
- **Pourquoi c'est pertinent**: 57K stars, MIT, IBM-backed, standard de facto pour document parsing dans les pipelines GenAI. Tres bon support communautaire.

### 2.2 MinerU
- **URL**: https://github.com/opendatalab/MinerU
- **GitHub**: https://github.com/opendatalab/MinerU
- **Stars**: 57 800
- **Licence**: AGPL-3.0 + CLA
- **Source de decouverte**: GitHub trending
- **Date de recherche**: 2026-04-02
- **Categorie suggeree**: 17_multimodal/document-ai
- **Modalites**: PDF + image + DOCX → Markdown/JSON
- **Description**: Outil de parsing documentaire qui convertit PDFs, images et DOCX en formats lisibles par machine (Markdown, JSON). Reconnat formules (LaTeX), tableaux (HTML), OCR en 109 langues, supprime headers/footers. Tres fort sur les documents scientifiques et techniques.
- **Pourquoi c'est pertinent**: 57.8K stars, performance excellent sur documents complexes (formules math, tableaux imbriques). Support multilingue massif.

### 2.3 Marker
- **URL**: https://github.com/VikParuchuri/marker
- **GitHub**: https://github.com/VikParuchuri/marker
- **Stars**: 33 300
- **Licence**: GPL (code) + AI Pubs Open Rail-M (modeles)
- **Source de decouverte**: GitHub trending
- **Date de recherche**: 2026-04-02
- **Categorie suggeree**: 17_multimodal/document-ai
- **Modalites**: PDF, images, PPTX, DOCX, XLSX, HTML, EPUB → Markdown/JSON/HTML
- **Description**: Outil de conversion documentaire rapide et precis. Formate tableaux et equations, extrait images, supprime headers/footers, integration optionnelle LLM pour meilleure precision. Fonctionne sur GPU/CPU/MPS.
- **Pourquoi c'est pertinent**: 33K stars, tres utilise en production. Bon compromis vitesse/precision. Licences permettent usage commercial pour startups <$2M.

### 2.4 Unstructured
- **URL**: https://github.com/Unstructured-IO/unstructured
- **GitHub**: https://github.com/Unstructured-IO/unstructured
- **Stars**: 14 400
- **Licence**: Apache 2.0
- **Source de decouverte**: GitHub search + RAG community
- **Date de recherche**: 2026-04-02
- **Categorie suggeree**: 17_multimodal/document-ai
- **Modalites**: PDF, HTML, Word, emails, images et plus
- **Description**: Solution ETL open-source pour transformer des documents complexes en formats structures pour LLMs. Preprocessing d'ingestion pour pipelines RAG et LLM. Supporte un large ecosysteme de types de fichiers avec chunking intelligent.
- **Pourquoi c'est pertinent**: Reference en preprocessing documents pour RAG. Tres bien integre avec LangChain, LlamaIndex. Dispose aussi d'une offre SaaS (Unstructured API).

### 2.5 PaddleOCR
- **URL**: https://github.com/PaddlePaddle/PaddleOCR
- **GitHub**: https://github.com/PaddlePaddle/PaddleOCR
- **Stars**: 74 700
- **Licence**: Apache 2.0
- **Source de decouverte**: GitHub stars ranking
- **Date de recherche**: 2026-04-02
- **Categorie suggeree**: 17_multimodal/document-ai
- **Modalites**: image + PDF → texte structure
- **Description**: Toolkit OCR et Document AI de Baidu. Inclut PaddleOCR-VL-1.5 (0.9B VLM, 94.5% sur OmniDocBench), PP-StructureV3 (PDF → Markdown/JSON avec coordonnees), PP-OCRv5 (100+ langues). Integre Dify, RAGFlow, Cherry Studio.
- **Pourquoi c'est pertinent**: 74.7K stars, le toolkit OCR le plus etoile. Architecture modulaire, supporte 111 langues, tres fort sur les documents asiatiques.

### 2.6 LayoutLMv3 (Microsoft UniLM)
- **URL**: https://github.com/microsoft/unilm/tree/master/layoutlmv3
- **GitHub**: https://github.com/microsoft/unilm
- **Stars**: 22 100 (repo unilm global)
- **Licence**: CC BY-NC-SA 4.0
- **Source de decouverte**: GitHub search
- **Date de recherche**: 2026-04-02
- **Categorie suggeree**: 17_multimodal/document-ai
- **Modalites**: texte + layout/format + image de document
- **Description**: Modele de fondation documentaire pre-entraine par masquage unifie texte+image. Excelle sur les taches text-centric (formulaires, tickets de caisse) et image-centric (classification documentaire, analyse de layout). Partie du projet UniLM de Microsoft qui inclut aussi Kosmos-2 et BEiT-3.
- **Pourquoi c'est pertinent**: Reference academique et industrielle pour document understanding. Licence NC limite usage commercial mais reste pertinent pour recherche.

### 2.7 MinerU PDF-Extract-Kit
- **URL**: https://github.com/opendatalab/PDF-Extract-Kit
- **GitHub**: https://github.com/opendatalab/PDF-Extract-Kit
- **Stars**: 9 500
- **Licence**: AGPL-3.0
- **Source de decouverte**: GitHub search
- **Date de recherche**: 2026-04-02
- **Categorie suggeree**: 17_multimodal/document-ai
- **Modalites**: PDF → contenu structure
- **Description**: Toolkit d'extraction PDF modulaire integrant des modeles leading pour detection de layout, reconnaissance de formules, OCR et parsing de tableaux. Architecture configurable pour personnaliser les workflows d'extraction.
- **Pourquoi c'est pertinent**: Complementaire a MinerU (meme organisation opendatalab). Plus bas niveau, utile pour des pipelines custom.

### 2.8 Table Transformer (Microsoft)
- **URL**: https://github.com/microsoft/table-transformer
- **GitHub**: https://github.com/microsoft/table-transformer
- **Stars**: 2 900
- **Licence**: MIT
- **Source de decouverte**: GitHub search
- **Date de recherche**: 2026-04-02
- **Categorie suggeree**: 17_multimodal/document-ai
- **Modalites**: PDF + image → tableaux structures
- **Description**: Modele deep learning base sur detection d'objets pour extraire des tableaux depuis PDFs et images. Inclut le dataset PubTables-1M (947K tableaux annotes) et la metrique GriTS pour evaluer la reconnaissance de structure de tableaux.
- **Pourquoi c'est pertinent**: Reference specifique pour l'extraction de tableaux. Tres utile pour les pipelines de document parsing necessitant une haute precision sur les tableaux.

---

## 3. VIDEO UNDERSTANDING

### 3.1 Video-LLaVA
- **URL**: https://github.com/PKU-YuanGroup/Video-LLaVA
- **GitHub**: https://github.com/PKU-YuanGroup/Video-LLaVA
- **Stars**: 3 500
- **Licence**: Apache 2.0
- **Source de decouverte**: GitHub search
- **Date de recherche**: 2026-04-02
- **Categorie suggeree**: 17_multimodal/vision-language (video)
- **Modalites**: texte + image + video
- **Description**: VLM qui apprend des representations visuelles unifiees par alignement avant projection. Permet aux LLMs de raisonner sur images et videos simultanement sans necessiter de donnees image-video pairees. Accepte EMNLP 2024.
- **Pourquoi c'est pertinent**: Approche elegante pour unified image+video understanding. Architecture inspire de nombreux travaux suivants.

### 3.2 VideoChat / VideoChat2
- **URL**: https://github.com/OpenGVLab/Ask-Anything
- **GitHub**: https://github.com/OpenGVLab/Ask-Anything
- **Stars**: 3 300
- **Licence**: MIT
- **Source de decouverte**: GitHub search
- **Date de recherche**: 2026-04-02
- **Categorie suggeree**: 17_multimodal/vision-language (video)
- **Modalites**: texte + video + image
- **Description**: Framework de comprehension video integrant plusieurs LLMs (miniGPT4, StableLM, MOSS). VideoChat2 avec instruction-tuning. Inclut MVBench, benchmark d'evaluation multimodal video. CVPR 2024 Highlight.
- **Pourquoi c'est pertinent**: Framework complet avec benchmark integration. Reference pour les pipelines video understanding.

### 3.3 Video-LLaMA
- **URL**: https://github.com/DAMO-NLP-SG/Video-LLaMA
- **GitHub**: https://github.com/DAMO-NLP-SG/Video-LLaMA
- **Stars**: 3 100
- **Licence**: BSD-3-Clause
- **Source de decouverte**: GitHub search
- **Date de recherche**: 2026-04-02
- **Categorie suggeree**: 17_multimodal/vision-language (video)
- **Modalites**: texte + video + audio
- **Description**: LLM avec comprehension video ET audio. Branch Vision-Language (ViT-G/14 + BLIP-2 Q-Former) et branch Audio-Language (ImageBind). Entraine sur WebVid-2.5M. Disponible en 7B et 13B parametres base sur Llama-2-Chat.
- **Pourquoi c'est pertinent**: Un des premiers modeles a integrer audio+video+texte coheremment. Reference pour les pipelines audio-video.

### 3.4 LLaMA-VID
- **URL**: https://github.com/dvlab-research/LLaMA-VID
- **GitHub**: https://github.com/dvlab-research/LLaMA-VID
- **Stars**: 862
- **Licence**: Multiple (code + data + poids)
- **Source de decouverte**: GitHub search
- **Date de recherche**: 2026-04-02
- **Categorie suggeree**: 17_multimodal/vision-language (video)
- **Modalites**: texte + image + video (long-terme, heure+)
- **Description**: Systeme multimodal specialise pour les videos tres longues (heure+). Principe "une image vaut 2 tokens dans les LLMs" permet de gerer jusqu'a 2000 frames ou 200K+ visual tokens. SOTA sur video long-context pour modeles 7B.
- **Pourquoi c'est pertinent**: Solution specifique pour les videos longues, un probleme non resolu par les VLMs classiques.

---

## 4. AUDIO-VISUAL / OMNIMODAL

### 4.1 ImageBind (Meta FAIR)
- **URL**: https://github.com/facebookresearch/ImageBind
- **GitHub**: https://github.com/facebookresearch/ImageBind
- **Stars**: 9 000
- **Licence**: CC BY-NC 4.0 (non-commercial)
- **Source de decouverte**: GitHub search
- **Date de recherche**: 2026-04-02
- **Categorie suggeree**: 17_multimodal/vision-language (audio-visual)
- **Modalites**: image + texte + audio + profondeur + thermique + IMU
- **Description**: Modele Meta FAIR qui apprend un espace d'embedding conjoint sur 6 modalites. Permet le retrieval et la generation cross-modal. Presente a CVPR 2023. Implémente en PyTorch avec modeles pre-entraines.
- **Pourquoi c'est pertinent**: Seul modele open-source majeur a couvrir 6 modalites incluant depth, thermal et IMU. Reference pour les applications robotiques et AR/VR.

### 4.2 SALMONN (ByteDance + Tsinghua)
- **URL**: https://github.com/bytedance/SALMONN
- **GitHub**: https://github.com/bytedance/SALMONN
- **Stars**: 1 400
- **Licence**: Apache 2.0
- **Source de decouverte**: GitHub search
- **Date de recherche**: 2026-04-02
- **Categorie suggeree**: 17_multimodal/vision-language (audio-visual)
- **Modalites**: audio + video + texte
- **Description**: Serie de modeles multimodaux avances (ByteDance + Tsinghua) pour traiter audio et informations visuelles conjointement. Inclut des versions specialisees video et des modeles pour l'evaluation de qualite vocale.
- **Pourquoi c'est pertinent**: Combine explicitement audio+video+texte dans un seul modele. Bon compromis entre capacites et accessibilite.

### 4.3 NExT-GPT (Any-to-Any)
- **URL**: https://github.com/NExT-GPT/NExT-GPT
- **GitHub**: https://github.com/NExT-GPT/NExT-GPT
- **Stars**: 3 600
- **Licence**: BSD-3-Clause
- **Source de decouverte**: GitHub search
- **Date de recherche**: 2026-04-02
- **Categorie suggeree**: 17_multimodal/vision-language (omnimodal)
- **Modalites**: texte + image + video + audio (input ET output)
- **Description**: Premier MM-LLM end-to-end a percevoir input ET generer output en combinaisons arbitraires de texte, image, video et audio. Publie comme oral paper a ICML 2024. Construit sur composants pre-entraines existants avec instruction tuning.
- **Pourquoi c'est pertinent**: Seul systeme truly any-to-any open-source. Architecture de reference pour les modeles omnimodaux generation+comprehension.

### 4.4 4M (EPFL + Apple)
- **URL**: https://github.com/apple/ml-4m
- **GitHub**: https://github.com/apple/ml-4m
- **Stars**: 1 800
- **Licence**: Apache 2.0 (code) + Sample Code License (modeles)
- **Source de decouverte**: GitHub search
- **Date de recherche**: 2026-04-02
- **Categorie suggeree**: 17_multimodal/vision-language (omnimodal)
- **Modalites**: nombreuses modalites et taches (vision, texte, depth, segmentation, etc.)
- **Description**: Framework EPFL/Apple pour entrainer des modeles de fondation multimodaux massifs any-to-any. Les modeles 4M et 4M-21 peuvent effectuer diverses taches vision, transferer a des modalites non vues et fonctionner comme modeles generatifs multimodaux flexibles.
- **Pourquoi c'est pertinent**: Approche de fondation scalable pour le multimodal. Soutenu par Apple Research, qualite academique elevee.

---

## 5. MULTIMODAL RAG

### 5.1 ColPali / ColQwen
- **URL**: https://github.com/illuin-tech/colpali
- **GitHub**: https://github.com/illuin-tech/colpali
- **Stars**: 2 600
- **Licence**: Apache 2.0 (ColQwen, ColSmol) / Gemma License (ColPali)
- **Source de decouverte**: HuggingFace + papers
- **Date de recherche**: 2026-04-02
- **Categorie suggeree**: 17_multimodal/vision-language (multimodal RAG)
- **Modalites**: image de document + texte (retrieval)
- **Description**: Famille de modeles VLM pour retrieval documentaire efficace. Utilise des transformateurs de vision pour traiter des images de documents directement, sans OCR ni pipeline de layout. Genere des embeddings multi-vecteurs dans l'espace visuel. SOTA sur ViDoRe benchmark (80-91 points selon variante). Inclut ColPali (Gemma-base), ColQwen2, ColSmol.
- **Pourquoi c'est pertinent**: Revolutionne le RAG documentaire en eliminant le besoin d'OCR. Approche plus robuste pour les documents avec elements visuels complexes (charts, tableaux, formules).

### 5.2 Grounding DINO (Visual Grounding)
- **URL**: https://github.com/IDEA-Research/GroundingDINO
- **GitHub**: https://github.com/IDEA-Research/GroundingDINO
- **Stars**: 9 900
- **Licence**: Apache 2.0
- **Source de decouverte**: GitHub + catalogue 07
- **Date de recherche**: 2026-04-02
- **Categorie suggeree**: 17_multimodal/vision-language (grounding)
- **Modalites**: image + texte → bounding boxes
- **Description**: Combine DINO avec grounding textuel pour detection d'objets open-set. Detecte n'importe quel objet decrit en langage naturel. 52.5 AP sur COCO zero-shot. Egalement note dans le catalogue 07_computer_vision.
- **Pourquoi c'est pertinent**: Composant cle des pipelines RAG multimodal pour le grounding spatial et la localisation.

---

## 6. BENCHMARKS ET EVALUATION MULTIMODALE

### 6.1 LMMS-Eval (EvolvingLMMs-Lab)
- **URL**: https://github.com/EvolvingLMMs-Lab/lmms-eval
- **GitHub**: https://github.com/EvolvingLMMs-Lab/lmms-eval
- **Stars**: 4 000
- **Licence**: Non specifie explicitement
- **Source de decouverte**: GitHub search
- **Date de recherche**: 2026-04-02
- **Categorie suggeree**: 17_multimodal (evaluation) / 13_benchmarks
- **Modalites**: texte + image + video + audio (evaluation)
- **Description**: Toolkit d'evaluation multimodale comprehensive. 100+ taches d'evaluation, 30+ backends de modeles. Emphase sur reproductibilite (meme pipeline, resultats deterministes), efficacite (async serving, video I/O) et fiabilite statistique (intervalles de confiance).
- **Pourquoi c'est pertinent**: Standard pour evaluer les VLMs de facon rigoureuse et reproductible. Essential pour comparer les modeles.

---

## 7. FONDATIONS VISION (COMPOSANTS)

### 7.1 Depth Anything
- **URL**: https://github.com/LiheYoung/Depth-Anything
- **GitHub**: https://github.com/LiheYoung/Depth-Anything
- **Stars**: 8 100
- **Licence**: Apache 2.0
- **Source de decouverte**: GitHub search
- **Date de recherche**: 2026-04-02
- **Categorie suggeree**: 17_multimodal / 07_computer_vision
- **Modalites**: image → carte de profondeur
- **Description**: Modele de fondation pour estimation de profondeur monoculaire entraine sur 1.5M images labelisees et 62M+ images non labelisees. CVPR 2024. 3 variantes (Small, Base, Large). Estimation de profondeur relative robuste sans training specifique.
- **Pourquoi c'est pertinent**: Composant fondamental pour les applications 3D, robotique et navigation. Apache 2.0 permet l'usage commercial.

---

## OUTILS NON RETENUS (SEUIL NON ATTEINT)

- **LLaMA-VID** (862 stars) : potentiellement utile mais seuil <1000 non atteint
- **Mantis** (239 stars) : trop peu de stars
- **RT-2** (556 stars) : implementation tierce, pas le papier original DeepMind
- **LongVA** (403 stars) : trop peu de stars
- **UniSim** : pas de repo public trouve
- **Gato** : pas de repo public officiel trouve

---

## ENTREES DEJA DANS LE CATALOGUE

- Grounding DINO : deja en 07_computer_vision, a referencer en 17 aussi
- LocalGPT (22K stars) : pertinent pour RAG multimodal mais mieux place en 05_rag_knowledge

---

## STATISTIQUES DE RECHERCHE

| Categorie | Nb outils | Stars totales (approx) |
|-----------|-----------|------------------------|
| Vision-Language Models | 12 | ~160K |
| Document AI | 8 | ~220K |
| Video Understanding | 4 | ~11K |
| Audio-Visual / Omnimodal | 4 | ~16K |
| Multimodal RAG | 2 | ~12K |
| Benchmarks / Eval | 1 | ~4K |
| Fondations Vision | 1 | ~8K |
| **Total** | **32** | **~431K** |

---

## PRIORITES POUR CATALOGAGE

### Priorite HAUTE (>10K stars ou reference majeure)
1. Docling (57K) - Document AI standard de facto
2. MinerU (58K) - Document parsing SOTA
3. PaddleOCR (75K) - OCR toolkit leader
4. Marker (33K) - Conversion documentaire populaire
5. LLaVA/LLaVA-NeXT (25K) - Reference VLM open-source
6. Florence-2 (1.2M downloads) - Vision foundation model polyvalent
7. Qwen2-VL/Qwen3-VL (19K) - VLM SOTA production
8. Janus (18K) - Comprehension+Generation unifiee
9. Unstructured (14K) - ETL documentaire pour RAG

### Priorite MOYENNE (1K-10K stars)
10. InternVL3.5 (10K) - VLM SOTA academique
11. GroundingDINO (10K) - Visual grounding
12. ImageBind (9K) - 6 modalites, robotique
13. PDF-Extract-Kit (9.5K) - Extraction PDF modulaire
14. MiniGPT-4 (26K) - Reference historique
15. DeepSeek-VL2 (5K) - Efficace MoE
16. ColPali (2.6K) - Multimodal RAG sans OCR
17. NExT-GPT (3.6K) - Any-to-any reference
18. LMMS-Eval (4K) - Evaluation standard
