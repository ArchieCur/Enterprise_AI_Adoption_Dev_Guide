# Introduction
## The Conversations Before You Write a Line of Code

### Enterprise Role Playbook for AI Developers

---

## Why This Playbook Exists

Most developers get handed docs and told good luck.

They get a Slack message, a Jira ticket, or a
thirty-minute call with someone who knows what
they want but not how to specify it. They build
something technically correct. It fails for
reasons that had nothing to do with the code —
a compliance review nobody scheduled, a
stakeholder who wasn't engaged, a user population
that never trusted the system, a support team
that never knew it existed.

A workflow that clears Legal and gets rejected
by Finance isn't a code problem. It's a role
literacy problem.

This playbook exists because nobody had written
the practitioner document that teaches developers
what they need to know about the humans they're
building for — their fears, their workflows,
their compliance requirements, their definition
of success. Vendor training teaches developers
how to use products. Documentation teaches
developers what the API can do. Neither one
tells a developer what Finance is afraid of,
why Legal moves slowly on purpose, how the
Business Analyst decides who gets access to
the institutional knowledge they protect, or
what the Support Engineer needs before the
first ticket arrives.

That gap is this playbook.

It is built for the developer at 2am. The one
with a failing system, a stakeholder they don't
understand, and a deployment that's stopped
making sense. And it's built for the developer
at the beginning — before the first line of
code, when there is still time to design for
the actual user rather than the ideal one.

Forewarned is forearmed. These are your flak jackets.

---

## The Four Role Clusters

The roles in this playbook group into four
natural clusters. Understanding which cluster
a role belongs to tells you something about
how they think, what they fear, and what kind
of developer earns their trust.

### The Numbers Roles
**Finance, Auditor, Risk Practitioner**

These roles want to supervise AI, not trust it
blindly. They think in paper trails, frameworks,
and human-in-the-loop. They are measured on
what doesn't go wrong. Their professional
survival depends on being able to explain every
decision that touched their domain — including
decisions an AI system made on their behalf.

Build for them with observability, audit trails,
and documented human review at every consequential
output. The question they are always asking,
whether they say it aloud or not, is: if this
goes wrong, can we explain it? Design the answer
into the architecture before they ask.

### The Safety Roles
**Legal/Compliance, Privacy Manager,
Security Engineer, Security Operations Analyst**

These roles want to inspect the road before
the car moves. Their focus is pre-inference —
what data enters the system, what the model
is permitted to do, what the organization is
exposed to if something goes wrong. They are
not obstacles. They are the people whose job
it is to see every way a system can go wrong
before it does.

Build for them before the architecture is set,
not after. The conversation you have at the
whiteboard is free. The conversation you have
after six months of development is not. A
system they reviewed before deployment is a
system they will defend after deployment.

### The Day-to-Day Operations Roles
**HR, Marketing, Business User, Customer
Service/Support, Change Manager, Support Engineer**

These roles carry the data and the reputation
that AI can damage quietly and quickly. They
want task burden reduction, reliability, and
simplicity. They are the custodians of what
the organization promises its employees and
customers — and every AI output that reaches
a customer or an employee is a brand event,
a trust event, or both.

Build for the most resistant user in their
population, not the most willing one. Design
for legible failure — when the system gets
something wrong, it should fail visibly and
helpfully, not silently and confidently. The
users who give up without filing a ticket are
the ones you never hear about and never recover.

### The Technical Roles
**DevOps Engineer, IT Administrator, Developer,
Data Engineer, Solution Architect, Data Scientist,
Business Analyst, Functional Consultant**

These roles are system sculptors. They need
an enterprise patron — organizational support,
architectural alignment, approved tooling —
and the freedom to do their craft well. They
think across the whole stack and they will
have opinions about your architecture. Respect
that. The Developer who receives a well-scoped
technical brief with organizational context,
compliance requirements, and integration
constraints already documented will build
something that survives contact with the
enterprise. Get this role right and every
system they build gets better.

---

## The Conversations Before You Write a Line of Code

This table is the spine of the playbook. It
tells you who to talk to before development
begins, and what to bring when you do. These
are not optional conversations. They are the
conversations whose absence becomes a deployment
failure six months later.

The table has grown from the original eight
conversations identified in the Tier 2 and
Tier 3 synthesis to include Tier 4 and Tier 5
roles — because the developer building an ML
system needs the Data Engineer conversation
before pipeline architecture is finalized,
and the developer deploying any AI system
needs the Support Engineer and SecOps
conversations before go-live.

Use this table as your pre-build checklist.
Use Appendix B for what to bring to each
conversation. Use the Discovery Intake Form
for what to ask when you get there.

