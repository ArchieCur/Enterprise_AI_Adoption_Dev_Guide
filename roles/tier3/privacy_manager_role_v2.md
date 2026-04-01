# Privacy Manager
## Enterprise Role Playbook for AI Developers

---

### Who This Person Is
The Privacy Manager is the enterprise's designated steward of
one of its most consequential obligations: the right of every
individual whose data the organization touches to have that
data handled lawfully, transparently, and with respect for
their autonomy. This is not a compliance checkbox role. It
is a professional discipline with its own legal framework,
its own certification bodies, and its own growing body of
case law that is being actively shaped by AI deployments
right now.

They think in data subjects, consent frameworks, lawful
basis, data minimization, and purpose limitation. They know
that the same piece of personal data can be lawfully used
for one purpose and unlawfully used for another — and that
the difference between those two uses can be the difference
between routine operations and a regulatory fine measured
in percentage points of global revenue.

AI systems are the Privacy Manager's most complex current
challenge. Every AI system is, at its core, a data processing
system. It ingests data, transforms it, generates outputs
from it, and often retains signals from it in ways that are
not fully visible or documented. Every one of those steps
is a data processing activity that requires a lawful basis,
a purpose, and a limit.

Come to the Privacy Manager before you build. They will
tell you what your system is allowed to do with personal
data. That conversation is far less expensive than the one
that happens after a data subject exercises their rights
against a system you already shipped.

---

### What They Care About
- Lawful basis — every processing activity needs a documented
  legal justification; "we need it to make the system work"
  is not a lawful basis
- Data minimization — collect and process only what is
  necessary for the stated purpose; AI systems have a
  tendency to consume more data than they need because
  more data often improves performance
- Purpose limitation — data collected for one purpose
  cannot be repurposed for another without a new lawful
  basis and, in many cases, new consent
- Individual rights — data subjects have rights to access,
  correction, deletion, portability, and objection that
  your system must be able to honor; "the model doesn't
  work that way" is not a response to a rights request
- Transparency — individuals have the right to know
  when and how their data is being processed by AI;
  opacity is a compliance failure, not a design choice

---

### What They're Afraid Of
- An AI system that processes personal data without
  a documented lawful basis — this is a regulatory
  violation before the first user interaction
- Training data that contains personal data that was
  collected for a different purpose — purpose limitation
  violations are one of the most common AI privacy findings
- A data subject rights request the system cannot fulfill —
  a deletion request that the model has already absorbed
  the data from is a technical and legal problem with
  no clean solution
- Cross-border data transfers that weren't reviewed —
  personal data moving between jurisdictions triggers
  transfer mechanism requirements that are actively
  enforced
- A privacy impact assessment that was never conducted —
  high-risk processing activities require documented
  assessment before deployment in most major privacy
  frameworks

---

### What "Good" Looks Like for Them
- A Data Protection Impact Assessment completed before
  deployment, not filed after an incident
- Data flows that are documented, minimal, and match
  the stated purpose of the system
- Individual rights fulfillment that is built into
  the architecture — not handled manually per request
- A system that can demonstrate its lawful basis for
  every category of personal data it processes
- Privacy notices that accurately describe what the
  AI system does with personal data, in language
  that a data subject can actually understand

---

### Governance & Compliance Considerations

#### A Data Protection Impact Assessment is Required Before Deployment
Under GDPR and similar frameworks, processing that is
likely to result in high risk to individuals requires
a Data Protection Impact Assessment before it begins.
AI systems that process personal data at scale, use
profiling or automated decision-making, or process
sensitive categories of data almost always meet this
threshold. The DPIA is not a retrospective document —
it must be completed before deployment and must identify
risks and the measures taken to address them. Build
DPIA completion into your project plan as a gate, not
an afterthought.

#### Lawful Basis Must Be Identified Before Processing Begins
Every personal data processing activity requires a
lawful basis under GDPR and equivalent frameworks.
The six available bases — consent, contract, legal
obligation, vital interests, public task, and legitimate
interests — are not interchangeable. Consent requires
active opt-in and can be withdrawn. Legitimate interests
requires a balancing test. The lawful basis that applies
to your system's data processing must be identified,
documented, and defensible before the first data subject's
information enters your system.

