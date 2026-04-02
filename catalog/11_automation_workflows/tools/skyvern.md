# Skyvern

> AI-powered browser automation platform that uses LLMs and computer vision to automate browser workflows without brittle selectors or custom scripts.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 11_automation_workflows |
| **URL** | https://skyvern.com |
| **GitHub** | https://github.com/Skyvern-AI/skyvern |
| **Stars** | ~12,000 |
| **License** | AGPL-3.0 |
| **Pricing** | Free (OSS self-hosted) / Cloud (usage-based) / Enterprise (custom) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Growth |

## What It Does
Skyvern automates browser-based workflows using LLMs and computer vision instead of traditional DOM selectors and scripts. Unlike Playwright or Selenium, which require writing code that targets specific HTML elements (and breaks when websites change), Skyvern "sees" web pages like a human and navigates them using visual understanding.

This approach makes automations resilient to UI changes -- the AI understands the page visually and semantically rather than relying on fragile CSS selectors. Skyvern is particularly powerful for automating workflows on websites you don't control (government portals, vendor sites, insurance forms) where traditional automation is fragile.

## Key Features
- **Visual understanding**: LLM + vision to understand web pages
- **No selectors required**: Navigates by visual/semantic understanding
- **Resilient to UI changes**: Adapts when websites change layout
- **Workflow builder**: Define multi-step browser workflows
- **Cloud browser infrastructure**: Managed browser instances
- **API-first**: REST API for triggering automations
- **Screenshot verification**: Visual confirmation at each step
- **Data extraction**: Extract structured data from any webpage
- **Form filling**: Intelligent form completion
- **Parallel execution**: Run multiple browser tasks concurrently

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 3 | Growing; cloud offering maturing |
| **Security** | 3 | AGPL license; cloud browsers |
| **Scalability** | 4 | Cloud infrastructure; parallel execution |
| **Support/Community** | 3 | 12K stars; growing community |
| **Documentation** | 3 | Good API docs; improving |
| **Integration Ease** | 4 | API-first; easy to trigger |

## Use Cases
1. **Government form automation** - Fill and submit government portal forms
2. **Insurance quoting** - Automate multi-site insurance quote collection
3. **Vendor portal management** - Navigate vendor/supplier portals
4. **Data extraction** - Scrape data from sites without APIs
5. **Competitive intelligence** - Monitor competitor websites

## Getting Started
```bash
# Self-hosted
git clone https://github.com/Skyvern-AI/skyvern
cd skyvern
docker-compose up -d

# Or use the cloud API
curl -X POST https://api.skyvern.com/api/v1/tasks \
  -H "x-api-key: YOUR_KEY" \
  -d '{"url": "...", "navigation_goal": "..."}'
```

## Strengths
- Resilient to website changes (visual understanding vs selectors)
- Works on any website without custom scripting
- Good for sites you don't control (government, vendor portals)
- Cloud browser infrastructure for scale
- API-first design

## Limitations
- Slower than traditional browser automation (LLM inference at each step)
- More expensive per execution (LLM API costs)
- AGPL license may be problematic for some enterprises
- Less precise than traditional automation for known, stable UIs
- Still maturing (some edge cases in visual understanding)

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Browser Use | Open source (MIT); Python framework; more community |
| Playwright | Traditional; precise; code-based; fragile to changes |
| Selenium | Traditional; widely used; fragile |
| Automa | Browser extension; visual builder; simpler |

## References
- https://skyvern.com
- https://github.com/Skyvern-AI/skyvern
