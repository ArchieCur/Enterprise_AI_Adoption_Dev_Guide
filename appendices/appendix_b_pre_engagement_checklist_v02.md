# Appendix B: Developer Pre-Engagement Checklist

## Enterprise Role Playbook for AI Developers

---

## How This Appendix Works

The Discovery Intake Form is the developer's
interview guide — the questions to ask the
enterprise in the first conversation. This
appendix is different. It is the preparation
guide — what the developer needs to have
already figured out, gathered, and produced
before walking into a specific role's room.

The Intake tells you what to ask.
This checklist tells you what to know before
you ask it.

Two sections follow. The first is the Universal
Pre-Engagement Kit — artifacts and answered
questions every developer needs before any
role conversation, regardless of tier or function.
Complete this before every meeting. It is not
repeated in the role-specific entries.

The second section covers role-specific
preparation — the delta that each role requires
beyond the universal kit. Each entry is scoped
to what that role will ask for, care about,
or use to decide whether the developer is
ready to be in the room.

Any checked red flag means stop. Do not schedule
the meeting until the flag is resolved. A developer
who walks into a Tier 2 or Tier 3 role's room
without the required preparation does not get
a second chance to make a first impression —
they get a delayed deployment.

---

## Part 1: Universal Pre-Engagement Kit

Complete this before every role conversation.
These items are not repeated in the role-specific
entries below.

### Artifacts to Bring to Every Conversation

**The completed Discovery Intake Form**
Sections 1 through 3 minimum — project information,
contacts, and tech stack. Section 4 (guardrails)
should be complete before any Tier 2 or Tier 3
conversation. A partially completed intake is
a signal that discovery is not finished and the
developer is not ready to be in this room.

**The AI behavior specification**
The document that translates the requirements
into AI system behavior decisions — confidence
thresholds, failure handling, edge case treatment,
human review triggers, and what the system does
when the model is uncertain or wrong. This is
distinct from the requirements document. The
developer owns it. Most roles will not know to
ask for it by name, but every role will ask
questions that require it to exist.

**The system architecture overview**
One page maximum: what the system does, what
data it touches, what enterprise systems it
connects to, what the data flows look like,
and where the model sits in the stack. This
is not a technical design document — it is
a communication artifact that any stakeholder
can understand and any reviewer can assess.

**The model provider and version information**
Which provider, which model, which version,
what the data handling terms are, whether the
provider is on the enterprise approved vendor
list, and what the provider's security
certifications are. Every governance role
will ask some version of this question.

**The project timeline**
Target go-live date, key milestones, compliance
review windows already scheduled, and the
change management plan if one exists. A developer
who cannot answer "when does this go live and
what reviews are between here and there" is
not ready for a stakeholder conversation.

### Questions to Arrive With Answered

- What data does this system process, and what
  is its classification level?
- What compliance reviews are required and
  which have been completed or scheduled?
- Who has already been briefed on this system
  and what was their response?
- What is the human-in-the-loop design — who
  reviews AI outputs before they are acted on,
  and for which output types?
- What happens when the system produces a
  wrong answer — what is the failure mode
  and who is accountable?

### Universal Red Flags

- [ ] Discovery Intake is incomplete — finish
  it before scheduling any role conversation
- [ ] No AI behavior specification exists —
  produce one before any Tier 2 or Tier 3 meeting
- [ ] Model provider is not on the enterprise
  approved vendor list — resolve with IT and
  Legal before proceeding
- [ ] Human-in-the-loop design is undefined —
  no role conversation should happen without
  a clear answer to who reviews what and when
- [ ] Compliance review requirements are unknown —
  identify them before scheduling any meeting
  with a governance role

---

## Part 2: Role-Specific Preparation

The entries below cover only the delta —
what each role specifically requires beyond
the Universal Pre-Engagement Kit above.

---

### Finance

#### Artifacts to Bring
- **Audit trail design** — how every AI-assisted
  financial output is logged, what fields are
  captured, how long records are retained, and
  how the trail satisfies SOX or applicable
  audit requirements
- **Human review specification for financial outputs**
  — which output types require human sign-off
  before use, who is authorized to sign off,
  and how that authorization is recorded

