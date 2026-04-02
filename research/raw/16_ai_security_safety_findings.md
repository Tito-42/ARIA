# 16_ai_security_safety — Research Findings
**Date**: 2026-04-01
**Sources**: GitHub repos, OWASP, web search, awesome lists

---

## Outils Identifiés

### Guardrails / Protection Runtime

### 1. Guardrails AI
- **URL**: https://github.com/guardrails-ai/guardrails
- **Stars**: ~6.6k
- **Licence**: Apache 2.0
- **Description**: Framework de validation des outputs LLM. Guards composables pour qualité, format, sécurité, PII.
- **Forces**: Hub de validators communautaires, composable, multi-LLM, bien documenté
- **Faiblesses**: Performance overhead, certains validators premium
- **Statut**: Actif (v0.9.2, mars 2026)

### 2. NeMo Guardrails (NVIDIA)
- **URL**: https://github.com/NVIDIA/NeMo-Guardrails
- **Stars**: ~5.9k
- **Licence**: Apache 2.0
- **Description**: Toolkit NVIDIA pour ajouter des guardrails programmables aux applications LLM. Colang DSL pour définir les rails.
- **Forces**: Colang DSL puissant, topical/safety/fact-checking rails, intégration NeMo
- **Faiblesses**: Courbe d'apprentissage Colang, dépendance écosystème NVIDIA
- **Statut**: Actif

### 3. LLM Guard (ProtectAI)
- **URL**: https://github.com/protectai/llm-guard
- **Stars**: ~2.8k
- **Licence**: MIT
- **Description**: Suite de scanners pour sécuriser inputs/outputs LLM. Détection toxicité, PII, prompt injection, code malveillant.
- **Forces**: Input + output scanning, modular, léger, MIT licence
- **Faiblesses**: Communauté plus petite que Guardrails AI
- **Statut**: Actif

### 4. Purple Llama / LlamaGuard + PromptGuard (Meta)
- **URL**: https://github.com/meta-llama/PurpleLlama
- **Stars**: ~4.1k
- **Licence**: MIT + Llama Community License
- **Description**: Suite d'outils Meta pour la sécurité des LLMs. Inclut LlamaGuard (content safety classifier) et PromptGuard (prompt injection detector).
- **Forces**: Modèles open-source performants, backed by Meta, CyberSecEval benchmark inclus
- **Faiblesses**: Licence Llama restrictive pour certains composants, modèles lourds
- **Statut**: Actif

### 5. Presidio (Microsoft)
- **URL**: https://github.com/microsoft/presidio
- **Stars**: ~7.5k
- **Licence**: MIT
- **Description**: Détection et anonymisation de PII (données personnelles). Regex + NER + custom recognizers.
- **Forces**: Enterprise-grade, extensible, multi-langue, intégration Azure
- **Faiblesses**: Configuration initiale complexe
- **Statut**: Actif (v2.2.362, mars 2026)

---

### Red-teaming / Scanning de Vulnérabilités

### 6. Promptfoo
- **URL**: https://github.com/promptfoo/promptfoo
- **Stars**: ~19k
- **Licence**: MIT
- **Description**: Framework de test et évaluation de prompts/LLMs. Red-teaming automatisé, détection vulnérabilités OWASP LLM Top 10.
- **Forces**: Le plus populaire dans sa catégorie, CLI + UI, multi-provider, OWASP intégré
- **Faiblesses**: Focus principalement prompt-level, moins pour model-level attacks
- **Statut**: Très actif (mars 2026)

### 7. Garak (NVIDIA)
- **URL**: https://github.com/NVIDIA/garak
- **Stars**: ~7.4k
- **Licence**: Apache 2.0
- **Description**: Scanner de vulnérabilités LLM. Tests automatisés pour hallucinations, toxicité, data leakage, prompt injection.
- **Forces**: Large bibliothèque d'attaques, framework extensible, NVIDIA-backed
- **Faiblesses**: Ralenti (dernier commit déc 2024)
- **Statut**: Ralenti

### 8. PyRIT (Microsoft)
- **URL**: https://github.com/microsoft/PyRIT
- **Stars**: ~3.6k
- **Licence**: MIT
- **Description**: Python Risk Identification Toolkit. Red-teaming automatisé pour systèmes d'IA générative.
- **Forces**: Orchestrateurs d'attaques sophistiqués, multi-modality, Microsoft-backed
- **Faiblesses**: Orienté Azure/OpenAI
- **Statut**: Actif (v0.12.0, mars 2026)

### 9. DeepTeam (Confident AI)
- **URL**: https://github.com/confident-ai/deepteam
- **Stars**: ~1.4k
- **Licence**: Apache 2.0
- **Description**: Red-teaming LLM open-source. Attaques automatisées et métriques de vulnérabilité.
- **Forces**: Intégré avec DeepEval, attaques automatisées, métriques standardisées
- **Faiblesses**: Relativement nouveau
- **Statut**: Actif (nov 2025)

