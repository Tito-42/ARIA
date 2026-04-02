# Cómo usar ARIA — Guía paso a paso para principiantes

**[English](how-to-use-aria.md) | [Français](how-to-use-aria.fr.md) | [Español](#qué-es-aria)**

---

# ¿Qué es ARIA?

ARIA es como una **enciclopedia gigante de herramientas de IA** — pero siempre está actualizada porque agentes de IA la actualizan cada noche. Contiene más de 323 fichas detalladas sobre herramientas que te ayudan a construir chatbots, automatizar tareas, procesar documentos, generar imágenes, y mucho más.

No necesitas ser desarrollador ni experto en IA para usarla. Solo necesitas saber hacer una pregunta.

---

# ¿Qué es un chatbot / asistente de IA?

Antes de empezar, pongámonos de acuerdo en los términos.

Un **chatbot de IA** (también llamado asistente de IA) es un sitio web donde puedes escribir preguntas en lenguaje normal y obtener respuestas inteligentes. Piensa en él como un buscador muy inteligente que realmente entiende lo que le preguntas y te da una respuesta directa en lugar de una lista de enlaces.

Los más populares (todos gratuitos para empezar):

| Nombre | Creado por | Sitio web | ¿Gratis? |
|--------|-----------|-----------|----------|
| **Claude** | Anthropic | [claude.ai](https://claude.ai) | Sí (versión gratuita) |
| **ChatGPT** | OpenAI | [chat.openai.com](https://chat.openai.com) | Sí (versión gratuita) |
| **Gemini** | Google | [gemini.google.com](https://gemini.google.com) | Sí (versión gratuita) |
| **Copilot** | Microsoft | [copilot.microsoft.com](https://copilot.microsoft.com) | Sí |

Todos funcionan igual: escribes una pregunta, la IA responde. Así de sencillo.

---

# Cómo usar ARIA (3 métodos)

## Método 1: Preguntarle a Claude (el más fácil — recomendado)

Este es el método recomendado. Sin instalación, sin código, sin conocimientos técnicos.

> **Importante:** Después de varios benchmarks, **Claude es el único LLM gratuito** que realmente lee la URL del catálogo, cita las herramientas reales con sus puntuaciones enterprise, y no alucina. ChatGPT y Gemini (gratuitos) no logran leer la URL y dan respuestas genéricas. Ver el [benchmark completo](../BENCHMARK_LLM.md).

### Paso 1 — Abre Claude

Ve a [claude.ai](https://claude.ai) y crea una cuenta gratuita si no tienes una.

- **Recomendado:** [claude.ai](https://claude.ai) — lee el catálogo, cita puntuaciones, sin alucinaciones
- No recomendado: [chat.openai.com](https://chat.openai.com) — no lee la URL, respuestas genéricas
- No recomendado: [gemini.google.com](https://gemini.google.com) — no lee la URL, respuestas genéricas

### Paso 2 — Escribe tu pregunta + el enlace de ARIA

En el cuadro de texto, escribe lo que buscas E incluye la URL del catálogo. La IA leerá las fichas y te responderá.

### Paso 3 — Obtén tu respuesta

La IA va a:
1. Leer el catálogo ARIA
2. Encontrar las herramientas relevantes para tu pregunta
3. Compararlas
4. Darte una recomendación con ventajas, desventajas y cómo empezar

### Ejemplos reales que puedes copiar y pegar

**Ejemplo 1 — Quieres crear un chatbot para tu empresa:**
```
Quiero montar un chatbot de IA para atención al cliente en mi sitio web.
¿Cuáles son las mejores opciones open-source? Necesito algo gratuito,
fácil de instalar y que funcione en español.
Lee https://tito-42.github.io/ARIA/CATALOG_SUMMARY.md
```

**Ejemplo 2 — Quieres automatizar el procesamiento de facturas:**
```
Mi empresa procesa cientos de facturas al mes de forma manual.
Me gustaría automatizarlo con IA. Recomiéndame herramientas que puedan
extraer datos de facturas PDF automáticamente.
Lee https://tito-42.github.io/ARIA/CATALOG_SUMMARY.md
```

**Ejemplo 3 — Quieres añadir IA a tu aplicación existente:**
```
Tengo una aplicación web y quiero añadir un asistente de IA que pueda
responder preguntas sobre nuestra documentación. ¿Qué herramientas RAG
debería usar? Explícamelo de forma sencilla, no soy experto en IA.
Lee https://tito-42.github.io/ARIA/CATALOG_SUMMARY.md
```

**Ejemplo 4 — Quieres explorar qué puede automatizar la IA:**
```
Dirijo una pequeña agencia de marketing. ¿Qué procesos de negocio puede
automatizar la IA hoy en día? Céntrate en herramientas open-source que
puedan automatizar al menos el 60% de una tarea.
Lee https://tito-42.github.io/ARIA/CATALOG_SUMMARY.md
```

**Ejemplo 5 — Quieres comparar herramientas:**
```
Necesito elegir una herramienta de generación de código con IA. Compara las
5 mejores opciones — dime cuál es la mejor para un equipo de 10 desarrolladores
que trabajan con Python y JavaScript.
Lee https://tito-42.github.io/ARIA/CATALOG_SUMMARY.md
```

### Consejos para obtener mejores resultados

- **Sé específico con lo que necesitas:** "Necesito un chatbot para una clínica dental" es mejor que "Necesito un chatbot"
- **Menciona tus restricciones:** presupuesto, idioma, tamaño del equipo, nivel técnico
- **Pide comparaciones:** "Compara X vs Y" te da una respuesta lista para decidir
- **Pide explicaciones sencillas:** "Explícamelo como si no fuera técnico" — la IA se adaptará

---

## Método 2: Navegar directamente en GitHub (sin IA)

Puedes explorar el catálogo como un sitio web, directamente en GitHub.

### Paso 1 — Ve al catálogo

Abre: [https://github.com/Tito-42/ARIA/tree/main/catalog](https://github.com/Tito-42/ARIA/tree/main/catalog)

### Paso 2 — Elige una categoría

Verás carpetas numeradas del 01 al 18. Cada una cubre un área diferente:

| Carpeta | Qué contiene |
|---------|-------------|
| `01_code_generation/` | Herramientas para escribir código con IA |
| `02_ai_agents/` | Frameworks para construir agentes de IA autónomos |
| `03_mcp/` | Conectores entre la IA y herramientas externas |
| `04_frontend_ui/` | Herramientas que generan sitios web e interfaces |
| `05_rag_knowledge/` | Bases de datos y herramientas para IA que busca en tus documentos |
| `06_finetuning_training/` | Herramientas para personalizar modelos de IA |
| `07_computer_vision/` | Reconocimiento de imágenes, generación, OCR |
| `08_nlp_text/` | Análisis de texto, clasificación, traducción |
| `09_voice_audio/` | Reconocimiento de voz, síntesis de voz, voice IA |
| `10_data_science_mlops/` | Herramientas para desplegar y gestionar IA en producción |
| `11_automation_workflows/` | Automatización de workflows (como Zapier, pero con IA) |
| `12_enterprise_integration/` | Monitoreo, seguridad, gestión de costes para IA |
| `13_benchmarks_competitions/` | Competiciones de IA y clasificaciones |
| `14_open_source_llms/` | Modelos de IA gratuitos que puedes ejecutar tú mismo |
| `15_domain_specific/` | IA para salud, finanzas, legal, educación, **automatización empresarial** |
| `16_ai_security_safety/` | Herramientas para hacer la IA segura y fiable |
| `17_multimodal/` | IA que entiende imágenes, vídeo y documentos |
| `18_ai_infrastructure/` | Hardware y optimización para ejecutar IA |

### Paso 3 — Haz clic en una herramienta

Cada archivo `.md` es una ficha completa con todo lo que necesitas saber.

---

## Método 3: Usar con Claude Code (para desarrolladores)

Si eres desarrollador y tienes [Claude Code](https://claude.ai/code) instalado:

```bash
git clone https://github.com/Tito-42/ARIA.git
cd ARIA
claude
```

Después, pregunta lo que quieras en lenguaje natural. Claude tiene acceso a las más de 323 fichas en local y puede buscar, comparar y recomendar al instante.

---

# Preguntas frecuentes

### ¿ARIA es gratis?
Sí, completamente. Es open source bajo licencia MIT. El catálogo, los scripts, todo.

### ¿Necesito saber programar?
No. El método 1 (preguntar a un chatbot) no requiere ningún conocimiento técnico. Solo escribes una pregunta en lenguaje normal.

### ¿Qué chatbot de IA debería usar?
Recomendamos **Claude** (claude.ai). Después de varios benchmarks, es el único LLM gratuito que realmente lee la URL del catálogo, cita las herramientas reales con puntuaciones enterprise, y no alucina. ChatGPT y Gemini (gratuitos) no logran leer la URL y dan respuestas genéricas.

### ¿Cada cuánto se actualiza ARIA?
Cada noche entre las 23:00 y las 07:00 (hora de París). Los agentes de IA comprueban nuevas herramientas, cambios de versión y repos en tendencia.

### ¿Puedo confiar en la información?
Cada ficha incluye una fecha de verificación, enlaces a la fuente y una evaluación honesta tanto de las fortalezas como de las limitaciones. No ocultamos los defectos. Dicho esto, las herramientas de IA evolucionan rápido — siempre revisa la documentación oficial antes de tomar una decisión crítica.

### ¿Y si la herramienta que busco no está en el catálogo?
¡Pregúntale al chatbot de todas formas! Puede encontrar algo similar. Y puedes abrir un issue en GitHub para solicitarla — o contribuirla tú mismo.

### No hablo bien inglés. ¿Puedo usar ARIA en mi idioma?
Las fichas del catálogo están principalmente en inglés, pero puedes preguntar al chatbot en cualquier idioma. Por ejemplo:
```
Lee https://tito-42.github.io/ARIA/CATALOG_SUMMARY.md y dime en español qué herramienta usar para un chatbot
```

La IA leerá las fichas en inglés y te responderá en tu idioma.

---

# Tarjeta de referencia rápida

Guarda esto para después:

```
[Tu pregunta]. Lee https://tito-42.github.io/ARIA/CATALOG_SUMMARY.md

Funciona con: Claude, ChatGPT, Gemini, Copilot,
o cualquier chatbot de IA.
```

---

<div align="center">

*ARIA — Deja de buscar en Google. Empieza a preguntar.*

</div>
