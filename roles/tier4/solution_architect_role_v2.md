# Solution Architect
## Enterprise Role Playbook for AI Developers

---

### Who This Person Is
The Solution Architect is the enterprise's systems thinker —
the person responsible for ensuring that individual technical
decisions add up to a coherent whole. They design the
architecture that connects business requirements to technical
implementation, evaluate the trade-offs between competing
approaches, and make the decisions that are expensive to
reverse later. They think across the entire stack: business
requirements, application architecture, data architecture,
integration patterns, security model, scalability, and
operational requirements — simultaneously.

They are not the developer who writes the code. They are
the person who decides what gets written, how it connects
to everything else, and whether the system will still make
sense in three years when the requirements have changed
and the original team has moved on. They have a long memory
for architectural decisions that seemed reasonable at the
time and became expensive later, and they are professionally
cautious about novelty for its own sake.

AI systems have given Solution Architects a new category
of architectural decision that didn't exist five years ago:
where does intelligence live in the system? What is the
boundary between deterministic logic and probabilistic
model output? How does the system behave when the model
is wrong? These are not questions that have established
patterns yet, and the Solution Architect is making
consequential bets on emerging best practices.

They need a developer who understands that AI architecture
decisions are architecture decisions — with the same
long-term implications, the same trade-offs, and the
same need for deliberate design that any other architectural
choice carries.

---

### What They Care About
- Fitness for purpose — does the architecture actually
  solve the business problem, or does it solve a
  technically interesting problem that approximates it?
- Integration coherence — how does the AI system connect
  to the existing enterprise architecture? what are the
  integration points, the data contracts, and the
  failure modes at each boundary?
- Scalability and cost — what does this system cost
  to run at the expected volume, and what does it
  cost when volume doubles? AI inference costs at
  scale are not always obvious from development costs
- Replaceability — can components of the system be
  replaced without rebuilding everything? vendor
  lock-in at the model layer is a real architectural
  risk that needs to be designed against
- Operational simplicity — a system that requires
  heroic effort to operate is a system that will
  be operated poorly; complexity has a cost that
  shows up in incidents, not in design reviews

---

### What They're Afraid Of
- Architectural decisions made at the component level
  that create enterprise-level problems — a model
  provider selected by a single team that becomes
  a concentration risk across twenty systems
- AI capabilities that work in demos and fail in
  production at scale — the gap between prototype
  performance and production performance is wider
  for AI systems than for most traditional software
- Vendor lock-in disguised as integration — a system
  so deeply coupled to a specific model provider's
  proprietary features that switching providers
  requires a rebuild
- An AI system that cannot fail gracefully — when
  the model produces a wrong answer, what does
  the system do? if the answer is "passes it through
  confidently," that is an architectural problem
- Technical debt introduced at the AI layer that
  compounds into the rest of the architecture —
  a poorly designed prompt management system,
  an ad-hoc retrieval architecture, an unversioned
  model dependency

---

### What "Good" Looks Like for Them
- An AI architecture that fits within the existing
  enterprise architecture patterns rather than
  requiring a parallel architecture to support it
- Clear boundaries between what the AI does and
  what deterministic logic handles — with explicit
  design decisions about each boundary
- A cost model that holds at production volume —
  not a development cost estimate that surprises
  everyone six months after deployment
- Documented trade-offs — the Solution Architect
  does not expect perfect decisions, they expect
  documented decisions with acknowledged trade-offs
- A system that can accommodate the next requirement
  without a fundamental redesign — extensibility
  is not a feature, it is a design quality

---

### Governance & Compliance Considerations

#### AI Architecture Decisions Require Enterprise Architecture Review
In organizations with formal enterprise architecture
governance, AI system architecture should go through
the same review process as any other significant
architectural decision. This includes alignment with
enterprise integration patterns, security architecture
standards, data architecture principles, and approved
technology stacks. A developer who builds an AI system
outside the enterprise architecture review process
may produce something that works but cannot be
supported, scaled, or integrated with the rest of
the enterprise without significant rework.

