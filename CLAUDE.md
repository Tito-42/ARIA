# ARIA - Advanced Research in Artificial Intelligence

## Objectif
Base de connaissances IA exhaustive cataloguant les meilleurs outils, architectures et pratiques (avril 2026).
Sert de "mémoire" réutilisable pour tous les projets professionnels futurs.

## Structure du Projet

| Répertoire | Rôle |
|------------|------|
| `catalog/` | Base de connaissances principale - fiches outils organisées en 18 catégories |
| `catalog/_schema/` | Templates et schéma JSON de validation des fiches |
| `research/` | Données de recherche brutes et méthodologie OSINT |
| `guides/` | Guides pratiques, frameworks de décision, blueprints d'architecture |
| `state/` | Suivi de l'avancement de la recherche par catégorie |
| `.claude/agents/` | Agents spécialisés pour la recherche et le catalogage |
| `logs/` | Journaux d'opérations |

## Catégories du Catalogue (01-18)

| # | Catégorie | Description |
|---|-----------|-------------|
| 01 | code_generation | Outils de génération de code (Claude Code, Cursor, Copilot...) |
| 02 | ai_agents | Frameworks et patterns d'agents IA |
| 03 | mcp | Model Context Protocol - serveurs, connecteurs, guides |
| 04 | frontend_ui | Génération UI/frontend avec IA |
| 05 | rag_knowledge | RAG, vector DBs, embeddings, knowledge management |
| 06 | finetuning_training | Fine-tuning LLM, LoRA, datasets |
| 07 | computer_vision | Détection, génération d'images, vidéo, OCR |
| 08 | nlp_text | Extraction structurée, résumé, classification, traduction |
| 09 | voice_audio | Speech-to-text, TTS, voice agents |
| 10 | data_science_mlops | MLOps, model serving, experiment tracking |
| 11 | automation_workflows | Automatisation, browser automation, workflows |
| 12 | enterprise_integration | Architecture enterprise, sécurité, compliance, coût |
| 13 | benchmarks_competitions | ARC-AGI, Kaggle, hackathons, leaderboards |
| 14 | open_source_llms | Modèles open source, déploiement local, quantization |
| 15 | domain_specific | IA par domaine métier (santé, finance, juridique, cybersec) |
| 16 | ai_security_safety | Red-teaming, guardrails, observabilité, alignment |
| 17 | multimodal | Vision-language, document AI, world models |
| 18 | ai_infrastructure | GPU cloud, edge deployment, orchestration |

## Agents Disponibles

| Agent | Rôle |
|-------|------|
| `researcher` | OSINT web research - cherche les meilleurs outils sur GitHub, HF, Kaggle, etc. |
| `cataloger` | Convertit les findings bruts en fiches catalogue structurées |
| `evaluator` | Score les outils sur la matrice enterprise (1-5 sur 6 dimensions) |
| `architect` | Recommande des stacks technologiques pour un use case donné |
| `updater` | Vérifie les mises à jour et l'actualité des fiches existantes |

## Règles Impératives

1. **Toute fiche outil** doit suivre le template `catalog/_schema/template-tool.md`
2. **Toute fiche competition** doit suivre `catalog/_schema/template-competition.md`
3. **Toute fiche pattern** doit suivre `catalog/_schema/template-pattern.md`
4. **Citer les sources** avec URL pour chaque affirmation
5. **Mettre à jour** `state/research_progress.json` après ajout d'entrées
6. **Ne jamais modifier** les templates dans `catalog/_schema/` sans instruction explicite
7. **Score enterprise** obligatoire pour chaque outil catalogué
8. **Vérifier les URLs** avant de les inclure dans une fiche
9. **Date de vérification** (`last_verified`) obligatoire sur chaque fiche

