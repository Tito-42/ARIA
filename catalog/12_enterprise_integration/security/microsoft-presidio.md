# Microsoft Presidio

> Microsoft's open source framework for PII detection and anonymization — protect sensitive data in text, images, and structured data before sending to LLMs.

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 12 - Enterprise Integration |
| **URL** | https://microsoft.github.io/presidio/ |
| **GitHub** | https://github.com/microsoft/presidio |
| **Stars** | 7 500 |
| **License** | MIT |
| **Pricing** | Open source free |
| **Last Verified** | 2026-04-02 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
Microsoft Presidio is a framework for detecting and anonymizing personally identifiable information (PII) in text, images, and structured data. It is built and maintained by Microsoft, providing enterprise credibility and long-term support guarantees.

For LLM applications, Presidio solves a critical compliance problem: user inputs and retrieved documents may contain PII (names, email addresses, credit card numbers, social security numbers, medical record numbers) that should not be sent to external LLM APIs. Presidio can be inserted as a middleware layer to detect, redact, or pseudonymize PII before the data reaches the LLM — and optionally reverse the anonymization on the response.

The framework is multi-modal: it handles raw text (Analyzer + Anonymizer), images (Image Redactor for DICOM medical images and standard formats), and structured data (JSON/tabular via the Structured component). Custom recognizers allow organizations to detect domain-specific PII like internal employee IDs, contract numbers, or IBAN numbers that standard NLP models won't recognize.

The last major release was in March 2026, confirming active maintenance.

## Key Features
- Text PII detection via NER (spaCy) + regex patterns + rule-based recognizers
- Text anonymization: replace, redact, hash, encrypt, or synthesize substitutes
- Image PII redaction for DICOM medical images and standard image formats
- Structured data anonymization for JSON and tabular (Pandas/PySpark) data
- 40+ built-in PII recognizers (names, emails, phones, SSN, credit cards, IBANs, etc.)
- Custom recognizer API for domain-specific PII
- Anonymization operators: replace, redact, hash, encrypt, mask, custom
- De-anonymization support (reverse mapping with encryption-based keys)
- REST API server for language-agnostic deployment
- Kubernetes and Docker deployment
- PySpark support for large-scale data engineering

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 5 | Microsoft backing; last release March 2026; used in enterprise production |
| **Security** | 5 | MIT license; self-hosted; Microsoft security standards; no PII leaves org |
| **Scalability** | 5 | PySpark support for big data; REST API server for horizontal scaling; K8s |
| **Support/Community** | 5 | Microsoft backing; 7.5k stars; active issue tracker; enterprise credibility |
| **Documentation** | 5 | Comprehensive Microsoft-quality docs; API reference; tutorials per entity type |
| **Integration Ease** | 4 | Python SDK straightforward; REST API for other languages; some NLP setup needed |

## Use Cases
1. LLM input sanitization — strip PII from user queries before sending to OpenAI/Anthropic APIs
2. RAG document preprocessing — anonymize documents in vector database before LLM retrieval
3. GDPR/HIPAA compliance — ensure no PII in external API calls or LLM logs
4. Medical data processing — DICOM image redaction for healthcare AI applications
5. Large-scale data anonymization — PySpark integration for anonymizing data lakes before ML training

## Getting Started
```python
pip install presidio-analyzer presidio-anonymizer
python -m spacy download en_core_web_lg

from presidio_analyzer import AnalyzerEngine
from presidio_anonymizer import AnonymizerEngine

analyzer = AnalyzerEngine()
anonymizer = AnonymizerEngine()

# Detect PII
text = "My name is John Smith, email john@example.com, SSN 123-45-6789"
results = analyzer.analyze(text=text, language="en")
# [RecognizerResult: PERSON 11-21, EMAIL_ADDRESS 29-45, US_SSN 51-62]

# Anonymize
anonymized = anonymizer.anonymize(text=text, analyzer_results=results)
print(anonymized.text)
# "My name is <PERSON>, email <EMAIL_ADDRESS>, SSN <US_SSN>"
```

## Architecture / How It Works
Presidio consists of four main components. The **Analyzer** processes text through a pipeline: language detection, NLP model execution (spaCy NER), and rule-based recognizers. Each recognizer produces `RecognizerResult` objects with entity type, position, and confidence score. The **Anonymizer** takes the results and applies configurable operators (replace with `<ENTITY_TYPE>`, redact, hash, encrypt, or custom). The **Image Redactor** uses OCR (Tesseract) to locate text in images, runs the Analyzer on detected text, and draws black boxes over PII regions. The **Structured** component applies the Analyzer/Anonymizer to JSON fields or Pandas/PySpark DataFrames column by column.

## Strengths
- Microsoft backing = enterprise credibility and long-term support
- Multi-modal: text + images (DICOM) + structured data (PySpark) in one framework
- Custom recognizer API for domain-specific PII detection
- REST API server enables polyglot integration
- De-anonymization support with encryption for round-trip use cases
- Active maintenance (March 2026 release)

## Limitations
- NLP model accuracy depends on spaCy model quality — false positives and misses occur
- Language support varies by entity type (strongest for English)
- Performance overhead at scale — NER inference adds latency per document
- Image redaction requires Tesseract OCR — separate dependency
- Threshold tuning required per use case (precision vs. recall trade-off)

## Alternatives
| Tool | Key Difference |
|------|---------------|
| AWS Comprehend (Detect PII Entities) | Managed cloud service; easier setup; AWS lock-in |
| Azure Text Analytics (PII detection) | Microsoft managed; less customizable |
| Guardrails AI | Broader input validation (not just PII); more LLM-specific |
| LLM Guard | Purpose-built LLM security; includes injection detection |

## References
- https://microsoft.github.io/presidio/
- https://github.com/microsoft/presidio
- https://microsoft.github.io/presidio/analyzer/adding_recognizers/

## Notes
Presidio is the reference choice for PII detection and anonymization in enterprise LLM pipelines. The Microsoft backing and MIT license remove procurement and legal friction. For organizations processing medical data (HIPAA), the DICOM image redaction capability is unique in open source. Presidio works best as part of a pipeline: integrate it as a preprocessing step in RAG ingestion and as a request middleware before LLM API calls. Combine with Langfuse or Opik to verify anonymization coverage in traces.
