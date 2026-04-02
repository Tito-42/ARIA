# 08_nlp_text — Research Findings
**Date**: 2026-04-01
**Sources**: GitHub repos, HuggingFace, web search, awesome lists

---

## Outils Identifiés

### 1. Hugging Face Transformers
- **URL**: https://github.com/huggingface/transformers
- **Stars**: ~159k
- **Licence**: Apache 2.0
- **Description**: Framework central pour NLP/NLU/NLG. Pipeline prêts à l'emploi pour classification, NER, résumé, traduction, Q&A.
- **Forces**: Écosystème dominant, 500k+ modèles, pipelines simples, communauté massive
- **Faiblesses**: Lourd pour tâches simples, overhead mémoire
- **Statut**: Très actif

### 2. spaCy
- **URL**: https://github.com/explosion/spaCy
- **Stars**: ~33.4k
- **Licence**: MIT
- **Description**: Bibliothèque NLP industrielle. NER, POS tagging, dependency parsing, text classification. Pipelines optimisés.
- **Forces**: Rapide, production-ready, pipelines composables, bonne documentation
- **Faiblesses**: Moins flexible que HF pour modèles custom, modèles pré-entraînés limités vs HF
- **Statut**: Actif (v3.8.14, mars 2026)

### 3. FastText
- **URL**: https://github.com/facebookresearch/fastText
- **Stars**: ~26.5k
- **Licence**: MIT
- **Description**: Classification de texte et word embeddings rapides par Meta. Modèle lid.176 pour détection de langue.
- **Forces**: Extrêmement rapide, léger, bon pour classification simple et langdetect
- **Faiblesses**: **ARCHIVÉ depuis mars 2024** — plus maintenu par Meta
- **Statut**: Archivé

### 4. Tiktoken
- **URL**: https://github.com/openai/tiktoken
- **Stars**: ~17.8k
- **Licence**: MIT
- **Description**: Tokenizer BPE rapide par OpenAI. Utilisé pour compter tokens et encoder/décoder pour GPT-3.5/4.
- **Forces**: Ultra-rapide (Rust backend), standard pour tokenization OpenAI, simple d'utilisation
- **Faiblesses**: Spécifique encodings OpenAI
- **Statut**: Actif (v0.12.0, oct 2025)

### 5. NLTK
- **URL**: https://github.com/nltk/nltk
- **Stars**: ~14.6k
- **Licence**: Apache 2.0
- **Description**: Natural Language Toolkit. Bibliothèque NLP classique pour tokenization, stemming, parsing, corpora.
- **Forces**: Très complet pour NLP classique, excellent pour apprentissage/enseignement, large collection de corpora
- **Faiblesses**: Lent comparé à spaCy, API vieillissante
- **Statut**: Actif

### 6. Flair
- **URL**: https://github.com/flairNLP/flair
- **Stars**: ~14.4k
- **Licence**: MIT
- **Description**: Framework NLP avec stacked embeddings. NER, POS, classification, sentiment analysis.
- **Forces**: NER state-of-the-art, stacked embeddings innovants, simple d'utilisation
- **Faiblesses**: Ralenti (v0.15.1, fév 2025), moins actif récemment
- **Statut**: Ralenti

### 7. Unstructured
- **URL**: https://github.com/Unstructured-IO/unstructured
- **Stars**: ~14.4k
- **Licence**: Apache 2.0
- **Description**: ETL pour documents non structurés. Parse PDF, DOCX, HTML, images en texte structuré pour RAG/NLP.
- **Forces**: Multi-format, pipeline ETL complet, intégration RAG, bonne communauté
- **Faiblesses**: Peut être lourd, certaines features enterprise payantes
- **Statut**: Actif

### 8. Outlines
- **URL**: https://github.com/dottxt-ai/outlines
- **Stars**: ~13.6k
- **Licence**: Apache 2.0
- **Description**: Génération structurée (JSON, regex, grammaire) à partir de LLMs. Garantit des outputs conformes au schema.
- **Forces**: Structured generation garantie, compatible multiple backends, grammaire CFG
- **Faiblesses**: Performance overhead sur génération libre
- **Statut**: Actif

### 9. Instructor
- **URL**: https://github.com/jxnl/instructor
- **Stars**: ~12.7k
- **Licence**: MIT
- **Description**: Extraction structurée via LLMs avec validation Pydantic. Supporte OpenAI, Anthropic, Ollama, etc.
- **Forces**: Standard de facto pour structured extraction, multi-provider, validation Pydantic native, retry automatique
- **Faiblesses**: Dépend des LLMs (coût API)
- **Statut**: Actif (v1.14.5, jan 2026)

### 10. Stanza (Stanford NLP)
- **URL**: https://github.com/stanfordnlp/stanza
- **Stars**: ~7.8k
- **Licence**: Apache 2.0
- **Description**: Bibliothèque NLP multilingue par Stanford. 70+ langues, tokenization, NER, POS, dependency parsing.
- **Forces**: Couverture multilingue excellente, qualité académique, 70+ langues
- **Faiblesses**: Plus lent que spaCy, API moins moderne
- **Statut**: Actif (v1.11.1, fév 2026)

