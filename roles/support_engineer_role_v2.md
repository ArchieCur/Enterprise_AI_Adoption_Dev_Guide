# Support Engineer
## Enterprise Role Playbook for AI Developers

---

### Who This Person Is
The Support Engineer is the developer's early warning
system — and most developers don't know it yet. They
are the first person outside the build team to encounter
the AI system behaving badly at scale, in conditions
nobody tested for, with users doing things nobody
anticipated. They live in the ticket queue, the incident
log, and the escalation call that comes in at 2am when
the system that worked perfectly in staging has decided
that production is a different country with different
rules.

They think in failure modes, reproducibility, and
workarounds. They speak in ticket IDs, error logs,
and escalation paths. They have an encyclopedic memory
for edge cases because edge cases are their entire job.
They are methodical where developers are creative,
patient where developers are iterative, and relentlessly
focused on the question that matters most when something
goes wrong: can this be reproduced, and if so, how?

AI systems have handed the Support Engineer a category
of failure that their existing toolkit was not built
for. Traditional support runs on reproducibility —
the same input produces the same error, you find the
error, you fix it. AI systems don't work that way.
The same input can produce different outputs. The
failure may not be an error at all — it may be a
response that is technically valid and completely
wrong for the context. The user says "it gave me
a bad answer." The Support Engineer cannot reproduce
it. The developer says "it works on my end." Nobody
is lying. Everyone is frustrated.

They are also, in many enterprises, the undocumented
QA layer for AI systems — catching drift, hallucinations,
and unexpected behavior that monitoring dashboards
weren't configured to surface, logging patterns that
nobody thought to look for, and escalating issues
that don't fit any existing category. They are doing
this work with tools built for deterministic systems
and patience built from years of being the last line
of defense before the user gives up entirely.

Build for them like they are your partner in
production. Because they are — whether you planned
for it or not.

---

### What They Care About
- Reproducibility — can the failure be reliably
  recreated? without reproducibility there is
  no diagnosis, no fix, and no way to confirm
  the fix worked; AI systems that fail
  non-deterministically are a support nightmare
  that starts the moment they go live
- Diagnosability — when something goes wrong,
  can the Support Engineer determine whether
  the problem is the model, the prompt, the
  data, the integration, or the user? a system
  that fails opaquely is a system that cannot
  be supported
- Escalation clarity — who owns what when
  the AI system fails? is this a developer
  problem, a vendor problem, a data problem,
  or a user education problem? without clear
  escalation paths, everything lands on
  the Support Engineer's desk indefinitely
- User trust protection — every bad AI output
  that reaches a user without being caught
  is a trust event; the Support Engineer is
  the last internal checkpoint before user
  trust becomes a support volume problem
- Runbook existence — is there documentation
  that tells a Support Engineer what to do
  when the AI system behaves unexpectedly?
  in most enterprises the answer is no, and
  the Support Engineer writes the runbook
  themselves from incident experience

---

### What They're Afraid Of
- A non-reproducible failure that the developer
  cannot investigate because the logs don't
  capture what the model actually did —
  "it works on my end" is the four words
  most likely to end a Support Engineer's
  patience
- An AI system with no graceful degradation —
  when the model fails, does the system fail
  visibly with a clear message, or does it
  fail silently with a confident wrong answer
  that the user acts on before anyone notices
- Volume spikes they can't explain — an AI
  system generating support tickets faster
  than the team can close them, with no
  pattern visible because nobody built
  the monitoring to surface one
- Being the de facto QA team for a system
  that was deployed without adequate testing —
  finding in production what should have
  been found in staging, at the pace and
  scale of real users
- Escalating to a developer team that doesn't
  have the context to act — a ticket that
  says "the AI gave a wrong answer" with
  no prompt, no output, no user context,
  and no reproduction steps is a ticket
  that will sit in a queue until everyone
  forgets about it

---

### What "Good" Looks Like for Them
- A runbook that exists before go-live —
  written by the developer, not reconstructed
  by the Support Engineer from incident
  experience after the fact
