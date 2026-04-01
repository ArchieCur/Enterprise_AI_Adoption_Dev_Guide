# Functional Consultant
## Enterprise Role Playbook for AI Developers

---

### Who This Person Is
The Functional Consultant is the enterprise's translator —
the person who speaks both business and technology fluently
enough to stand between them and make sure neither side
loses something critical in the conversation. They are
typically aligned to a specific enterprise platform —
SAP, Salesforce, ServiceNow, Microsoft Dynamics, Workday —
and they know that platform's capabilities, limitations,
and configuration options with a depth that comes from
years of implementation experience.

They think in business processes, configuration options,
and implementation patterns. They understand what the
platform can do out of the box, what requires configuration,
what requires customization, and what requires a workaround
that will become technical debt within eighteen months.
They have sat in enough requirements workshops to know
that what stakeholders say they want and what they actually
need are often different things — and that the job is to
figure out the difference before it becomes a change order.

AI capabilities are being embedded into every major
enterprise platform right now. The Functional Consultant
is on the front line of this change — configuring AI
features in platforms they know deeply, advising clients
on AI adoption within workflows they understand intimately,
and navigating the gap between what the platform's AI
features promise in the sales deck and what they actually
deliver in a configured enterprise environment.

They are not AI researchers. They are AI implementers —
and the quality of their implementation advice is the
quality of the AI adoption it produces.

---

### What They Care About
- Business process fit — does the AI capability actually
  improve the business process it is being applied to,
  or does it add complexity without proportionate value?
- Platform alignment — AI features that work within
  the platform's existing architecture are more
  sustainable than custom AI layers bolted on top;
  they know where the platform's AI capabilities
  end and where custom development begins
- Client adoption — a technically correct implementation
  that the client's users don't adopt is a failed
  implementation; the Functional Consultant thinks
  about change management as a design constraint,
  not an afterthought
- Configuration vs. customization discipline — every
  customization creates upgrade risk and maintenance
  burden; AI features that require deep customization
  to be useful are features to approach carefully
- Requirement completeness — missing requirements
  discovered during implementation are more expensive
  than requirements discovered during design

---

### What They're Afraid Of
- AI features that work in the demo environment
  and fail in the configured client environment —
  the gap between sandbox and production is where
  Functional Consultant credibility gets spent
- Client expectations set by vendor AI marketing
  that the actual platform AI features cannot meet —
  they are often the person who has to deliver
  that conversation
- AI outputs that interact badly with downstream
  platform processes — a generated field value
  that triggers an unexpected workflow, a
  suggested record that violates a platform
  validation rule, an AI recommendation that
  conflicts with configured business rules
- Scope creep driven by AI enthusiasm — clients
  who see AI capabilities and immediately want
  to apply them everywhere, without understanding
  the implementation and maintenance implications
- Being the last person to find out about a
  compliance or data governance requirement
  that affects the AI implementation they
  already designed

---

### What "Good" Looks Like for Them
- AI features that are configured, not customized —
  sustainable, upgradeable, and supportable by
  the client's internal team after the implementation
  engagement ends
- Clear boundaries between what the platform's
  native AI does and what requires additional
  development — no surprises for the client
  about what is included in the implementation scope
- Adoption metrics that show users actually using
  the AI features — not a technically complete
  implementation that collects dust
- A requirements process that surfaced the edge
  cases before implementation, not during testing
- A client who understands what the AI feature
  does, what it doesn't do, and what to do
  when it produces an unexpected output

---

### Governance & Compliance Considerations

#### Platform AI Features Inherit Platform Data Governance
AI features embedded in enterprise platforms —
copilots, suggested actions, automated summaries,
intelligent routing — process data that lives in
that platform. The data governance and compliance
requirements that apply to the platform apply to
its AI features. A Salesforce AI feature that
accesses customer records operates under the same
data handling obligations as the CRM itself.
A Workday AI feature that processes HR data
operates under employment law and privacy
requirements. Functional Consultants need to
confirm that AI feature configuration satisfies
existing data governance requirements before
enabling features in production.

