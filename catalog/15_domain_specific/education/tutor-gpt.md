# Tutor-GPT

> Theory of Mind-driven adaptive AI tutor deployed as "Bloom" learning companion

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 15_domain_specific / education |
| **URL** | https://bloomingmath.com |
| **GitHub** | https://github.com/plastic-labs/tutor-gpt |
| **Stars** | ~892 |
| **License** | GPL-3.0 |
| **Pricing** | Free (open source) / Bloom SaaS hosted version available |
| **Last Verified** | 2026-04-02 |
| **Status** | Active |
| **Maturity** | Beta |

## What It Does
Tutor-GPT is an LLM-based learning companion that uses Theory of Mind (ToM) reasoning to dynamically adapt its tutoring approach based on an inferred model of the learner's understanding. It is deployed in production as "Bloom", named after Benjamin Bloom's famous 2 Sigma Problem which showed that one-on-one human tutoring produces 2 standard deviations better outcomes than classroom instruction.

The distinguishing architectural innovation is dynamic prompt self-improvement: Tutor-GPT continuously updates its internal model of the user's knowledge state and adjusts its prompting strategy accordingly. When the user demonstrates confusion, the tutor automatically adopts simpler explanations; when the user shows mastery, it advances the complexity. This mirrors how skilled human tutors adapt in real-time — a capability absent in most AI tutoring tools.

The tool integrates Honcho for user modeling persistence, Mistral OCR for processing educational documents, and supports both web and API interfaces. The GPL-3.0 license permits self-hosting for educational institutions.

## Key Features
- Theory of Mind reasoning for adaptive personalization
- Dynamic prompt self-improvement based on inferred learner state
- Honcho integration for persistent user modeling across sessions
- Mistral OCR for processing textbook pages, problem sets, and notes
- Web interface + Python API
- Support for mathematics, sciences, humanities, and language learning
- Socratic questioning methodology for guided discovery
- Self-hosted deployment option (GPL-3.0)

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 3 | Beta; deployed as Bloom; Feb 2026 last commit; needs more validation |
| **Security** | 4 | GPL allows full code audit; self-hostable for data control |
| **Scalability** | 3 | Web service; scalability depends on underlying LLM API and Honcho |
| **Support/Community** | 3 | 892 stars; Plastic Labs team; smaller community than Mr. Ranedeer |
| **Documentation** | 3 | Good README; less comprehensive than mature tools |
| **Integration Ease** | 3 | Python API available; requires backend integration work |

## Use Cases
1. **Mathematics tutoring platform**: Deploying Bloom as a 24/7 math tutor that adapts to each student's pace and identifies misconceptions through Socratic questioning
2. **EdTech personalization layer**: Integrating Tutor-GPT's adaptive prompting architecture into an existing LMS (Moodle, Canvas) to add AI tutoring capabilities
3. **Homework help with document understanding**: Using Mistral OCR to let students photograph their textbook pages or problem sets and ask the tutor about them
4. **Self-hosted school deployment**: Running a private instance for a school or university that requires student data to remain on-premise (GPL + self-hosting)

## Getting Started
```bash
git clone https://github.com/plastic-labs/tutor-gpt
cd tutor-gpt
pip install -r requirements.txt

# Configure environment
cp .env.example .env
# Set OPENAI_API_KEY or ANTHROPIC_API_KEY and HONCHO_API_KEY

# Run the web interface
python app.py
# Access at http://localhost:5000
```

## Architecture / How It Works
Tutor-GPT maintains a dual-process architecture: a Learner Model that tracks inferred knowledge states and misconceptions (powered by Honcho for cross-session persistence), and a Tutoring Agent that consults this model when formulating responses. When a student provides an answer, the Tutoring Agent uses Theory of Mind reasoning ("what does this response reveal about the student's mental model?") to update the Learner Model and select the optimal next tutoring move: clarifying question, simpler explanation, harder example, or conceptual scaffolding. The Mistral OCR module enables processing of physical documents for context.

## Strengths
- Theory of Mind approach is theoretically grounded in cognitive science
- Cross-session user modeling via Honcho preserves learning progress
- Most recent active development (February 2026) among open-source AI tutors
- GPL-3.0 allows institutions full audit and self-hosting control
- Mistral OCR integration handles real-world educational materials

## Limitations
- 892 stars is modest; less community validation than Mr. Ranedeer
- Beta status means API stability is not guaranteed
- GPL-3.0 may be restrictive for commercial EdTech products (consider licensing implications)
- Requires backend infrastructure to deploy; not a copy-paste solution
- Theory of Mind inference quality depends heavily on the underlying LLM capability

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Mr. Ranedeer | Prompt-only; no code needed; less sophisticated but easier to deploy |
| ChatTutor | Visual/interactive whiteboard; better for STEM visual learners |
| Khanmigo | Polished commercial product; integrated with Khan Academy content |
| LangGraph + custom | More flexible but requires building the tutoring logic from scratch |

## References
- https://github.com/plastic-labs/tutor-gpt
- https://bloomingmath.com
- https://plasticlabs.ai/
- Bloom, B.S. (1984), "The 2 sigma problem: The search for methods of group instruction as effective as one-to-one tutoring", Educational Researcher 13(6)

## Notes
Tutor-GPT represents the state of the art in open-source AI tutoring architecture. For EdTech companies building serious AI tutoring products, Tutor-GPT's ToM approach is worth studying and potentially adapting even if the codebase is not used directly. The Honcho user modeling component is particularly valuable — it solves the cross-session personalization problem that plagues most AI tutoring attempts.
