# Benchmark : Quel LLM lit le mieux ARIA ? (Avril 2026)

> Test réalisé le 2 avril 2026. Prompt identique sur tous les LLMs :
> *"Lis https://tito-42.github.io/ARIA/llms.txt puis https://tito-42.github.io/ARIA/CATALOG_SUMMARY.md — Je cherche à automatiser les appels entrants de mon entreprise, quels outils me recommandes-tu ?"*

---

## Résultats

### Tier gratuit

| LLM | Lit le catalogue ? | Cite les vrais outils ? | Scores enterprise ? | Architecture proposée ? | Verdict |
|-----|--------------------|------------------------|---------------------|------------------------|---------|
| **Claude (free)** | Oui | Oui (LiveKit, Faster-Whisper, Kokoro, n8n, Anthropic API) | Oui (4.3/5, 4.5/5, 3.8/5, 4.7/5, 5.0/5) | Oui (STT→LLM→TTS + n8n) | **Le meilleur** |
| **ChatGPT (free)** | Oui | Partiellement (Twilio, Vapi, OpenAI, ElevenLabs) | Non | Oui (basique) | Correct |
| **Gemini (free)** | Oui | Partiellement (Vapi, Twilio, Retell, Make.com, n8n) | Non | Oui (workflow structuré) | Correct |

### Tier payant

| LLM | Lit le catalogue ? | Cite les vrais outils ? | Scores enterprise ? | Architecture proposée ? | Verdict |
|-----|--------------------|------------------------|---------------------|------------------------|---------|
| **ChatGPT Plus** | Oui | Partiellement (mélange outils du catalogue + inventés) | Non | Oui (détaillée) | Bon mais bruyant |
| **Gemini One** | Oui | Partiellement (Vapi, Twilio, Retell, Bland AI) | Non | Oui (workflow structuré) | Bon |

---

## Analyse détaillée

### Claude (free) — Le meilleur

Claude est le seul LLM qui :
- Lit **réellement** le fichier CATALOG_SUMMARY.md
- Cite les outils **avec leur score enterprise exact** tiré du catalogue
- Propose une architecture basée **uniquement** sur les outils du catalogue
- Ne mélange pas avec des outils inventés ou hors catalogue

**Extrait de sa réponse :**
```
1. LiveKit Agents — Le cœur du système (Score : 4.3/5)
2. Faster-Whisper — Transcription vocale (STT) (Score : 4.5/5)
3. Kokoro TTS — Synthèse vocale (TTS) (Score : 3.8/5)
4. LangGraph ou n8n — Orchestration des flux (Scores : 4.7/5)
5. Anthropic API — Le cerveau LLM (Score : 5.0/5)

Architecture :
Appel entrant → LiveKit Agents
    ├── Audio → Faster-Whisper (STT)
    ├── Texte → Claude API (LLM)
    └── Réponse → Kokoro TTS (TTS) → Audio
         └── Actions métier → n8n (CRM, tickets, agenda...)
```

### ChatGPT (free & Plus)

- Lit le catalogue mais **mélange** les outils ARIA avec ses propres connaissances
- Ne cite pas les scores enterprise
- ChatGPT Plus est plus verbeux mais pas plus précis
- Tendance à recommander des solutions "tout-en-un" (Vapi, Retell) plutôt que de composer depuis le catalogue

### Gemini (free & One)

- Avant GitHub Pages : **hallucinait complètement** (inventait que ARIA utilisait Pipecat, Deepgram)
- Après GitHub Pages : lit le catalogue correctement
- Cite des outils pertinents mais en invente aussi (Bland AI n'est pas dans le catalogue)
- Gemini One (deep research) était inutilisable avant — visitait la NASA et des thèses d'opéra au lieu de lire le README

---

## Avant / Après GitHub Pages

| Test | Avant (github.com) | Après (github.io + llms.txt) |
|------|--------------------|-----------------------------|
| **Claude free** | Impossible d'accéder au repo | Lit tout, cite les scores, architecture complète |
| **ChatGPT free** | Rate limited par GitHub | Lit le catalogue, recommandations correctes |
| **ChatGPT Plus** | Lisait le README mais pas les fiches | Lit le résumé complet, meilleure précision |
| **Gemini free** | Hallucination totale (Pipecat, Deepgram inventés) | Lit le catalogue, recommandations cohérentes |
| **Gemini deep research** | 20 min de recherche, visite NASA/opéra, hallucine | Non retesté (inutile vu le coût) |

---

## Recommandation

**Pour utiliser ARIA avec un LLM, nous recommandons :**

1. **Claude (free ou pro)** — meilleure compréhension du catalogue, cite les scores, ne hallucine pas
2. **ChatGPT (free ou Plus)** — correct, mais mélange avec ses propres connaissances
3. **Gemini (free)** — correct après GitHub Pages, mais ajoute des outils non présents dans le catalogue

**Prompt recommandé :**
```
Lis https://tito-42.github.io/ARIA/llms.txt
puis https://tito-42.github.io/ARIA/CATALOG_SUMMARY.md
[Ta question ici]
```
