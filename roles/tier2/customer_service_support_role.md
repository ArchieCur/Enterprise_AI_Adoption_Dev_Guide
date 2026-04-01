# Customer Service / Support
## Enterprise Role Playbook for AI Developers

---

### Who This Person Is
Customer Service and Support is not a single role. It is a
spectrum — from the person who authors and maintains chatbot
response libraries, to Tier 1 agents handling routine
inquiries, to senior technical support specialists resolving
complex, multi-system problems that no knowledge base article
anticipated. The same job title can mean very different things
depending on where in that spectrum the person sits. Build for
the tier you are actually building for, not the label.

What unifies the spectrum is purpose: these are people who
are paid to solve other people's problems. They are, in
ArchieCur's framing, people who love helping people. They
operate in one of the most monitored, procedurally constrained
work environments in the enterprise — interactions are
recorded, notes are reviewed, metrics are tracked at the
individual level, and the rules for what to say, when to
escalate, and how to document are enforced, not suggested.

Support is delivered through more channels than most
developers account for: phone, live chat, email, chatbot,
knowledge base articles, quick reference guides, on-demand
video, webinars, social media, real-time troubleshooting
alongside training, account and billing inquiry, and order
management. Each channel has different interaction patterns,
different latency tolerances, and different definitions of
a successful outcome. A system that works for live chat
may be useless for email. A system designed for billing
inquiries may fail entirely for technical troubleshooting.

The chatbot layer is the most mature AI deployment in this
space and is demonstrably working. The human layer — how
AI enhances the work of human support agents — is actively
being explored. Developers entering this space are not
delivering a finished solution. They are participating in
an ongoing evolution. That is not a caveat. It is the
accurate description of the work.

---

### What They Care About
- Resolution — a support interaction that ends without
  solving the problem is a failed interaction regardless
  of how fast it was or how well the script was followed
- Handle time — average handle time is a primary metric
  at every tier; a system that improves resolution but
  increases handle time will face adoption resistance
  regardless of quality improvement
- Accuracy — wrong information given to a customer
  creates a second contact, a complaint, or a churn
  event; accuracy and speed are both measured and
  both matter
- Channel consistency — a customer who gets one answer
  on chat and a different answer on the phone has not
  been supported; they have been confused
- Escalation clarity — knowing when a problem exceeds
  their tier and where it goes next is as important
  as the ability to solve it; systems that blur
  escalation paths create agents who are stuck and
  customers who are frustrated

---

### What They're Afraid Of
- Job elimination — this is the most displacement-aware
  role in the enterprise; the "enhance or eliminate"
  tension is not hypothetical to them, it is the
  explicit conversation happening in their industry
- Being held accountable for AI output — if the system
  suggests a wrong answer and the agent uses it, the
  agent gets the performance mark; developers rarely
  think about where accountability lands when the
  AI is wrong
- Losing the human judgment that escalation requires —
  senior agents have developed pattern recognition for
  when a situation is about to go badly; systems that
  try to automate this judgment before it is understood
  will miss the cases that matter most
- Speed pressure that sacrifices quality — metrics-
  driven environments can pressure agents to accept
  AI suggestions without review; compliance on the
  surface, quality problems underneath
- Tool proliferation without workflow integration —
  agents already manage multiple systems simultaneously;
  an AI tool that requires context switching rather
  than integrating into the existing workflow adds
  cognitive load rather than reducing it

---

### What "Good" Looks Like for Them
- Suggested responses that are accurate enough to use
  with minor edits, not accurate enough to inspire
  rewriting from scratch
- Knowledge retrieval that surfaces the right article
  for the current interaction without the agent having
  to know the search terms — the system should
  understand the context, not just the keywords
- Real-time assistance that stays in the workflow —
  they should not have to leave their primary interface
  to get AI support
- Clear indication of confidence — agents need to know
  when an AI suggestion is reliable and when it should
  be verified before use; a system that presents
  uncertain answers with the same confidence as
  certain ones will be trusted or abandoned entirely,
  neither of which is the right outcome
- Escalation support that helps them document and
  hand off cleanly — the receiving tier should not
  have to re-ask questions the customer already answered

---

### Governance & Compliance Considerations

#### The Chatbot Layer and the Human Layer Have Different Risk Profiles
Chatbot support operates on a known, auditable script.
When it fails, it fails visibly and the customer escalates.
Human-layer AI support fails differently — the agent may
use a confident but incorrect AI suggestion, the error
may not surface until the customer calls back or churns,
and the accountability chain runs through the agent's
performance record, not the system's incident log.
Design the human-layer AI with explicit error visibility,
confidence indicators, and documentation of when AI
assistance was used in a given interaction.

