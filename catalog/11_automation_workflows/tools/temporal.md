# Temporal

> Open-source durable execution platform for building reliable, long-running workflows and microservices with automatic state management, retries, and fault tolerance.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 11_automation_workflows |
| **URL** | https://temporal.io |
| **GitHub** | https://github.com/temporalio/temporal |
| **Stars** | ~12,500 |
| **License** | MIT |
| **Pricing** | Free (self-hosted OSS) / Temporal Cloud (usage-based, from ~$200/mo) / Enterprise (custom) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Temporal is a durable execution platform that enables developers to build reliable, long-running workflows without worrying about infrastructure failures. Unlike visual automation tools (n8n, Zapier), Temporal is code-first -- developers write workflows in their language of choice (Go, Java, TypeScript, Python, .NET) and Temporal guarantees that those workflows will complete even if servers crash, networks fail, or services go down.

Temporal emerged from the team behind Uber's Cadence workflow engine and has become the de facto standard for durable execution in backend systems. It is increasingly relevant for AI applications because AI agent workflows (multi-step reasoning, tool calls, human-in-the-loop) benefit enormously from Temporal's durability guarantees -- an agent workflow can run for hours or days without risk of losing state.

## Key Features
- **Durable execution**: Workflows survive process/server crashes automatically
- **Multi-language SDKs**: Go, Java, TypeScript, Python, .NET
- **Automatic retries**: Configurable retry policies for activities
- **Workflow versioning**: Update workflow code without breaking running instances
- **Visibility**: Query workflow state and history at any time
- **Timers and schedules**: Durable timers that survive restarts
- **Child workflows**: Hierarchical workflow composition
- **Signals and queries**: External interaction with running workflows
- **Activity heartbeating**: Long-running task monitoring
- **Temporal Cloud**: Managed service with SLA guarantees
- **Namespace isolation**: Multi-tenant workflow separation

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | Battle-tested at scale (Uber, Netflix, Stripe) |
| **Security** | 5 | mTLS, encryption, namespace isolation |
| **Scalability** | 5 | Handles millions of concurrent workflows |
| **Support/Community** | 4 | 12.5K stars; enterprise support; Slack community |
| **Documentation** | 5 | Excellent docs; courses; examples |
| **Integration Ease** | 3 | Requires understanding of workflow patterns |

## Use Cases
1. **AI agent orchestration** - Durable multi-step agent workflows with human-in-the-loop
2. **Order processing** - E-commerce order fulfillment with saga pattern
3. **Financial transactions** - Reliable payment processing and reconciliation
4. **Data pipelines** - ETL workflows with retry and error handling
5. **Infrastructure provisioning** - Long-running deployment workflows

## Getting Started
```bash
# Start Temporal server locally
temporal server start-dev

# Install SDK (TypeScript example)
npm install @temporalio/client @temporalio/worker @temporalio/workflow @temporalio/activity
```

## Strengths
- Gold standard for durable execution
- Battle-tested at massive scale (Uber, Netflix, Stripe, Snap)
- Multi-language support with native SDKs
- Perfect for AI agent workflows (durability + long-running)
- MIT license for self-hosted

## Limitations
- Steep learning curve (workflow patterns, determinism constraints)
- Overkill for simple automations (use n8n/Zapier instead)
- Self-hosting requires operational expertise
- Temporal Cloud pricing can be significant at scale
- Code-first approach requires developer skills

## Alternatives
| Tool | Key Difference |
|------|---------------|
| n8n | Visual; no-code; simpler; less durable |
| Apache Airflow | DAG-based; data pipeline focused |
| Prefect | Python; data engineering focused |
| Inngest | Serverless; simpler; event-driven |
| Restate | Newer; simpler API; less mature |

## References
- https://temporal.io
- https://github.com/temporalio/temporal
- https://docs.temporal.io
- https://learn.temporal.io
