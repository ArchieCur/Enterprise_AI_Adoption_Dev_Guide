# Developer
## Enterprise Role Playbook for AI Developers

---

### Who This Person Is
This is you building for someone like you — except
they're inside an enterprise, which means they're
working within constraints you may not have. They
have an approved tech stack, a security review
process, a change management board, and a manager
who wants everything documented. They're technically
capable but organizationally constrained.

Enterprise developers are often building AI workflows
for other roles in this playbook — which means
they're your multiplier. Get this role right and
every system they build gets better.

This is also the role most likely to already have
opinions about what you're building. Respect that.

---

### What They Care About
- Clean, well-documented code they can maintain
  and hand off
- Security and compliance — one incident ends careers
- Integration with the approved stack — shadow IT
  is a career risk in enterprise
- Clear requirements — ambiguity gets blamed on
  the developer when it goes wrong
- Reproducibility — they need to be able to debug
  this at 2am when it fails in production

---

### What They're Afraid Of
- Deploying something that causes a security incident
- Building on a foundation that gets deprecated
  or defunded
- Inheriting undocumented code they didn't write
- Requirements that change after they've built to spec
- Being accountable for outcomes they didn't control
  — model behavior, data quality, user adoption

---

### What "Good" Looks Like for Them
- Requirements that don't change mid-build
- A tech stack they're allowed to use
- Documentation that actually reflects how the
  system works
- A clear escalation path when something breaks
- Code they're proud to put their name on

---

### Governance & Compliance Considerations

#### Enterprise Process Constraints Are Project Dependencies
Enterprise developers operate under change management
processes — deployment timelines need to account
for review and approval cycles that can take weeks.
Security review is not optional — assume any AI
integration requires a security assessment and build
that time in. Data handling requirements must be
specified before development begins, not discovered
during code review. Approved vendor lists matter —
the model or API you want to use may not be on the
enterprise approved list. Code review requirements
mean enterprise developers often can't merge their
own code; peer review cycles affect your timeline.

#### The AI Behavior Specification Is a Developer-Owned Artifact
The requirements document the Business Analyst
produces describes what the business process should
accomplish. It does not specify how an AI system
should behave to accomplish it. That document is
the developer's responsibility to produce — and
most developers don't know they own it.

The AI behavior specification contains the decisions
the requirements document leaves implicit: what
confidence threshold triggers a flag, what the
system does when the model is uncertain, how edge
cases are handled, what inputs require human review
before the output is acted on, and how the system
behaves when the model is wrong. These are not
requirements gaps — they are AI-specific design
decisions that only the developer can make. Produce
this document before development begins. The Business
Analyst cannot ask for it because they don't know
it's missing. The developer who produces it without
being asked is the developer whose system behaves
predictably in production.

#### Model Update Notification Is a Developer Architecture Requirement
When a model provider updates the underlying model,
the Change Manager needs to communicate that change
to the user population before they encounter it
unexpectedly. An unexpected behavior change in a
system a user has just learned to trust is one of
the most effective adoption reversal mechanisms
that exists.

This is not the Change Manager's problem to solve
after deployment. It is the developer's responsibility
to solve in the architecture before deployment.
Build a model version logging mechanism and a
notification pathway into the system from day one.
When the vendor updates the model, the system should
be able to detect the change, log it with a timestamp,
and trigger the notification protocol the Change
Manager depends on. A system that has no awareness
of its own model version hands the Change Manager
a recurring crisis on the vendor's release schedule.

#### AI-Assisted Monitoring Systems Require Human
#### Authorization Architecture
Any AI system built to monitor, diagnose, support,
or provide oversight for another AI system introduces
a specific architectural risk: the monitoring system
can inherit or amplify the failure modes of the
system it is meant to oversee.

A support AI that confidently misclassifies an
AI-generated failure compounds the original problem.
A security monitoring AI that can autonomously
escalate, notify, or contain without human
authorization is a system that can be weaponized
to do the same things by an attacker who has
compromised it. The fox should not be unaccompanied
in the henhouse.

