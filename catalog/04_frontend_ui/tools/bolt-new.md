# Bolt.new

> Full-stack AI development environment in the browser by StackBlitz, powered by WebContainers for instant Node.js execution without a server.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 04_frontend_ui |
| **URL** | https://bolt.new |
| **GitHub** | https://github.com/stackblitz/bolt.new |
| **Stars** | ~16,300 |
| **License** | MIT |
| **Pricing** | Free (limited) / Pro $20/mo / Team $40/user/mo |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Bolt.new is StackBlitz's AI-powered full-stack development environment that runs entirely in the browser. It leverages WebContainers -- a browser-based Node.js runtime -- to allow users to prompt, run, edit, and deploy full-stack applications without any local setup. Users describe an application in natural language, and Bolt.new generates the complete project including frontend, backend, and configuration, then runs it live in the browser.

The key differentiator from other AI code generators is that Bolt.new can install npm packages, run Node.js servers, and execute terminal commands directly in the browser via WebContainers. This means the AI can see runtime errors and fix them in a self-correcting loop.

## Key Features
- **Browser-based full-stack**: Complete Node.js environment in browser via WebContainers
- **Multi-framework**: React, Next.js, Vue, Svelte, Astro, and more
- **Self-correcting**: AI sees runtime errors and auto-fixes them
- **Package management**: Install and use any npm package
- **Terminal access**: Full terminal emulation in browser
- **Live preview**: Real-time app preview alongside code
- **One-click deploy**: Deploy to Netlify, Vercel, or other platforms
- **File system**: Full file tree management in browser
- **No local setup**: Zero installation required
- **Conversation-driven**: Iterative development through chat

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | StackBlitz-backed; WebContainers mature |
| **Security** | 3 | Code runs in browser sandbox; cloud-based |
| **Scalability** | 3 | Per-seat licensing; browser-bound resources |
| **Support/Community** | 4 | 16.3K stars; StackBlitz community |
| **Documentation** | 4 | Good docs and examples |
| **Integration Ease** | 5 | Zero setup; browser-only |

## Use Cases
1. **Rapid prototyping** - Build full-stack apps from prompts in minutes
2. **Client demos** - Generate working prototypes for stakeholder review
3. **Learning/education** - Students build apps without local environment setup
4. **Hackathons** - Quick app generation for time-limited events
5. **Bug reproduction** - Create minimal reproductions in browser

## Getting Started
```
# Visit bolt.new
# Describe your application in the prompt
# Watch it generate, install dependencies, and run
# Iterate and deploy
```

## Strengths
- Full Node.js runtime in browser (not just frontend)
- Self-correcting loop -- sees and fixes runtime errors
- Zero setup requirement lowers barrier to entry dramatically
- Multi-framework support (not locked to React)
- Open source (MIT license)

## Limitations
- Browser-based runtime has resource constraints
- Complex backend logic (databases, APIs) can be challenging
- Requires good internet connection
- WebContainers limited to Node.js ecosystem
- Token limits on AI interactions in free tier

## Alternatives
| Tool | Key Difference |
|------|---------------|
| v0 | React/Next.js focused; Vercel ecosystem |
| Bolt.diy | Community fork; fully self-hostable |
| Lovable | Full app builder; Supabase integration |
| Replit Agent | Full IDE; supports more languages |
| Firebase Studio | Google ecosystem; Firebase integration |

## References
- https://bolt.new
- https://github.com/stackblitz/bolt.new
- https://stackblitz.com/webcontainers