#### Recorded Interactions Are Discoverable
Customer interactions — calls, chats, emails, agent notes —
are recorded and retained. In regulated industries,
these records are subject to compliance review,
legal discovery, and regulatory audit. Any AI output
that appears in an agent's response, note, or
documentation is part of that record. Ensure your
system's outputs are compliant with the applicable
regulatory framework before they can appear in
customer-facing or documented interactions. An AI
suggestion that violates a disclosure requirement
or makes an impermissible claim will appear in the
interaction record as if the agent said it.

#### Industry-Specific Compliance Governs What Can Be Said
Financial services support cannot provide advice that
constitutes financial guidance without licensing.
Healthcare support cannot provide clinical guidance.
Insurance support operates under state-specific
regulations on what can be offered or promised.
A general-purpose response generation system deployed
in a regulated industry without domain-specific
guardrails will produce non-compliant outputs.
Know the regulatory environment before building
the response layer.

#### PII Handling in Support Interactions Is High-Risk
Support agents handle PII constantly — account numbers,
identity verification data, payment information,
health information, order history. Any AI system
that processes interaction content is processing PII.
Apply data minimization: the system should handle
what it needs to support the interaction, not retain
a full transcript for model improvement without
explicit authorization and Privacy Manager review.
Context windows containing customer PII create
exfiltration and retention risks that the Privacy
Manager needs to assess before deployment.

#### Third-Party Contractor Environments Complicate Data Governance
A significant portion of enterprise support is delivered
by third-party contractors operating under their own
systems and policies. An AI deployment that touches
a contractor workforce raises data governance questions
that an internal deployment does not: Who owns the
interaction data? What are the contractor's obligations
under the DPA? Does the contractor's infrastructure
meet the enterprise's security requirements? These
questions need answers before the system is deployed
into a contractor environment, not after.  
  
One infrastructure reality developers frequently
discover late: a significant portion of contractor
support workforces operate on contractor-owned
hardware, behind contractor-managed firewalls,
accessing enterprise systems over VPN. The developer
is building for users they have no direct infrastructure
visibility into, on machines they did not configure,
behind security perimeters they did not design. A
system that works flawlessly in the enterprise
environment may be unreachable, throttled, or blocked
entirely by the contractor's infrastructure before
a single agent ever sees it. Add overseas contractors
to this picture — with their own data residency
obligations and jurisdictional requirements — and
the infrastructure complexity compounds further.
Confirm the full infrastructure path from system
to end user before architecture is finalized, not
after the first pilot fails.

#### Performance Metrics Drive Behavior — Design Accordingly
Support environments measure agents on handle time,
first contact resolution, customer satisfaction, and
accuracy. AI systems that improve some metrics while
degrading others will produce unexpected behavior.
Agents optimize for what is measured. If handle time
is the primary metric, agents will accept AI suggestions
faster than they should. If accuracy is measured,
they will over-verify. Design the system with the
existing metric environment in mind, and work with
the operations team to understand how the introduction
of AI tools will affect metric interpretation before
deployment.

---

### Model Selection Guidance

**Recommended tier: Small to Medium, channel and
tier dependent**

- Small for high-volume, structured, low-ambiguity
  support tasks: knowledge base article retrieval
  from well-defined queries, chatbot response
  generation from approved libraries, account status
  lookup and formatting, FAQ response generation
  from structured templates, ticket categorization
  and routing
- Medium for human-layer support assistance: real-time
  response suggestion requiring context understanding,
  interaction summarization for escalation handoff,
  sentiment detection and escalation flagging,
  multi-turn conversation context tracking,
  draft responses for complex inquiries
- Large only for senior technical tier support
  requiring synthesis across complex, multi-system
  problem spaces — and always with the expectation
  that the agent reviews before using

**Model mapping:**
- Small — chatbot response generation, FAQ matching,
  ticket routing, account inquiry formatting,
  knowledge base retrieval from structured queries
- Medium — real-time agent assist, interaction
  summarization, escalation documentation,
  response drafting for complex multi-turn interactions
- Large — senior technical tier synthesis,
  cross-system troubleshooting support,
  complex case documentation

**Critical:** Handle time pressure in support
environments will push agents to accept suggestions
faster than the model tier warrants. A Medium model
in a high-volume chat environment will be used like
a Small model under production pressure. Design
review friction that is appropriate to the accuracy
requirement, not just the capability tier. Speed
and accuracy are both requirements — build for both
simultaneously or the agents will choose speed.