#### Questions to Arrive With Answered
- Which financial data categories does this
  system process and what are their classification
  levels?
- What is the reconciliation process if the
  system produces an incorrect financial output?
- Does any output from this system feed into
  financial reporting, and if so, what controls
  exist at that handoff?

#### Red Flags — Do Not Enter This Room If:
- [ ] The audit trail design does not exist or
  has not been reviewed by someone with SOX
  knowledge
- [ ] Any financial output can reach a report
  or decision without a human review step
- [ ] The system touches financial data whose
  classification or handling requirements
  are unknown

---

### Legal / Compliance

#### Artifacts to Bring
- **Architecture diagram for legal review** —
  not the full technical design; a diagram
  that shows data flows, external connections,
  model provider, and where personal or
  regulated data enters and exits the system
- **Jurisdiction map** — which regulations apply
  to this system based on where it operates,
  where its users are located, and what data
  it processes

#### Questions to Arrive With Answered
- Has Legal been identified as a required
  reviewer, and is this meeting early enough
  for their input to change the architecture?
- What is the system's EU AI Act classification
  if the organization operates in or serves EU
  residents?
- What contracts with vendors, data providers,
  or platforms govern what can be built on
  top of them?

#### Red Flags — Do Not Enter This Room If:
- [ ] This is the first Legal has heard of
  the system — that is not a pre-engagement
  meeting, it is a disclosure
- [ ] The architecture is finalized and Legal's
  input cannot change it — Legal review at
  that stage is documentation, not governance
- [ ] The jurisdiction analysis has not been done

---

### HR

#### Artifacts to Bring
- **Consent and disclosure framework** — how
  employees are informed that AI is being used
  in workflows that affect them, what they
  are consenting to, and how that consent
  is recorded
- **Employment law touchpoint summary** — which
  employment decisions or workflows this system
  affects and what the legal constraints on
  AI-assisted employment decisions are in
  the relevant jurisdictions

#### Questions to Arrive With Answered
- Does this system affect any workflow that
  influences hiring, performance, compensation,
  or termination decisions?
- What is the human review requirement for
  any output that touches an employment decision?
- Has Legal reviewed the consent framework?

#### Red Flags — Do Not Enter This Room If:
- [ ] The system affects employment decisions
  and no legal review of that use case has
  been completed
- [ ] Employee consent and disclosure has not
  been designed — this is not optional in
  any jurisdiction with AI employment law

---

### IT Administrator

#### Artifacts to Bring
- **Architecture diagram for stack validation**
  — what the system requires from IT: compute,
  storage, network access, authentication
  integration, data classification handling,
  and log retention infrastructure
- **Integration specification** — every enterprise
  system the AI system connects to, with data
  flow direction, authentication method, and
  the IT owner of each connected system

#### Questions to Arrive With Answered
- Is every component of this system on the
  enterprise approved technology list?
- What access provisioning is required and
  what is the provisioning timeline?
- What are the log retention and classification
  requirements for this system's data category?

#### Red Flags — Do Not Enter This Room If:
- [ ] Any component is not on the approved
  technology list and no exception process
  has been started
- [ ] The integration specification is incomplete —
  IT cannot validate a stack they cannot see
- [ ] Log retention and classification requirements
  are unknown

---

### Security Engineer

#### Artifacts to Bring
- **Threat model** — the AI-specific threat
  model for this system: attack surface, trust
  boundaries, prompt injection exposure,
  data exfiltration risk, and agent tool
  access blast radius if applicable
- **AI-specific attack class brief** — what
  prompt injection, indirect prompt injection
  through retrieved content, and anomalous
  tool calls look like in this system's
  specific architecture and logs

#### Questions to Arrive With Answered
- Has a threat model been produced, and was
  it produced by someone with AI security
  knowledge rather than adapted from a
  traditional application security template?
- What is the least-privilege design for
  every component that has data access
  or tool execution capability?
- What is the incident response plan for
  a prompt injection attack on this system?

#### Red Flags — Do Not Enter This Room If:
- [ ] No threat model exists
- [ ] The threat model was adapted from a
  traditional application template without
  AI-specific attack classes added
- [ ] Any agent or tool-using component has
  not had its blast radius assessed

---

### Privacy Manager

