# Appendix A: Unified Logging Architecture
## for Enterprise AI Systems

### Enterprise Role Playbook for AI Developers

---

## Why This Appendix Exists

Every enterprise AI system has multiple stakeholders
who need something from the logs — and they all
need something different. The DevOps Engineer needs
operational metrics. The Security Engineer needs
threat signals. The Privacy Manager needs data
subject records. The Auditor needs tamper-evident
evidence. The IT Administrator needs access control
records. The Data Scientist needs experiment
provenance. The Data Engineer needs pipeline
lineage. The Support Engineer needs diagnostic
context. The SecOps Analyst needs behavioral
baseline signals.

Nine stakeholders. One logging architecture.

The developer who designs nine separate logging
systems will build something that satisfies no one
completely and creates maintenance overhead that
compounds with every system update. The developer
who designs one unified schema — with outputs
routed to the right consumer at the right retention
level — builds something that scales, satisfies
audit requirements, and doesn't require heroic
effort when a new stakeholder requirement emerges.

This appendix provides that schema. It is a
starting point, not a final specification. Every
deployment will have constraints that require
adaptation. Design for the nine stakeholders
below and you will have addressed the most
common logging requirements for enterprise
AI systems. Add stakeholders as your deployment
requires. Never remove the "what never gets
logged" constraints — those are compliance
floors, not preferences.

---

## The Nine-Stakeholder Logging Schema