### 11. BERTopic
- **URL**: https://github.com/MaartenGr/BERTopic
- **Stars**: ~7.5k
- **Licence**: MIT
- **Description**: Topic modeling avec transformers et c-TF-IDF. Modélisation de thèmes dans les corpus de texte.
- **Forces**: State-of-the-art topic modeling, visualisations intégrées, modulaire
- **Faiblesses**: Dépendances lourdes (UMAP, HDBSCAN)
- **Statut**: Stable

### 12. Presidio (Microsoft)
- **URL**: https://github.com/microsoft/presidio
- **Stars**: ~7.5k
- **Licence**: MIT
- **Description**: Détection et anonymisation de PII (données personnelles). Regex + NER + custom recognizers.
- **Forces**: Enterprise-grade, extensible, multi-langue, intégration Azure
- **Faiblesses**: Configuration initiale peut être complexe
- **Statut**: Actif (v2.2.362, mars 2026)

### 13. Guardrails AI
- **URL**: https://github.com/guardrails-ai/guardrails
- **Stars**: ~6.6k
- **Licence**: Apache 2.0
- **Description**: Validation et structuration des outputs LLM. Guards composables pour qualité, format, sécurité.
- **Forces**: Composable, hub de validators, intégration multiple LLMs
- **Faiblesses**: Overlap avec Instructor pour structured output
- **Statut**: Actif (v0.9.2, mars 2026)

### 14. Marvin
- **URL**: https://github.com/prefecthq/marvin
- **Stars**: ~6.1k
- **Licence**: Apache 2.0
- **Description**: Extraction structurée et classification via LLMs. Approche fonctionnelle avec décorateurs Python.
- **Forces**: API élégante, décorateurs intuitifs, v3.0 avec agents
- **Faiblesses**: Dépend de l'écosystème Prefect/OpenAI
- **Statut**: Actif (v3.0)

### 15. GLiNER
- **URL**: https://github.com/urchade/GLiNER
- **Stars**: ~3k
- **Licence**: Apache 2.0
- **Description**: NER zero-shot/few-shot. Extraction d'entités sans entraînement spécifique, labels arbitraires.
- **Forces**: Zero-shot NER révolutionnaire, léger, rapide, labels dynamiques
- **Faiblesses**: Moins précis que modèles fine-tunés pour domaines spécifiques
- **Statut**: Actif (v0.2.26, mars 2026)

### 16. SetFit
- **URL**: https://github.com/huggingface/setfit
- **Stars**: ~2.7k
- **Licence**: Apache 2.0
- **Description**: Few-shot text classification avec Sentence Transformers. Fine-tune avec seulement 8-16 exemples par classe.
- **Forces**: Classification avec très peu d'exemples, pas besoin de LLM, rapide
- **Faiblesses**: Limité à la classification
- **Statut**: Stable (v1.1.3, août 2025)

### 17. LangDetect
- **URL**: https://github.com/Mimino666/langdetect
- **Stars**: ~1.9k
- **Licence**: Apache 2.0
- **Description**: Détection de langue basée sur les profils n-gram de Google. Port Python de language-detection Java.
- **Forces**: Simple, léger, 55 langues
- **Faiblesses**: Peu maintenu (2021), non-déterministe par défaut
- **Statut**: Peu maintenu

### 18. Lingua-py
- **URL**: https://github.com/pemistahl/lingua-py
- **Stars**: ~1.7k
- **Licence**: Apache 2.0
- **Description**: Détection de langue précise, surtout pour textes courts. Alternative moderne à LangDetect.
- **Forces**: Meilleure précision sur textes courts, déterministe, 75 langues
- **Faiblesses**: Plus lent que FastText/LangDetect
- **Statut**: Stable (v2.2.0)

### 19. spacy-llm
- **URL**: https://github.com/explosion/spacy-llm
- **Stars**: ~1.4k
- **Licence**: MIT
- **Description**: Intégration LLMs dans les pipelines spaCy. NER, classification, etc. via prompts LLM.
- **Forces**: Combine puissance LLM avec pipeline spaCy, composable
- **Faiblesses**: Communauté petite, dépend de spaCy
- **Statut**: Actif (v0.7.4, mars 2026)

### 20. NLLB-200 (Meta)
- **URL**: https://huggingface.co/facebook/nllb-200-distilled-600M
- **Stars**: N/A (HuggingFace model)
- **Licence**: CC-BY-NC 4.0
- **Description**: Modèle de traduction multilingue par Meta. 200 langues, y compris langues à faibles ressources.
- **Forces**: 200 langues, incluant langues rares, qualité compétitive, modèles distillés disponibles
- **Faiblesses**: Licence non-commerciale, qualité variable selon les paires de langues
- **Statut**: Actif (912k téléchargements/mois)

---

## Tendances Clés (Avril 2026)

1. **Structured extraction via LLMs** — Instructor et Outlines dominent, rendant l'extraction structurée accessible
2. **Zero-shot NER** — GLiNER bouleverse l'approche traditionnelle du NER
3. **Few-shot classification** — SetFit permet de classifier avec 8-16 exemples seulement
4. **FastText archivé** — Meta a abandonné le projet, mais le modèle lid.176 reste utilisé
5. **Convergence NLP/LLM** — spacy-llm et Marvin montrent la fusion entre NLP classique et LLMs
6. **Outils abandonnés** — AllenNLP, FARM (deepset), TextBlob, Pattern sont tous archivés