#### Artifacts to Bring
- **Data flow map** — every point where personal
  data enters, is processed, is stored, or
  exits the system, with the legal basis for
  each processing activity
- **DPIA plan** — whether a Data Protection
  Impact Assessment is required, and if so,
  the timeline and owner

#### Questions to Arrive With Answered
- What personal data categories does this
  system process and under what legal basis?
- What are the data subject rights obligations
  for data processed by this system?
- Does the system use personal data for model
  improvement or fine-tuning, and if so,
  has that been reviewed separately from
  operational data processing?

#### Red Flags — Do Not Enter This Room If:
- [ ] The data flow map is incomplete — Privacy
  cannot assess a system whose data flows
  are unknown
- [ ] The legal basis for each processing
  activity has not been identified
- [ ] A DPIA requirement has been identified
  but not scheduled

---

### Auditor

#### Artifacts to Bring
- **Evidence framework** — how the system
  produces evidence of its outputs, decisions,
  and human review events in a form that
  satisfies audit requirements; include
  the tamper-evident storage design
- **AI output separation design** — how the
  system distinguishes AI-generated content
  from human-authored content in records
  that will be subject to audit

#### Questions to Arrive With Answered
- What audit standard applies to this system
  (SOX, ISO, SOC 2, industry-specific)?
- How long must records be retained and in
  what format must they be produced for audit?
- Is the tamper-evident storage design in
  place before go-live or retrofitted after?

#### Red Flags — Do Not Enter This Room If:
- [ ] The evidence framework does not exist
- [ ] Tamper-evident storage has not been
  designed — this cannot be retrofitted
  after the first audit-relevant event
- [ ] AI output separation is not designed
  into the system — auditors will ask

---

### Risk Practitioner

#### Artifacts to Bring
- **Threat model** (same artifact as Security
  Engineer — bring the same document; if the
  Security Engineer conversation has already
  occurred, this is not a separate exercise;
  the Risk Practitioner adds risk register
  framing to the threat model discussion,
  they do not require a new threat modeling
  effort)
- **Risk register proposal** — the initial
  risk register for this AI system: identified
  risks, likelihood, impact, proposed controls,
  and risk owner for each item

#### Questions to Arrive With Answered
- What is the organization's risk tolerance
  for AI-specific risks — model error,
  bias, drift, and adversarial inputs?
- What existing risk frameworks apply to
  this system and what gaps exist in those
  frameworks for AI-specific risk categories?
- Who owns the ongoing risk monitoring for
  this system post-deployment?

#### Red Flags — Do Not Enter This Room If:
- [ ] No risk register exists — Risk Practitioner
  cannot review controls that have not been
  proposed
- [ ] AI-specific risk categories (model error,
  drift, bias, adversarial inputs) are absent
  from the risk register

---

### Project Manager

#### Artifacts to Bring
- **Complete dependency identification** —
  every compliance review, stakeholder approval,
  integration dependency, and external timeline
  constraint that affects this project
- **Compliance review schedule** — every required
  review identified, owner confirmed, timeline
  confirmed, and scheduled as a project milestone

#### Questions to Arrive With Answered
- Is the definition of done agreed — what
  performance level is acceptable, measured
  how, accepted by whom?
- What is the status communication protocol —
  how will probabilistic progress (eval metrics,
  not feature completion) be reported to
  project stakeholders?
- What is the rollback criteria and who can
  authorize a rollback?

#### Red Flags — Do Not Enter This Room If:
- [ ] The dependency identification is incomplete —
  the PM cannot schedule what they do not know about
- [ ] The definition of done has not been agreed —
  do not begin development without it
- [ ] Compliance reviews have not been scheduled
  as project milestones with confirmed timelines

---

### Data Scientist

#### Artifacts to Bring
- **Problem statement and success metrics** —
  the specific problem the model is solving,
  how success will be measured, and what
  the evaluation framework looks like
- **Evaluation framework proposal** — what
  will be measured, on what data, using
  what methodology, and what threshold
  constitutes acceptable performance

#### Questions to Arrive With Answered
- Is the evaluation framework designed before
  any modeling begins, or is it being designed
  after results are in hand?
- What fairness metrics apply to this use
  case and are they part of the evaluation
  framework?
