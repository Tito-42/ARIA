# How to Use ARIA — Step-by-Step Beginner Guide

**[English](#what-is-aria) | [Français](how-to-use-aria.fr.md) | [Español](how-to-use-aria.es.md)**

---

# What is ARIA?

ARIA is like a **giant encyclopedia of AI tools** — except it's always up-to-date because AI agents refresh it every night. It contains 323+ detailed entries about tools that can help you build chatbots, automate tasks, process documents, generate images, and much more.

You don't need to be a developer or an AI expert to use it. You just need to know how to ask a question.

---

# What is a chatbot / AI assistant?

Before we start, let's make sure we're on the same page.

An **AI chatbot** (also called an AI assistant) is a website where you can type questions in plain language and get intelligent answers. Think of it as a very smart search engine that actually understands what you're asking and gives you a direct answer instead of a list of links.

The most popular ones (all free to start):

| Name | Made by | Website | Free? |
|------|---------|---------|-------|
| **Claude** | Anthropic | [claude.ai](https://claude.ai) | Yes (free tier) |
| **ChatGPT** | OpenAI | [chat.openai.com](https://chat.openai.com) | Yes (free tier) |
| **Gemini** | Google | [gemini.google.com](https://gemini.google.com) | Yes (free tier) |
| **Copilot** | Microsoft | [copilot.microsoft.com](https://copilot.microsoft.com) | Yes |

They all work the same way: you type a question, the AI answers. That's it.

---

# How to use ARIA (3 methods)

## Method 1: Ask Claude (easiest — recommended)

This is the recommended way. No installation, no coding, no technical skills needed.

> **Important:** After multiple benchmarks, **Claude is the only free LLM** that actually reads the catalog URL, cites the real tools with enterprise scores, and doesn't hallucinate. ChatGPT and Gemini (free) fail to fetch the URL and give generic answers instead. See [full benchmark](../BENCHMARK_LLM.md).

### Step 1 — Open Claude

Go to [claude.ai](https://claude.ai) and create a free account if you don't have one.

- **Recommended:** [claude.ai](https://claude.ai) — reads the catalog, cites scores, no hallucination
- Not recommended: [chat.openai.com](https://chat.openai.com) — cannot read the URL, generic answers
- Not recommended: [gemini.google.com](https://gemini.google.com) — cannot read the URL, generic answers

### Step 2 — Write your question + the ARIA link

In the chat box, type what you're looking for AND include the catalog URL. The AI will read the structured entries and answer you.

### Step 3 — Get your answer

The AI will:
1. Read the ARIA catalog
2. Find the tools relevant to your question
3. Compare them
4. Give you a recommendation with pros, cons, and how to get started

### Real examples you can copy-paste

**Example 1 — You want to build a chatbot for your business:**
```
I want to set up an AI chatbot for customer support on my website.
What are the best open-source options? I need something free, easy
to set up, and that works in French.
Read https://tito-42.github.io/ARIA/CATALOG_SUMMARY.md
```

**Example 2 — You want to automate invoice processing:**
```
My company processes hundreds of invoices per month manually.
I'd like to automate this with AI. Recommend tools that can extract
data from PDF invoices automatically.
Read https://tito-42.github.io/ARIA/CATALOG_SUMMARY.md
```

**Example 3 — You want to add AI to your existing app:**
```
I have a web application and I want to add an AI assistant that can
answer questions about our documentation. What RAG tools should I use?
Explain it simply, I'm not an AI expert.
Read https://tito-42.github.io/ARIA/CATALOG_SUMMARY.md
```

**Example 4 — You're exploring what AI can automate:**
```
I run a small marketing agency. What business processes can AI automate
for me today? Focus on tools that are open-source and can automate
at least 60% of a task.
Read https://tito-42.github.io/ARIA/CATALOG_SUMMARY.md
```

**Example 5 — You want to compare tools:**
```
I need to choose a tool for AI code generation. Compare the top 5
options — tell me which one is best for a team of 10 developers
working with Python and JavaScript.
Read https://tito-42.github.io/ARIA/CATALOG_SUMMARY.md
```

### Tips for better results

- **Be specific about your needs:** "I need a chatbot for a dentist's office" is better than "I need a chatbot"
- **Mention constraints:** budget, language, team size, technical level
- **Ask for comparisons:** "Compare X vs Y" gives you a decision-ready answer
- **Ask for simple explanations:** "Explain it like I'm not technical" — the AI will adapt

---

## Method 2: Browse directly on GitHub (no AI needed)

You can explore the catalog like a website, directly on GitHub.

### Step 1 — Go to the catalog

Open: [https://github.com/Tito-42/ARIA/tree/main/catalog](https://github.com/Tito-42/ARIA/tree/main/catalog)

### Step 2 — Pick a category

You'll see folders numbered 01 to 18. Each one covers a different area:

| Folder | What's inside |
|--------|--------------|
| `01_code_generation/` | Tools that help you write code with AI |
| `02_ai_agents/` | Frameworks to build autonomous AI agents |
| `03_mcp/` | Connectors between AI and external tools |
| `04_frontend_ui/` | Tools that generate websites and user interfaces |
| `05_rag_knowledge/` | Databases and tools for AI that searches your documents |
| `06_finetuning_training/` | Tools to customize AI models |
| `07_computer_vision/` | Image recognition, generation, OCR |
| `08_nlp_text/` | Text analysis, classification, translation |
| `09_voice_audio/` | Speech-to-text, text-to-speech, voice AI |
| `10_data_science_mlops/` | Tools to deploy and manage AI in production |
| `11_automation_workflows/` | Workflow automation (like Zapier, but with AI) |
| `12_enterprise_integration/` | Monitoring, security, cost management for AI |
| `13_benchmarks_competitions/` | AI competitions and leaderboards |
| `14_open_source_llms/` | Free AI models you can run yourself |
| `15_domain_specific/` | AI for healthcare, finance, legal, education, **business automation** |
| `16_ai_security_safety/` | Tools to make AI safe and secure |
| `17_multimodal/` | AI that understands images, video, and documents |
| `18_ai_infrastructure/` | Hardware and optimization for running AI |

### Step 3 — Click on a tool

Each `.md` file is a complete tool sheet with everything you need to know.

---

## Method 3: Use with Claude Code (for developers)

If you're a developer with [Claude Code](https://claude.ai/code) installed:

```bash
git clone https://github.com/Tito-42/ARIA.git
cd ARIA
claude
```

Then ask anything in natural language. Claude has access to all 323+ entries locally and can search, compare, and recommend instantly.

---

# Frequently Asked Questions

### Is ARIA free?
Yes, completely. It's open source under the MIT license. The catalog, the scripts, everything.

### Do I need to know how to code?
No. Method 1 (asking a chatbot) requires zero technical skills. You just type a question in plain language.

### Which AI chatbot should I use?
We recommend **Claude** (claude.ai). After multiple benchmarks, it's the only free LLM that actually reads the catalog URL, cites the real tools with enterprise scores, and doesn't hallucinate. ChatGPT and Gemini (free) fail to fetch the URL and give generic answers instead.

### How often is ARIA updated?
Every night between 23:00 and 07:00 (Paris time). AI agents check for new tools, version changes, and trending repos.

### Can I trust the information?
Every entry includes a "Last Verified" date, links to the source, and honest assessments of both strengths and limitations. We don't hide the cons. That said, AI tools evolve fast — always check the official docs before making a critical decision.

### What if a tool I need isn't in the catalog?
Ask the chatbot anyway! It may find something close. And you can open an issue on GitHub to request it — or contribute it yourself.

### I don't speak English well. Can I use ARIA in my language?
The catalog entries are mostly in English, but you can ask the AI chatbot in any language. For example:
```
Lis https://tito-42.github.io/ARIA/CATALOG_SUMMARY.md et dis-moi en français quel outil utiliser pour un chatbot
```
```
Lee https://tito-42.github.io/ARIA/CATALOG_SUMMARY.md y dime en español qué herramienta usar para procesar facturas
```

The AI will read the English entries and answer you in your language.

---

# Quick Reference Card

Save this for later:

```
[Your question]. Read https://tito-42.github.io/ARIA/CATALOG_SUMMARY.md

Works with: Claude, ChatGPT, Gemini, Copilot, or any AI chatbot.
```

---

<div align="center">

*ARIA — Stop Googling. Start querying.*

</div>
