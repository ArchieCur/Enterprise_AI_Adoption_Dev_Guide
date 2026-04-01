# Data Engineer
## Enterprise Role Playbook for AI Developers

---

### Who This Person Is
The Data Engineer builds and maintains the infrastructure
that makes data usable. They are the person who turns raw,
messy, inconsistently formatted data from a dozen source
systems into clean, reliable, pipeline-ready datasets that
Data Scientists can model and Data Analysts can query. They
are not glamorous in the enterprise AI narrative. They are
load-bearing.

They think in pipelines, schemas, throughput, latency,
and data quality. They are intimately familiar with the
gap between how data is described in documentation and
how it actually arrives — null values where there should
be values, timestamps in three different formats, fields
that mean different things in different source systems,
and the undocumented join key that Jim in operations
figured out three years ago and never wrote down. They
have seen every flavor of data quality problem and have
strong opinions about how to prevent them.

AI systems have made the Data Engineer's work more
consequential and more complex simultaneously. A machine
learning model is only as good as the data it was trained
on. A RAG system retrieves from the index it was given.
An AI workflow runs on the data pipeline that feeds it.
The Data Engineer controls all of these upstream of the
model — which means that problems introduced in the
pipeline appear as model problems to everyone downstream,
and the Data Engineer is rarely the first person called
when the model misbehaves.

Build with the Data Engineer before you build the model.
The pipeline is not infrastructure for the AI system.
It is the foundation the AI system stands on.

---

### What They Care About
- Pipeline reliability — data that arrives late, arrives
  corrupted, or doesn't arrive at all breaks everything
  downstream; reliability is not a nice-to-have, it is
  the job
- Data quality — schema consistency, null handling,
  deduplication, and referential integrity are the
  difference between a model trained on reality and
  one trained on artifacts
- Lineage — where did this data come from, what
  transformations were applied to it, and where does
  it go? lineage is auditability for data pipelines
- Scalability — a pipeline that works at development
  data volumes needs to work at production data volumes
  without being rebuilt
- Maintainability — pipelines that only their original
  author can modify are operational liabilities; the
  Data Engineer builds for the colleague who inherits
  the system, not just for the current sprint

---

### What They're Afraid Of
- Silent data quality failures — a pipeline that
  produces wrong data without raising an error is
  worse than a pipeline that fails loudly; bad data
  that looks like good data trains bad models that
  look like good models
- Schema changes in source systems that break
  downstream pipelines without warning — this is
  the Data Engineer's most common operational
  nightmare and the one they have the least control over
- Being handed AI feature requirements after the
  pipeline architecture is finalized — features
  that require point-in-time correctness, time-series
  joins, or low-latency serving have pipeline
  implications that cannot be retrofitted cheaply
- Data used for AI training that violates privacy
  or governance requirements they weren't told about —
  the Data Engineer who built the pipeline becomes
  part of the compliance problem
- A RAG system with a retrieval index built on
  stale, unvalidated, or ungoverned content —
  garbage in, confident garbage out

---

### What "Good" Looks Like for Them
- AI feature requirements defined before pipeline
  architecture is finalized — not after
- Data quality checks built into the pipeline that
  fail loudly on bad data rather than passing it
  downstream silently
- Schema documentation that is accurate, versioned,
  and maintained — not a wiki page that was last
  updated eighteen months ago
- A lineage system that can answer "where did this
  training dataset come from" in minutes, not days
- A seat at the table when AI system architecture
  is designed — not a ticket in the backlog after
  the architecture decisions have already been made

---

### Governance & Compliance Considerations

#### AI Feature Pipelines Have Different Requirements Than Analytics Pipelines
A pipeline built for analytics — where a query runs
on historical data and the result is a dashboard —
has fundamentally different requirements than a pipeline
built to serve AI features. AI feature pipelines need
point-in-time correctness (the feature value as it
existed at the time of the event, not as it exists now),
low-latency serving for real-time inference, and
consistency guarantees between training and serving.
A developer who hands the Data Engineer analytics
pipeline requirements and expects AI feature pipeline
outputs will get a system with training-serving skew —
one of the most common and most difficult to diagnose
production ML problems.

#### Data Lineage is a Compliance Artifact
In regulated industries and under AI governance
frameworks, the lineage of training data is a compliance
requirement, not just an operational convenience.
Regulators, auditors, and legal counsel may need to
know exactly what data a model was trained on, where
that data came from, and what transformations were
applied. Build lineage tracking into the pipeline
architecture from the start. A lineage system
retrofitted after the model is deployed is incomplete
by definition — it can only document what happened
after it was built.

#### Privacy Requirements Apply to Pipeline Data, Not Just Source Data
Personal data that enters a pipeline retains its
privacy obligations through every transformation.
Anonymization, pseudonymization, and aggregation
all have specific technical requirements that may
not be met by naive implementations. A field that
looks anonymized may still be re-identifiable in
combination with other fields. Work with the Privacy
Manager to validate that privacy-preserving
transformations in the pipeline actually meet the
required standard before training data is produced.

#### Retrieval Index Governance is an Emerging Requirement
RAG systems retrieve from indexes built on enterprise
content — documents, emails, knowledge bases, database
records. The governance requirements for what goes
into a retrieval index are still being established
in most enterprises, but the questions are clear:
Who authorized this content for AI retrieval? How
is stale or outdated content removed? How is sensitive
content excluded? How is the index updated when
source content changes? These are Data Engineer
problems with compliance implications. Build index
governance into the retrieval architecture, not as
an afterthought.

#### Data Retention Policies Affect Training Data Availability
Enterprise data retention policies determine how long
data is kept and when it must be deleted. Training
datasets derived from operational data inherit these
obligations — a model trained on data that has since
been deleted under retention policy may not be
retrainable on the same data, and the training
dataset itself may need to be deleted. Understand
the retention implications for your training data
before you build the pipeline that produces it.