- What does model drift look like for this
  system and what is the retraining trigger?

#### Red Flags — Do Not Enter This Room If:
- [ ] The evaluation framework does not exist
  before modeling begins
- [ ] Fairness metrics have not been identified
  for any use case that affects people
- [ ] The monitoring and retraining plan
  has not been designed

---

### Data Engineer

#### Artifacts to Bring
- **AI feature requirements** — the features
  the model needs, their definitions, their
  expected latency at inference time, and
  their availability requirements; produced
  before pipeline architecture is finalized

#### Questions to Arrive With Answered
- Are the required features available at
  inference time without data leakage?
- What is the pipeline latency requirement
  and can the current data infrastructure
  meet it?
- What is the data quality standard for
  features entering the model and how
  will quality be monitored?

#### Red Flags — Do Not Enter This Room If:
- [ ] Feature requirements have not been
  produced — the Data Engineer cannot design
  a pipeline for features that are not specified
- [ ] Pipeline architecture has been finalized
  before feature requirements were agreed —
  that conversation needs to happen again

---

### Solution Architect

#### Artifacts to Bring
- **System design context** — the business
  requirements, integration constraints,
  scalability requirements, and operational
  requirements that must be satisfied before
  component design begins

#### Questions to Arrive With Answered
- Has the build vs. buy vs. orchestrate
  decision been evaluated formally?
- What are the enterprise architecture
  standards this system must conform to?
- What is the cost model at 3x and 10x
  current projected volume?

#### Red Flags — Do Not Enter This Room If:
- [ ] Component design has begun before
  system design is agreed — the Solution
  Architect needs to be in the room before
  the component exists, not after
- [ ] The build vs. buy vs. orchestrate
  decision has been made without formal
  evaluation

---

### Functional Consultant

#### Artifacts to Bring
- **Platform license tier confirmation** —
  whether the current license supports the
  AI integration being designed, including
  API access, data volume limits, and any
  AI-specific feature entitlements; a system
  scoped to features the platform license
  does not support is a scope problem that
  surfaces at the worst possible moment
- **Data quality assessment** — the quality,
  completeness, and schema consistency of
  the platform data the AI system will consume;
  produced before pipeline architecture is
  finalized; building a pipeline before knowing
  the data quality produces a system that
  fails in production on inputs nobody anticipated

#### Questions to Arrive With Answered
- What platform configuration constraints
  limit what can be built on top of this
  system, and are those constraints documented?
- What is the data quality standard for the
  fields the AI system will consume, and who
  owns remediation if quality is insufficient?
- What vendor support or documentation governs
  AI integrations on this platform, and has
  it been reviewed?

#### Red Flags — Do Not Enter This Room If:
- [ ] Platform license tier is unknown —
  the Functional Consultant cannot validate
  an integration design that may exceed
  license scope
- [ ] Data quality has not been assessed —
  the Functional Consultant's credibility
  with the client rests on implementations
  that work in the client's actual data
  environment, not in a clean demo dataset

---

### Business Analyst

#### Artifacts to Bring
- **AI behavior specification draft** — the
  document that translates requirements into
  AI system behavior decisions (already in
  the Universal Kit, but the BA conversation
  is where this document gets validated;
  bring it explicitly and walk the BA through it)
- **Hidden decisions list** — the implicit
  decisions the requirements document leaves
  unstated: confidence thresholds, failure
  handling, edge case treatment, human review
  triggers; surface these before the meeting
  so the BA can confirm or correct them

#### Questions to Arrive With Answered
- Where does the business process actually
  break — not where the documentation says
  it works, but where the exceptions and
  workarounds live?
- How will the system's value be measured
  and who will be measuring it for the
  C-Suite?
- What institutional knowledge governs
  this process that does not appear in
  any documentation?

#### Red Flags — Do Not Enter This Room If:
- [ ] The AI behavior specification does not
  exist — the BA cannot validate a document
  that has not been produced
- [ ] The ROI measurement framework has not
  been discussed — the BA will be asked to
  defend the system's value; give them
  the framework before they need it

---

### Change Manager

#### Artifacts to Bring
- **Resistant-user persona** — who in the
  target population is most likely to resist
  adoption, which resistance category applies
  (mental model gap, tool friction, compliance
  concern, or legitimate grievance), and what
  design accommodations have been made
