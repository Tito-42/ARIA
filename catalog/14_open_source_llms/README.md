# 14 - Open Source LLMs

> Modèles de langage open source, déploiement local et quantization

## Vue d'ensemble
Les LLMs open source permettent un contrôle total sur les données et l'inférence. Essentiels pour la privacy, le coût, la latence et les cas d'usage nécessitant un déploiement on-premise.

## Sous-catégories

### Modèles
- [ ] Llama 3/4 (Meta) - La famille de modèles open source la plus populaire
- [ ] Mistral / Mixtral - Modèles européens performants
- [ ] Qwen (Alibaba) - Modèles multilingues
- [ ] DeepSeek - Modèles chinois très performants
- [ ] Gemma (Google) - Modèles légers
- [ ] Phi (Microsoft) - Small language models
- [ ] Command R (Cohere) - Optimisé pour RAG

### Déploiement Local
- [ ] Ollama - Le plus simple pour local
- [ ] LM Studio - UI desktop pour LLMs
- [ ] LocalAI - API compatible OpenAI
- [ ] Jan - Desktop app open source

### Quantization
- [ ] GGUF - Format universel
- [ ] GPTQ / AWQ - Quantization GPU
- [ ] ExLlamaV2 - Inférence optimisée

## Matrice de Décision

| Besoin | Solution Recommandée |
|--------|---------------------|
| Meilleur modèle open source | Llama 4 ou DeepSeek |
| Déploiement local simple | Ollama |
| UI desktop | LM Studio |
| Inférence production | vLLM (voir cat. 10) |
| Small model efficace | Phi ou Gemma |
| Multilingue | Qwen |
