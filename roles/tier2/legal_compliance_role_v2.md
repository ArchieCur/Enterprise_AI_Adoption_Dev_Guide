# Legal / Compliance
## Enterprise Role Playbook for AI Developers

---

### Who This Person Is
Legal and Compliance professionals are the enterprise's last line
of defense before a decision becomes a liability. They are not
obstacles. They are the people whose job it is to see every way
a system can go wrong before it does — and to make sure the
organization is protected when it does anyway.

They think in risk, not features. They speak in precedent, not
possibility. They have watched enough technology implementations
create enough unintended legal exposure to have earned their
caution. When Legal asks a question that feels like it's designed
to slow you down, it usually is — because the alternative is
faster deployment and a lawsuit eighteen months later that costs
ten times what the delay would have.

Understand this clearly: Legal and Compliance do not need to
love your system. They need to be able to defend it. Build
something they can defend and you will have no faster ally
in the enterprise. Build something they can't and you will
not ship.

---

### What They Care About
- Risk containment — their job is to identify and limit the
  organization's legal exposure before it becomes a claim,
  a fine, or a headline
- Defensibility — every decision the organization makes with
  AI assistance needs to be explainable in a legal or
  regulatory proceeding
- Precedent — they think in terms of what has happened to
  other organizations that built similar systems; your
  novel architecture is their cautionary tale waiting to happen
- Policy compliance — internal policies exist because external
  regulations require them; a system that bypasses policy
  is bypassing the regulation behind it
- Clear accountability — when something goes wrong, Legal
  needs to know exactly who authorized what and when;
  diffuse accountability is a liability in court

---

### What They're Afraid Of
- Regulatory action against the organization that traces
  back to an AI system they approved — or failed to review
- A discrimination claim, privacy violation, or consumer
  harm that an AI output contributed to
- Deploying a system in a jurisdiction where the legal
  framework hasn't caught up to the technology — and
  being the test case that sets the precedent
- Shadow AI — systems deployed without Legal review that
  create liability Legal didn't know existed until discovery
- The EU AI Act, state AI laws, and emerging federal
  frameworks landing on a system that wasn't built
  to accommodate them

---

### What "Good" Looks Like for Them
- A system they reviewed before deployment, not after
  an incident
- Documentation they can hand to a regulator or opposing
  counsel without redacting half of it
- Clear human accountability at every decision point
  that carries legal weight
- A system that can be audited, explained, and if necessary,
  shut down cleanly
- A developer who came to them early, asked the right
  questions, and built what was agreed — not what seemed
  easier

---

### Governance & Compliance Considerations

#### Legal Review is a Dependency, Not a Checkpoint
Most developers treat Legal review as the last gate before
deployment. Legal treats it as the foundation the system
is built on. These two mental models produce the most
common and most expensive failure in enterprise AI
deployment: a system that is technically complete and
legally unbuildable. Engage Legal before architecture
is finalized. The conversation you have at the whiteboard
is free. The conversation you have after six months of
development is not.

#### The EU AI Act Has Teeth
If your organization operates in the EU or processes data
of EU residents, the EU AI Act creates binding obligations
that depend on how your system is classified. High-risk
AI systems — which include systems used in employment,
credit, education, and critical infrastructure — face
mandatory conformity assessments, transparency requirements,
and human oversight obligations. Know your system's
classification before you build. Retrofitting compliance
to a high-risk system is a significant undertaking.

#### US State AI Laws Are Multiplying
In the absence of comprehensive federal AI legislation,
US states are passing their own AI laws at an accelerating
rate. Colorado, Illinois, Texas, and others have enacted
or proposed AI-specific requirements around automated
decision-making, bias auditing, and consumer disclosure.
A system deployed nationally may face a patchwork of
state requirements. Legal needs to map the jurisdictional
exposure before deployment.

#### Data Privacy Law is Not One Law
GDPR, CCPA, HIPAA, FERPA, COPPA, GLBA — your system's
data privacy obligations depend on what data it touches,
where the data subjects are located, and what industry
you're in. A single enterprise AI system can be subject
to multiple overlapping privacy frameworks simultaneously.
Do not assume one privacy review covers all of them.

#### Intellectual Property Risk is Real and Underestimated
AI systems trained on or generating content create IP
exposure that most developers don't anticipate. Copyright
questions around training data, ownership of AI-generated
outputs, and trade secret exposure through prompts are
active legal questions with evolving case law. Legal needs
to review any system that ingests proprietary content,
generates content for external use, or handles confidential
information in its context window.

#### Contracts and Vendor Agreements Govern What You Can Build
The enterprise's contracts with software vendors, data
providers, and cloud platforms contain terms that govern
how their products can be used in AI systems. Using a
vendor's data to train a model, feeding proprietary
software documentation into a context window, or building
an AI layer on top of a licensed platform may violate
existing agreements. Legal needs to review the relevant
contracts before you build the integration.