- **Model update notification pathway** — how
  the system will detect and communicate
  model version changes to the Change Manager
  before users encounter them

#### Questions to Arrive With Answered
- Has the Change Manager been engaged during
  design, or is this the first conversation?
- Which departments are highest-resistance
  and what is the specific nature of their
  resistance?
- What is the Champion identification and
  activation plan, and when does it begin
  relative to go-live?

#### Red Flags — Do Not Enter This Room If:
- [ ] This is the first conversation with
  the Change Manager and the system design
  is already finalized — adoption requirements
  cannot be incorporated after architecture
  is set
- [ ] The resistant-user persona does not
  exist — Change Manager cannot design
  an adoption program for a user population
  that has not been characterized
- [ ] The model update notification pathway
  does not exist — the Change Manager will
  discover this gap at the worst possible moment

---

### Support Engineer

#### Artifacts to Bring
- **Draft runbook** — at minimum, the eight
  sections specified in the Support Engineer
  role file: known failure modes, failure
  classification framework, escalation contacts
  by category, logging fields required for
  diagnosis, workarounds for known failures,
  model version history, incident declaration
  criteria, and rollback criteria
- **Escalation path design** — the five-category
  routing framework (model behavior, integration,
  data quality, prompt, user error) with named
  owners and expected response times for each

#### Questions to Arrive With Answered
- What does a non-reproducible failure look
  like for this system and what logging exists
  to support diagnosis without reproduction?
- What are the PII logging decisions — what
  fields are logged in full, pseudonymized,
  or excluded — and have those decisions
  been reviewed by Legal and Privacy?
- What is the model version logging mechanism
  and how will behavior changes following
  vendor updates be detected?

#### Red Flags — Do Not Enter This Room If:
- [ ] The runbook does not exist in draft form —
  the Support Engineer cannot prepare for
  failures that have not been characterized
- [ ] The PII logging middle path has not been
  decided with Legal and Privacy — do not
  ask the Support Engineer to operate a
  logging system whose compliance boundaries
  are undefined
- [ ] The escalation path has no named owners —
  "contact the developer" is not an escalation
  path

---

### Security Operations Analyst

#### Artifacts to Bring
- **Behavioral profile** — what normal operation
  looks like in the enterprise environment:
  API call volume and patterns, data access
  scope, external connections, expected alert
  signatures
- **AI-specific attack class brief** — what
  prompt injection, indirect prompt injection
  through retrieved content, and anomalous
  tool calls look like in this system's
  specific log format; system-specific, not
  generic (see Appendix A, SecOps row)

#### Questions to Arrive With Answered
- Has the system been registered with SecOps
  before this meeting, or is this the
  registration conversation?
- What detection rules need to be written
  for AI-specific attack classes and who
  will write them?
- What is the incident response plan for
  a prompt injection attack on this system
  specifically?

#### Red Flags — Do Not Enter This Room If:
- [ ] The behavioral profile does not exist —
  SecOps cannot configure detection rules
  for behavior they have never seen described
- [ ] The AI-specific attack class brief is
  generic rather than system-specific —
  "prompt injection is bad" is not a
  detection rule
- [ ] Any component of the system can take
  autonomous action without human authorization —
  resolve this in the architecture before
  briefing SecOps, not after

---

## A Note on Timing

Every role entry in this checklist assumes the
developer is arriving before architecture is
finalized. That assumption is intentional.

The pre-deployment window — the period during
which a role's input can change the system's
design — closes before the developer thinks
it does. For Legal, it closes when the
architecture is set. For the Change Manager,
it closes when the onboarding flow is built.
For the Support Engineer, it closes when the
logging architecture is deployed. For SecOps,
it closes when the system goes live in the
environment they are responsible for monitoring.

A developer who schedules these conversations
after the system is built is not doing
pre-engagement. They are doing disclosure.
The checklist works when it is used early.
Used late, it is an audit of what was missed.

---

*Enterprise Role Playbook for AI Developers |
Appendix B: Developer Pre-Engagement Checklist v0.1 |
ArchieCur + Sonnet + Claude Code | MIT License | 2026*