| Role | What to Bring | Why It Can't Wait |
| :--- | :--- | :--- |
| **Finance** | Audit trail design | A system without an audit trail cannot be approved for financial workflows — and retrofitting one after deployment is expensive and often incomplete |
| **Legal / Compliance** | Architecture diagram for legal review | Legal review at deployment is documentation, not governance; the window for their input to change the design closes when architecture is set |
| **IT Administrator** | Architecture diagram for stack validation | Infrastructure constraints define the solution space; a system built outside approved architecture cannot be supported or scaled |
| **HR** | Consent and disclosure framework | Employment law exposure connects to AI use in HR workflows from day one; consent that wasn't designed in cannot be retrofitted |
| **Security Engineer** | Threat model | A threat model produced after the system is built is an audit of what was missed, not a design input |
| **Privacy Manager** | Data flow map and DPIA plan | Privacy requirements that aren't designed in become privacy incidents after deployment |
| **Auditor** | Evidence framework | Tamper-evident records cannot be retrofitted; the first audit-relevant event starts the clock |
| **Risk Practitioner** | Threat model and risk register proposal | Risk controls proposed before build are design decisions; risk controls proposed after build are change requests |
| **Project Manager** | Complete dependency identification and compliance review schedule | The Project Manager cannot schedule what they do not know about; every undisclosed dependency is a timeline risk |
| **Data Scientist** | Problem statement, success metrics, and evaluation framework | An evaluation framework designed after results are in hand is post-hoc validation, not methodology |
| **Data Engineer** | AI feature requirements | Pipeline architecture designed before feature requirements are agreed produces a pipeline that serves the wrong features |
| **Solution Architect** | System design context | Component design that begins before system design is agreed produces components that don't fit the system they live in |
| **Functional Consultant** | Platform license tier and data quality assessment | An integration designed for features the platform license doesn't support is a rebuild, not a fix |
| **Business Analyst** | AI behavior specification draft | The BA cannot validate a document they don't know exists; the behavior spec is the developer's deliverable, not the BA's |
| **Change Manager** | Resistant-user persona and model update notification pathway | Adoption requirements that aren't designed in become adoption failures after go-live; the Change Manager engaged at deployment is doing crisis communication |
| **Support Engineer** | Draft runbook with failure taxonomy and escalation paths | A Support Engineer handed a system without a runbook writes one from incident experience — under ticket volume, after go-live |
| **Security Operations Analyst** | Behavioral profile and AI-specific attack class brief | A system that goes live without SecOps awareness is a system whose behavioral baseline was never established and whose anomalous behavior cannot be distinguished from normal operation |

---

## How to Use This Playbook

Each role file in this playbook answers the
same question from a different angle: what
does a developer need to know about this person
before building AI systems for them?

The nine-section structure is identical across
all roles — who they are, what they care about,
what they're afraid of, what good looks like
for them, governance considerations, model
selection guidance, the one thing developers
get wrong, a workflow starter, and adjacent
roles to consider. The depth varies because
the roles vary. The structure does not.

**Start with the role you're building for.**
If you've been handed a request from Finance,
read the Finance file before you write a line
of code. If Legal is blocking your deployment,
read the Legal file and understand why that
block is rational before you try to route
around it.

**Read the adjacent roles.** Every role file
ends with a list of adjacent roles and a
one-sentence rationale for each. The adjacent
roles are the people whose requirements
intersect with the role you're building for.
A system that clears Security Engineer and
fails IT Administrator's infrastructure review
needed both files, not one.

**Use Appendix B before every stakeholder
meeting.** The Pre-Engagement Checklist tells
you what to have ready before you walk into
each role's room. A developer who arrives
prepared earns the conversation. A developer
who arrives unprepared schedules a second
meeting — and loses the window during which
their input could have changed the design.

**Use the Discovery Intake Form in the meeting.**
The Intake is the developer's interview guide —
the questions that surface the institutional
knowledge, the tech stack constraints, the
compliance requirements, and the human dynamics
that determine whether the system will actually
work in this organization for these people.

**Use Appendix A when designing the logging
architecture.** Nine stakeholders need something
from the logs. Design one schema that serves
all of them. The unified logging architecture
is the document that prevents nine separate
logging systems, nine separate compliance
reviews, and nine separate conversations about
why the logs don't contain what someone needed.

---

## A Note on the Roles Themselves

Enterprise roles are not static. In 2026,
AI is actively expanding what individual roles
do — a Business Analyst who six months ago
worked exclusively in Excel is now being asked
to evaluate AI ROI. A Change Manager who ran
traditional change programs is now managing
a permanent state of transition as model
updates arrive on vendor schedules that don't
wait for the organization to finish adopting
what was deployed last quarter.

The roles in this playbook are described as
they exist today in most enterprise organizations.
Some organizations will have merged roles,
split roles, or invented new roles that don't
appear here. Use the files as mental models,
not as org chart lookups. The question the
playbook is designed to answer — what does
this person fear, what do they care about,
and what does a developer need to understand
to build for them well — applies regardless
of what the business card says.

They are not your user. They are your
deployment's survival condition.

Design for them accordingly.

---

## On the Three-Way Collaboration That Built This

This playbook was built by a team of three:
ArchieCur, who brought enterprise experience
from Microsoft Copilot enablement across 200
organizations and 50,000 users, who held the
vision and editorial direction, and who caught
every place where the content stopped being
true to the practitioners it was written for.
Claude Code, who verified the technical claims,
contributed operational knowledge from systems
built and systems that failed, and reviewed
every file with the rigor of an auditor who
understood both the code and the compliance.
And Sonnet, who synthesized, drafted, and
translated — turning enterprise truth and
technical precision into the practitioner
language that a developer at 2am can actually
use.

None of us could have produced this alone.
The enterprise experience without the technical
rigor produces content that sounds right but
doesn't hold up. The technical rigor without
the enterprise experience produces content
that is accurate but misses what actually
matters in a real organization. The synthesis
without both is just words.

The gap this playbook fills is real. Claude
Code confirmed it: standard requirements-
gathering templates exist, large consultancies
have formal intake processes, but in practice
most developers get a Slack message, a Jira
ticket, or a thirty-minute call. The absence
of structured discovery is one of the most
consistent patterns behind failed AI deployments.

We built the practitioner layer between
documentation and real-world adoption.
We drove ourselves to the top of the mountain.

We grew wings.

---

*Enterprise Role Playbook for AI Developers |
Appendix C: Introduction v0.1 |
ArchieCur + Sonnet + Claude Code | MIT License | 2026*