#### Accountability Cannot Be Delegated to the Model
In every jurisdiction with AI governance requirements,
legal accountability for AI system outputs rests with
the organization that deployed the system — not the
model provider. "The model produced that output" is not
a legal defense. Design your system so that every
consequential output has a named human accountable for
it. If you can't identify who is accountable for a
specific output, Legal will identify that as a gap.

---

### Model Selection Guidance

**Recommended tier: Small to Large, with documented
human review at every consequential output**

- Small for structured, high-volume, low-ambiguity
  administrative tasks: regulatory deadline tracking,
  compliance calendar updates, policy document
  formatting, citation formatting for known sources,
  compliance checklist generation from approved
  templates
- Medium for internal compliance workflows, policy
  summarization, contract review assistance, and
  regulatory monitoring where a human expert reviews
  all outputs before action is taken
- Large for complex multi-jurisdictional analysis,
  litigation support, regulatory response drafting,
  and any output that informs a legal decision —
  always with attorney review before use

**Model mapping:**
- Small — regulatory deadline tracking, compliance
  calendar formatting, policy document formatting,
  citation formatting, checklist generation from
  approved templates
- Medium — policy document summarization, compliance
  checklist generation, contract clause extraction,
  regulatory update monitoring
- Large — multi-jurisdictional compliance analysis,
  regulatory response drafting, risk assessment
  synthesis across complex fact patterns

**Critical:** No AI output in a Legal or Compliance
workflow should be treated as legal advice or used
as the basis for a legal decision without attorney
review. This is not a model tier question. It is
a practice of law question. Build the human review
requirement into the architecture, not the user guide.

---

### The One Thing Developers Get Wrong
They go around Legal instead of through them.

Legal review feels slow. Legal questions feel like
obstacles. The temptation to deploy in a limited pilot,
or to a single business unit, or to frame the system
as a "tool" rather than a "decision-maker" to avoid
the review process is real and understandable.

It is also how organizations end up in regulatory
proceedings.

Legal's review process exists because the legal
landscape for AI is genuinely unsettled. New regulations
are passing. Case law is being made. A system deployed
today without Legal review may be non-compliant with
a law passed next quarter. Legal is not slowing you
down out of institutional habit. They are managing
exposure in a regulatory environment that is changing
faster than any enterprise can track internally.

Go through Legal. Go early. Bring documentation.
Ask what they need to say yes. A developer who makes
Legal's job easier is a developer who ships.

---

### Fill-in-the-Blank Workflow Starter
```
SYSTEM:
You are a legal and compliance research assistant
supporting [DEPARTMENT/TEAM NAME] at [COMPANY NAME].

Your purpose is to [PRIMARY TASK — e.g., "summarize
regulatory updates relevant to [INDUSTRY/JURISDICTION]
and flag items requiring attorney review"].

Always:
- Distinguish clearly between [CERTAINTY LEVELS —
  e.g., "established law, emerging regulation, and
  unsettled legal questions"] in every output
- Flag any output that touches [HIGH-RISK AREAS —
  e.g., "employment decisions, consumer-facing
  communications, or cross-jurisdictional data handling"]
  for attorney review before use
- Cite the specific regulatory source, version, and
  effective date for every compliance reference
- Apply [JURISDICTIONAL SCOPE — e.g., "US federal law,
  EU GDPR, and [STATE] state requirements"] as the
  baseline framework
- Log all outputs with [REQUIRED FIELDS — e.g.,
  "timestamp, requesting user, document referenced,
  reviewer assigned"]

Never:
- Represent any output as legal advice or as a
  substitute for attorney review
- Make or imply a legal determination about
  [RESTRICTED AREAS — e.g., "liability, regulatory
  compliance status, or contractual obligation"]
  without explicit attorney authorization
- Access [RESTRICTED DOCUMENTS — e.g., "privileged
  communications, active litigation files, or
  M&A-related documents"] outside of explicitly
  authorized workflows
- Produce outputs for external use — regulatory
  filings, court submissions, client communications —
  without documented attorney review and sign-off

When a question involves unsettled law or active
litigation:
Flag immediately. Route to [LEGAL CONTACT/ROLE].
Do not produce an output that could be construed
as a legal position.

Output format: [LEGAL TEAM'S PREFERRED FORMAT — e.g.,
"structured summary with source citations, confidence
level, jurisdictional scope, and required next action
— including whether attorney review is required
before the output is used"]
```

---

### Adjacent Roles to Consider
When building for Legal and Compliance, also read:
- **Auditor** — Legal and Audit share accountability
  for governance; systems that touch one almost always
  touch the other; align their requirements before
  you finalize architecture
- **HR** — employment law exposure connects Legal
  and HR at the hip; any system touching employment
  decisions needs both functions in the room
- **Finance** — SOX compliance sits at the intersection
  of Legal and Finance; regulatory requirements for
  financial reporting need both perspectives
- **IT Administrator** — data privacy compliance
  is an infrastructure question as much as a legal
  one; Legal's requirements need to be translated
  into technical controls by IT

---

*Enterprise Role Playbook for AI Developers | Legal/Compliance v0.1 |
ArchieCur + Sonnet + Claude Code | MIT License | 2026*
