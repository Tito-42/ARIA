# Agent2Agent (A2A) Protocol

> Open protocol for agent-to-agent communication and interoperability, governed by the Linux Foundation and contributed by Google.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 02 - AI Agents |
| **URL** | https://a2aprotocol.ai |
| **GitHub** | https://github.com/google-a2a/A2A |
| **Stars** | 22,900 |
| **License** | Apache 2.0 |
| **Pricing** | Free (open standard) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production (v1.0.0 released March 2026) |

## What It Does
The Agent2Agent (A2A) Protocol is an open standard for enabling AI agents built on different frameworks to communicate and collaborate while preserving their internal opacity. Contributed by Google and governed by the Linux Foundation, A2A defines how agents discover each other's capabilities, negotiate interaction modalities, and collaborate on tasks -- all without exposing internal state, memory, or tools.

A2A is to AI agents what HTTP is to web applications: a common protocol that enables interoperability regardless of implementation. With SDKs for Python, Go, JavaScript, Java, and .NET, it supports the broadest range of programming environments.

## Key Features
- **Agent discovery**: "Agent Cards" describe capabilities and connection details
- **JSON-RPC 2.0**: Communication over HTTP(S) with standard protocol
- **Multiple modes**: Synchronous request/response, streaming (SSE), and async push notifications
- **Rich data exchange**: Text, files, and structured JSON
- **Framework-agnostic**: Works with any agent framework
- **Multi-language SDKs**: Python, Go, JavaScript, Java, .NET
- **Linux Foundation governance**: Open, vendor-neutral standard
- **v1.0.0**: Stable release as of March 2026

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | v1.0.0; backed by Google and Linux Foundation |
| **Security** | 4 | HTTPS; opaque agent internals; enterprise-grade |
| **Scalability** | 5 | Protocol-level; scales independently |
| **Support/Community** | 5 | Google + Linux Foundation; 22.9K stars; multi-language SDKs |
| **Documentation** | 4 | Good spec docs; sample implementations |
| **Integration Ease** | 4 | SDK-based; requires protocol implementation |

## Use Cases
1. **Cross-organization agent collaboration** - Agents from different vendors working together
2. **Agent marketplaces** - Discoverable, composable agent services
3. **Enterprise integration** - Connecting agent teams across departments
4. **Multi-framework ecosystems** - Agents built with different frameworks communicating

## Strengths
- Open standard with strong governance (Linux Foundation)
- Google backing ensures long-term viability
- Multi-language SDK support is comprehensive
- Addresses a fundamental interoperability gap
- v1.0.0 signals stability

## Limitations
- Adoption is still early; not all frameworks support A2A natively
- Protocol overhead for simple agent interactions
- Requires both sides to implement the protocol
- Competing with MCP for mind-share in agent communication

## References
- https://a2aprotocol.ai
- https://github.com/google-a2a/A2A
- https://blog.google/technology/ai/agent-to-agent-protocol/

## Notes
A2A and MCP are complementary protocols: MCP standardizes how agents access tools, while A2A standardizes how agents communicate with each other. For enterprise agent ecosystems, both protocols will likely be necessary. A2A's Linux Foundation governance and v1.0.0 release make it the leading standard for agent interoperability.
