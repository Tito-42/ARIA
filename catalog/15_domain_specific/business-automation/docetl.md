# DocETL

> Agentic document ETL system with semantic intelligence for complex unstructured document pipelines

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 15_domain_specific / business-automation |
| **URL** | https://docetl.org |
| **GitHub** | https://github.com/ucbepic/docetl |
| **Stars** | ~3,700 |
| **License** | {TODO} (check GitHub for license details) |
| **Pricing** | Free / Open Source |
| **Last Verified** | 2026-04-02 |
| **Status** | Active |
| **Maturity** | Beta |

## What It Does
DocETL is a UC Berkeley research project that brings ETL (Extract, Transform, Load) pipeline concepts to complex document processing with LLM intelligence. Where traditional ETL tools process structured data deterministically, DocETL handles unstructured documents that require semantic understanding: research papers, legal documents, medical records, reports, and other complex text corpora.

The system provides a YAML-defined pipeline syntax where each step uses LLM operations (map, reduce, filter, resolve, gleaning) to transform documents semantically. The "gleaning" operator is particularly innovative: it iteratively refines LLM outputs through repeated self-review until the extraction quality meets a defined standard, addressing the inconsistency problem in single-pass LLM extraction.

DocWrangler, the companion UI, enables prompt engineers to visually inspect pipeline outputs at each stage and iterate on prompts with real-time feedback — critical for complex document workflows where prompt quality directly determines pipeline accuracy.

## Key Features
- YAML-defined semantic ETL pipelines for document processing
- LLM operators: map (transform), reduce (aggregate), filter (select), resolve (deduplicate), split (chunk)
- Gleaning operator: iterative LLM self-review for quality improvement
- DocWrangler UI: visual pipeline inspection and prompt engineering
- Multi-LLM support: OpenAI GPT-4o-mini, AWS Bedrock, and multi-LLM via LiteLLM
- Parallel processing of large document collections
- Output to JSON, CSV, or structured databases
- UC Berkeley EPIC Lab backing for research credibility

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 3 | Beta/Research; UC Berkeley project; 3.7k stars; production use cases documented |
| **Security** | 3 | Documents sent to configured LLM API; Bedrock for AWS-contained processing |
| **Scalability** | 4 | Parallel pipeline execution; handles large document corpora |
| **Support/Community** | 3 | UC Berkeley team; 3.7k stars; research community focus |
| **Documentation** | 4 | Good docs; DocWrangler guide; example pipelines for common tasks |
| **Integration Ease** | 3 | YAML config; Python API; requires ML and pipeline expertise |

## What It Automates
DocETL automates **80%** of complex document processing workflows. Document analysis pipelines that previously required custom NLP code for each document type are replaced by YAML-defined semantic pipelines. The remaining 20% involves documents requiring specialized domain knowledge, complex cross-document reasoning, or quality thresholds too high for current LLM capabilities.

## Use Cases
1. **Medical literature analysis**: Processing hundreds of clinical trial papers to extract structured data (patient populations, interventions, outcomes) for systematic reviews
2. **Legal contract portfolio analysis**: Running a pipeline that extracts key clauses from thousands of contracts, deduplicates similar provisions, and generates portfolio-level statistics
3. **Research synthesis**: Building academic literature review pipelines that extract findings, categorize by methodology, and synthesize conclusions across paper collections
4. **Regulatory compliance screening**: Processing policy documents and regulations to extract requirements, map to existing controls, and identify compliance gaps

## Getting Started
```bash
pip install docetl

# Define a pipeline in YAML
cat > pipeline.yaml << 'EOF'
datasets:
  papers:
    type: file
    source: ./research_papers/*.pdf

pipeline:
  steps:
    - name: extract_findings
      input: papers
      type: map
      prompt: |
        Extract the main finding, methodology, and sample size
        from this research paper excerpt.
      output:
        schema:
          main_finding: string
          methodology: string
          sample_size: integer

    - name: aggregate_findings
      input: extract_findings
      type: reduce
      reduce_key: methodology
      prompt: |
        Summarize the findings across these papers using
        the same methodology.

output:
  type: file
  path: ./synthesis_report.json
EOF

# Run the pipeline
docetl run pipeline.yaml
```

## Architecture / How It Works
DocETL processes documents through a directed acyclic graph (DAG) of operators defined in YAML. Each operator applies an LLM transformation to the documents in the current stage. The map operator applies a prompt to each document independently; reduce aggregates multiple documents based on a key; filter removes documents not matching criteria; resolve identifies and merges duplicate entities across documents; gleaning runs the map operation repeatedly until the output passes a quality check. DocWrangler provides a side-by-side view of inputs, outputs, and intermediate stages for debugging. LiteLLM abstraction enables using any LLM backend in the pipeline.

## Strengths
- YAML-first approach makes pipelines reproducible and version-controllable
- Gleaning operator addresses LLM inconsistency systematically
- DocWrangler UI enables non-engineers to debug and iterate on pipelines
- UC Berkeley EPIC Lab provides academic rigor and research credibility
- Handles complex multi-step reasoning that single-pass extraction cannot do

## Limitations
- Beta status; API may change between versions
- License not clearly specified (verify before commercial use)
- Processing large document corpora generates significant LLM API costs
- Complex pipelines require pipeline design expertise
- Less polished than commercial document intelligence platforms

## Alternatives
| Tool | Key Difference |
|------|---------------|
| Unstract | More user-friendly; Prompt Studio; better for non-technical users |
| ExtractThinker | ORM-style API; simpler but less pipeline flexibility |
| Apache Airflow + LangChain | More mature orchestration; requires more custom code |
| Unstructured.io | Document preprocessing; complements DocETL rather than competing |

## References
- https://docetl.org
- https://github.com/ucbepic/docetl
- https://docetl.org/docs (DocWrangler and pipeline docs)
- UC Berkeley EPIC Lab: https://epic.cs.berkeley.edu/

## Notes
DocETL is the most sophisticated open-source tool for complex multi-step document analysis pipelines. Its gleaning operator is a genuinely innovative contribution to LLM document processing. For simpler extraction tasks (invoice processing, form field extraction), Unstract is more accessible. DocETL shines for research-grade document analysis where pipeline reproducibility and semantic accuracy are paramount. Verify the license before enterprise deployment.
