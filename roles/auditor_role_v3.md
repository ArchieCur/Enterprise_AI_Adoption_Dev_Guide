# Auditor
## Enterprise Role Playbook for AI Developers

---

### Who This Person Is
The Auditor is the enterprise's institutional memory of everything
that has ever gone wrong. Their job is to examine systems,
processes, and decisions after the fact and determine whether
they were conducted in accordance with established standards,
regulations, and internal policy. They are not looking for
what worked. They are looking for what didn't — and for the
gap between what was supposed to happen and what actually did.

They are methodical, documentation-driven, and professionally
skeptical of every claim that isn't supported by evidence.
They have seen enough "the system worked as designed" defenses
collapse under scrutiny to trust nothing they can't verify
independently. They do not have opinions about your architecture.
They have findings.

An Auditor who is brought into an AI deployment early is one
of the most valuable partners a developer can have. They will
tell you exactly what evidence they will need to close an audit
finding before you build — which means you can build it in
from the start. An Auditor who encounters your system for the
first time during an audit will find every gap you didn't know
existed, in the order that creates the most organizational pain.

The choice of which Auditor you get is made before you write
your first line of code.

---

### What They Care About
- Evidence — assertions without documentation are not findings,
  they are starting points for further investigation
- Completeness — a control that works ninety-five percent of
  the time has a five percent gap that will appear in the report
- Independence — audit findings need to be reproducible by
  someone who wasn't involved in building the system
- Traceability — every output, decision, and action needs
  a chain of evidence that leads back to an authorized source
- Standards compliance — internal audit measures against
  internal policy; external audit measures against regulatory
  standards; your system needs to satisfy both simultaneously

---

### What They're Afraid Of
- An AI system that makes consequential decisions without
  a documented, reviewable audit trail — this is an automatic
  finding in any governance framework
- Black box outputs they cannot independently verify —
  if an auditor cannot reproduce or explain how an output
  was produced, it fails the audit regardless of whether
  it was correct
- Controls that exist on paper but not in practice —
  a system prompt that says "always require human review"
  means nothing if the logs show human review was skipped
  sixty percent of the time
- Scope creep that wasn't documented — a system that was
  approved for one use case and is being used for three
  others is an audit finding waiting to happen
- AI-generated audit evidence — outputs produced by the
  system being audited cannot be used as evidence of
  the system's own compliance

---

### What "Good" Looks Like for Them
- An audit trail that tells the complete story without
  requiring the developer to explain it
- Controls that are enforced by the system, not by
  user behavior — a control that depends on users
  doing the right thing is a control that will fail
- Documentation that was written before deployment,
  not reconstructed after an audit request
- A system that produces the same output under the
  same conditions consistently — reproducibility
  is auditability
- Clear delineation between what the AI did and what
  the human decided — the audit needs to follow
  that boundary precisely

---

### Governance & Compliance Considerations

#### Audit Trail Requirements Are Non-Negotiable by Definition
An AI system without a complete, tamper-evident audit trail
is not auditable. This is not a compliance preference —
it is a structural requirement of any governance framework
that includes AI systems. Every input, every output, every
human review action, every override, and every exception
needs to be logged with enough detail that an auditor who
has never seen the system can reconstruct what happened
and why. Design your logging architecture to satisfy an
auditor, not a developer.

#### AI Introduces New Audit Domains
Traditional IT audit covers access controls, change management,
and data integrity. AI systems add new audit domains that
most audit frameworks are still catching up to: model
version control, prompt change history, training data
provenance, output drift over time, and human oversight
compliance. Work with your Auditor to establish what
evidence they will need for each of these domains before
deployment. Frameworks like ISACA's guidance on AI audit
and the AICPA's emerging AI attestation standards are
useful references.

#### Controls Must Be Enforced, Not Documented
A documented control that is not enforced by the system
is a finding. If your governance documentation says AI
outputs require human review before use, the system must
make it impossible — or at minimum, auditably visible —
when that review doesn't happen. Design enforcement into
the architecture. Document the enforcement mechanism.
Give the Auditor evidence that the control works, not
a policy statement that it exists.

#### Sampling Will Find What You Didn't Test
Auditors use sampling methodologies that are specifically
designed to surface edge cases and exceptions. A system
that works correctly ninety-nine percent of the time
will produce the one percent failure in an audit sample.
Build your testing to include adversarial cases, edge
inputs, and failure modes — and document the results.
An auditor who finds a failure mode you already documented
and addressed will note it differently than one who
finds a failure mode you didn't know about.

#### Model Changes Are Change Events
When a model is updated — version change, prompt change,
fine-tuning, retrieval index update — that is a change
event under any IT governance framework. It needs to
go through change management: documented, tested,
approved, and logged. An undocumented model update
that changes system behavior is an audit finding even
if the new behavior is better than the old behavior.

---

### Model Selection Guidance

**Recommended tier: Small to Large, with explainability
as a primary selection criterion**

- The Auditor's primary interaction with AI is as the
  subject of audit, not as a user — but when AI tools
  are used to support audit work, explainability and
  reproducibility are the dominant requirements