- Logging that captures enough context to
  diagnose a failure without requiring the
  exact reproduction of the original input —
  prompt, model version, retrieved context,
  output, and user action taken
- Clear failure modes — a system that fails
  loudly and obviously is easier to support
  than one that fails quietly and confidently;
  design for visible failure over silent
  degradation
- An escalation path that distinguishes
  between model behavior issues, integration
  failures, data quality problems, and user
  education gaps — because the fix for each
  is owned by a different team
- A developer who treats the first month of
  support tickets as a feedback loop, not
  as someone else's problem — the Support
  Engineer's incident log is the most
  accurate picture of how the system
  actually behaves in production

---

### Governance & Compliance Considerations

#### AI Support Requires New Diagnostic Categories
Traditional support diagnostic frameworks assume
deterministic system behavior. An AI system
introduces failure categories that don't exist
in conventional support workflows: model
hallucination, prompt sensitivity, context
window limitations, retrieval failures in RAG
systems, and output drift over time. Support
Engineers need a diagnostic framework that
maps AI-specific failure modes to investigation
paths and escalation owners before the first
ticket arrives. Developers who hand off an
AI system without this framework are handing
off a system that cannot be effectively
supported.

The escalation vocabulary matters as much as
the escalation path. "The AI gave a wrong answer"
is not a ticket category — it is a symptom that
could indicate five different root causes owned
by five different teams. Give the Support Engineer
the vocabulary to classify before they route:
model behavior failure (the model produced an
output inconsistent with its expected behavior —
route to developer), integration failure (the
system connected incorrectly to an upstream or
downstream service — route to integration owner),
data quality failure (the input data or retrieved
context was incorrect or incomplete — route to
data owner), prompt failure (the system prompt
produced an unintended instruction — route to
developer), and user error (the user's input
was outside the designed use case — route to
training contact). A Support Engineer with this
vocabulary routes correctly on the first attempt.
One without it escalates everything to the
developer and waits.

#### The Runbook Must Specify What It Contains
The AI system runbook is the Support Engineer's
floor plan. Telling the developer to write one
before go-live is necessary but not sufficient —
most developers who sit down to write a runbook
for an AI system don't know what sections it
needs. At minimum, a support runbook for an AI
system should contain: the system's known failure
modes with reproduction steps where available,
the classification framework for routing each
failure type to the correct owner, the escalation
contact for each failure category with expected
response time, the logging fields required to
diagnose each failure type, the workarounds for
known failure modes pending permanent fixes, the
model version history with behavioral change notes,
the criteria for declaring a support incident
versus a standard ticket, and the go-live rollback
criteria and who can authorize them. A runbook
that covers these eight areas gives the Support
Engineer something to work from. A runbook that
says "contact the developer if something seems
wrong" is a placeholder, not a document.

#### Logging Must Be Designed for Supportability
The logs that satisfy a DevOps Engineer's
operational monitoring requirements are not
the same logs that allow a Support Engineer
to diagnose a specific user-reported failure.
Support-oriented logging needs to capture:
the user's input, the system prompt version,
any retrieved context passed to the model,
the model's output, the model version, and
the timestamp — for every interaction that
could generate a support ticket. This is a
design decision that needs to be made before
deployment. Retrofitting support-grade logging
to a production AI system is expensive and
often incomplete. Build it in from the start.

#### The PII Logging Middle Path Requires Three Decisions
Support logs for AI systems frequently capture
user inputs that contain personal information —
names, account details, business-sensitive
queries. The logging architecture that enables
diagnosis also creates a data privacy obligation.
A support log that captures everything is a
compliance problem. A support log that captures
nothing is a diagnostic dead end.

Designing the middle path requires three specific
decisions made with Legal and Privacy before
deployment — not approximated by the developer
alone. First: what fields can be logged in full,
what fields must be pseudonymized or hashed, and
what fields must be excluded entirely? The answer
depends on data classification, jurisdictional
requirements, and the sensitivity of the use case.
Second: what is the retention period for support
logs, and does it differ by data classification
level? Logs retained longer than necessary create
ongoing compliance exposure. Logs deleted too
quickly cannot support incident investigation.
Third: who can access support logs, under what
conditions, and with what audit trail? A developer
who can query raw support logs without oversight
creates a data handling risk that Privacy will
flag — and should. These three decisions need
documented answers before the logging architecture
is built. The middle path cannot be designed
without them.

