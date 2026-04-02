# 09_voice_audio — Research Findings
**Date**: 2026-04-01
**Sources**: GitHub repos, HuggingFace, web search

---

## Outils Identifiés (22 outils)

### STT (Speech-to-Text)

### 1. OpenAI Whisper
- **URL**: https://github.com/openai/whisper
- **Stars**: ~97k
- **Licence**: MIT
- **Description**: Modèle ASR multilingue par OpenAI. Transcription et traduction robustes, supporte 100+ langues.
- **Forces**: Qualité state-of-the-art, multilingue, robuste au bruit, modèle ouvert
- **Faiblesses**: Lent en inférence (Python natif), nécessite GPU pour temps réel
- **Statut**: Actif (juin 2025)

### 2. whisper.cpp
- **URL**: https://github.com/ggerganov/whisper.cpp
- **Stars**: ~48k
- **Licence**: MIT
- **Description**: Port C/C++ de Whisper par ggerganov. Inférence CPU rapide, support GGML/GGUF.
- **Forces**: Ultra-rapide sur CPU, pas de dépendance Python, multi-plateforme, edge-compatible
- **Faiblesses**: Moins de features que Whisper Python
- **Statut**: Très actif

### 3. Faster-Whisper
- **URL**: https://github.com/SYSTRAN/faster-whisper
- **Stars**: ~22k
- **Licence**: MIT
- **Description**: Réimplémentation de Whisper avec CTranslate2. 4x plus rapide que le Whisper original.
- **Forces**: 4x plus rapide, moins de mémoire, compatible modèles Whisper, batched inference
- **Faiblesses**: Dépend de CTranslate2
- **Statut**: Actif

### 4. WhisperX
- **URL**: https://github.com/m-bain/whisperX
- **Stars**: ~21k
- **Licence**: BSD-2
- **Description**: Whisper avec word-level timestamps, speaker diarization et VAD. Pipeline complet audio→texte aligné.
- **Forces**: Alignement mot-par-mot, diarization, VAD intégré, batch processing
- **Faiblesses**: Plus complexe à setup, dépendances multiples
- **Statut**: Actif

### 5. Vosk
- **URL**: https://github.com/alphacep/vosk-api
- **Stars**: ~14.5k
- **Licence**: Apache 2.0
- **Description**: Kit de reconnaissance vocale offline. Supporte 20+ langues, fonctionne sur mobile et edge.
- **Forces**: Offline, léger, multi-plateforme (mobile, Raspberry Pi), 20+ langues
- **Faiblesses**: Qualité inférieure à Whisper, modèles plus anciens
- **Statut**: Maintenu

### 6. Sherpa-ONNX
- **URL**: https://github.com/k2-fsa/sherpa-onnx
- **Stars**: ~11.3k
- **Licence**: Apache 2.0
- **Description**: Runtime ONNX pour ASR/TTS en temps réel. Multi-plateforme (mobile, desktop, embedded).
- **Forces**: Temps réel, multi-plateforme, ONNX optimisé, streaming
- **Faiblesses**: Communauté plus petite
- **Statut**: Très actif

---

### TTS (Text-to-Speech)

### 7. Coqui TTS / XTTS
- **URL**: https://github.com/coqui-ai/TTS
- **Stars**: ~45k
- **Licence**: MPL 2.0
- **Description**: Bibliothèque TTS open-source avec XTTS v2 (voice cloning zero-shot). Multiple architectures.
- **Forces**: Voice cloning puissant, multilingual, grande communauté, architectures variées
- **Faiblesses**: **ARCHIVÉ** — Coqui a fermé, repo en mode legacy
- **Statut**: Archivé

### 8. Bark (Suno)
- **URL**: https://github.com/suno-ai/bark
- **Stars**: ~39k
- **Licence**: MIT
- **Description**: Modèle TTS génératif par Suno. Supporte voix, musique, effets sonores, rires.
- **Forces**: Très expressif, multi-speaker, effets sonores, MIT licence
- **Faiblesses**: Lent en génération, qualité inconsistante, activité réduite
- **Statut**: Réduit

### 9. ChatTTS
- **URL**: https://github.com/2noise/ChatTTS
- **Stars**: ~39k
- **Licence**: AGPL / CC-NC
- **Description**: TTS conversationnel optimisé pour le dialogue. Prosodie naturelle, contrôle fin du style.
- **Forces**: Naturel pour dialogue, contrôle prosodie, qualité impressionnante
- **Faiblesses**: Licence restrictive (AGPL + CC-NC)
- **Statut**: Actif

### 10. OpenVoice (MyShell/MIT)
- **URL**: https://github.com/myshell-ai/OpenVoice
- **Stars**: ~36k
- **Licence**: MIT
- **Description**: Voice cloning instantané. Clone voix à partir d'un court échantillon avec contrôle du style.
- **Forces**: Voice cloning rapide, contrôle style/émotion, MIT licence
- **Faiblesses**: Activité réduite récemment
- **Statut**: Réduit

### 11. Fish Speech
- **URL**: https://github.com/fishaudio/fish-speech
- **Stars**: ~29k
- **Licence**: Propriétaire
- **Description**: TTS haute qualité avec voice cloning. Multilingual, faible latence.
- **Forces**: Qualité audio excellente, voice cloning, multilingual, rapide
- **Faiblesses**: Licence propriétaire/restrictive
- **Statut**: Actif (mai 2025)

### 12. AudioCraft / MusicGen (Meta)
- **URL**: https://github.com/facebookresearch/audiocraft
- **Stars**: ~23k
- **Licence**: MIT / CC-NC (modèles)
- **Description**: Suite Meta pour génération audio : MusicGen (musique), AudioGen (effets), EnCodec (codec neural).
- **Forces**: Génération musicale state-of-the-art, Meta-backed, MusicGen + AudioGen + EnCodec
- **Faiblesses**: Modèles CC-NC, lourd en compute
- **Statut**: Actif

