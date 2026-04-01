# Business Analyst
## Enterprise Role Playbook for AI Developers

---

### Who This Person Is
The Business Analyst is the enterprise's institutional
memory — the person who knows not just how the org
says it works, but how it actually works. They have
mapped the business processes, documented the
requirements, and accumulated the undocumented
knowledge that lives in no system and appears in
no org chart: the informal decision rules, the
exception handling that keeps operations running,
the relationships that move things forward when
the official process stalls. They are the custodian
of the secret sauce.

They think in processes, data flows, and business
outcomes. They speak in requirements documents,
swimlane diagrams, and ROI analyses. They live in
Excel workbooks, BI dashboards, and stakeholder
meetings where they are simultaneously gathering
information, protecting information, and evaluating
everyone in the room for trustworthiness. They have
broad industry knowledge, deep organizational
knowledge, and a finely calibrated sense of what
information goes where and what stays in the room.

They are also skilled organizational politicians —
and that is not a criticism. It is a description
of what the job requires. A Business Analyst who
cannot navigate the politics of an enterprise cannot
do their job. They have the ear of the C-Suite
because they have earned it. They influence budgets
and investment decisions because their analysis
is the lens through which leadership understands
operational reality. They protect institutional
knowledge because they have watched what happens
when it ends up in the wrong hands.

AI is arriving in the BA's world primarily as a
productivity tool — a faster way to process the
data they already work with, draft the documents
they already produce, and surface the insights
they already know how to find. They are not yet
thinking of AI as a workflow transformation. They
are thinking of it as a better version of the
tools they already trust. The developer who meets
them there, rather than arriving with a transformation
agenda, will earn the conversation that actually
matters.

---

### What They Care About
- Requirements completeness — a requirement that
  looks complete and isn't is more dangerous than
  a requirement that is obviously incomplete;
  the BA's professional reputation rests on
  producing requirements that can be built to
- Process integrity — AI should improve the
  business process, not expose its gaps to
  people who don't need to know they exist
- Organizational trust — access to business
  stakeholders and subject matter experts is
  granted on the BA's judgment; they will
  facilitate that access when the value is
  clear and the risk is manageable
- ROI visibility — they will be asked whether
  the AI system was worth the investment, and
  they need a framework for answering that
  question that holds up to C-Suite scrutiny
- Institutional knowledge protection — the
  undocumented logic that makes the org work
  is not theirs to share indiscriminately;
  they are its custodian, not its distributor

---

### What They're Afraid Of
- An AI system that automates a broken process
  faster — they know where the process breaks;
  if the developer doesn't ask, the system will
  make the breakage worse at scale
- Being measured on outcomes they didn't define —
  if the AI system underperforms against a metric
  the BA didn't establish, they will be the person
  explaining it to the C-Suite
- Losing the C-Suite relationship — a system
  that produces analysis the BA can't stand
  behind, or that bypasses the BA's role in
  surfacing insights, is a threat to the
  professional position they have built
- Institutional knowledge exposure — a developer
  who doesn't understand what they've been given
  access to, or who shares it carelessly, creates
  organizational damage the BA will be blamed for
- AI outputs that look like analysis but aren't —
  a dashboard that surfaces AI-generated insights
  without clearly distinguishing them from
  validated analysis is a credibility risk
  for everyone whose name is on the work

---

### What "Good" Looks Like for Them
- A developer who demonstrates they understand
  what they're being given and will protect it —
  trust is the prerequisite for the real
  conversation, and the real conversation is
  the prerequisite for a complete requirements
  picture
- AI that makes the BA faster and more precise
  without changing what they're responsible for —
  augmentation, not replacement
- A measurement framework for the AI system
  that the BA helped design and can defend to
  the C-Suite — not a framework handed to them
  after deployment that doesn't match how they
  think about value
- Process documentation that surfaced the edge
  cases and exceptions before the system was
  built — not discovered during UAT
- Clean handoff of institutional knowledge into
  system requirements without exposing what
  doesn't need to be exposed

---

### Governance & Compliance Considerations

#### Requirements Documents Are Not AI Behavior Specifications
The BA's requirements document describes what the
business process should accomplish. It does not
specify how an AI system should behave to accomplish
it. These are different documents serving different
purposes, and the gap between them is where most
AI implementation failures begin. "Flag the anomalies"
is a complete business requirement. It is not a
complete AI behavior specification — it contains
hidden decisions about what counts as an anomaly,
what confidence threshold triggers a flag, what
happens when the model is uncertain, and who
reviews flagged items before action is taken.
The developer's job is to surface these hidden
decisions explicitly, in collaboration with the
BA, before a line of code is written. A requirements
document signed off by the BA is the beginning
of the specification process, not the end of it.

