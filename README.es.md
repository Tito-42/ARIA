<div align="center">

**[English](README.md)** | **[Francais](README.fr.md)** | **[Espanol](#por-que-existe-aria)** | **[Tutorial para principiantes](guides/how-to-use-aria.md)**

<br/>

<picture>
  <img alt="ARIA — Advanced Research in Artificial Intelligence" src="assets/aria-header.svg">
</picture>

<br/>

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Entries](https://img.shields.io/badge/Fichas-323+-blue)]()
[![Categories](https://img.shields.io/badge/Categorias-18-green)]()
[![Updated](https://img.shields.io/badge/Ultima_Actualizacion-Abril_2026-brightgreen)]()
[![Agents](https://img.shields.io/badge/Mantenido_por-Agentes_IA-purple)]()

[**Como usarlo**](#como-usar-aria) | [**El catalogo**](#que-hay-dentro) | [**Como funciona**](#como-funciona) | [**Contribuir**](#contribuir)

</div>

---

## Por que existe ARIA

El mundo de la IA encontro su acelerador. Nuevas herramientas, modelos y frameworks se publican **cada dia**. Lo que era "la mejor opcion" la semana pasada ya esta obsoleto. Y buscar a la antigua — escribir palabras clave en Google, hacer scroll por articulos de blog SEO escritos en 2024 — ya no es suficiente.

Para cuando encuentras, comparas y evaluas una herramienta, tres nuevas alternativas ya se han publicado.

**ARIA fue creado para resolver este problema.**

Es una base de conocimiento viva del ecosistema IA — 323 herramientas en 18 categorias — donde cada entrada esta estructurada, puntuada y verificada. Pero lo mas importante: **ARIA no depende de humanos para mantenerse actualizado.** Un equipo de 5 agentes IA especializados trabaja cada noche para recorrer la web, encontrar novedades, verificar cambios y actualizar el catalogo automaticamente.

Te despiertas por la manana. La base esta actualizada. Haces una pregunta. Obtienes una respuesta.

> *"El cuello de botella ya no es la inteligencia — es saber que existe."*

---

## Como usar ARIA

### El metodo mas simple: preguntar a Claude (recomendado)

No necesitas ser tecnico. No necesitas instalar nada. Abre [claude.ai](https://claude.ai) (gratis) y pega tu pregunta con la URL del catalogo. Claude lee Markdown puro via GitHub Pages y cita las herramientas con sus puntuaciones enterprise exactas.

> **Por que Claude?** Despues de varios benchmarks, Claude es el unico LLM gratuito que realmente lee el catalogo, cita las herramientas reales con puntuaciones, y no alucina. ChatGPT y Gemini (gratis) no logran leer la URL y responden con sus propios conocimientos genericos. Ver el [benchmark completo](BENCHMARK_LLM.md).

> **No sabes que es un chatbot de IA?** Es como un asistente personal al que puedes hacer preguntas en lenguaje natural. Los mas conocidos: [Claude](https://claude.ai) (de Anthropic — **recomendado**), [ChatGPT](https://chat.openai.com) (de OpenAI), [Gemini](https://gemini.google.com) (de Google).

**Ejemplos:**

| Tu necesidad | Lo que escribes |
|-------------|-----------------|
| Crear un chatbot para clientes | *"Quiero crear un chatbot de IA para soporte al cliente. Cuales son las mejores opciones open-source? Lee https://tito-42.github.io/ARIA/CATALOG_SUMMARY.md"* |
| Elegir una base de datos vectorial | *"Estoy montando un pipeline RAG. Compara las bases de datos vectoriales. Lee https://tito-42.github.io/ARIA/CATALOG_SUMMARY.md"* |
| Automatizar el procesamiento de facturas | *"Que herramientas de IA pueden automatizar la extraccion de facturas? Lee https://tito-42.github.io/ARIA/CATALOG_SUMMARY.md"* |
| Encontrar un motor de voz | *"Necesito un motor text-to-speech open-source. Que recomiendas? Lee https://tito-42.github.io/ARIA/CATALOG_SUMMARY.md"* |
| Automatizar el cold mailing | *"Que herramientas open-source pueden automatizar el cold emailing con IA? Lee https://tito-42.github.io/ARIA/CATALOG_SUMMARY.md"* |

**Eso es todo.** La IA lee las fichas estructuradas, compara herramientas, verifica licencias, y te da una recomendacion — con puntuaciones de madurez, alternativas, y como empezar.

> **Por que es mejor que Google?** Google te da articulos de opinion, a menudo patrocinados, a menudo desactualizados. ARIA te da **fichas estructuradas, verificadas y actualizadas diariamente** por agentes de IA. GitHub Pages sirve Markdown puro — los LLMs lo leen directamente sin luchar con el renderizado JavaScript. Respuestas mas rapidas, mas fiables, mas baratas en tokens.

> **Tutorial completo para principiantes:** Si nunca has usado un chatbot de IA, consulta la [guia paso a paso](guides/how-to-use-aria.md) con explicaciones detalladas.

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
> Cual es la herramienta de code review IA mas madura?
> Compara Langfuse vs Helicone para monitoreo de LLM
> Que procesos de negocio se pueden automatizar al 80% con IA?
```

---

## Que hay dentro

### 18 categorias, 323+ fichas

| | Categoria | Fichas | Ejemplos |
|---|----------|:-------:|----------|
| 01 | **Generacion de codigo** | 11 | Claude Code, Cursor, Gemini CLI, Aider, OpenHands |
| 02 | **Agentes IA** | 35 | LangChain, CrewAI, AutoGPT, Dify, Browser Use |
| 03 | **Protocolo MCP** | 17 | FastMCP, Playwright-MCP, GitHub-MCP, AWS-MCP |
| 04 | **Frontend / UI** | 9 | v0, Bolt, Lovable, Firebase Studio |
| 05 | **RAG & Conocimiento** | 13 | Qdrant, ChromaDB, LlamaIndex, embeddings |
| 06 | **Fine-tuning** | 18 | Unsloth, Axolotl, TRL, PEFT, LLaMA-Factory |
| 07 | **Vision por computadora** | 24 | SAM2, Stable Diffusion, FLUX, ComfyUI, PaddleOCR |
| 08 | **NLP & Texto** | 20 | Instructor, Outlines, spaCy, HF Transformers |
| 09 | **Voz & Audio** | 22 | Whisper, Faster-Whisper, Kokoro TTS, LiveKit |
| 10 | **MLOps** | 24 | MLflow, vLLM, Ollama, Ray, W&B, Airflow |
| 11 | **Automatizacion** | 8 | n8n, Skyvern, Activepieces, Temporal |
| 12 | **Enterprise** | 20 | Langfuse, Portkey, Kong AI Gateway, Infisical |
| 13 | **Benchmarks** | 7 | ARC-AGI, SWE-bench, Chatbot Arena |
| 14 | **LLMs Open Source** | 13 | Llama, Mistral, Qwen, DeepSeek, Phi |
| 15 | **Dominio & Negocio** | 29 | Salud, Finanzas, Legal, Ciberseguridad, **Automatizacion** |
| 16 | **Seguridad IA** | 15 | Promptfoo, Garak, NeMo Guardrails |
| 17 | **Multimodal** | 19 | LLaVA, Qwen-VL, Docling, MinerU, ImageBind |
| 18 | **Infraestructura** | 19 | llama.cpp, TensorRT-LLM, Flash Attention |

### Automatizacion de procesos de negocio

La categoria mas practica: herramientas open-source que automatizan **hoy** tareas reales de negocio.

| Herramienta | Lo que automatiza | Cuanto | Stars |
|-------------|-------------------|:------:|:-----:|
| [Firecrawl](catalog/15_domain_specific/business-automation/firecrawl.md) | Extraccion de datos web | ~90% | 103K |
| [Flowise](catalog/15_domain_specific/business-automation/flowise.md) | Creacion de agentes IA (visual) | 70-90% | 51K |
| [MindsDB](catalog/15_domain_specific/business-automation/mindsdb.md) | Analytics IA sobre datos en vivo | ~75% | 39K |
| [Chatwoot](catalog/15_domain_specific/business-automation/chatwoot.md) | Soporte al cliente | 60-70% | 28K |
| [WrenAI](catalog/15_domain_specific/business-automation/wrenai.md) | Business intelligence (text-to-SQL) | ~80% | 15K |
| [PR-Agent](catalog/15_domain_specific/business-automation/pr-agent.md) | Code review | 70-80% | 11K |
| [GPT Researcher](catalog/15_domain_specific/business-automation/gpt-researcher.md) | Investigacion automatica | ~85% | 10K+ |
| [Unstract](catalog/15_domain_specific/business-automation/unstract.md) | Procesamiento de facturas y contratos | 85-90% | 6.5K |

---

## Cada ficha se ve asi

Cada herramienta esta documentada con una estructura consistente para ayudarte a decidir rapido:

> **Metadata** — Stars GitHub, licencia, precio, fecha de verificacion, nivel de madurez
>
> **Que hace** — Explicacion en lenguaje simple
>
> **Funcionalidades clave** — Lo que lo distingue
>
> **Puntuacion Enterprise** — Nota de 1 a 5 en: Madurez, Seguridad, Escalabilidad, Comunidad, Documentacion, Facilidad de integracion
>
> **Casos de uso** — Escenarios concretos
>
> **Para empezar** — Comandos para copiar y pegar
>
> **Fortalezas & Limitaciones** — Evaluacion honesta
>
> **Alternativas** — Que mas existe y como se compara

---

## Como funciona

### El sistema multi-agentes

ARIA no se mantiene a mano. Lo mantiene un equipo de **5 agentes de IA especializados**, cada uno con un rol preciso — como una pequena empresa de investigacion que nunca duerme.

<div align="center">
  <picture>
    <img alt="ARIA Pipeline Multi-Agentes" src="assets/aria-pipeline.svg" width="800">
  </picture>
</div>

| Agente | Lo que hace |
|--------|------------|
| **Investigador** | Recorre GitHub Trending, Awesome Lists, HuggingFace, arXiv, Reddit, Hacker News, Product Hunt. Encuentra nuevas herramientas y tendencias. |
| **Catalogador** | Transforma los descubrimientos brutos en fichas estructuradas segun la plantilla estandar. |
| **Evaluador** | Puntua cada herramienta en 6 dimensiones: Madurez, Seguridad, Escalabilidad, Comunidad, Documentacion, Integracion. |
| **Vigilante** | Ejecuta el script de verificacion de versiones en 200+ repos de GitHub. Detecta nuevas releases, cambios de stars, proyectos archivados. |
| **Arquitecto** | Para una necesidad dada ("Necesito un pipeline RAG para documentos legales"), recomienda la mejor combinacion de herramientas del catalogo. |

### El script de vigilancia

Un script ligero que mantiene el catalogo honesto. Verifica cada repo de GitHub y senala lo que ha cambiado — para que los agentes no pierdan tiempo re-investigando herramientas que no se han movido.

Lo que detecta:
- Nuevas releases y cambios de version
- Variaciones significativas en el numero de stars
- Proyectos archivados o abandonados
- Repos recientemente activos (push < 7 dias)

Gestiona automaticamente los limites de la API de GitHub — si alcanza el limite, espera y reanuda. Disenado para funcionar sin supervision en un servidor.

### De donde vienen los datos

| Nivel | Fuentes |
|-------|---------|
| **Primario** | GitHub Trending, Awesome Lists, HuggingFace, Papers with Code |
| **Comunidad** | Reddit (r/LocalLLaMA, r/MachineLearning), Hacker News, Product Hunt |
| **Investigacion** | arXiv, LabLab.ai, Devpost, LMSys Chatbot Arena |

### Barra de calidad

No todo entra en ARIA:
- **Open source preferido** (codigo fuente disponible como minimo)
- **Mantenimiento activo** (commits en los ultimos 6 meses)
- **Traccion real** (500+ stars en GitHub, o valor unico en su nicho)
- **Enlaces verificados** (todas las URLs probadas antes del catalogado)
- **Puntuacion honesta** (fortalezas Y limitaciones documentadas)

---

## En numeros

| | |
|---|---|
| Fichas catalogo | **323+** |
| Categorias | **18** |
| Repos GitHub vigilados | **200+** |
| Agentes IA | **5** |
| Frecuencia de actualizacion | **Diaria** (23h-7h CET) |
| Ultima actualizacion | **Abril 2026** |

---

## Contribuir

ARIA es open source. Si encuentras una herramienta que falta, una ficha desactualizada, o una categoria que necesita mas cobertura — las contribuciones son bienvenidas.

**Anadir una herramienta:**
1. Copia la plantilla desde `catalog/_schema/template-tool.md`
2. Rellena todas las secciones (metadata, funcionalidades, puntuacion enterprise, etc.)
3. Colocalo en la carpeta de categoria correcta
4. Abre una Pull Request

**Reportar un problema:**
Enlace roto? Informacion incorrecta? Version obsoleta? Abre una issue.

---

## Estructura del proyecto

```
ARIA/
  catalog/            323+ fichas estructuradas en 18 categorias
  research/raw/       Descubrimientos brutos de los agentes investigadores
  guides/             Tutoriales, frameworks de decision, blueprints
  state/              Seguimiento de progreso, snapshots de versiones
  .claude/agents/     Definiciones de agentes
```

---

<div align="center">

### Deja de googlear. Empieza a preguntar.

El ecosistema IA va demasiado rapido para la investigacion manual.<br/>
Deja que los agentes hagan el trabajo. Tu toma las decisiones.

---

**[Licencia MIT](LICENSE)** | Construido con [Claude Code](https://claude.ai/code) | Mantenido por agentes IA

*Creado por [Tito_42](https://github.com/Tito-42)*

</div>