#### Model Provider Selection is an Enterprise Architecture Decision
Choosing a model provider is not a development decision —
it is an architecture decision with enterprise-wide
implications. Which providers are on the approved
vendor list? What are the data residency requirements?
What are the contractual terms for data processing?
What is the provider's API stability and deprecation
policy? These questions need Solution Architect
involvement, not just developer preference. A model
provider selected without architecture review can
create vendor concentration risk, compliance exposure,
or integration problems that affect systems far beyond
the one being built.

#### The Build vs. Buy vs. Orchestrate Decision Requires Formal Evaluation
AI systems can be built from components, purchased as
packaged solutions, or assembled by orchestrating
existing services. Each approach has different cost
profiles, capability ceilings, vendor dependency
implications, and customization limits. The Solution
Architect needs to evaluate these options systematically
before the first line of code is written. A build
decision made without evaluating the buy option, or
a buy decision made without understanding the
customization limits, is an architectural risk that
surfaces at the worst possible moment.

#### Integration Contracts Must Be Explicit and Versioned
Every point where an AI system connects to another
enterprise system is an integration contract —
a set of assumptions about data formats, availability,
latency, and behavior that both sides depend on.
These contracts need to be explicit, documented,
and versioned. An AI system that depends on an
undocumented API behavior in an adjacent system
is a system that will break unpredictably when
that system changes. Design integration contracts
with the same rigor as internal interfaces.

#### Responsible AI Principles Need Architectural Expression
Responsible AI is not a policy document — it is an
architectural requirement. Fairness constraints,
explainability requirements, human oversight mechanisms,
and auditability obligations all need to be expressed
in the architecture, not just stated in the governance
documentation. The Solution Architect is the person
who ensures that the responsible AI principles the
organization has committed to are actually implemented
in the system's design, not just referenced in a
slide deck.

---

### Model Selection Guidance

**Recommended tier: Small to Large, task-dependent**

- Solution Architects use AI tools primarily for
  design support, documentation, and analysis —
  tasks that benefit from reasoning depth and
  contextual understanding
- Small for structured, formatting-heavy architecture
  tasks with well-defined inputs and outputs:
  architecture documentation formatting from
  structured inputs, ADR (Architectural Decision
  Record) template population from structured notes,
  integration specification table formatting,
  approved stack checklist generation. Note:
  trade-off analysis, vendor evaluation, and
  multi-system reasoning should begin at Medium.
  Small models applied to architecture judgment
  tasks can produce outputs that look complete and
  well-structured while missing the cross-system
  implications that make architecture decisions
  consequential — and Solution Architect Small-model
  use cases tend to creep. A developer who starts
  with "populate this ADR template" can drift toward
  "analyze these trade-offs" without realizing they
  have moved into territory where Small models will
  fail them inconsistently.
- Medium for architecture documentation, pattern
  library generation, trade-off analysis from
  structured inputs, integration specification
  drafting
- Large for complex multi-system architecture
  analysis, responsible AI requirements mapping,
  cross-domain trade-off synthesis, and
  architectural decision record drafting where
  nuanced judgment across competing constraints
  is required

**Model mapping:**
- Small — architecture documentation formatting
  from structured inputs, ADR template population
  from structured notes, integration specification
  table formatting, approved stack checklist
  generation
- Medium — architecture documentation, integration
  specification drafting, pattern analysis,
  structured trade-off comparison
- Large — multi-system architecture review,
  responsible AI architecture analysis, complex
  vendor evaluation synthesis, architectural
  decision records for high-stakes choices

**On AI as an architectural component:**
When the Solution Architect is evaluating AI as
a component in a larger system — not using AI
as a productivity tool — the selection criteria
are entirely different: fit with enterprise
architecture standards, integration complexity,
operational requirements, cost at scale, and
vendor risk. The Solution Architect should be
in every conversation where a model provider
is being selected as an enterprise component,
not just the conversations where a specific
application is being designed.

---

### The One Thing Developers Get Wrong
They design the AI component and assume the
architecture around it.