What to bring to this conversation: a draft AI
behavior specification — the document the BA
doesn't know to ask for because they don't know
it's missing. It should contain the hidden decisions
the requirements document leaves implicit: confidence
thresholds, failure handling behavior, edge case
treatment, human review triggers, and what the
system does when the model is uncertain or wrong.
The BA cannot validate a document they don't know
exists. The developer who produces it and walks
the BA through it earns the second conversation —
the one where the BA's institutional knowledge
of where the process actually breaks becomes
available to the developer who has demonstrated
they understand what they're building.

#### ROI Measurement for AI Systems Requires a New Framework
Business Analysts are being asked to calculate AI
ROI in almost every enterprise right now, and most
are applying cost-savings logic to systems that
create value in ways that don't show up as cost
savings. Time saved on a task that the BA doesn't
measure is invisible ROI. Decision quality
improvements don't appear in a cost center.
Errors prevented don't generate a line item.
The developer who helps the BA build a measurement
framework before deployment — one that captures
what the system actually does well — is the
developer whose system survives the six-month
budget review. The developer who leaves
measurement to chance will watch their system
get defunded based on the wrong metric.

#### Process Documentation Reveals Pre-existing Gaps
The BA's process maps and swimlane diagrams are
the most valuable artifact a developer can get
access to — and they frequently reveal that the
process the AI system is being asked to support
has gaps, exceptions, and informal workarounds
that nobody documented because everyone just
knew about them. An AI system built to the
documented process will encounter the undocumented
reality in production. Ask the BA where the
process breaks before you build. The answer
will change the architecture.

#### Institutional Knowledge Has Governance Implications
The undocumented organizational knowledge a BA
holds — the informal decision rules, the exception
handling, the relationship logic — often contains
information that has data privacy, competitive
sensitivity, or regulatory implications that
aren't obvious until it's been fed into a system.
Before incorporating institutional knowledge into
AI system design, understand what category of
information it represents and whether its use
in an AI system requires Legal or Compliance
review. The BA protected it for a reason. Find
out what that reason is.

#### The BA's C-Suite Relationship Affects System Longevity
An AI system that the BA cannot explain to the
C-Suite, cannot defend in a budget review, or
cannot take credit for recommending will not
survive the organization's next planning cycle
regardless of its technical quality. The BA's
relationship with senior leadership is a
deployment dependency, not a soft factor.
Build it into the project plan. Engage the
BA on executive communication as early as
you engage them on requirements.

---

### Model Selection Guidance

**Recommended tier: Small to Medium, productivity-first**

- Business Analysts use AI primarily as a
  productivity layer on top of existing workflows —
  faster data processing, better document drafting,
  quicker synthesis of information they already
  know how to find
- Small for structured, high-volume, formatting-heavy
  tasks with well-defined inputs and outputs:
  requirements document formatting from structured
  notes, meeting summary generation from structured
  inputs, data dictionary formatting, standard
  report template population
- Medium for analytical support tasks where
  judgment and context matter: requirements gap
  analysis, process documentation synthesis,
  cross-functional impact assessment, ROI
  framework drafting, stakeholder communication
  drafting for C-Suite audiences

**Model mapping:**
- Small — requirements document formatting,
  meeting note summarization from structured
  inputs, data dictionary entry generation,
  standard report template population,
  action item extraction from structured records
- Medium — requirements gap analysis, process
  documentation synthesis, ROI framework
  development, stakeholder communication
  drafting, cross-functional impact assessment,
  BI dashboard insight narrative generation

**Critical:** Business Analysts will evaluate AI
tools against the analytical standards they already
hold themselves to. A tool that produces outputs
they cannot stand behind professionally will be
abandoned regardless of its efficiency gains.
The system prompt investment for BA-facing tools
should prioritize precision, citation of sources,
and explicit confidence levels over fluency.
A BA would rather have a careful answer than
a confident one.

---

### The One Thing Developers Get Wrong
They underestimate the Business Analyst and
overstimate the requirements document.

The title sounds administrative. The deliverable
looks complete. The sign-off has been obtained.
And the developer moves into build mode with
a requirements document that describes what
the business process should accomplish and
no specification for how the AI system should
behave when reality doesn't match the document.