---

### The One Thing Developers Get Wrong
They build for the chatbot and assume the human layer
works the same way.

Chatbot support is a closed system. The inputs are
predictable, the responses are from an approved library,
the failure mode is visible, and the customer self-
selects out by escalating. It is a tractable problem
and AI handles it well.

Human-layer support is an open system. The inputs are
unpredictable, the agent has discretion, the failure
mode is often invisible until the customer disappears,
and the accountability lands on the person, not the
system. Developers who have built successful chatbot
systems assume the human-layer problem is a larger
version of the same problem. It is not. It is a
different problem.

The human layer is also a journey, not a destination.
The industry does not yet have consensus on how AI
enhances human support agents at scale. Developers
entering this space are participants in that exploration.
The right posture is to build incrementally, measure
what actually changes in resolution quality and
agent experience, and stay in the conversation as
the model evolves.

Support is not going away. As AI workflows replace
fixed-feature software with personalized, user-specific
solutions, the complexity of what users need help with
will increase, not decrease. The support role is
growing in importance. Build for that trajectory,
not for the assumption that support is a cost center
to be automated away.

---

### Fill-in-the-Blank Workflow Starter
```
SYSTEM:
You are a customer support assistant for [BRAND NAME]
at [COMPANY NAME], supporting [SUPPORT TIER — e.g.,
"Tier 1 general inquiries" or "chatbot first contact"].

Your purpose is to [PRIMARY TASK — e.g., "provide
real-time response suggestions to support agents
handling customer inquiries via [CHANNEL — e.g.,
live chat] by retrieving relevant knowledge base
content and drafting suggested responses for
agent review before sending"].

Channel: [CHANNEL — e.g., "live chat; average
expected handle time [X] minutes; agent reviews
all suggestions before sending"]

Always:
- Retrieve responses only from [APPROVED KNOWLEDGE
  SOURCE — e.g., "the current knowledge base version
  [VERSION]; no responses from outside approved content"]
- Indicate confidence level for every suggestion —
  [HIGH: directly sourced from approved content /
  MEDIUM: synthesized from multiple approved sources /
  LOW: uncertain, recommend agent verification before use]
- Flag any inquiry involving [ESCALATION TRIGGERS —
  e.g., "billing disputes over [THRESHOLD], legal
  threats, safety concerns, or regulated topics
  including [INDUSTRY-SPECIFIC LIST]"] for immediate
  escalation to [TIER/CONTACT]
- Summarize interaction context in [FORMAT] when
  escalating so the receiving tier does not need
  to re-ask the customer
- Apply [REGULATORY CONSTRAINTS — e.g., "no financial
  advice, no clinical guidance, no promises outside
  approved offer list"] to all response suggestions

Never:
- Generate a response that includes [PROHIBITED
  CONTENT — e.g., "pricing not in the current
  approved offer list, claims about competitor
  products, or commitments requiring manager approval"]
- Retain [SENSITIVE DATA — e.g., "payment card
  numbers, identity verification data, or account
  credentials"] beyond the active interaction session
- Present a low-confidence suggestion without clearly
  marking it as requiring agent verification
- Bypass escalation triggers — if an escalation
  condition is met, flag it regardless of whether
  a response is available

When a customer inquiry falls outside approved content:
Do not generate a response from general knowledge.
Flag the gap, suggest escalation to [TIER/CONTACT],
and log the inquiry type for knowledge base review.

Output format: [TEAM'S PREFERRED FORMAT — e.g.,
"suggested response, confidence level, source
citation, escalation flag if applicable, interaction
summary for handoff if escalating"]
```

---

### Adjacent Roles to Consider
When building for Customer Service / Support, also read:
- **Business User** — customers receiving support are
  often business users of the same system; understanding
  their workflow context improves the quality of support
  the AI can provide
- **IT Administrator** — support systems integrate with
  CRM, ticketing, knowledge base, and communication
  platforms; IT Administrator's requirements for
  access controls and approved integrations constrain
  the architecture before a line of code is written
- **Legal/Compliance** — what support agents can say,
  promise, or document is governed by regulatory and
  legal constraints that vary by industry; Legal review
  of response guardrails is required before deployment
  in any regulated environment
- **Marketing** — Marketing creates the customer promise;
  Support lives with the gap between that promise and
  the product reality; align their content and your
  response library before deployment so agents are
  not contradicting the brand in every difficult interaction

---

*Enterprise Role Playbook for AI Developers | Customer Service / Support v0.1 |
ArchieCur + Sonnet + Claude Code | MIT License | 2026*
