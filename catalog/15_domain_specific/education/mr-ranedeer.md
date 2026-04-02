# Mr. Ranedeer AI Tutor

> Highly customizable AI tutor meta-prompt for GPT-4 adapting to any learning style and academic level

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 15_domain_specific / education |
| **URL** | https://github.com/JushBJJ/Mr.-Ranedeer-AI-Tutor |
| **GitHub** | https://github.com/JushBJJ/Mr.-Ranedeer-AI-Tutor |
| **Stars** | ~29,700 |
| **License** | Unspecified (prompt open-sourced publicly) |
| **Pricing** | Free (requires ChatGPT Plus subscription for GPT-4) |
| **Last Verified** | 2026-04-02 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Mr. Ranedeer is a sophisticated system prompt (meta-prompt) that transforms any powerful LLM — primarily designed for GPT-4 — into a highly personalized AI tutor. It is not a software application but rather a carefully engineered prompt that configures the LLM to behave as an adaptive educational agent.

The prompt defines a complete pedagogical framework: the user specifies their knowledge level (ELI5 to PhD-level), preferred learning style (textbook, layman, storytelling, Socratic method), communication tone, and reasoning framework. The tutor then adapts all explanations, examples, and assessments to these preferences, creating a genuinely personalized learning experience.

With 29,700 stars it is by far the most popular AI tutoring approach on GitHub and has been deployed by teachers, autodidacts, and EdTech companies worldwide. The methodology is transferable to any capable LLM (Claude, Gemini) making it model-agnostic despite being optimized for GPT-4.

## Key Features
- Configurable knowledge depth levels: Elementary, Middle School, High School, Undergraduate, PhD
- Multiple learning style modes: Textbook, Layman, Story, Socratic, Analogical
- Adaptive communication tone: Friendly, Professional, Humorous, Formal
- Structured commands: `/test` (create assessments), `/plan` (lesson planning), `/explain` (deep dives)
- Multilingual support: teaches in any language upon request
- Progress tracking via conversation memory
- Subject coverage: mathematics, programming, sciences, humanities, languages
- v2.7 (November 2023) stable release

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | v2.7 stable; 29.7k validation; used in real educational products |
| **Security** | 3 | Depends entirely on the underlying LLM provider's security posture |
| **Scalability** | 4 | Prompt-based; scales with LLM API throughput; no compute infrastructure needed |
| **Support/Community** | 4 | 29.7k stars, active issues and PRs, community modifications |
| **Documentation** | 4 | Comprehensive README, usage examples, configuration guide |
| **Integration Ease** | 5 | Copy-paste prompt; no code required to use; API integration is trivial |

## Use Cases
1. **Self-directed learning platform**: Integrating Mr. Ranedeer's prompt methodology into an EdTech platform to provide personalized tutoring at PhD quality for subjects from K-12 through university
2. **Corporate training tool**: Adapting the framework for employee onboarding and skill development with custom company knowledge bases
3. **Exam preparation**: Generating adaptive practice tests, identifying knowledge gaps, and providing targeted remediation
4. **Language learning**: Using the Socratic and story-based modes for conversational language practice with native-level explanations

## Getting Started
```
# Step 1: Open ChatGPT with GPT-4 enabled
# Step 2: Paste the full Mr. Ranedeer system prompt from GitHub
# Step 3: Configure your preferences:

/config
- Depth: Undergraduate
- Learning Style: Socratic
- Communication Style: Friendly
- Tone: Encouraging
- Language: English

# Step 4: Start learning
/start
Please teach me about neural networks from scratch.
```

## Architecture / How It Works
Mr. Ranedeer is purely prompt-based: no code, no database, no deployment infrastructure. The system prompt defines a persona (Mr. Ranedeer, a deer tutor), a configuration schema for personalization parameters, and a set of slash commands that trigger specific pedagogical behaviors. The LLM interprets this configuration and maintains it throughout the conversation. The prompt engineering relies on the LLM's instruction-following capability, chain-of-thought reasoning, and ability to role-play a specific educational persona. The `v2.7` version introduced improved lesson planning and test generation.

## Strengths
- Zero infrastructure cost: just a prompt and a ChatGPT Plus subscription
- 29.7k community validation across diverse subjects and languages
- Highly accessible: no technical knowledge required to use or adapt
- Transferable to Claude, Gemini, or local LLMs with minimal modification
- Methodology is reproducible and well-documented for building custom versions

## Limitations
- Not a standalone deployable application; requires GPT-4 or equivalent
- No persistent user state across sessions; conversation memory resets
- Requires ChatGPT Plus ($20/month) for the full GPT-4 experience
- Cannot access real-time information unless used with web-browsing plugins
- Prompt-based approach has less reliability than a structured software application

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Tutor-GPT (Bloom) | Software application with Theory of Mind; more sophisticated architecture |
| ChatTutor | Visual/interactive; adds whiteboard for STEM; actual application |
| Khanmigo (Khan Academy) | Proprietary; integrated with Khan Academy curriculum |
| Socratic (Google) | Mobile app; photo-based homework help |

## References
- https://github.com/JushBJJ/Mr.-Ranedeer-AI-Tutor
- Bloom's 2-Sigma Problem: Bloom, B.S. (1984), "The 2 sigma problem: The search for methods of group instruction as effective as one-to-one tutoring", Educational Researcher

## Notes
Mr. Ranedeer demonstrates the power of prompt engineering for education and is a useful reference for EdTech teams building AI tutors. However, for a production product, the Tutor-GPT (Bloom) or ChatTutor approach — actual software applications with persistent state — is more appropriate than a raw prompt. Mr. Ranedeer's value is as a methodology reference and rapid prototyping tool.
