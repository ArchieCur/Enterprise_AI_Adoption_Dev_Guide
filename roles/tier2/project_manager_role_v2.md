# Project Manager
## Enterprise Role Playbook for AI Developers

---

### Who This Person Is
The Project Manager is the person responsible for making
sure the AI system actually gets built — on time, within
scope, within budget, and with enough organizational
alignment that it survives contact with the enterprise.
They are not the person who decides what gets built or
how it gets built. They are the person who makes sure
the decisions get made, the dependencies get resolved,
the stakeholders stay informed, and the timeline holds
together when reality starts disagreeing with the plan.

They think in milestones, dependencies, risks, and
resource constraints. They speak in status updates,
RAID logs (Risks, Assumptions, Issues, Dependencies —
the PM's running ledger of everything that could affect
delivery), and change requests. They have seen enough
projects where the technical work was excellent and the
delivery failed — because a stakeholder wasn't engaged,
a compliance review wasn't scheduled, a dependency
wasn't tracked, or scope crept quietly until the
timeline collapsed — to be professionally skeptical
of any plan that doesn't account for what goes wrong.

AI projects have given Project Managers a new category
of management challenge that traditional project
frameworks don't fully address. The requirements are
harder to lock because AI system behavior is inherently
probabilistic. The definition of done is harder to
establish because model performance is a spectrum,
not a binary. The stakeholder landscape is broader
because AI touches compliance, legal, security, and
privacy in ways that a traditional software project
may not. And the timeline is harder to defend because
AI development involves experimentation that doesn't
fit neatly into sprint planning.

The developer who understands what the Project Manager
is managing will make their job easier at every stage.
The developer who treats project management as overhead
will make it harder — and will feel the consequences
when stakeholder alignment fails, scope expands
without budget, or a compliance review nobody scheduled
stops the deployment two weeks before go-live.

---

### What They Care About
- Scope integrity — what is in scope and what is not
  needs to be documented, agreed, and defended; scope
  creep in AI projects is particularly dangerous because
  "the model could also do X" is always true and always
  tempting
- Timeline reliability — a milestone that slips because
  of an undisclosed dependency is a project management
  failure even when the technical work was done correctly
- Stakeholder alignment — every stakeholder who needs
  to approve, review, or accept the system needs to be
  identified, engaged, and kept informed from the start
- Risk visibility — risks that are known and managed
  are project risks; risks that are discovered at
  deployment are incidents
- Clear definition of done — for AI systems this is
  harder than for traditional software and needs to
  be established explicitly before development begins;
  the developer needs to bring a proposed eval
  framework to this conversation, not wait for
  business stakeholders to define it without them

---

### What They're Afraid Of
- A compliance or legal review that wasn't scheduled
  appearing as a blocker two weeks before go-live —
  this is the most common AI project delivery failure
  and almost always preventable
- Scope that expands continuously because AI capabilities
  keep suggesting new possibilities — "while we're at
  it" is a project timeline's worst enemy
- Stakeholders who were not engaged during development
  exercising veto power at deployment — the Business
  Leader who sees the system for the first time at
  the demo is a risk, not an audience
- A definition of done that nobody agreed on — is the
  model good enough? good enough for whom? by what
  measure? decided by whom? these questions need answers
  before development begins, not during UAT
- Dependencies that were assumed rather than confirmed —
  the API that was supposed to be available, the data
  that was supposed to be clean, the approval that was
  supposed to be straightforward

---

### What "Good" Looks Like for Them
- A project plan that accounts for compliance review,
  security assessment, and stakeholder approval cycles
  as scheduled activities with real duration — not
  as assumptions that those things will happen quickly
- A scope document that was agreed by all stakeholders
  before development began and has a change control
  process for anything that comes after
- A definition of done that specifies what performance
  level is acceptable, who makes that determination,
  and what the process is for resolving disagreement
- Status that is visible without requiring the developer
  to be asked — dashboards, regular updates, and
  proactive flagging of risks before they become issues
- A go-live plan that includes rollback criteria —
  under what conditions does the deployment pause
  or reverse, and who makes that call?

---

### Governance & Compliance Considerations

#### Compliance Review Cycles Must Be Scheduled as Project Activities
Legal review, security assessment, privacy impact
assessment, and IT architecture review are not
instantaneous. Each has its own queue, its own
process, and its own timeline. In most enterprises
these reviews take weeks, not days. A project plan
that assumes these reviews will happen quickly —
or that schedules them as parallel activities without
confirming availability — will produce a compliance
blocker at the worst possible moment. The Project
Manager needs to identify every required review,
confirm the process and timeline for each, and
schedule them as explicit project milestones with
realistic duration. Developers should surface every
compliance dependency they are aware of at project
kickoff — not when the code is ready for deployment.

#### Change Control is an AI Project Requirement, Not Optional Process
AI projects are particularly susceptible to scope
creep because the technology's flexibility makes
expansion feel natural and low-cost. Every change
to the system's scope — new use cases, additional
integrations, expanded data access, new user
populations — has timeline, budget, compliance, and
risk implications that need to be assessed before
the change is accepted. A formal change control
process that requires documentation, impact assessment,
and stakeholder approval for every scope change is
not bureaucratic overhead — it is the mechanism that
keeps AI projects deliverable.

