# 02 - AI Agents & Orchestration

> Frameworks et patterns pour construire des agents IA autonomes et des systèmes multi-agents

## Vue d'ensemble
Les agents IA sont des systèmes capables d'agir de façon autonome pour accomplir des tâches complexes. Cette catégorie couvre les frameworks pour les construire, les patterns d'architecture, et les cas d'usage enterprise.

## Outils Catalogués

### Frameworks
| Framework | Stars | License | Multi-Agent | Multi-Model |
|-----------|-------|---------|-------------|-------------|
| [Anthropic Agent SDK](frameworks/anthropic-agent-sdk.md) | 6,023 | MIT | Via subagents | Claude only |

### Patterns
(à documenter)

## Outils à Cataloguer
- [ ] LangChain / LangGraph
- [ ] CrewAI
- [ ] AutoGen / AG2 (Microsoft)
- [ ] OpenAI Agents SDK (ex-Swarm)
- [ ] PydanticAI
- [ ] Smolagents (Hugging Face)
- [ ] Magentic-One (Microsoft)
- [ ] LlamaIndex Agents

## Patterns à Documenter
- [ ] ReAct (Reason + Act)
- [ ] Plan-and-Execute
- [ ] Multi-Agent Debate
- [ ] Human-in-the-Loop
- [ ] Tool Use Patterns
- [ ] Hierarchical Agents

## Matrice de Décision

| Besoin | Framework Recommandé |
|--------|---------------------|
| Écosystème Claude | Anthropic Agent SDK |
| Multi-model flexible | LangGraph |
| Multi-agent simple | CrewAI |
| Type-safe Python | PydanticAI |
| Lightweight/HF | Smolagents |
| Écosystème OpenAI | OpenAI Agents SDK |