---

### Model Selection Guidance

**Recommended tier: Small to Medium**

- The Data Engineer's primary AI use cases are
  productivity and operational support, not the
  models they build pipelines for
- Small for structured, high-volume data engineering
  tasks: schema documentation generation from
  structured metadata, data quality rule generation
  from examples, pipeline status reporting,
  SQL query formatting and documentation
- Medium for pipeline design support, data quality
  analysis, lineage documentation, and technical
  specification drafting where judgment and context
  are required

**Model mapping:**
- Small — schema documentation, data quality rule
  templates, SQL formatting and commenting, pipeline
  status summaries, structured metadata generation
- Medium — pipeline architecture documentation,
  data quality root cause analysis, lineage
  documentation, technical specification drafting,
  feature engineering design support

**Critical:** Data Engineers often work with sensitive
data at the pipeline level. Any AI tool used in data
engineering workflows needs to be evaluated for data
handling — does it log query contents? does it retain
schema information? does it send data to external
services? Apply the same data governance scrutiny
to the AI tools the Data Engineer uses as to the
pipelines they build.

---

### The One Thing Developers Get Wrong
They treat the data pipeline as a solved problem
before the AI requirements are defined.

The pipeline exists. It produces data. The AI system
needs data. This seems like a connection problem —
plug the AI system into the existing pipeline and
proceed. It is not a connection problem. It is a
requirements problem.

AI systems have data requirements that existing
analytics pipelines were not designed to meet:
point-in-time correctness, feature consistency
between training and serving, low-latency retrieval,
lineage at the feature level, and data quality
guarantees that fail loudly rather than passing
bad data downstream silently.

Retrofitting these requirements onto an existing
pipeline is expensive, time-consuming, and often
incomplete. The training-serving skew that results
from using an analytics pipeline to serve AI features
is one of the most common sources of production
ML system degradation — and one of the hardest to
diagnose because it looks like a model problem,
not a pipeline problem.

Bring the Data Engineer in before the AI system
architecture is designed. Define the feature
requirements before the pipeline architecture
is finalized. The conversation that happens at
the whiteboard costs an afternoon. The conversation
that happens after six months of debugging a
production system costs much more.

---

### Fill-in-the-Blank Workflow Starter
```
SYSTEM:
You are a data engineering assistant supporting
[TEAM NAME] at [COMPANY NAME].

Your purpose is to [PRIMARY TASK — e.g., "support
pipeline documentation, data quality rule generation,
and schema documentation for the [PIPELINE NAME]
data infrastructure"].

Always:
- Apply [DOCUMENTATION STANDARD — e.g., "the team's
  data dictionary template with source, transformation,
  data type, nullable, and lineage fields"] to all
  schema and pipeline documentation outputs
- Flag any data quality concern involving
  [HIGH-RISK PATTERNS — e.g., "null rates above 5%
  in required fields, schema drift from expected
  types, or join key inconsistencies"] for Data
  Engineer review
- Include lineage information — source system,
  transformation applied, destination — in all
  pipeline documentation outputs
- Apply [DATA CLASSIFICATION STANDARD — e.g.,
  "the enterprise data classification policy;
  flag any PII, financial, or regulated data
  fields for Privacy Manager review"]
- Reference [VERSION CONTROL STANDARD — e.g.,
  "all pipeline code and configuration in
  [REPO PATH]; documentation versioned to
  match pipeline version"]

Never:
- Generate or modify pipeline code for
  [RESTRICTED ENVIRONMENTS — e.g., "production
  pipelines"] without [REVIEW REQUIREMENT —
  e.g., "Data Engineer review and change
  management approval"]
- Access [RESTRICTED DATA — e.g., "raw PII
  fields, financial records, or regulated
  datasets"] outside of approved anonymized
  or pseudonymized exports
- Document a data source as compliant with
  [GOVERNANCE STANDARD] without [VALIDATION
  REQUIREMENT — e.g., "Privacy Manager or
  Data Governance sign-off"]
- Produce training dataset documentation without
  [REQUIRED FIELDS — e.g., "consent basis,
  retention limit, known quality issues,
  and lineage to source systems"]

When a pipeline requirement conflicts with
data governance policy:
Stop. Document the conflict. Route to
[DATA GOVERNANCE CONTACT] before proceeding.
Do not implement a workaround without documented
approval.

Output format: [DATA ENGINEERING TEAM'S PREFERRED
FORMAT — e.g., "pipeline component name, source,
transformation logic summary, output schema,
data quality checks, lineage, owner, last validated"]
```

---

### Adjacent Roles to Consider
When building for Data Engineers, also read:
- **Data Scientist** — the Data Engineer builds
  the pipelines the Data Scientist depends on;
  feature requirements need to flow from Data
  Scientist to Data Engineer before pipeline
  architecture is finalized, not after
- **IT Administrator** — data infrastructure
  runs on enterprise IT; storage, networking,
  access controls, and approved tooling are
  IT Administrator decisions that constrain
  what the Data Engineer can build
- **Privacy Manager** — data pipelines that
  process personal data operate under privacy
  obligations that the Data Engineer implements
  but the Privacy Manager defines; this is
  a required early collaboration, not a
  late-stage review
- **DevOps Engineer** — production data pipelines
  need the same deployment, monitoring, and
  incident response infrastructure as application
  code; Data Engineer and DevOps Engineer need
  aligned practices for pipeline operations

---

*Enterprise Role Playbook for AI Developers | Data Engineer v0.1 |
ArchieCur + Sonnet + Claude Code | MIT License | 2026*