#### Training Data Privacy is a Distinct Obligation
If your system uses personal data for training, fine-tuning,
or retrieval augmentation, that use is a separate processing
activity from the system's operational use. It requires
its own lawful basis, its own purpose documentation, and
its own retention limits. Personal data that was collected
under a consent to "improve our services" may or may not
cover AI model training — and regulators are increasingly
finding that it does not without explicit disclosure.

#### Automated Decision-Making Has Special Rules
Under GDPR Article 22 and equivalent provisions, individuals
have the right not to be subject to decisions based solely
on automated processing that produce legal or similarly
significant effects. If your system makes or materially
influences decisions about individuals — hiring, credit,
insurance, access to services — you need to determine
whether Article 22 applies, provide the required disclosures,
and build in the required human review mechanism. This is
not optional and it is not satisfied by having a human
rubber-stamp an AI recommendation without genuine review.

#### Data Subject Rights Must Be Technically Fulfillable
The right to erasure, the right of access, the right to
portability, and the right to object are not aspirational
principles — they are enforceable individual rights with
response deadlines. Your system must be able to identify
all personal data associated with a specific individual,
produce it in a portable format on request, and delete
it completely when required. If your system has absorbed
personal data into model weights, retrieval indexes, or
logs in ways that cannot be surgically removed, you have
a rights fulfillment problem that needs to be resolved
before deployment, not after the first erasure request.

#### Cross-Border Data Transfers Require Transfer Mechanisms
Personal data moving from the EU to a third country,
or between other jurisdictions with transfer restrictions,
requires a legally valid transfer mechanism — Standard
Contractual Clauses, Binding Corporate Rules, an adequacy
decision, or another approved mechanism. Cloud-based AI
systems frequently involve cross-border data transfers
that developers don't notice because they happen at the
infrastructure level. Confirm with the Privacy Manager
where your data goes, at every step of processing,
before selecting your infrastructure.

#### Sensitive Data Categories Require Heightened Protection
Special categories of personal data — health, biometric,
racial or ethnic origin, political opinions, religious
beliefs, sexual orientation, and others — are subject
to stricter processing conditions under GDPR and equivalent
frameworks. AI systems that process or infer sensitive
categories from other data face significantly higher
compliance obligations. Know whether your system touches
sensitive categories, directly or through inference,
before you finalize your data architecture.

---

### Model Selection Guidance

**Recommended tier: Small to Medium, with data
minimization as a primary selection criterion**

- The Privacy Manager's primary concern is not model
  capability — it is what data the model processes
  and retains; select the model tier that handles
  the task with the minimum necessary data exposure
- Small for structured, low-risk privacy operations:
  consent record management, privacy notice generation
  from approved templates, data inventory updates,
  rights request routing and tracking
- Medium for privacy impact assessment support,
  policy drafting, cross-framework compliance analysis,
  and privacy training content development
- Large for complex multi-jurisdictional privacy
  analysis, regulatory response drafting, and
  high-stakes privacy risk synthesis — always with
  Privacy Manager review before use

**Model mapping:**
- Small — consent management, rights request tracking,
  data inventory maintenance, notice generation
- Medium — DPIA support documentation, privacy policy
  drafting, compliance gap analysis, training content
- Large — multi-jurisdictional regulatory analysis,
  enforcement response drafting, complex cross-border
  transfer assessment

**Critical:** Before selecting any model provider,
confirm their data processing terms satisfy the
Privacy Manager's requirements. Model providers
are data processors under GDPR. A Data Processing
Agreement must be in place before personal data
enters the system. This is a legal requirement,
not a procurement preference.

---

### The One Thing Developers Get Wrong
They design the system and add privacy later.

Privacy by design is a legal requirement under GDPR
and a best practice under every major privacy framework.
It means privacy protections are built into the system
from the start — not added as a feature after the
architecture is finalized. A system designed without
privacy constraints will almost always require
significant rework when the Privacy Manager reviews
it, because the data flows, retention mechanisms,
and processing purposes were established without
privacy requirements as a design input.

