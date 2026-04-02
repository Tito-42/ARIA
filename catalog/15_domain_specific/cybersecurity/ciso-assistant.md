# CISO Assistant

> Open-source GRC platform supporting 130+ security frameworks for enterprise cybersecurity governance

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 15_domain_specific / cybersecurity |
| **URL** | https://intuitem.com/ciso-assistant |
| **GitHub** | https://github.com/intuitem/ciso-assistant-community |
| **Stars** | ~3,900 |
| **License** | AGPL-3.0 (community) / Commercial (enterprise) |
| **Pricing** | Free (community) / Paid (enterprise features) |
| **Last Verified** | 2026-04-02 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
CISO Assistant is a comprehensive open-source GRC (Governance, Risk, and Compliance) platform that provides enterprises with a structured approach to managing cybersecurity risk and regulatory compliance. It is an open-source alternative to expensive commercial GRC platforms like ServiceNow GRC, RSA Archer, and OneTrust, delivering comparable functionality for organizations that cannot or will not pay enterprise licensing fees.

The platform's most distinctive capability is its support for 130+ security frameworks simultaneously, including ISO 27001/27002, NIST CSF 2.0, SOC 2, PCI DSS, GDPR, HIPAA, NIS2, DORA, and dozens more. More importantly, it automatically maps controls between frameworks, so when a control is implemented for ISO 27001, CISO Assistant identifies which equivalent controls in NIST CSF, SOC 2, or GDPR are also satisfied — eliminating redundant compliance work across multiple standards.

This cross-framework mapping capability is particularly valuable for European enterprises that must simultaneously comply with GDPR, NIS2, DORA (financial sector), and potentially ISO 27001 for certification purposes.

## Key Features
- 130+ supported frameworks: ISO 27001/27002, NIST CSF 2.0, SOC 2, PCI DSS, GDPR, HIPAA, NIS2, DORA, CIS Controls, MITRE ATT&CK, and more
- Automatic cross-framework control mapping (implement once, satisfy multiple standards)
- Risk assessment and risk register with heat maps
- Security control tracking and implementation evidence management
- Compliance reporting and audit preparation
- Threat library integration for context-aware risk assessment
- Multi-organization and multi-auditor support
- REST API for integration with other security tools

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Production-grade; used by enterprises; stable release history |
| **Security** | 4 | AGPL; full code audit possible; handles sensitive compliance data |
| **Scalability** | 4 | Multi-organization; REST API for integration; manages large control sets |
| **Support/Community** | 4 | Intuitem corporate backing; 3.9k stars; active enterprise community |
| **Documentation** | 4 | Comprehensive docs; framework guides; API documentation |
| **Integration Ease** | 3 | Docker deployment; REST API; some configuration effort required |

## Use Cases
1. **ISO 27001 certification preparation**: Tracking implementation of all 93 Annex A controls, managing evidence, and preparing for certification audit with gap analysis
2. **NIS2 compliance for European organizations**: Meeting the NIS2 Directive requirements for network and information systems security with built-in NIS2 framework support
3. **Multi-framework compliance efficiency**: Leveraging cross-framework mapping to demonstrate GDPR + ISO 27001 + NIS2 compliance without tripling the compliance workload
4. **Vendor risk management**: Using the platform to track third-party vendor compliance posture as part of supply chain security programs

## Getting Started
```bash
# Docker deployment (recommended)
git clone https://github.com/intuitem/ciso-assistant-community
cd ciso-assistant-community

# Configure environment
cp .env.example .env
# Edit .env with your database and SMTP settings

docker-compose up -d

# Access at http://localhost:8080
# Default admin: admin@example.com / changeme
```

## Architecture / How It Works
CISO Assistant uses a Django backend with a PostgreSQL database and a modern JavaScript frontend. The framework library contains machine-readable definitions of 130+ security standards with their control requirements and mappings between equivalent controls across frameworks. When a user assesses compliance against ISO 27001, the system identifies which SOC 2, NIST, and GDPR controls are addressed by the same implementation — this mapping is maintained by the community and Intuitem's security experts. Risk assessments use a configurable risk matrix with likelihood and impact scoring, linked to threat scenarios from built-in threat libraries.

## Strengths
- 130+ frameworks is unmatched in open-source GRC tools
- Cross-framework control mapping eliminates the biggest inefficiency in multi-standard compliance
- AGPL allows full audit of a tool that will hold sensitive compliance data
- Active maintenance with NIS2/DORA support (critical for European organizations)
- Alternative to $100k+/year commercial GRC platforms

## Limitations
- AGPL license may be restrictive for GRC tool vendors building on top of CISO Assistant
- Some advanced enterprise features (SSO, advanced reporting) require commercial license
- AI-powered analysis is limited; primarily a tracking and documentation tool
- Last commit noted as January 2025 — verify current activity level
- Implementation requires security governance expertise to use effectively

## Alternatives
| Tool | Key Difference |
|------|---------------|
| ServiceNow GRC | Enterprise-grade; vastly more expensive; commercial only |
| OneTrust | Privacy-focused; commercial; better UI but very expensive |
| OpenRMF | NIST/DISA-focused; good for US federal compliance |
| Eramba | Open-source GRC; smaller framework coverage than CISO Assistant |

## References
- https://intuitem.com/ciso-assistant
- https://github.com/intuitem/ciso-assistant-community
- https://docs.ciso-assistant.com/
- NIS2 Directive: https://nis2directive.eu/
- ISO 27001:2022: https://www.iso.org/standard/82875.html

## Notes
CISO Assistant is the most mature open-source GRC platform available and an excellent choice for organizations that need to demonstrate compliance with multiple frameworks simultaneously. The NIS2 support makes it particularly relevant for European enterprises facing the October 2024 NIS2 implementation deadline. For organizations with specialized needs (FedRAMP, CMMC for US defense), verify coverage before committing — US government frameworks may have less complete coverage than EU standards.