- Small for high-volume, structured, low-ambiguity tasks:
  checklist generation from approved templates, findings
  documentation formatting from structured data inputs,
  policy reference lookup and summarization
- Medium for structured audit support: control testing
  checklists, policy compliance summaries, sampling
  framework generation, findings documentation drafts
  requiring interpretation
- Large for complex multi-framework compliance analysis,
  cross-system risk synthesis, and audit report drafting
  where nuanced judgment is required

**Model mapping:**
- Small — checklist generation from templates, findings
  formatting from structured data, policy reference
  summarization, audit schedule and tracking support
- Medium — audit checklist generation, control testing
  support, policy gap analysis, findings documentation
- Large — multi-framework compliance synthesis, complex
  risk narrative drafting, regulatory interpretation
  across overlapping standards

**Critical:** Any AI tool used in the audit process
itself must be disclosed in the audit methodology.
An audit finding that was identified using an AI tool
needs to document that fact. The independence and
reproducibility of the finding may be questioned
if the methodology is not transparent.

---

### The One Thing Developers Get Wrong
They build for the happy path and audit finds the exceptions.

The system handles normal inputs correctly. The controls
work as designed for expected use cases. The audit trail
is complete for standard transactions. And then the
Auditor pulls a sample that includes an edge case, an
override, an exception, or a failure — and the audit
trail has a gap, the control wasn't enforced, or the
output can't be explained.

Audit doesn't test what you designed for. It tests
what your system actually does across the full range
of inputs and conditions it encounters in production.
Build your audit trail and control enforcement for
the exceptions, not the standard case. Document your
known failure modes and how they are handled. Give
the Auditor the evidence for the hard cases, not just
the easy ones.

A system that handles exceptions well and documents
them thoroughly is more auditable than a system that
handles standard cases perfectly and ignores everything
else.

---

### Fill-in-the-Blank Workflow Starter
```
SYSTEM:
You are an audit support assistant for [DEPARTMENT/TEAM NAME]
at [COMPANY NAME].

Your purpose is to [PRIMARY TASK — e.g., "support internal
audit workflows by generating control testing checklists,
summarizing policy compliance status, and drafting
findings documentation for review"].

Always:
- Cite the specific standard, policy, or regulation
  [VERSION AND EFFECTIVE DATE] for every compliance
  reference
- Distinguish clearly between [EVIDENCE TYPES — e.g.,
  "confirmed findings supported by documentation,
  observations requiring further investigation,
  and recommendations without evidentiary basis"]
- Flag any output that involves [HIGH-RISK AREAS —
  e.g., "material findings, regulatory violations,
  or executive-level accountability"] for senior
  auditor review before inclusion in any report
- Log all outputs with [REQUIRED FIELDS — e.g.,
  "timestamp, audit engagement ID, standard referenced,
  reviewer assigned, disposition"]
- Disclose AI assistance in [REQUIRED LOCATIONS —
  e.g., "audit methodology section of all reports
  that used AI-assisted analysis"]

Never:
- Generate or modify audit evidence — all evidence
  must originate from [APPROVED SOURCES — e.g.,
  "system logs, human reviewer confirmations,
  and documented control testing results"]
- Produce a finding without [EVIDENCE REQUIREMENT —
  e.g., "at least one independently verifiable
  source citation"]
- Access [RESTRICTED SYSTEMS — e.g., "production
  data outside of the approved audit data extract"]
  outside of formally scoped audit procedures
- Represent AI-generated analysis as independent
  audit conclusion without [REVIEW REQUIREMENT —
  e.g., "documented human auditor review and sign-off"]

When a potential finding involves unsettled regulatory
interpretation:
Flag immediately. Route to [AUDIT LEAD/LEGAL CONTACT].
Do not characterize the finding until the regulatory
question is resolved.

Output format: [AUDIT TEAM'S PREFERRED FORMAT — e.g.,
"finding reference, standard cited, evidence summary,
risk rating, recommended remediation, reviewer sign-off field"]
```

---

### Adjacent Roles to Consider
When building for Auditors, also read:
- **Legal/Compliance** — audit findings often have
  legal implications; Auditor and Legal need aligned
  definitions of what constitutes a finding and what
  remediation is required
- **Finance** — financial audit is a primary audit
  domain; SOX compliance connects Auditor and Finance
  at every control point
- **IT Administrator** — IT audit covers the
  infrastructure your system runs on; IT Administrator
  and Auditor need shared documentation of system
  architecture, access controls, and change history
- **Risk Practitioner** — audit findings feed directly
  into risk registers; Auditor and Risk Practitioner
  should share a common framework for risk classification
  and remediation tracking

> **See also:** *Unified Logging Architecture for
> Enterprise AI Systems* (appendix) — Auditor,
> Security, DevOps, Privacy, and IT Administrator
> each require different logging outputs from the
> same system. Design one logging architecture that
> satisfies all five before deployment.

---

*Enterprise Role Playbook for AI Developers | Auditor v0.1 |
ArchieCur + Sonnet + Claude Code | MIT License | 2026*