### 10. FuzzyAI (CyberArk)
- **URL**: https://github.com/cyberark/FuzzyAI
- **Stars**: ~1.3k
- **Licence**: Apache 2.0
- **Description**: Framework de fuzzing pour LLMs. Teste les guardrails via mutations et techniques de jailbreak.
- **Forces**: Approche fuzzing unique, CyberArk expertise sécurité
- **Faiblesses**: Niche, communauté petite
- **Statut**: Actif

### 11. Agentic Security
- **URL**: https://github.com/msoedov/agentic_security
- **Stars**: ~1.8k
- **Licence**: FFCC19
- **Description**: Tests de sécurité pour agents IA et applications LLM.
- **Forces**: Spécialisé agents, interface web
- **Faiblesses**: Licence non-standard, ralenti (jan 2025)
- **Statut**: Ralenti

---

### Évaluation & Observabilité

### 12. DeepEval (Confident AI)
- **URL**: https://github.com/confident-ai/deepeval
- **Stars**: ~14.4k
- **Licence**: MIT
- **Description**: Framework d'évaluation de LLMs. 14+ métriques (hallucination, faithfulness, toxicity, bias, etc.).
- **Forces**: Métriques complètes, intégration pytest, CI/CD friendly, très actif
- **Faiblesses**: Certaines features enterprise payantes
- **Statut**: Actif

### 13. Giskard
- **URL**: https://github.com/Giskard-AI/giskard
- **Stars**: ~5.2k
- **Licence**: Apache 2.0
- **Description**: Testing et monitoring de modèles ML/LLM. Détection automatique de vulnérabilités, biais, performance.
- **Forces**: Scan automatique de vulnérabilités, rapport détaillé, intégration CI/CD
- **Faiblesses**: Communauté modérée
- **Statut**: Actif (mars 2026)

### 14. LangKit (WhyLabs)
- **URL**: https://github.com/whylabs/langkit
- **Stars**: ~980
- **Licence**: Apache 2.0
- **Description**: Monitoring et observabilité pour LLMs. Métriques de qualité, toxicité, sentiment, PII.
- **Forces**: Intégration WhyLabs, métriques prêtes à l'emploi
- **Faiblesses**: Ralenti (nov 2024), dépendance WhyLabs
- **Statut**: Ralenti

---

### Sécurité ML Généraliste

### 15. Adversarial Robustness Toolbox (ART)
- **URL**: https://github.com/Trusted-AI/adversarial-robustness-toolbox
- **Stars**: ~5.9k
- **Licence**: MIT
- **Description**: Bibliothèque IBM/Linux Foundation pour la robustesse adversariale des modèles ML. Attaques + défenses.
- **Forces**: Très complet, académiquement rigoureux, multi-framework (PyTorch, TF, scikit-learn)
- **Faiblesses**: Courbe d'apprentissage, plus orienté ML classique que LLM
- **Statut**: Actif (juillet 2025)

---

### Référence Normative

### 16. OWASP Top 10 for LLMs
- **URL**: https://github.com/OWASP/www-project-top-10-for-llm
- **Stars**: ~1.2k
- **Licence**: CC-BY-SA 4.0
- **Description**: Référence OWASP des 10 risques majeurs pour les applications LLM. Guide de sécurité standardisé.
- **Forces**: Standard industrie, communauté OWASP, mis à jour régulièrement
- **Faiblesses**: Document de référence (pas un outil technique)
- **Statut**: Actif

### 17. Agentic Radar (Splx.ai)
- **URL**: https://github.com/splx-ai/agentic-radar
- **Stars**: ~941
- **Licence**: Apache 2.0
- **Description**: Analyse statique de sécurité pour systèmes agentiques. Visualise les flux, identifie les vulnérabilités.
- **Forces**: Unique dans son créneau (sécurité agents), visualisation des flux
- **Faiblesses**: Nouveau, communauté petite
- **Statut**: Nouveau (2025)

---

### Déprécié / Archivé

### 18. Rebuff (ProtectAI)
- **URL**: https://github.com/protectai/rebuff
- **Stars**: N/A
- **Licence**: N/A
- **Description**: Détection de prompt injection. **ARCHIVÉ depuis mai 2025**.
- **Statut**: Archivé

---

### Services Commerciaux (SaaS, pas de repo public)
- **Lakera Guard** — SaaS protection LLM en temps réel
- **Patronus AI** — SaaS évaluation et sécurité LLM
- **Cleanlab** — SaaS qualité données + détection d'erreurs

---

## Tendances Clés (Avril 2026)

1. **Promptfoo domine le red-teaming** — 19k stars, le plus populaire et complet
2. **Convergence eval + security** — DeepEval, Giskard combinent évaluation et sécurité
3. **Sécurité agentique émergente** — Agentic Radar, Agentic Security = nouveau créneau
4. **OWASP LLM Top 10** — Devient la référence normative pour la sécurité LLM
5. **Meta open-source la sécurité** — LlamaGuard et PromptGuard via Purple Llama
6. **Certains outils ralentissent** — Garak, LangKit, Agentic Security montrent des signes de ralentissement
