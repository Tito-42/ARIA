# Chatwoot

> Open-source omnichannel customer support platform with Captain AI for automated resolution

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 15_domain_specific / business-automation |
| **URL** | https://www.chatwoot.com |
| **GitHub** | https://github.com/chatwoot/chatwoot |
| **Stars** | ~28,200 |
| **License** | MIT |
| **Pricing** | Free (self-hosted) / Cloud from $19/month |
| **Last Verified** | 2026-04-02 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Chatwoot is the leading open-source omnichannel customer support platform, providing a unified inbox for managing customer conversations across live chat, email, social media (Facebook, Twitter/X, Instagram), WhatsApp, Telegram, and other channels. Its Captain AI feature integrates AI-powered response automation directly into the support workflow, automating routine inquiries and freeing human agents for complex issues.

Captain AI learns from your support knowledge base and past conversation history to automatically resolve common customer questions, with human escalation when the AI's confidence is insufficient. The system includes Google Translate integration for multilingual support, making it suitable for global customer service operations.

With 28,200 stars and an April 2026 update, Chatwoot is the most mature and widely deployed open-source customer support platform available, used by thousands of businesses as a replacement for Intercom, Freshdesk, and Zendesk.

## Key Features
- Unified inbox: live chat, email, WhatsApp, Telegram, Facebook, Twitter/X, Instagram, SMS
- Captain AI: automated response using knowledge base and conversation history
- Canned responses and automated workflows
- Human-in-the-loop: automatic escalation when AI confidence is low
- Google Translate integration for multilingual support
- Custom attributes and CRM-like contact management
- Reports and analytics: response time, resolution rate, agent performance
- REST API and webhooks for integration
- Self-hosted (Ruby on Rails) or managed cloud

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | April 2026 update; 28.2k stars; thousands of production deployments |
| **Security** | 5 | MIT; self-hostable; full data control; SOC 2 cloud offering |
| **Scalability** | 5 | Used by companies handling millions of conversations; Kubernetes support |
| **Support/Community** | 5 | Full-time team at Chatwoot Inc; enterprise support plans; active community |
| **Documentation** | 5 | Comprehensive docs; deployment guides; API reference; integration tutorials |
| **Integration Ease** | 4 | Docker deployment; REST API; webhooks; some Ruby knowledge helps for customization |

## What It Automates
Chatwoot with Captain AI automates **60-70%** of customer support interactions. Routine inquiries (order status, FAQs, account questions, policy information) are handled automatically without agent involvement. Complex issues, complaints, billing disputes, and cases requiring human judgment are automatically escalated to human agents, keeping the 30-40% requiring human expertise properly routed.

## Use Cases
1. **E-commerce customer support**: Automating responses to shipping inquiries, return requests, and product questions via WhatsApp and live chat with AI, escalating disputes to human agents
2. **SaaS product support**: Providing 24/7 tier-1 support from the knowledge base via Captain AI, routing bug reports and advanced technical issues to engineers
3. **Replacing Intercom/Freshdesk**: Migrating from expensive SaaS support platforms to a self-hosted Chatwoot instance for cost savings while maintaining feature parity
4. **Multilingual global support**: Using Google Translate integration to serve customers in their language without hiring multilingual agents for every market

## Getting Started
```bash
# Docker Compose deployment
git clone https://github.com/chatwoot/chatwoot
cd chatwoot
cp .env.example .env
# Configure database, Redis, LLM API key for Captain AI

docker-compose up -d

# Cloud: sign up at app.chatwoot.com
# Configure Captain AI in Settings > AI

# Webhook integration example
curl -X POST https://your-chatwoot.com/api/v1/profile \
  -H "api_access_token: your_token" \
  -H "Content-Type: application/json"
```

## Architecture / How It Works
Chatwoot uses a Ruby on Rails backend with a Vue.js frontend. The omnichannel layer maintains integrations with all messaging platforms and normalizes conversation data into a unified format. Captain AI connects to a configured LLM (Chatwoot's proprietary model or Dialogflow) with access to the knowledge base articles and past conversation embeddings. When a new message arrives, Captain AI evaluates whether it can respond with sufficient confidence; if yes, it sends an automated reply; if no, it routes to a human agent with the AI-generated suggested response as context. Automated workflows (assignment rules, SLA escalations) handle routing logic independently of AI.

## Strengths
- MIT license enables full self-hosting with zero vendor lock-in
- Most mature open-source support platform with 28.2k community validation
- April 2026 update confirms active maintenance at the latest date
- Captain AI reduces routine support volume without replacing human agents for complex issues
- Enterprise deployment at scale with Kubernetes support

## Limitations
- Captain AI uses Chatwoot's own model or Dialogflow; bringing your own LLM requires customization
- Self-hosting requires DevOps expertise (Redis, PostgreSQL, background workers)
- WhatsApp and some channel integrations require Business API accounts (cost)
- Not a CRM replacement; limited deal/sales pipeline features
- AI capabilities are less sophisticated than purpose-built AI customer service platforms

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Intercom | Polished SaaS; much more expensive; better AI features |
| Freshdesk | Full ITSM features; SaaS only; expensive at scale |
| Zammad | Open-source; more IT help desk focused; less omnichannel |
| Tiledesk | Open-source; lighter; specifically designed for LLM-based agents |

## References
- https://www.chatwoot.com
- https://github.com/chatwoot/chatwoot
- https://www.chatwoot.com/docs/
- https://www.chatwoot.com/docs/product/captain/ (Captain AI docs)

## Notes
Chatwoot is the obvious first choice for any organization that needs an open-source customer support platform. The combination of MIT license, comprehensive channel coverage, and Captain AI makes it a complete solution for most SMB to mid-market use cases. For enterprise deployments requiring custom AI models, plan for integration work to connect your preferred LLM to Captain AI's hooks. The cloud-managed version eliminates DevOps complexity for teams without infrastructure expertise.
