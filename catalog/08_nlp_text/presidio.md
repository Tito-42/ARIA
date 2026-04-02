# Presidio (Microsoft)

> Détection et anonymisation de PII (données personnelles) — enterprise-grade, extensible, multi-langue.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 08 - NLP & Text / Privacy & PII |
| **URL** | https://microsoft.github.io/presidio |
| **GitHub** | https://github.com/microsoft/presidio |
| **Stars** | ~7,500 |
| **License** | MIT |
| **Pricing** | Free (Open Source) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Enterprise |

## What It Does
Presidio est une solution enterprise de Microsoft pour la détection et l'anonymisation de données personnelles (PII) dans du texte et des images. Il détecte les noms, emails, numéros de téléphone, numéros de carte de crédit, SSN, et bien d'autres, puis les anonymise par masquage, remplacement ou chiffrement.

## Key Features
- **PII detection**: 30+ types d'entités (noms, emails, CC, SSN, etc.)
- **Anonymization**: Masquage, remplacement, hash, chiffrement
- **Multi-engine**: Regex, NER (spaCy, HF), custom recognizers
- **Multi-langue**: Support multilingue via les modèles NER
- **Image PII**: Détection de PII dans les images (OCR + PII)
- **Azure integration**: Intégration native Azure AI

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | Enterprise-grade, Microsoft backed |
| **Security** | 5 | MIT, conçu pour la privacy |
| **Scalability** | 4 | API REST, batch processing |
| **Support/Community** | 4 | 7.5k stars, Microsoft backing |
| **Documentation** | 5 | Docs complètes, samples Azure |
| **Integration Ease** | 4 | Python API + REST API |

## Use Cases
1. **GDPR compliance** — Anonymiser les PII pour la conformité GDPR
2. **Data sanitization** — Nettoyer les données avant le training ML
3. **RAG safety** — Anonymiser les documents avant ingestion RAG

## Getting Started
```python
from presidio_analyzer import AnalyzerEngine
from presidio_anonymizer import AnonymizerEngine

analyzer = AnalyzerEngine()
results = analyzer.analyze(text="My name is John and my email is john@example.com", language="en")

anonymizer = AnonymizerEngine()
anonymized = anonymizer.anonymize(text="My name is John and my email is john@example.com", analyzer_results=results)
print(anonymized.text)
# My name is <PERSON> and my email is <EMAIL_ADDRESS>
```

## Architecture / How It Works
Presidio Analyzer utilise un registry de recognizers (regex, NER models, custom). Chaque recognizer détecte un type d'entité. Les résultats sont fusionnés et dédupliqués. L'Anonymizer prend ces résultats et applique les opérations d'anonymisation configurées.

## Strengths
- Enterprise-grade, Microsoft backed
- Extensible avec custom recognizers
- MIT licence
- Image PII support

## Limitations
- Configuration initiale peut être complexe
- Faux positifs possibles (tuning nécessaire)
- Moins de langues que des solutions spécialisées

## Alternatives
| Tool | Key Difference |
|------|---------------|
| AWS Comprehend PII | AWS managed, payant |
| Google DLP | GCP managed, payant |
| piilo | Plus léger, moins complet |

## References
- https://microsoft.github.io/presidio
- https://github.com/microsoft/presidio

## Notes
Presidio v2.2.362 (mars 2026). Le choix par défaut pour la détection PII en enterprise. Essentiel pour la conformité GDPR et pour sécuriser les pipelines RAG/ML.