#### Vendor AI Feature Updates Can Change Compliance Posture
Enterprise platform vendors update their AI features
on their own release schedules, which may not align
with the client's change management or compliance
review cycles. A platform AI feature that was
compliant at implementation may behave differently
after a vendor update. Functional Consultants need
to advise clients to include platform AI features
in their ongoing compliance monitoring, not just
their initial implementation review.

#### AI-Generated Content in Business Records Creates Audit Questions
When AI features generate or suggest content that
is saved to business records — a summarized case
note, a suggested contract clause, a generated
email — that content becomes part of the record.
Auditors, regulators, and legal counsel may ask
whether the content was human-authored or AI-generated,
and the answer has implications for how the record
is interpreted. Configure AI features to mark
AI-generated content clearly, and advise clients
on their record-keeping obligations for AI-assisted
documentation.

#### Customization Scope Determines Compliance Responsibility
When AI capabilities are delivered through platform
native features, the vendor carries significant
responsibility for their compliance posture. When
AI capabilities require custom development — custom
models, custom integrations, custom logic — the
compliance responsibility shifts substantially
to the implementing organization. Functional
Consultants need to understand where this boundary
falls for each AI feature in scope and advise
clients accordingly.

#### Change Management for AI Features Requires Different Framing
AI features change user workflows in ways that differ
from traditional feature releases. They introduce
outputs that users need to evaluate, not just consume.
They require new user behaviors — checking AI suggestions,
flagging incorrect outputs, understanding when not
to trust the system. Change management programs
for AI feature adoption need to address these
behaviors explicitly, not just train users on
where to click. Functional Consultants who treat
AI feature rollout like any other feature release
will see adoption rates that reflect the difference.

---

### Model Selection Guidance

**Recommended tier: Small to Medium, platform-constrained**

- The Functional Consultant's model selection is
  largely determined by the platform they implement —
  most enterprise platforms offer AI features at
  specific capability tiers with limited external
  model selection flexibility
- Small for structured, high-volume platform tasks
  where AI assistance is embedded in configured
  workflows: field suggestions, record categorization,
  routing recommendations, template generation
  from structured data
- Medium for more complex platform AI use cases:
  case summarization, document analysis, cross-record
  synthesis, and recommendation generation where
  nuance and context matter

**Model mapping:**
- Small — field suggestions, record categorization,
  routing logic, template population from structured
  data, simple workflow automation
- Medium — case and ticket summarization, document
  analysis within platform context, cross-record
  synthesis, intelligent recommendation generation

**On platform AI capability tiers:**
Many enterprise platforms offer AI features in
tiered packages — basic, standard, advanced — that
map loosely to Small/Medium/Large capability levels.
Functional Consultants need to understand which
platform AI tier is included in the client's license
and what the upgrade path and cost look like before
scoping AI features into an implementation. An AI
feature scoped at implementation that requires
a license upgrade to deliver is a scope and budget
problem.

---

### The One Thing Developers Get Wrong
They build for the platform's AI capabilities without
understanding the client's process maturity.

The platform AI feature is configured. It works.
It produces outputs that are technically correct.
And the users don't trust it, don't use it, or use
it incorrectly in ways that create downstream problems.

AI features in enterprise platforms fail at adoption
when the client's process maturity doesn't match
the feature's assumptions. A case routing AI that
assumes clean, consistent case categorization will
underperform in a client where case categorization
is inconsistently applied. A contract summarization
feature that assumes well-structured documents will
struggle with the client's actual contract repository.
An intelligent approval routing system that assumes
clear approval authority will create confusion in
an organization where authority is informally distributed.

The technical implementation is necessary but not
sufficient. The Functional Consultant's value is in
understanding the gap between the platform's AI
assumptions and the client's actual operating reality —
and designing the implementation to bridge that gap,
or to be honest with the client about why it can't.

