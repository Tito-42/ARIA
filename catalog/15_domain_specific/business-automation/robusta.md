# Robusta

> AI-powered Kubernetes monitoring with HolmesGPT for intelligent alert enrichment and auto-remediation

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 15_domain_specific / business-automation |
| **URL** | https://robusta.dev |
| **GitHub** | https://github.com/robusta-dev/robusta |
| **Stars** | ~3,000 |
| **License** | MIT |
| **Pricing** | Free (self-hosted) / Cloud from $249/month |
| **Last Verified** | 2026-04-02 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Robusta is an AI-powered Kubernetes monitoring and remediation platform that extends Prometheus alerting with intelligent context enrichment and automated remediation. Its key innovation is HolmesGPT, an AI component that automatically investigates Kubernetes alerts, correlates relevant logs and metrics, and provides human-readable explanations — replacing the manual alert triage process that consumes significant engineer time in on-call rotations.

When a Kubernetes alert fires, traditional setups require an engineer to manually look up the relevant pod logs, check deployment events, inspect resource usage, and diagnose the root cause. Robusta automates this investigation: HolmesGPT gathers all relevant context automatically and delivers a pre-analyzed, enriched alert to Slack with the likely root cause and recommended action.

The platform also handles intelligent alert grouping (related alerts become a single Slack thread rather than flooding the channel), automated remediation for well-understood issues (restart a pod, scale a deployment), and integration with incident management tools (PagerDuty, Opsgenie, Jira, ServiceNow).

## Key Features
- HolmesGPT: AI investigation engine for Kubernetes alert root cause analysis
- Intelligent alert grouping: correlated alerts consolidated into threaded Slack/Teams notifications
- AI-enriched alerts: logs, events, and metrics automatically included with each alert
- Auto-remediation: configurable automated fixes for known patterns (pod restarts, scaling)
- Prometheus, Grafana, and Alertmanager integration
- Slack, PagerDuty, Opsgenie, PagerDuty, Jira, ServiceNow notification integrations
- Custom playbooks: Python-based automation scripts triggered by alerts
- Kubernetes event monitoring: deployments, pod crashes, OOMKill events

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | MIT; 3k stars; enterprise cloud offering; production at multiple companies |
| **Security** | 4 | MIT self-hosted; HolmesGPT can use local LLM; Kubernetes RBAC integration |
| **Scalability** | 4 | Multi-cluster support; handles large Kubernetes environments |
| **Support/Community** | 4 | Robusta.dev company; enterprise SLAs; active Slack community |
| **Documentation** | 4 | Good docs; playbook library; HolmesGPT configuration guide |
| **Integration Ease** | 4 | Helm chart deployment; integrates with existing Prometheus stack |

## What It Automates
Robusta automates **65-70%** of Kubernetes alert triage and DevOps monitoring tasks. The manual process of investigating alerts (fetching logs, checking events, reading metrics dashboards) is automated by HolmesGPT. Auto-remediation handles the 20-30% of alerts with well-known solutions. The remaining 30-35% involves novel issues, complex multi-service debugging, capacity planning decisions, and architectural problems that require experienced engineers.

## Use Cases
1. **On-call alert fatigue reduction**: Replacing hundreds of raw Prometheus alerts with HolmesGPT-enriched, pre-analyzed alert threads in Slack that engineers can act on immediately without additional investigation
2. **Auto-remediation of common issues**: Configuring automated responses to well-understood alerts (pod OOMKill → restart + increase memory limit, HPA stuck → force reconcile)
3. **Post-incident analysis**: Using Robusta's event history and HolmesGPT to generate post-mortems automatically from the alert timeline
4. **Multi-cluster Kubernetes governance**: Monitoring all clusters from a single Robusta instance, with intelligent routing of alerts to the right team channels

## Getting Started
```bash
# Helm deployment (recommended)
helm repo add robusta https://robusta-charts.storage.googleapis.com
helm repo update

# Install with your configuration
helm install robusta robusta/robusta \
  --set clusterName=production \
  --set slackApiKey=xoxb-your-slack-token \
  --set slackChannel="#alerts" \
  --set holmesGPT.openaiApiKey=your-openai-key

# Verify installation
kubectl get pods -n default | grep robusta
```

## Architecture / How It Works
Robusta deploys as a Kubernetes controller that watches for pod events, deployment changes, and Prometheus alert webhooks. When an alert fires, the Alert Pipeline processes it: first, context gatherers collect relevant logs, events, metrics, and Kubernetes object state; next, HolmesGPT analyzes this context with an LLM to generate a root cause hypothesis and recommended action; finally, notification sinks deliver the enriched alert to configured destinations (Slack, PagerDuty, etc.). Custom playbooks (Python scripts) can be triggered by any alert to execute automated remediation steps. The alert grouping system uses similarity matching to thread related alerts together rather than creating separate notifications.

## Strengths
- MIT license for full production deployment without licensing costs
- HolmesGPT dramatically reduces mean time to investigation (MTTI) for Kubernetes alerts
- Intelligent alert grouping solves the Slack alert flood problem
- Existing Prometheus stack is reused — Robusta augments rather than replaces
- Active company (Robusta.dev) with enterprise support available

## Limitations
- 3k stars is modest; less community testing than mature monitoring tools
- HolmesGPT requires LLM API access (cost, potential cloud data exposure)
- Complex multi-service issues may still require manual investigation
- Auto-remediation must be carefully configured to avoid unintended actions in production
- Some advanced playbooks require Python development

## Alternatives
| Tool | Key Difference |
|------|---------------|
| PagerDuty AIOps | Proprietary; more polished; expensive; no Kubernetes-specific AI |
| Komodor | Kubernetes-specific; focused on change correlation; less AI |
| Datadog | Full observability suite; expensive; Kubernetes AI features |
| OpenTelemetry + LangChain | DIY approach; more flexible but requires significant custom development |

## References
- https://robusta.dev
- https://github.com/robusta-dev/robusta
- https://docs.robusta.dev/
- https://docs.robusta.dev/main/holmesgpt/ (HolmesGPT docs)

## Notes
Robusta is the most practical open-source tool for bringing AI intelligence to Kubernetes operations. For teams using Prometheus + Alertmanager + Slack for monitoring, Robusta integrates seamlessly without replacing any existing infrastructure. The HolmesGPT component requires careful LLM selection for production — consider using Ollama with a local model if Kubernetes logs contain sensitive data that should not be sent to external APIs. The enterprise cloud offering simplifies deployment for teams without Kubernetes expertise.