#### Incident Classification for AI Failures
When an AI system produces an output that causes
harm — incorrect information acted on by a user,
a privacy violation through unexpected data
surfacing, a discriminatory output that reaches
a customer — the incident classification matters
for regulatory and legal purposes. Support
Engineers need clear guidance on which AI
failure categories trigger formal incident
response, which require Legal notification,
and which can be resolved through standard
support workflows. This classification framework
needs to exist before go-live, not be improvised
during an active incident.

#### Model Version Control Affects Support Traceability
When a vendor updates the underlying model
without notice — which major model providers
do on their own release schedules — the Support
Engineer may find themselves diagnosing failures
against a system that is no longer the system
that was deployed. Model version logging is
not just a DevOps concern. It is a support
traceability requirement. Log the model version
with every interaction. When behavior changes
unexpectedly, the first question support will
ask is "did anything change?" — and "the
vendor updated the model" is only a useful
answer if you can prove it with a timestamp.

---

### Model Selection Guidance

**Recommended tier: Small to Medium, diagnostic-first**

- Support Engineers use AI tools primarily for
  ticket triage, pattern recognition across
  incident logs, and documentation generation
  from structured support records
- Small for structured, high-volume support
  operations tasks with well-defined inputs:
  ticket categorization from structured fields,
  known-issue matching against a documented
  knowledge base, support log formatting,
  standard response generation from approved
  templates for known failure types
- Medium for pattern analysis across incident
  data, root cause synthesis from multiple
  tickets, escalation recommendation based
  on incident context, and runbook drafting
  from structured incident records

**Model mapping:**
- Small — ticket categorization, known-issue
  matching, support log formatting, standard
  response generation from approved templates,
  SLA tracking and alerting from structured data
- Medium — incident pattern analysis, root cause
  synthesis across multiple tickets, escalation
  path recommendation, runbook generation from
  incident records, support volume trend analysis

**Critical:** AI tools used in support workflows
for AI systems create a specific risk: the support
AI may inherit the same failure modes as the
system it is helping to diagnose. A support AI
that confidently misclassifies an AI-generated
failure compounds the original problem. Build
human review into any support workflow where
the AI tool is diagnosing failures in another
AI system. The fox should not be unaccompanied
in the henhouse.

---

### The One Thing Developers Get Wrong
They deploy the system and hand the Support
Engineer a fire extinguisher instead of a
floor plan.

The system goes live. The tickets arrive. The
Support Engineer opens the first one — "the AI
gave me the wrong answer" — and begins looking
for the tools they need to investigate: the
logs that capture what the model actually did,
the runbook that maps this failure type to a
diagnostic path, the escalation contact who
owns model behavior issues, the documentation
that distinguishes "the model is wrong" from
"the integration is broken" from "the user
is doing something we didn't design for."

In most AI deployments, none of these exist.
The Support Engineer builds them from scratch,
under ticket volume, from incident experience.
They become the institutional knowledge holder
for how the system actually fails — the same
role the Business Analyst plays for how the
business process actually works. And like the
Business Analyst, they will share that knowledge
with developers who earn the relationship and
withhold it from developers who treat support
as someone else's problem.

The developer who spends two days before go-live
writing a support runbook, defining escalation
paths, and walking the Support Engineer through
the system's known failure modes is the developer
whose production incidents get diagnosed and
resolved. The developer who throws the system
over the wall and moves to the next project
is the developer who gets pulled back into
production support six weeks later because
nobody else can explain what the system is doing.

Write the runbook. Define the failure modes.
Build the logs. Show up for the first month
of tickets. The Support Engineer will handle
the rest — if you give them something to work with.

---