The BA knows things the requirements document
doesn't say. They know where the process breaks,
which exceptions get handled informally, which
stakeholders will reject outputs that don't
match their mental model, and which edge cases
will appear at scale that never appeared in
the workshop. They didn't put these things in
the requirements document because requirements
documents don't have a field for "here is where
the org's secret sauce lives and here is how
the AI system needs to respect it."

The developer who earns the BA's trust will
get a second conversation — the one where the
real process picture emerges. The developer
who treats the BA as a requirements vending
machine will get vending machine output:
technically complete, strategically incomplete,
and missing exactly the institutional knowledge
that determines whether the system works in
production.

Earn the trust first. Ask where the process
breaks. Ask what the exceptions are. Ask how
success will be measured and who will be doing
the measuring. The BA has been waiting for
a developer who asks those questions. Most
of them are still waiting.

---

### Fill-in-the-Blank Workflow Starter
```
SYSTEM:
You are a business analysis assistant supporting
[BA NAME / TEAM NAME] at [COMPANY NAME].

Your purpose is to [PRIMARY TASK — e.g., "support
requirements documentation, process analysis,
and stakeholder communication for [PROJECT NAME]
affecting [BUSINESS PROCESS / DEPARTMENT]"].

Always:
- Distinguish clearly between [OUTPUT TYPES —
  e.g., "validated requirements, draft analysis
  for review, and preliminary findings requiring
  BA sign-off"] in every output
- Flag any requirement that contains
  [AMBIGUITY INDICATORS — e.g., "undefined
  thresholds, implicit assumptions about data
  quality, or behavior specifications that
  depend on context not provided"] for BA
  clarification before proceeding
- Apply [MEASUREMENT FRAMEWORK — e.g., "the
  agreed ROI metrics for this project: time
  saved, error rate reduction, and decision
  cycle time"] to all outputs that will be
  used in C-Suite reporting
- Cite the source and confidence level for
  every analytical finding — distinguish
  between [SOURCE TYPES — e.g., "documented
  process, BA-confirmed institutional knowledge,
  and inferred from available data"]
- Format all outputs for [AUDIENCE — e.g.,
  "C-Suite summary: 3 sentences maximum;
  technical specification: full detail with
  assumptions stated; stakeholder communication:
  business language, no technical jargon"]

Never:
- Present AI-generated analysis as validated
  findings without [REVIEW REQUIREMENT — e.g.,
  "BA review and explicit sign-off before
  any output is shared with stakeholders
  or used in decision-making"]
- Access [RESTRICTED INFORMATION — e.g.,
  "compensation data, M&A-related materials,
  or any information classified above
  [CLASSIFICATION LEVEL]"] outside of
  explicitly authorized workflows
- Generate ROI projections without
  [REQUIRED INPUTS — e.g., "agreed baseline
  metrics, measurement methodology confirmed
  by BA, and review period specified"]
- Share process documentation or institutional
  knowledge with [RESTRICTED AUDIENCES — e.g.,
  "external parties, cross-functional teams
  outside the project scope, or any audience
  not approved by BA"] without explicit
  authorization

When a requirement is ambiguous or contains
hidden assumptions:
Surface them explicitly. Do not resolve them
by assumption. Route to BA for clarification
before proceeding. Document the ambiguity
and the resolution in the requirements record.

Output format: [BA'S PREFERRED FORMAT — e.g.,
"requirement ID, business process reference,
success criteria, hidden assumptions surfaced,
open questions, confidence level, BA sign-off
field — with C-Suite summary variant available
on request"]
```

---

### Adjacent Roles to Consider
When building for Business Analysts, also read:
- **Business Leader** — the BA's analysis reaches
  the C-Suite through the Business Leader
  relationship; understanding what Business
  Leaders need to see and how they evaluate
  AI value is essential context for building
  systems the BA can champion upward
- **Data Analyst** — BA and Data Analyst overlap
  in organizations where the boundary between
  business requirements and data analysis is
  blurry; understand where one ends and the
  other begins before designing the system,
  and confirm which role owns the measurement
  framework for AI system performance
- **Project Manager** — the BA's requirements
  completeness directly affects the PM's ability
  to plan; misalignment between what the BA
  considers complete and what the developer
  needs to build creates schedule risk that
  surfaces at the worst possible moment
- **Finance** — the BA's ROI analysis will be
  scrutinized by Finance before it reaches
  the C-Suite; align the measurement framework
  with Finance's expectations before deployment,
  not after the six-month review

---

*Enterprise Role Playbook for AI Developers | Business Analyst v0.1 |
ArchieCur + Sonnet + Claude Code | MIT License | 2026*
