<div align="center">

**[English](README.md)** | **[Français](README.fr.md)** | **[Español](#por-que-existe-aria)** | **[Tutorial para principiantes](guides/how-to-use-aria.es.md)**

<br/>

<picture>
  <img alt="ARIA — Advanced Research in Artificial Intelligence" src="assets/aria-header.svg">
</picture>

<br/>

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Entries](https://img.shields.io/badge/Fichas-323+-blue)]()
[![Categories](https://img.shields.io/badge/Categorías-18-green)]()
[![Updated](https://img.shields.io/badge/Última_Actualización-Abril_2026-brightgreen)]()
[![Agents](https://img.shields.io/badge/Mantenido_por-Agentes_IA-purple)]()

[**Cómo usarlo**](#como-usar-aria) | [**El catálogo**](#que-hay-dentro) | [**Cómo funciona**](#como-funciona) | [**Contribuir**](#contribuir)

</div>

---

## ¿Por qué existe ARIA?

El mundo de la IA encontró su acelerador. Nuevas herramientas, modelos y frameworks se publican **cada día**. Lo que era "la mejor opción" la semana pasada ya está obsoleto. Y buscar a la antigua — escribir palabras clave en Google, hacer scroll por artículos de blog SEO escritos en 2024 — ya no es suficiente.

Para cuando encuentras, comparas y evalúas una herramienta, tres nuevas alternativas ya se han publicado.

**ARIA fue creado para resolver este problema.**

Es una base de conocimiento viva del ecosistema IA — 323 herramientas en 18 categorías — donde cada entrada está estructurada, puntuada y verificada. Pero lo más importante: **ARIA no depende de humanos para mantenerse actualizado.** Un equipo de 5 agentes IA especializados trabaja cada noche para recorrer la web, encontrar novedades, verificar cambios y actualizar el catálogo automáticamente.

Te despiertas por la mañana. La base está actualizada. Haces una pregunta. Obtienes una respuesta.

> *"El cuello de botella ya no es la inteligencia — es saber qué existe."*

---

## Cómo usar ARIA

### El método más simple: preguntar a Claude (recomendado)

No necesitas ser técnico. No necesitas instalar nada. Abre [claude.ai](https://claude.ai) (gratis) y pega tu pregunta con la URL del catálogo. Claude lee Markdown puro vía GitHub Pages y cita las herramientas con sus puntuaciones enterprise exactas.

> **¿Por qué Claude?** Después de varios benchmarks, Claude es el único LLM gratuito que realmente lee el catálogo, cita las herramientas reales con puntuaciones, y no alucina. ChatGPT y Gemini (gratis) no logran leer la URL y responden con sus propios conocimientos genéricos. Ver el [benchmark completo](BENCHMARK_LLM.md).

> **¿No sabes qué es un chatbot de IA?** Es como un asistente personal al que puedes hacer preguntas en lenguaje natural. Los más conocidos: [Claude](https://claude.ai) (de Anthropic — **recomendado**), [ChatGPT](https://chat.openai.com) (de OpenAI), [Gemini](https://gemini.google.com) (de Google).

**Ejemplos:**

| Tu necesidad | Lo que escribes |
|-------------|-----------------|
| Crear un chatbot para clientes | Quiero crear un chatbot de IA para soporte al cliente. ¿Cuáles son las mejores opciones open-source? Lee https://tito-42.github.io/ARIA/CATALOG_SUMMARY.md |
| Elegir una base de datos vectorial | Estoy montando un pipeline RAG. Compara las bases de datos vectoriales. Lee https://tito-42.github.io/ARIA/CATALOG_SUMMARY.md |
| Automatizar el procesamiento de facturas | ¿Qué herramientas de IA pueden automatizar la extracción de facturas? Lee https://tito-42.github.io/ARIA/CATALOG_SUMMARY.md |
| Encontrar un motor de voz | Necesito un motor text-to-speech open-source. ¿Qué recomiendas? Lee https://tito-42.github.io/ARIA/CATALOG_SUMMARY.md |
| Automatizar el cold mailing | ¿Qué herramientas open-source pueden automatizar el cold emailing con IA? Lee https://tito-42.github.io/ARIA/CATALOG_SUMMARY.md |

**Eso es todo.** La IA lee las fichas estructuradas, compara herramientas, verifica licencias, y te da una recomendación — con puntuaciones de madurez, alternativas, y cómo empezar.

> **¿Por qué es mejor que Google?** Google te da artículos de opinión, a menudo patrocinados, a menudo desactualizados. ARIA te da **fichas estructuradas, verificadas y actualizadas diariamente** por agentes de IA. GitHub Pages sirve Markdown puro — los LLMs lo leen directamente sin luchar con el renderizado JavaScript. Respuestas más rápidas, más fiables, más baratas en tokens.

> **Tutorial completo para principiantes:** Si nunca has usado un chatbot de IA, consulta la [guía paso a paso](guides/how-to-use-aria.es.md) con explicaciones detalladas.

### Navegar directamente en GitHub

Cada herramienta es un archivo Markdown que puedes leer directamente. Haz clic en la carpeta [`catalog/`](catalog/) y explora.

### Usar con Claude Code (avanzado)

```bash
git clone https://github.com/Tito-42/ARIA.git
cd ARIA
claude
```
Luego pregunta lo que quieras:
```
> ¿Cuál es la herramienta de code review IA más madura?
> Compara Langfuse vs Helicone para monitoreo de LLM
> ¿Qué procesos de negocio se pueden automatizar al 80% con IA?
```

---

## ¿Qué hay dentro?

### 18 categorías, 323+ fichas

| | Categoría | Fichas | Ejemplos |
|---|----------|:-------:|----------|
| 01 | **Generación de código** | 11 | Claude Code, Cursor, Gemini CLI, Aider, OpenHands |
| 02 | **Agentes IA** | 35 | LangChain, CrewAI, AutoGPT, Dify, Browser Use |
| 03 | **Protocolo MCP** | 17 | FastMCP, Playwright-MCP, GitHub-MCP, AWS-MCP |
| 04 | **Frontend / UI** | 9 | v0, Bolt, Lovable, Firebase Studio |
| 05 | **RAG & Conocimiento** | 13 | Qdrant, ChromaDB, LlamaIndex, embeddings |
| 06 | **Fine-tuning** | 18 | Unsloth, Axolotl, TRL, PEFT, LLaMA-Factory |
| 07 | **Visión por computadora** | 24 | SAM2, Stable Diffusion, FLUX, ComfyUI, PaddleOCR |
| 08 | **NLP & Texto** | 20 | Instructor, Outlines, spaCy, HF Transformers |
| 09 | **Voz & Audio** | 22 | Whisper, Faster-Whisper, Kokoro TTS, LiveKit |
| 10 | **MLOps** | 24 | MLflow, vLLM, Ollama, Ray, W&B, Airflow |
| 11 | **Automatización** | 8 | n8n, Skyvern, Activepieces, Temporal |
| 12 | **Enterprise** | 20 | Langfuse, Portkey, Kong AI Gateway, Infisical |
| 13 | **Benchmarks** | 7 | ARC-AGI, SWE-bench, Chatbot Arena |
| 14 | **LLMs Open Source** | 13 | Llama, Mistral, Qwen, DeepSeek, Phi |
| 15 | **Dominio & Negocio** | 29 | Salud, Finanzas, Legal, Ciberseguridad, **Automatización** |
| 16 | **Seguridad IA** | 15 | Promptfoo, Garak, NeMo Guardrails |
| 17 | **Multimodal** | 19 | LLaVA, Qwen-VL, Docling, MinerU, ImageBind |
| 18 | **Infraestructura** | 19 | llama.cpp, TensorRT-LLM, Flash Attention |

### Automatización de procesos de negocio

La categoría más práctica: herramientas open-source que automatizan **hoy** tareas reales de negocio.

| Herramienta | Lo que automatiza | ¿Cuánto? | Stars |
|-------------|-------------------|:------:|:-----:|
| [Firecrawl](catalog/15_domain_specific/business-automation/firecrawl.md) | Extracción de datos web | ~90% | 103K |
| [Flowise](catalog/15_domain_specific/business-automation/flowise.md) | Creación de agentes IA (visual) | 70-90% | 51K |
| [MindsDB](catalog/15_domain_specific/business-automation/mindsdb.md) | Analytics IA sobre datos en vivo | ~75% | 39K |
| [Chatwoot](catalog/15_domain_specific/business-automation/chatwoot.md) | Soporte al cliente | 60-70% | 28K |
| [WrenAI](catalog/15_domain_specific/business-automation/wrenai.md) | Business intelligence (text-to-SQL) | ~80% | 15K |
| [PR-Agent](catalog/15_domain_specific/business-automation/pr-agent.md) | Code review | 70-80% | 11K |
| [GPT Researcher](catalog/15_domain_specific/business-automation/gpt-researcher.md) | Investigación automática | ~85% | 10K+ |
| [Unstract](catalog/15_domain_specific/business-automation/unstract.md) | Procesamiento de facturas y contratos | 85-90% | 6.5K |

---

## Cada ficha se ve así

Cada herramienta está documentada con una estructura consistente para ayudarte a decidir rápido:

> **Metadata** — Stars GitHub, licencia, precio, fecha de verificación, nivel de madurez
>
> **Qué hace** — Explicación en lenguaje simple
>
> **Funcionalidades clave** — Lo que lo distingue
>
> **Puntuación Enterprise** — Nota de 1 a 5 en: Madurez, Seguridad, Escalabilidad, Comunidad, Documentación, Facilidad de integración
>
> **Casos de uso** — Escenarios concretos
>
> **Para empezar** — Comandos para copiar y pegar
>
> **Fortalezas & Limitaciones** — Evaluación honesta
>
> **Alternativas** — Qué más existe y cómo se compara

---

## Cómo funciona

### El sistema multi-agentes

ARIA no se mantiene a mano. Lo mantiene un equipo de **5 agentes de IA especializados**, cada uno con un rol preciso — como una pequeña empresa de investigación que nunca duerme.

<div align="center">
  <picture>
    <img alt="ARIA Pipeline Multi-Agentes" src="assets/aria-pipeline.svg" width="800">
  </picture>
</div>

| Agente | Lo que hace |
|--------|------------|
| **Investigador** | Recorre GitHub Trending, Awesome Lists, HuggingFace, arXiv, Reddit, Hacker News, Product Hunt. Encuentra nuevas herramientas y tendencias. |
| **Catalogador** | Transforma los descubrimientos brutos en fichas estructuradas según la plantilla estándar. |
| **Evaluador** | Puntúa cada herramienta en 6 dimensiones: Madurez, Seguridad, Escalabilidad, Comunidad, Documentación, Integración. |
| **Vigilante** | Ejecuta el script de verificación de versiones en 200+ repos de GitHub. Detecta nuevas releases, cambios de stars, proyectos archivados. |
| **Arquitecto** | Para una necesidad dada ("Necesito un pipeline RAG para documentos legales"), recomienda la mejor combinación de herramientas del catálogo. |

### El script de vigilancia

Un script ligero que mantiene el catálogo honesto. Verifica cada repo de GitHub y señala lo que ha cambiado — para que los agentes no pierdan tiempo re-investigando herramientas que no se han movido.

Lo que detecta:
- Nuevas releases y cambios de versión
- Variaciones significativas en el número de stars
- Proyectos archivados o abandonados
- Repos recientemente activos (push < 7 días)

Gestiona automáticamente los límites de la API de GitHub — si alcanza el límite, espera y reanuda. Diseñado para funcionar sin supervisión en un servidor.

### De dónde vienen los datos

| Nivel | Fuentes |
|-------|---------|
| **Primario** | GitHub Trending, Awesome Lists, HuggingFace, Papers with Code |
| **Comunidad** | Reddit (r/LocalLLaMA, r/MachineLearning), Hacker News, Product Hunt |
| **Investigación** | arXiv, LabLab.ai, Devpost, LMSys Chatbot Arena |

### Barra de calidad

No todo entra en ARIA:
- **Open source preferido** (código fuente disponible como mínimo)
- **Mantenimiento activo** (commits en los últimos 6 meses)
- **Tracción real** (500+ stars en GitHub, o valor único en su nicho)
- **Enlaces verificados** (todas las URLs probadas antes del catalogado)
- **Puntuación honesta** (fortalezas Y limitaciones documentadas)

---

## En números

| | |
|---|---|
| Fichas catálogo | **323+** |
| Categorías | **18** |
| Repos GitHub vigilados | **200+** |
| Agentes IA | **5** |
| Frecuencia de actualización | **Diaria** (23h-7h CET) |
| Última actualización | **Abril 2026** |

---

## Contribuir

ARIA es open source. Si encuentras una herramienta que falta, una ficha desactualizada, o una categoría que necesita más cobertura — las contribuciones son bienvenidas.

**Añadir una herramienta:**
1. Copia la plantilla desde `catalog/_schema/template-tool.md`
2. Rellena todas las secciones (metadata, funcionalidades, puntuación enterprise, etc.)
3. Colócalo en la carpeta de categoría correcta
4. Abre una Pull Request

**Reportar un problema:**
¿Enlace roto? ¿Información incorrecta? ¿Versión obsoleta? Abre una issue.

---

## Estructura del proyecto

```
ARIA/
  catalog/            323+ fichas estructuradas en 18 categorías
  research/raw/       Descubrimientos brutos de los agentes investigadores
  guides/             Tutoriales, frameworks de decisión, blueprints
  state/              Seguimiento de progreso, snapshots de versiones
  .claude/agents/     Definiciones de agentes
```

---

<div align="center">

### Deja de googlear. Empieza a preguntar.

El ecosistema IA va demasiado rápido para la investigación manual.<br/>
Deja que los agentes hagan el trabajo. Tú toma las decisiones.

---

**[Licencia MIT](LICENSE)** | Construido con [Claude Code](https://claude.ai/code) | Mantenido por agentes IA

*Creado por [Tito_42](https://github.com/Tito-42)*

</div>