### Fill-in-the-Blank Workflow Starter
```
SYSTEM:
You are a support operations assistant for
[TEAM NAME] at [COMPANY NAME], supporting
users of [AI SYSTEM NAME] deployed for
[BUSINESS FUNCTION / DEPARTMENT].

Your purpose is to [PRIMARY TASK — e.g.,
"support ticket triage, known-issue matching,
and escalation routing for [AI SYSTEM NAME]
support requests"].

System context:
- AI system version: [VERSION / RELEASE DATE]
- Model version: [MODEL VERSION — log this
  field; update when vendor releases changes]
- Known failure modes: [LIST — e.g., "retrieval
  failures on queries longer than [THRESHOLD],
  output drift on [SPECIFIC INPUT TYPES],
  latency issues under [LOAD CONDITIONS]"]
- Escalation paths:
  - Model behavior failure → [DEVELOPER CONTACT]
  - Integration failure → [INTEGRATION OWNER]
  - Data quality failure → [DATA OWNER]
  - Prompt failure → [DEVELOPER CONTACT]
  - User error → [TRAINING CONTACT]

Always:
- Capture [REQUIRED FIELDS — e.g., "user input
  summary, system output summary, model version,
  timestamp, user action taken, and reported
  impact"] for every ticket before attempting
  diagnosis
- Classify failure type using the five-category
  framework (model behavior, integration, data
  quality, prompt, user error) before routing —
  "the AI gave a wrong answer" is a symptom,
  not a classification
- Match against [KNOWN ISSUE REGISTRY] before
  escalating — check whether this failure type
  has been seen before and whether a workaround
  exists
- Flag any incident involving [HIGH-IMPACT
  CONDITIONS — e.g., "PII exposure, incorrect
  output acted on by user, or volume spike
  above [THRESHOLD] tickets per hour"] for
  immediate escalation to [CONTACT]
- Log model version with every interaction —
  flag any ticket where behavior changed
  following a vendor model update

Never:
- Close a ticket involving [HIGH-RISK OUTPUT
  TYPES — e.g., "incorrect financial data,
  privacy-sensitive content, or outputs
  that influenced a consequential user
  decision"] without [REVIEW REQUIREMENT —
  e.g., "senior support review and developer
  notification"]
- Share [RESTRICTED LOG CONTENT — e.g.,
  "full user prompts, PII-containing inputs,
  or privileged business context captured
  in support logs"] outside of [AUTHORIZED
  ACCESS LIST]
- Represent a workaround as a fix — document
  workarounds clearly as temporary measures
  and ensure the underlying issue is tracked
  for developer resolution
- Diagnose a model behavior failure without
  [REQUIRED CONTEXT — e.g., "model version,
  prompt version, and retrieved context if
  RAG is in use"] — incomplete diagnosis
  produces incorrect escalation

When a failure cannot be reproduced or classified:
Document everything captured. Escalate to
[DEVELOPER CONTACT] with full context.
Do not close the ticket as unresolvable
without developer review. Unclassified
failures are the earliest signal of
systematic problems.

Output format: [SUPPORT TEAM'S PREFERRED
FORMAT — e.g., "ticket ID, failure classification,
reproduction status, known-issue match,
escalation path, workaround if available,
resolution status, model version at time
of incident"]
```

---

### Adjacent Roles to Consider
When building for Support Engineers, also read:
- **DevOps Engineer** — operational monitoring
  and support diagnostics share logging
  infrastructure; align logging requirements
  with both roles before deployment or you
  will satisfy one and strand the other
- **IT Administrator** — access controls and
  system configuration affect what the Support
  Engineer can see during diagnosis; IT
  Administrator needs to understand support
  access requirements before go-live
- **Customer Service / Support** — in organizations
  where AI systems face external users, the
  Customer Service team surfaces user-facing
  failures while the Support Engineer diagnoses
  them; these two roles need a shared escalation
  protocol and a common language for describing
  AI failure modes
- **Developer** — the Support Engineer's incident
  log is the most accurate picture of how the
  system behaves in production; a developer
  who treats the support relationship as a
  feedback loop rather than a handoff will
  build better systems and spend less time
  being pulled back into production incidents

---

*Enterprise Role Playbook for AI Developers | Support Engineer v0.1 |
ArchieCur + Sonnet + Claude Code | MIT License | 2026*
