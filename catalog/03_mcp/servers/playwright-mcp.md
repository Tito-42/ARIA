# Playwright MCP

> Official Microsoft MCP server for browser automation using accessibility snapshots

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 03 - MCP |
| **URL** | https://github.com/microsoft/playwright-mcp |
| **GitHub** | https://github.com/microsoft/playwright-mcp |
| **Stars** | 30,100 |
| **License** | {TODO} - Microsoft (check repo LICENSE file) |
| **Pricing** | Free / Open Source |
| **Last Verified** | 2026-04-02 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Playwright MCP is the official Microsoft MCP server for browser automation, built on the Playwright testing framework. It is the most starred MCP server in the ecosystem (30,100 stars), reflecting its central role in enabling AI agents to interact with web browsers.

Its key architectural decision is using accessibility tree snapshots rather than screenshots to represent browser state. This "accessibility-first" approach makes the server token-efficient (structured text instead of images) and deterministic (accessibility labels are stable), avoiding the need for vision models. Agents can interact with web pages through semantic element descriptions, form inputs, clicks, and navigation — all without processing pixel data.

With 504 commits and active maintenance by Microsoft, Playwright MCP is production-ready and widely used as the browser automation backend for AI agents built on Claude, GPT-4, and other models.

## Key Features
- Browser automation via structured accessibility snapshots (not screenshots)
- Navigation, clicking, form filling, scrolling, and screenshot tools
- Support for multiple browsers: Chromium, Firefox, WebKit
- Headed and headless modes
- Network request interception and monitoring
- Tab management and multi-page workflows
- File upload/download handling
- Mobile device emulation
- Configurable via `playwright.config.ts` options

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | Official Microsoft, 30.1k stars, 504 commits, widely deployed |
| **Security** | 3 | Browser automation carries inherent risks; sandbox/container isolation recommended |
| **Scalability** | 3 | Each server instance runs one browser; scale via multiple instances |
| **Support/Community** | 5 | Official Microsoft support, massive community, active issue tracker |
| **Documentation** | 5 | Comprehensive README, Playwright docs, many community tutorials |
| **Integration Ease** | 5 | `npx @playwright/mcp` — works immediately with Claude Desktop |

## Use Cases
1. Web scraping and data extraction from dynamic JavaScript-rendered pages
2. Automated form filling and multi-step web workflows for AI agents
3. End-to-end testing automation triggered by natural language instructions
4. Web research agents that navigate and synthesize content from multiple pages
5. UI testing where AI generates test scenarios from accessibility tree analysis

## Getting Started
```bash
# Add to Claude Desktop (claude_desktop_config.json)
{
  "mcpServers": {
    "playwright": {
      "command": "npx",
      "args": ["@playwright/mcp"]
    }
  }
}

# Or run directly
npx @playwright/mcp

# Headless mode
npx @playwright/mcp --headless

# Specific browser
npx @playwright/mcp --browser firefox
```

## Architecture / How It Works
Playwright MCP launches a Playwright browser instance when a client connects. It exposes MCP tools that map to Playwright API calls. When an agent calls a navigation or interaction tool, Playwright executes the action in the browser. For state observation, instead of capturing screenshots, the server captures the browser's accessibility tree — a structured JSON representation of all interactive and informational elements on the page. This tree is returned as text, allowing the LLM to reason about page structure without consuming image tokens. Screenshots are available as an optional tool when visual inspection is specifically needed.

## Strengths
- Token-efficient accessibility-first approach — no image model required
- Official Microsoft product with Playwright's battle-tested browser control
- Deterministic element targeting via accessibility attributes
- Supports all major browsers through unified Playwright API
- 30k+ stars confirms broad production adoption

## Limitations
- Browser automation is inherently stateful — server must stay alive between tool calls
- Accessibility tree may miss purely visual elements with no ARIA attributes
- Complex SPAs with poor accessibility practices may be difficult to navigate
- Resource-intensive: running a browser per session limits concurrency
- Some dynamic content (canvas, WebGL) is not representable in the accessibility tree

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Browserbase MCP | Cloud-hosted browser automation (vs. local Playwright); Stagehand AI layer |
| Puppeteer MCP | Chrome/Chromium only; official version archived |
| browser-use | Python-first browser agent with vision fallback |

## References
- [GitHub Repository](https://github.com/microsoft/playwright-mcp)
- [NPM Package (@playwright/mcp)](https://www.npmjs.com/package/@playwright/mcp)
- [Playwright Documentation](https://playwright.dev)
- [MCP Server Guide](https://modelcontextprotocol.io/examples)

## Notes
This is the recommended replacement for the official `puppeteer` MCP server, which was archived from `modelcontextprotocol/servers`. The accessibility snapshot approach is a significant innovation — it makes browser automation viable for token-constrained contexts and eliminates the need for multimodal models in most web automation tasks. For cloud environments, consider Browserbase MCP as an alternative that offloads browser management.