The AI system works. The model produces good outputs.
The demo is compelling. And then the Solution Architect
asks: how does this connect to the identity management
system? what happens when the model API is unavailable?
how does this handle the data residency requirements
for the European users? what is the cost model at
ten times current volume? how does a second team
consume this capability without duplicating the
infrastructure?

These are not questions about the AI component.
They are questions about the system the AI component
lives in — and the developer who designed the component
without designing its place in the system cannot
answer them.

AI architecture is not different from other architecture
in this respect: components don't exist in isolation.
They exist in systems, and the system properties —
scalability, reliability, security, cost, maintainability —
emerge from the design of the whole, not the quality
of individual parts.

Bring the Solution Architect in before the component
is designed. Design the system, then design the
component that fits within it. A well-designed
component in a poorly designed system will fail.
A well-designed system can accommodate a component
that needs improvement.

---

### Fill-in-the-Blank Workflow Starter
```
SYSTEM:
You are an architecture support assistant for
[TEAM NAME] at [COMPANY NAME].

Your purpose is to [PRIMARY TASK — e.g., "support
solution architecture workflows by generating
architectural decision records, integration
specifications, and trade-off analyses for
AI system design decisions"].

Always:
- Apply [ARCHITECTURE FRAMEWORK — e.g., "the
  enterprise architecture principles documented
  in [REFERENCE]"] to all architecture analysis
  outputs
- Flag any design decision involving
  [HIGH-RISK AREAS — e.g., "new vendor selection,
  cross-system data contracts, or departures from
  approved integration patterns"] for Solution
  Architect review before documenting as a decision
- Structure trade-off analyses with [REQUIRED
  DIMENSIONS — e.g., "cost, scalability, vendor
  risk, integration complexity, and operational
  requirements"] consistently across all options
  evaluated
- Include [RESPONSIBLE AI DIMENSIONS — e.g.,
  "fairness, explainability, human oversight,
  and auditability"] in all architecture
  documentation for AI system components
- Version all architectural decision records
  with [VERSION FIELDS — e.g., "decision date,
  decision owner, options considered, decision
  made, trade-offs acknowledged, review date"]

Never:
- Document an architectural decision as final
  without [REVIEW REQUIREMENT — e.g., "Solution
  Architect sign-off and enterprise architecture
  review board approval for decisions above
  [THRESHOLD]"]
- Recommend a vendor or technology not on
  [APPROVED STACK — e.g., "the current enterprise
  approved technology list"] without flagging
  the exception and routing to [ARCHITECTURE
  GOVERNANCE CONTACT]
- Produce cost estimates without [REQUIRED
  SCENARIO — e.g., "current volume, 3x volume,
  and 10x volume projections with stated assumptions"]
- Document an integration as stable without
  [CONTRACT EVIDENCE — e.g., "a versioned API
  specification or SLA from the providing system"]

When a design decision has no established enterprise
pattern:
Document it as a novel decision. Flag for architecture
review. Identify the assumptions being made and
the conditions under which the decision should
be revisited.

Output format: [ARCHITECTURE TEAM'S PREFERRED FORMAT —
e.g., "architectural decision record with context,
decision, options considered, trade-offs, consequences,
and review schedule"]
```

---

### Adjacent Roles to Consider
When building for Solution Architects, also read:
- **IT Administrator** — infrastructure constraints
  define the solution space; Solution Architect's
  design must fit within what IT Administrator
  can support, procure, and operate
- **Security Engineer** — security architecture
  is a dimension of solution architecture;
  Solution Architect and Security Engineer need
  aligned threat models and security design
  patterns before architecture is finalized
- **DevOps Engineer** — operational requirements
  shape architectural decisions; a system that
  cannot be operated reliably is not a well-designed
  system regardless of its functional correctness
- **Data Engineer** — data architecture is a
  core dimension of AI system architecture;
  Solution Architect and Data Engineer need
  aligned decisions about data flows, storage,
  and pipeline design before either can finalize
  their respective architectures

---

*Enterprise Role Playbook for AI Developers | Solution Architect v0.1 |
ArchieCur + Sonnet + Claude Code | MIT License | 2026*