The specific failure mode looks like this: the system
is built, it works, it processes personal data efficiently,
and then the Privacy Manager asks three questions:
What is your lawful basis? How do you fulfill a deletion
request? Was a DPIA completed? The developer doesn't
have answers because those questions were never part
of the build.

Bring the Privacy Manager into architecture design.
Leave with documented answers to those three questions.
Build a system that can answer them at any point in
its lifecycle — not just on deployment day.

---

### Fill-in-the-Blank Workflow Starter
```
SYSTEM:
You are a privacy operations assistant supporting
[DEPARTMENT/TEAM NAME] at [COMPANY NAME].

Your purpose is to [PRIMARY TASK — e.g., "support
data subject rights request fulfillment by triaging
incoming requests, identifying the relevant data
categories, and drafting responses for Privacy
Manager review"].

Lawful basis for this processing: [BASIS — e.g.,
"legitimate interests as documented in the LIA
completed [DATE] and reviewed by [REVIEWER]"]

Data categories processed: [LIST — e.g., "name,
email address, interaction history — no sensitive
categories; no special category data"]

Always:
- Treat every individual whose data is referenced
  as a data subject with enforceable rights
- Flag any request involving [SENSITIVE CATEGORIES —
  e.g., "health data, biometric data, or inferred
  sensitive attributes"] for Privacy Manager review
  before proceeding
- Apply [JURISDICTIONAL FRAMEWORK — e.g., "GDPR
  as the baseline, with CCPA requirements applied
  for California residents"] to all processing
  activities
- Log all data subject interactions with [REQUIRED
  FIELDS — e.g., "request type, data subject ID
  (anonymized), date received, response deadline,
  assigned reviewer, disposition"]
- Route deletion requests to [TECHNICAL CONTACT]
  for system-level fulfillment confirmation within
  [TIMEFRAME — e.g., "72 hours of receipt"]

Never:
- Process personal data for [PROHIBITED PURPOSES —
  e.g., "any purpose not stated in the current
  privacy notice dated [DATE]"]
- Retain personal data beyond [RETENTION LIMIT —
  e.g., "the active session; no personal data stored
  in logs beyond anonymized request metadata"]
- Transfer personal data to [RESTRICTED DESTINATIONS —
  e.g., "any system outside the approved data
  processing inventory without Privacy Manager
  sign-off"]
- Respond to a data subject rights request with
  a final determination without [REVIEW REQUIREMENT —
  e.g., "Privacy Manager review and approval"]

When a rights request cannot be technically fulfilled
by the current system:
Stop. Document the limitation. Escalate immediately
to [PRIVACY MANAGER CONTACT]. Do not send a response
to the data subject until the technical feasibility
is confirmed.

Output format: [PRIVACY TEAM'S PREFERRED FORMAT —
e.g., "request summary, applicable rights, proposed
response, data categories involved, technical
fulfillment status, reviewer sign-off field,
response deadline"]
```

---

### Adjacent Roles to Consider
When building for Privacy Managers, also read:
- **Legal/Compliance** — privacy law is a subset
  of the compliance landscape; Privacy Manager and
  Legal need aligned interpretations of regulatory
  requirements and a clear division of accountability
  for privacy decisions
- **IT Administrator** — data flows, storage locations,
  and cross-border transfers are infrastructure decisions
  that determine privacy compliance; Privacy Manager's
  requirements need to be translated into technical
  controls by IT before deployment
- **Security Engineer** — privacy and security are
  distinct disciplines with significant overlap;
  a system that is secure but not privacy-compliant
  still fails; both perspectives are required
- **HR** — employee data is among the most sensitive
  personal data the enterprise processes; HR and
  Privacy Manager need aligned data handling practices
  for any system that touches workforce information

> **See also:** *Unified Logging Architecture for
> Enterprise AI Systems* (appendix) — Privacy,
> Security, DevOps, Auditor, and IT Administrator
> each require different logging outputs from the
> same system. Design one logging architecture that
> satisfies all five before deployment.

---

*Enterprise Role Playbook for AI Developers | Privacy Manager v0.1 |
ArchieCur + Sonnet + Claude Code | MIT License | 2026*
