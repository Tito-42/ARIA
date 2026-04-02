# AWS MCP Servers

> Official AWS Labs suite of MCP servers for interacting with the AWS ecosystem via natural language

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 03 - MCP |
| **URL** | https://github.com/awslabs/mcp |
| **GitHub** | https://github.com/awslabs/mcp |
| **Stars** | 8,700 |
| **License** | Apache-2.0 |
| **Pricing** | Free / Open Source (AWS service costs apply separately) |
| **Last Verified** | 2026-04-02 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
The AWS MCP Servers repository is the official collection of MCP servers published by AWS Labs, providing comprehensive access to Amazon Web Services through the Model Context Protocol. It enables AI agents and developers using tools like Claude Code, Cursor, or Amazon Q Developer to query AWS documentation, manage infrastructure, interact with container services, handle serverless functions, and more — all through natural language.

The suite covers the full AWS service breadth, with dedicated servers for documentation lookup, Infrastructure as Code, EKS/ECS container management, Lambda, serverless frameworks, CloudFormation, and AWS Support. With 8,700 stars, it is the most popular cloud provider MCP suite.

An important operational note: the SSE transport was removed from AWS MCP servers in May 2025. All servers currently support stdio transport only, which means they must be run locally rather than as remote endpoints.

## Key Features
- **AWS Documentation Server**: Search and retrieve AWS service documentation, code examples, CDK constructs
- **AWS IaC Server**: Generate and validate CloudFormation templates and CDK code
- **Amazon EKS Server**: Manage EKS clusters, nodes, pods, and deployments
- **Amazon ECS Server**: Manage ECS clusters, tasks, services, and containers
- **AWS Lambda Server**: Create, invoke, update, and monitor Lambda functions
- **AWS Serverless Server**: SAM framework integration for serverless application development
- **CloudFormation Server**: Deploy and manage CloudFormation stacks
- **AWS Support Server**: Create and manage AWS Support tickets
- Stdio transport only (SSE removed May 2025)
- AWS credential chain support (env vars, profiles, IAM roles)

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Official AWS Labs, 8.7k stars, actively maintained |
| **Security** | 4 | Inherits AWS IAM; principle of least privilege via IAM policies; no credentials stored |
| **Scalability** | 3 | Stdio-only limits to local use; no hosted endpoint |
| **Support/Community** | 5 | Official AWS Labs support, large AWS community |
| **Documentation** | 4 | Per-server READMEs, AWS documentation integration |
| **Integration Ease** | 4 | Requires AWS credentials; each server installed separately via uvx/npx |

## Use Cases
1. AWS documentation lookup during development without leaving the IDE
2. Generating CDK/CloudFormation code for new infrastructure requirements
3. Querying EKS cluster status and pod logs during incident response
4. Creating and invoking Lambda functions via natural language prompts
5. Managing ECS services and monitoring container health
6. Filing AWS Support cases with full context from the current conversation

## Getting Started
```bash
# AWS Documentation Server
uvx awslabs.aws-documentation-mcp-server

# AWS IaC Server
uvx awslabs.aws-iac-mcp-server

# Amazon EKS Server (requires kubectl configured)
uvx awslabs.amazon-eks-mcp-server

# Claude Desktop config example:
{
  "mcpServers": {
    "aws-docs": {
      "command": "uvx",
      "args": ["awslabs.aws-documentation-mcp-server"],
      "env": {
        "AWS_REGION": "us-east-1",
        "AWS_PROFILE": "my-profile"
      }
    }
  }
}
```

## Architecture / How It Works
Each AWS MCP server in the suite is an independent Python package (published to PyPI) that wraps the corresponding AWS SDK (boto3) or AWS CLI functionality. They run as stdio processes and use the MCP Python SDK with FastMCP. AWS authentication follows the standard boto3 credential chain: environment variables (`AWS_ACCESS_KEY_ID`, `AWS_SECRET_ACCESS_KEY`), shared credential files (`~/.aws/credentials`), IAM roles, or AWS SSO profiles. Each server exposes a focused set of MCP tools mapping to AWS API operations relevant to its service domain.

## Strengths
- Official AWS Labs endorsement and maintenance
- Comprehensive coverage across the AWS service spectrum
- Standard AWS credential chain — integrates with existing IAM setup
- Apache-2.0 license suitable for enterprise use
- Per-service granularity allows installing only what is needed

## Limitations
- Stdio transport only (SSE removed May 2025) — no remote hosted endpoint
- Must install and configure each server separately
- AWS API costs apply for operations that call AWS services
- IAM permissions must be carefully configured to limit blast radius
- No unified management interface across the server suite

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Cloudflare MCP | Cloudflare infrastructure (Workers, KV, R2, D1) |
| Terraform MCP | Infrastructure-as-Code across multiple cloud providers |
| Kubernetes MCP | K8s-native management (works with EKS) |

## References
- [GitHub Repository](https://github.com/awslabs/mcp)
- [AWS Labs on PyPI](https://pypi.org/search/?q=awslabs+mcp)
- [AWS MCP Blog Announcement](https://aws.amazon.com/blogs/machine-learning/mcp-servers-aws/)
- [MCP Documentation](https://modelcontextprotocol.io)

## Notes
Each server in the suite is published as a separate PyPI package prefixed with `awslabs.` (e.g., `awslabs.aws-documentation-mcp-server`). The mono-repo structure at `awslabs/mcp` contains all servers but they are versioned and released independently. For teams heavily invested in AWS, this suite is the standard MCP integration path and should be part of any AI-assisted AWS development workflow.