| Stakeholder | Primary Logging Requirement | Key Fields | Retention and Access |
| :--- | :--- | :--- | :--- |
| **DevOps Engineer** | Operational metrics, output drift detection, token consumption, system performance | Request timestamp, response time, token count (input/output), model version, endpoint, success/failure flag, error type if applicable, output quality signal if monitored | Operational retention period (typically 30–90 days); access: DevOps and SRE teams |
| **Security Engineer** | Injection attempts, anomalous outputs, tool calls, trust boundary events | Input hash, output hash, prompt classification (injection indicator flag), tool calls made (name, parameters, result), trust boundary crossing events, model version, session ID | Security retention period (typically 90–365 days); access: Security Engineer and SecOps; privileged access only |
| **Privacy Manager** | Data subject records, processing purpose documentation, retention limit compliance, consent basis | Data subject identifier (pseudonymized), processing purpose, consent basis, data categories present in input, retention expiry flag, deletion confirmation events | Privacy retention period per applicable regulation (GDPR: typically erasure on request; CCPA: per policy); access: Privacy Manager and Legal only |
| **Auditor** | Tamper-evident records, human decision events, AI output separation, accountability chain | Interaction ID (immutable), AI output flag (AI-generated vs. human-authored), human review event (reviewer ID, timestamp, decision), change history, model version at time of output, output hash | Audit retention period (typically 7 years for regulated industries); access: Auditor and Legal; read-only, tamper-evident storage required |
| **IT Administrator** | Access control records, data flow documentation, log retention classification, infrastructure events | User ID, role, access level, data classification of inputs accessed, infrastructure events (provisioning, deprovisioning, configuration changes), log retention tier assigned | Per data classification policy; access: IT Administrator and Security; privileged access controls required |
| **Data Scientist** | Experiment provenance logs — the audit trail for how a model was built, what data it was built on, and what methodology was applied | Experiment ID, hypothesis, dataset name and version, feature set version, methodology, evaluation metrics, model version, limitations noted, peer review status, deployment decision and rationale | ML provenance retention (retain for model lifetime plus regulatory hold period); access: Data Science team and Model Governance |
| **Data Engineer** | Pipeline lineage logs — the audit trail for how data moved from source to feature, including quality checks and schema versions | Pipeline run ID, source system, transformation applied, destination, data quality check results, schema version, run timestamp, failure events and resolution, SLA compliance flag | Pipeline retention (typically 90 days operational; longer for regulated data lineage requirements); access: Data Engineering and Data Governance |
| **Support Engineer** | Diagnostic interaction logs — sufficient context to diagnose a specific user-reported failure without requiring exact reproduction of the original input | User input summary (not raw input — see constraints below; the summary should capture the user's intent and topic category without retaining verbatim phrasing, named entities, or any content that would allow the original input to be reconstructed), system prompt version, retrieved context summary (RAG systems), model output, model version, user action taken post-output, ticket ID if escalated, failure classification if assigned | Support diagnostic retention (typically 30–90 days; adjust for incident investigation requirements); access: Support Engineering; PII fields restricted to authorized investigators |
| **SecOps Analyst** | Behavioral baseline logs — aggregate pattern detection, anomaly flagging, AI-specific attack surface monitoring | Session ID, input classification (injection indicator flag — system-specific detection criteria, see Appendix B; anomaly flag), output classification (exfiltration indicator, anomaly flag), tool calls (name, authorization status), API call volume and pattern, model version, alert generated (Y/N, severity), analyst review flag | Security behavioral retention (typically 90–365 days); access: SecOps Analyst and Security Engineer; privileged access; cross-reference with Security Engineer logs required |

---

## ⚠ What Never Gets Logged — Applies to All Stakeholders

These categories must be excluded from all logging
fields across all nine stakeholders. No operational,
diagnostic, security, or compliance requirement
justifies logging these fields. Including them
creates new compliance exposure that is more
costly than any diagnostic benefit they provide.

**Raw PII in log fields.**
User names, email addresses, account numbers,
government identifiers, health information, and
any other directly identifying personal data
must not appear in log fields. Where user identity
is required for audit or support purposes, use
pseudonymized identifiers with a separate, access-
controlled mapping table. Logging raw PII creates
a data retention obligation, a breach notification
surface, and a regulatory exposure that persists
for the full log retention period.

**Authentication tokens, API keys, and credentials.**
System prompts, tool call parameters, and retrieved
context frequently contain authentication material.
Log hashes, not values. A credential that appears
in a log is a credential that will eventually be
exposed through log access, log export, or log
breach. No exception.

**Full prompt contents containing user data.**
The full text of a user's input — especially in
enterprise deployments where users query against
business-sensitive data — must not be logged in
full. Log input hashes for integrity verification,
input classification flags for security monitoring,
and input summaries for support diagnostics. The
full prompt is a data processing event, not a
logging artifact.

**Privileged communications and legal hold material.**
Inputs from Legal, in-house counsel, or any user
operating under privilege must not be logged in
any form that could compromise that privilege.
Work with Legal to establish privilege-aware
logging controls before deployment in environments
where Legal is a user population.

**Model provider internal identifiers and system metadata.**
Vendor-specific internal identifiers, routing
metadata, and system-level fields that are not
necessary for your organization's logging purposes
create unnecessary vendor dependency in your
compliance records. Log what you need. Do not
log what the vendor happens to include in the
response payload.

---

## Schema Design Principles

**One event, multiple outputs.**
A single interaction event should generate one
log entry that is then routed to the appropriate
consumers by field and retention tier. Do not
build nine separate logging calls — build one
structured event with fields tagged by consumer
and retention requirement. This is the architecture
that scales.

**Retention tiers, not retention periods.**
Different fields within the same log entry may
have different retention requirements. An Auditor
needs the interaction ID and output hash for
seven years. The Support Engineer needs the
input summary for ninety days. Design the schema
with retention tiers attached to fields, not
to log entries. Deleting the whole entry to
satisfy the Support Engineer's ninety-day window
while the Auditor still needs the record is a
compliance gap that surfaces at the worst moment.

**Immutable audit fields.**
The fields required by the Auditor — interaction
ID, output hash, human review events, change
history — must be written to tamper-evident
storage. These are not operational logs. They
are legal records. Treat them accordingly from
day one. Retrofitting tamper-evident storage
to an operational logging system is expensive
and often incomplete.

**Model version is a required field for every entry.**
Every log entry, regardless of stakeholder
consumer, must include the model version at
the time of the interaction. This is the single
field most commonly missing from enterprise AI
logging schemas and the single field most commonly
needed when diagnosing behavior changes, responding
to regulatory inquiries, and reconstructing
incident timelines. Log it. Always.

**Access controls are part of the schema.**
The logging schema is not complete without the
access control specification for each field and
retention tier. A Privacy Manager's data subject
records in the same accessible log store as
DevOps operational metrics is a data governance
failure regardless of how well the fields are
structured. Design access controls alongside
field definitions, not after.

---

## Forward References

The following role files in this playbook reference
this appendix directly. When the logging architecture
for a deployment is being designed, the governance
sections of these files should be reviewed alongside
this appendix:

- **DevOps Engineer** — operational metrics and
  drift detection requirements
- **Security Engineer** — AI-specific threat
  logging and injection detection
- **Privacy Manager** — data subject logging,
  consent basis, and retention controls
- **Auditor** — tamper-evident records and
  human decision event logging
- **IT Administrator** — access control records
  and data classification
- **Data Scientist** — experiment provenance
  and model governance logging
- **Data Engineer** — pipeline lineage and
  data quality logging
- **Support Engineer** — diagnostic interaction
  logging and PII middle path
- **SecOps Analyst** — behavioral baseline
  and anomaly detection logging

---

*Enterprise Role Playbook for AI Developers |
Appendix A: Unified Logging Architecture v0.1 |
ArchieCur + Sonnet + Claude Code | MIT License | 2026*
