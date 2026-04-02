# Screenshot-to-Code

> Open-source tool that converts screenshots, mockups, and Figma designs into clean, functional code using GPT-4 Vision and Claude.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 04_frontend_ui |
| **URL** | https://screenshottocode.com |
| **GitHub** | https://github.com/abi/screenshot-to-code |
| **Stars** | ~67,000 |
| **License** | MIT |
| **Pricing** | Free (OSS, BYO API key) / Hosted version available |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Screenshot-to-Code is an open-source tool that uses multimodal AI (GPT-4 Vision, Claude 3.5 Sonnet) to convert screenshots, mockups, and designs into functional frontend code. Users upload a screenshot or paste a URL, and the tool generates corresponding HTML/CSS, React, Vue, or other framework code that visually matches the original design.

With ~67K GitHub stars, it is one of the most popular AI frontend tools. The tool supports multiple output formats and frameworks, and can generate both static HTML/Tailwind and component-based React/Vue code. It works particularly well for converting existing designs, wireframes, or competitor UIs into code -- a common workflow for frontend developers.

## Key Features
- **Screenshot to code**: Upload image, get functional code
- **URL to code**: Paste a URL, get code for that page
- **Multi-framework output**: HTML/Tailwind, React, Vue, Bootstrap, Ionic, SVG
- **Video/GIF support**: Convert screen recordings to animated code
- **Multi-model**: GPT-4 Vision, Claude 3.5 Sonnet, DALL-E for images
- **Figma integration**: Import Figma designs directly
- **Self-hostable**: Run with your own API keys
- **Iterative refinement**: Edit and regenerate specific sections
- **Dark mode support**: Generates code for both themes
- **Responsive output**: Generated code is responsive by default

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Mature; widely used |
| **Security** | 4 | Self-hostable with own API keys |
| **Scalability** | 4 | Lightweight; API-key based |
| **Support/Community** | 5 | 67K stars; active community |
| **Documentation** | 4 | Good README; clear setup |
| **Integration Ease** | 4 | Simple Docker setup; BYO API key |

## Use Cases
1. **Design-to-code conversion** - Convert mockups/wireframes to functional code
2. **Rapid cloning** - Quickly reproduce existing UI patterns
3. **Legacy modernization** - Screenshot old UIs, generate modern code
4. **Competitive analysis** - Convert competitor UIs into inspectable code
5. **Prototyping** - Turn hand-drawn sketches into working code

## Getting Started
```bash
# Clone and run
git clone https://github.com/abi/screenshot-to-code
cd screenshot-to-code

# Backend
cd backend
pip install -r requirements.txt
OPENAI_API_KEY=... python main.py

# Frontend
cd frontend
npm install && npm run dev
```

## Strengths
- Open source (MIT) -- fully self-hostable
- Extremely popular and well-maintained (67K stars)
- Multi-framework output options
- Video/GIF support is unique differentiator
- Simple, focused tool that does one thing well

## Limitations
- Quality depends on screenshot clarity and complexity
- Complex layouts may require manual cleanup
- API costs (GPT-4V/Claude are not cheap for image analysis)
- Generated code may not match pixel-perfect
- No backend/logic generation (pure frontend)

## Alternatives
| Tool | Key Difference |
|------|---------------|
| v0 | Prompt-based; generates from description not screenshot |
| Figma to Code plugins | Native Figma integration; less AI |
| Locofy | Figma/XD to code; enterprise-focused |
| TeleportHQ | Visual builder with AI assist |

## References
- https://github.com/abi/screenshot-to-code
- https://screenshottocode.com