Developers who hand off a technically complete AI
implementation without this conversation have handed
off half an implementation.

---

### Fill-in-the-Blank Workflow Starter
```
SYSTEM:
You are a functional consulting assistant supporting
[CONSULTANT NAME / TEAM NAME] at [COMPANY NAME],
implementing [PLATFORM NAME] for [CLIENT NAME].

Your purpose is to [PRIMARY TASK — e.g., "support
the implementation of [PLATFORM] AI features by
generating configuration documentation, requirements
gap analysis, and change management content for
[CLIENT NAME]'s [BUSINESS PROCESS] workflow"].

Platform context:
- Platform: [PLATFORM NAME, VERSION]
- AI features in scope: [LIST — e.g., "Einstein
  Case Classification, Einstein Article Recommendations"]
- License tier: [TIER — e.g., "Enterprise with
  Einstein for Service add-on"]
- Custom development in scope: [YES/NO — if yes,
  list components]

Always:
- Distinguish clearly between [DELIVERY TYPES —
  e.g., "native platform configuration, custom
  configuration, and custom development"] in all
  documentation and client communications
- Flag any AI feature requirement that exceeds
  [PLATFORM CAPABILITY BOUNDARY — e.g., "native
  Einstein capabilities without custom model
  development"] for scope review before client
  commitment
- Include [CHANGE MANAGEMENT ELEMENTS — e.g.,
  "user behavior changes required, training
  implications, and adoption success metrics"]
  in all AI feature implementation documentation
- Apply [DATA GOVERNANCE STANDARD — e.g.,
  "client's data classification policy and
  [PLATFORM] data handling requirements"] to
  all AI feature configuration recommendations
- Document AI-generated content marking
  requirements per [CLIENT RECORD-KEEPING POLICY]

Never:
- Commit to AI feature delivery that requires
  [OUT-OF-SCOPE COMPONENTS — e.g., "custom model
  development, third-party AI integration, or
  platform license upgrades"] without explicit
  scope and budget approval
- Configure AI features that access
  [RESTRICTED DATA — e.g., "compensation records,
  privileged communications, or regulated client
  data"] without [GOVERNANCE SIGN-OFF]
- Recommend enabling a platform AI feature
  in production without [TESTING REQUIREMENT —
  e.g., "configuration testing in sandbox,
  UAT with client super users, and sign-off
  from [CLIENT CONTACT]"]
- Document a platform AI feature as compliant
  with [REGULATORY REQUIREMENT] without
  [VALIDATION — e.g., "Legal or Compliance
  review of the specific feature configuration"]

When a client requirement cannot be met by
platform native AI capabilities:
Document the gap explicitly. Present the options:
custom development, third-party integration,
process redesign, or descoping. Do not imply
the requirement can be met without flagging
the delivery approach and its implications.

Output format: [CONSULTING TEAM'S PREFERRED FORMAT —
e.g., "requirement ID, platform capability mapping,
delivery approach, configuration notes, change
management implications, open questions,
client sign-off field"]
```

---

### Adjacent Roles to Consider
When building for Functional Consultants, also read:
- **Business Analyst** — Functional Consultants
  and Business Analysts often share requirements
  gathering responsibilities; understand the
  division of accountability for requirement
  completeness in the specific engagement
- **IT Administrator** — platform AI features
  operate within the client's IT environment;
  IT Administrator's requirements for security,
  access control, and integration affect what
  AI features can be configured and how
- **Solution Architect** — when AI implementation
  scope extends beyond platform native capabilities,
  Solution Architect needs to be involved in
  the architecture of the custom components;
  Functional Consultant defines what is needed,
  Solution Architect designs how to build it
- 

---

*Enterprise Role Playbook for AI Developers | Functional Consultant v0.1 |
ArchieCur + Sonnet + Claude Code | MIT License | 2026*