In most engineering contexts, surfacing additional
capabilities is considered good instinct. In enterprise
AI, it requires a discipline shift. Every capability
addition is a potential new compliance surface, a new
stakeholder engagement requirement, a new entry on
the RAID log. The developer who surfaces new
possibilities should route them through change
control — not implement them and report them at the
next status meeting. This is not a restriction on
good engineering thinking. It is a recognition that
in an enterprise AI project, the whiteboard and the
sprint are not the same room.

#### Stakeholder Identification Must Include Governance Roles
Traditional project stakeholder maps focus on business
sponsors, end users, and technical teams. AI projects
require an expanded stakeholder map that includes Legal,
Compliance, Privacy, Security, and IT Architecture —
because each of these functions has approval authority
over some aspect of the AI system's deployment. A
stakeholder who was not identified and engaged during
the project will exercise their approval authority at
deployment, when the cost of their feedback is highest.
The Discovery Intake in this playbook is the starting
point for building a complete stakeholder map. Use it
before the kickoff meeting, not after.

#### Definition of Done for AI Systems Requires Explicit Agreement
Traditional software has a relatively clear definition
of done: the specified functionality works correctly.
AI system definition of done is more complex: what
performance level is acceptable? measured on what
data? by what methodology? acceptable to whom? A
system that the developer considers done because it
meets their internal performance benchmark may not
be considered done by the business stakeholder whose
workflow it affects, the compliance team that needs
to review its outputs, or the IT team that needs to
certify its infrastructure.

The Project Manager needs to drive explicit agreement
on the definition of done before development begins.
But the developer must come to that conversation with
something concrete to agree on. The developer is often
the only person in the room who can define what
"acceptable performance" actually means technically —
what eval dataset, what methodology, what threshold,
and why that threshold is defensible to a business
stakeholder. Without the developer's input, the DoD
agreement is made between non-technical stakeholders
deciding something they do not have the information
to decide correctly. Arrive at the DoD conversation
with a proposed eval framework. A developer who waits
for the business to define performance criteria will
end up delivering against criteria that cannot be
measured, or that measure the wrong thing entirely.

#### Communicating AI Progress Requires a New Protocol
Project Managers run on RAG status: Red, Amber, Green.
A developer who reports "the model is at 87% accuracy
and we think we can reach 91% with another two days
of prompt engineering" has handed the PM something
they have no framework to put in a status report.
What does 87% mean for the milestone? Is the milestone
the eval threshold or the deployment date? Who decides
if 87% is good enough to move forward?

Probabilistic progress does not map to feature
completion. A developer and PM who haven't agreed
on a status communication framework before the first
milestone will improvise one under pressure — which
usually means the developer reports numbers and the
PM reports dates, and neither is tracking the same
thing. Establish the protocol before the first
sprint review: what metric, what threshold, what
format, who decides when the threshold is met. The
DoD agreement and the status communication protocol
are companion documents. Build them together.

#### Go-Live Planning Must Include Rollback Criteria
AI system deployments can fail in ways that are not
immediately visible — output quality degradation,
edge case failures at scale, user adoption problems
that surface as support volume spikes. The go-live
plan needs to specify: what metrics are being monitored
post-deployment, what threshold triggers a rollback
conversation, who makes the rollback decision, and
how quickly the system can be rolled back if the
decision is made. A deployment without rollback
criteria is a deployment with no exit if something
goes wrong.

---

### Model Selection Guidance

**Recommended tier: Small to Medium**

- Project Managers use AI tools primarily for
  productivity support — documentation, communication,
  status synthesis, and planning support
- Small for structured, high-volume project management
  tasks: meeting note summarization from structured
  inputs, status report generation from structured
  data, risk register formatting, action item extraction
  from structured meeting records
- Medium for planning support, stakeholder communication
  drafting, risk analysis synthesis, and project
  documentation requiring judgment and context

**Model mapping:**
- Small — meeting note formatting, status report
  generation from structured inputs, action item
  extraction, risk register updates, project
  schedule formatting
- Medium — stakeholder communication drafting,
  risk analysis synthesis, project plan documentation,
  change request impact assessment support,
  go-live readiness checklist generation

**Critical:** Project Managers working on AI projects
should not use AI tools to generate project plans
without understanding the AI-specific activities
those plans need to include — compliance reviews,
security assessments, model evaluation cycles,
and stakeholder approval gates. A project plan
generated from a generic template will miss these
activities. The tool is only as good as the
requirements given to it.

---

### The One Thing Developers Get Wrong
They treat project management as overhead and
compliance reviews as someone else's problem.

The developer who submits a security review request
two weeks before go-live, who surfaces a privacy
question during UAT, who discovers a missing
stakeholder approval at the demo — that developer
has not made a technical error. They have made a
project management error. The distinction matters
because the fix is not more technical skill. It is
earlier, more complete communication about what
the project requires and when.