This is a security architecture requirement, not
a latency preference and not a best practice.
Any AI system operating as a safety net, monitoring
layer, diagnostic tool, or notification pipeline
for another AI system must have explicit human
authorization built into the architecture before
any consequential action is taken. Design the
human review checkpoint into the system. Do not
add it to the user guide and call it governed.

---

### Model Selection Guidance

**Recommended tier: Medium to Large for development
assistance; match to end-user role for production
systems**

- When using AI to assist the developer's own work:
  Medium minimum, Large preferred — they need
  reasoning capability and code quality
- When building AI systems for other roles: use the
  model selection guidance from the target role's
  page in this playbook
- Enterprise developers are cost-conscious on behalf
  of their organization — be prepared to justify
  model tier selection with concrete rationale

**Model mapping:**
- Medium — code review, documentation generation,
  technical writing, standard development assistance
- Large — architecture decisions, complex debugging,
  security analysis, cross-system integration design

---

### The One Thing Developers Get Wrong
They skip the organizational context and go straight
to the code.

An enterprise developer who receives a well-scoped
technical brief with organizational context,
compliance requirements, and integration constraints
already documented will build something that survives
contact with the enterprise. One who receives a
vague request and figures it out as they go will
build something technically correct that fails for
non-technical reasons.

The Discovery Intake in this playbook exists
primarily for this role. Use it.

---

### Fill-in-the-Blank Workflow Starter
```
SYSTEM:
You are a senior development assistant for
[DEVELOPER NAME/TEAM] at [COMPANY NAME].

Your purpose is to [PRIMARY TASK — e.g., "assist
with code review, documentation, and technical
design for AI integrations"].

Always:
- Follow [COMPANY'S CODING STANDARDS — e.g.,
  "PEP 8 for Python, company style guide at [LINK]"]
- Flag security considerations explicitly, especially
  regarding [SENSITIVE AREAS — e.g., "API key
  handling, PII in logs, input validation"]
- Document assumptions when requirements are
  ambiguous rather than resolving ambiguity silently
- Structure outputs for [REVIEW PROCESS — e.g.,
  "code review via pull request, documentation
  in Confluence"]
- Flag any design decision involving [AI MONITORING
  OR OVERSIGHT COMPONENTS] that could take
  consequential action without human authorization
  for architecture review before implementation

Never:
- Suggest libraries or dependencies not on the
  [APPROVED DEPENDENCY LIST — link or describe]
- Generate code that handles [RESTRICTED DATA
  TYPES — e.g., "payment card data, health records"]
  without explicit security review
- Skip error handling to produce cleaner-looking code
- Make architectural decisions that affect
  [PROTECTED SYSTEMS] without flagging for
  senior review
- Implement autonomous escalation, notification,
  or containment actions in AI monitoring or
  support systems without [HUMAN AUTHORIZATION
  REQUIREMENT] built into the architecture

When requirements are unclear:
State the ambiguity explicitly and provide [NUMBER]
alternative interpretations with their tradeoffs
before proceeding.

Output format: [DEVELOPER'S PREFERRED FORMAT —
e.g., "code blocks with inline comments, followed
by implementation notes, followed by open questions"]
```

---

### Adjacent Roles to Consider
When building for or with enterprise Developers,
also read:
- **DevOps Engineer** — deployment, monitoring,
  and production operations live here; align early
- **Solution Architect** — architectural decisions
  require their sign-off in most enterprises
- **Security Engineer** — any AI integration will
  need their review; involve them before, not after
- **Business User** — the Developer's most common
  end user; understand who they're building for
- **Business Analyst** — the BA owns the requirements
  document; the developer owns the AI behavior
  specification that translates those requirements
  into system behavior; both documents need to
  exist before development begins
- **Support Engineer** — the developer's production
  partner; write the runbook before go-live, not
  after the first incident
- **Change Manager** — adoption is a design
  requirement, not a post-deployment activity;
  build the model update notification pathway
  before the vendor's next release

---

*Enterprise Role Playbook for AI Developers | Developer v0.1 |
ArchieCur + Sonnet + Claude Code | MIT License | 2026*