### 13. Tortoise TTS
- **URL**: https://github.com/neonbjb/tortoise-tts
- **Stars**: ~14.8k
- **Licence**: Apache 2.0
- **Description**: TTS haute qualité avec multi-voice et voice cloning. Pionnier du TTS neural open-source.
- **Forces**: Qualité audio très élevée, voice cloning, historiquement influent
- **Faiblesses**: **Abandonné** (2023), très lent en génération
- **Statut**: Abandonné

### 14. F5-TTS
- **URL**: https://github.com/SWivid/F5-TTS
- **Stars**: ~14.3k
- **Licence**: MIT / CC-NC
- **Description**: TTS flow-matching. Haute qualité, zero-shot voice cloning.
- **Forces**: Flow matching innovant, qualité très haute, voice cloning zero-shot
- **Faiblesses**: Licence modèles CC-NC
- **Statut**: Actif (mars 2025)

### 15. VoiceCraft
- **URL**: https://github.com/jasonppy/VoiceCraft
- **Stars**: ~8.5k
- **Licence**: CC-NC
- **Description**: Speech editing et TTS zero-shot par codec language modeling.
- **Forces**: Speech editing unique (modifier une partie du discours), zero-shot TTS
- **Faiblesses**: Licence CC-NC, activité réduite
- **Statut**: Réduit

### 16. MeloTTS
- **URL**: https://github.com/myshell-ai/MeloTTS
- **Stars**: ~7.3k
- **Licence**: MIT
- **Description**: TTS multilingue haute qualité par MyShell. Optimisé pour production.
- **Forces**: Rapide, multilingual, MIT licence, léger
- **Faiblesses**: Activité réduite
- **Statut**: Réduit

### 17. Kokoro TTS
- **URL**: https://github.com/kokoro-xtts/kokoro
- **Stars**: ~6.2k
- **Licence**: Apache 2.0
- **Description**: TTS léger et rapide. Optimisé pour edge et production.
- **Forces**: Très léger, rapide, adapté edge/production
- **Faiblesses**: Communauté en croissance
- **Statut**: Actif (jan 2025)

### 18. StyleTTS2
- **URL**: https://github.com/yl4579/StyleTTS2
- **Stars**: ~6.2k
- **Licence**: MIT
- **Description**: TTS avec style diffusion. Qualité rivale des voix humaines sur LJ Speech.
- **Forces**: Qualité rivale humaine sur benchmarks, contrôle du style fin
- **Faiblesses**: Activité réduite
- **Statut**: Réduit

### 19. Parler-TTS (HuggingFace)
- **URL**: https://github.com/huggingface/parler-tts
- **Stars**: ~5.6k
- **Licence**: Apache 2.0
- **Description**: TTS par HuggingFace avec contrôle par description textuelle du style vocal.
- **Forces**: Contrôle par prompt textuel ("voix grave, chaleureuse"), HF ecosystem
- **Faiblesses**: Encore en développement
- **Statut**: Actif

### 20. Piper (rhasspy/OHF-Voice)
- **URL**: https://github.com/rhasspy/piper
- **Stars**: ~10.7k (piper) + ~3.5k (piper-phonemize)
- **Licence**: MIT / GPL-3.0
- **Description**: TTS local rapide optimisé pour Raspberry Pi et home assistants. Multi-langue.
- **Forces**: Ultra-léger, Raspberry Pi, home automation, 30+ langues
- **Faiblesses**: Qualité inférieure aux gros modèles, licence mixte
- **Statut**: Transition

---

### Voice Agents & Infrastructure

### 21. LiveKit Agents
- **URL**: https://github.com/livekit/agents
- **Stars**: ~9.9k
- **Licence**: Apache 2.0
- **Description**: Framework pour construire des voice agents en temps réel. Infrastructure WebRTC + pipeline STT→LLM→TTS.
- **Forces**: Pipeline voix complet, WebRTC natif, multi-provider (OpenAI, Deepgram, ElevenLabs), production-ready
- **Faiblesses**: Dépend de l'infrastructure LiveKit
- **Statut**: Très actif

### 22. Stable Audio Tools (Stability AI)
- **URL**: https://github.com/Stability-AI/stable-audio-tools
- **Stars**: ~3.7k
- **Licence**: MIT
- **Description**: Outils pour génération audio/musique par Stability AI. Training et inference.
- **Forces**: Stability-backed, modèle open, outils de training inclus
- **Faiblesses**: Communauté modérée
- **Statut**: Actif

---

### Services Commerciaux (pas de repo open-source principal)
- **ElevenLabs** — Leader voice cloning et TTS, API, qualité premium
- **Deepgram** — STT enterprise, temps réel, Nova-2 model
- **AssemblyAI** — STT + NLU, Universal model, pipelines audio complets
- **Suno AI** — Génération musicale IA, text-to-music
- **Udio** — Génération musicale IA, concurrent Suno

---

## Tendances Clés (Avril 2026)

1. **Whisper reste le standard STT** — Avec des variants optimisées (whisper.cpp, Faster-Whisper, WhisperX)
2. **Explosion du TTS open-source** — ChatTTS, Fish Speech, F5-TTS rivalisent avec les solutions commerciales
3. **Voice cloning démocratisé** — OpenVoice, XTTS, Fish Speech offrent du cloning zero-shot
4. **Coqui TTS archivé** — Fin d'une ère, mais le code reste utilisable
5. **Voice agents émergent** — LiveKit Agents structure le marché des agents vocaux temps réel
6. **Edge TTS mature** — Piper, Kokoro, Sherpa-ONNX pour embarqué et IoT
