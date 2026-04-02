# ChatTutor

> Interactive visual AI teacher with whiteboard and mindmap generation for STEM education

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 15_domain_specific / education |
| **URL** | https://chattutor.app |
| **GitHub** | https://github.com/HugeCatLab/ChatTutor |
| **Stars** | ~987 |
| **License** | AGPL-3.0 |
| **Pricing** | Free (open source) / Hosted version at chattutor.app |
| **Last Verified** | 2026-04-02 |
| **Status** | Active |
| **Maturity** | Beta |

## What It Does
ChatTutor differentiates itself from text-only AI tutors by providing an interactive visual teaching environment. It combines LLM-driven explanations with an interactive mathematical canvas and conceptual mindmap generation, directly addressing the limitation of text-only tutoring for STEM subjects where visual representation is essential.

When teaching mathematics or physics, ChatTutor can render equations on a live canvas, draw diagrams, and generate concept maps that show how ideas relate to each other. This visual dimension mirrors how skilled human STEM tutors use whiteboards, and research in educational psychology shows that visual-spatial representation significantly improves conceptual understanding compared to text alone.

The platform supports multiple LLM backends including OpenAI, Anthropic (Claude), and DeepSeek, making it model-agnostic and cost-flexible. Its web-based interface means no installation is required for students. January 2026 commits indicate active development.

## Key Features
- Interactive mathematical canvas with real-time equation rendering
- Conceptual mindmap generation for topic exploration
- Multi-model support: OpenAI GPT-4o, Anthropic Claude, DeepSeek
- Web-based interface (no installation required for students)
- Structured curriculum pathways and learning progression
- Code execution for programming education
- Multi-language interface support
- Self-hostable via Docker (AGPL-3.0)

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 3 | Beta; active development Jan 2026; deployed at chattutor.app |
| **Security** | 3 | AGPL; full code audit possible; student data handling needs review |
| **Scalability** | 3 | Web service; canvas rendering may be resource-intensive at scale |
| **Support/Community** | 3 | 987 stars; HugeCatLab team; growing community |
| **Documentation** | 3 | Good README; setup instructions; deployment guide available |
| **Integration Ease** | 3 | Web application; API integration possible; Docker deployment |

## Use Cases
1. **STEM tutoring platform**: Deploying ChatTutor as the interactive learning component for mathematics and physics courses where visual representation is critical
2. **University office hours supplement**: Providing students with 24/7 access to visual problem-solving assistance between human office hours
3. **Concept mapping for complex topics**: Using mindmap generation to help students understand the relationships between concepts in complex subjects (calculus, organic chemistry)
4. **Programming education**: Leveraging code execution capabilities to teach programming with immediate feedback and visual output

## Getting Started
```bash
git clone https://github.com/HugeCatLab/ChatTutor
cd ChatTutor
docker-compose up -d

# Or local development
pip install -r requirements.txt
cp .env.example .env
# Configure OPENAI_API_KEY or ANTHROPIC_API_KEY
python app.py
# Access at http://localhost:3000
```

## Architecture / How It Works
ChatTutor uses a web application architecture with a React frontend providing the interactive canvas and mindmap UI, and a Python backend (FastAPI) orchestrating LLM calls. When a student asks a question, the backend determines whether visual output (equation, diagram, mindmap) is appropriate and generates both a text explanation and the visual representation simultaneously. The canvas component renders LaTeX mathematics and supports interactive manipulation. Mindmaps are generated as structured graph data and rendered with a graph visualization library. Multiple LLM providers are supported via an abstraction layer.

## Strengths
- Unique visual dimension addresses STEM tutoring's biggest limitation (text-only explanation)
- Model-agnostic (OpenAI, Claude, DeepSeek) enables cost optimization
- Web-based requires no student installation
- AGPL allows institutional self-hosting for data privacy
- Active January 2026 commits indicate ongoing development

## Limitations
- AGPL-3.0 requires any distributed modifications to be open-sourced (may affect commercial use)
- Beta status; feature stability not guaranteed
- Canvas and mindmap quality depends on the underlying LLM's reasoning
- 987 stars is modest; less community testing than mature tools
- Not designed for non-STEM subjects where visual representation is less relevant

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Mr. Ranedeer | Text-only but simpler; more flexible subjects; 29.7k star validation |
| Tutor-GPT (Bloom) | Theory of Mind adaptation; no visual canvas |
| Khanmigo | Polished with Khan Academy content; proprietary |
| Wolfram Alpha | Computation-focused; less conversational tutoring |

## References
- https://github.com/HugeCatLab/ChatTutor
- https://chattutor.app
- Mayer, R.E. (2009), "Multimedia Learning" (theoretical basis for visual learning)

## Notes
ChatTutor's whiteboard approach is the right direction for serious STEM education AI. For EdTech companies targeting mathematics, physics, or chemistry, the visual canvas feature is a genuine differentiator over text-only tutors. The AGPL license requires careful review for commercial products — if modifications will be kept proprietary, a commercial license agreement with HugeCatLab would be needed. For a production deployment, the hosted version at chattutor.app is the lower-risk starting point.