The Project Manager cannot schedule what they do not
know about. Every compliance dependency, every
required approval, every integration assumption, every
data requirement is a project activity that needs to
be identified at kickoff and tracked through delivery.
The developer who treats the project kickoff as a
formality and the Discovery Intake as optional will
rediscover these requirements later — at the point
in the project where they are most expensive to address.

And one behavioral shift that most developers don't
see coming: the instinct to surface new capabilities
is good engineering in most contexts. In enterprise
AI, it requires a different discipline. Every "while
we're in here, we could also..." is a potential new
compliance surface, a new stakeholder conversation,
a new line on the RAID log. The idea doesn't go into
the sprint. It goes through change control. That is
not a restriction on good thinking — it is how good
thinking survives contact with the enterprise.

The Project Manager is not the developer's adversary.
They are the person who makes sure the work the
developer does actually reaches production. Give them
what they need to do that job: complete dependency
identification at the start, honest status throughout,
and early escalation when something is at risk.

---

### Fill-in-the-Blank Workflow Starter
```
SYSTEM:
You are a project management assistant supporting
[PROJECT MANAGER NAME / TEAM NAME] at [COMPANY NAME],
managing [PROJECT NAME — e.g., "the AI workflow
deployment for the [DEPARTMENT] team"].

Your purpose is to [PRIMARY TASK — e.g., "support
project documentation, status reporting, and
stakeholder communication for this AI deployment
project"].

Project context:
- Phase: [CURRENT PHASE — e.g., "discovery,
  development, UAT, deployment"]
- Key stakeholders: [LIST — e.g., "Business Sponsor,
  IT Lead, Compliance, Legal, Privacy, Security,
  End User Champion"]
- Compliance reviews in scope: [LIST — e.g.,
  "Security assessment, Privacy Impact Assessment,
  Legal review, IT Architecture review"]
- Definition of done: [AGREED CRITERIA — e.g.,
  "model performance at or above [THRESHOLD]
  on [EVALUATION DATASET], accepted by
  [ACCEPTANCE AUTHORITY]"]
- Status communication format: [AGREED PROTOCOL —
  e.g., "eval metric, current value, target threshold,
  decision authority, and milestone impact —
  reported on [CADENCE] to [STAKEHOLDER LIST]"]

Always:
- Structure status updates with [FORMAT — e.g.,
  "accomplishments this period, planned next period,
  risks and issues, decisions needed"]
- Flag any risk involving [HIGH-IMPACT AREAS — e.g.,
  "compliance review timeline, stakeholder approval
  gaps, scope change requests, definition of done
  disputes"] for Project Manager attention
- Track action items with [REQUIRED FIELDS — e.g.,
  "owner, due date, status, dependencies"]
- Route scope change requests through [CHANGE
  CONTROL PROCESS] before acknowledging feasibility
  to any stakeholder

Never:
- Commit to timeline, scope, or budget changes
  without [APPROVAL REQUIREMENT — e.g., "Project
  Manager review and stakeholder sign-off through
  the change control process"]
- Generate a go-live recommendation without
  [REQUIRED ELEMENTS — e.g., "completed compliance
  reviews, confirmed stakeholder acceptance,
  rollback criteria documented, and monitoring
  plan in place"]
- Represent project status as green when
  [RISK CONDITIONS — e.g., "any open compliance
  review, unresolved definition of done dispute,
  or unconfirmed critical dependency"] are present
- Omit negative status or risks from stakeholder
  communications to maintain a positive narrative

When a new requirement or scope addition is raised:
Document it. Route it to the change control process.
Do not estimate feasibility or timeline impact
without Project Manager review. Do not communicate
feasibility to stakeholders before impact assessment
is complete.

Output format: [PROJECT TEAM'S PREFERRED FORMAT —
e.g., "structured status report: RAG status,
period summary, risks and issues log, decisions
needed, action items — distributed to
[STAKEHOLDER LIST] on [CADENCE]"]
```

---

### Adjacent Roles to Consider
When building for Project Managers, also read:
- **Business Leader** — the Project Manager reports
  project status to Business Leaders and manages
  their approval requirements; understanding what
  Business Leaders need to see and when is essential
  for stakeholder management
- **Legal/Compliance** — compliance review cycles
  are project schedule dependencies; the Project
  Manager needs Legal and Compliance engaged as
  scheduled participants from kickoff, not as
  late-stage reviewers
- **IT Administrator** — infrastructure readiness,
  access provisioning, and security review are
  IT-owned project dependencies; misalignment
  between project timeline and IT processes is
  one of the most common AI project delays
- **Developer** — the Project Manager depends on
  the Developer for honest status, early risk
  escalation, and complete dependency identification;
  this is the most operationally critical relationship
  in the project and the one most often managed
  informally when it should be managed explicitly

---

*Enterprise Role Playbook for AI Developers | Project Manager v0.1 |
ArchieCur + Sonnet + Claude Code | MIT License | 2026*
