# Risk Practitioner
## Enterprise Role Playbook for AI Developers

---

### Who This Person Is
The Risk Practitioner is the enterprise's professional
pessimist — and they are paid to be. Their job is to
imagine everything that could go wrong before it does,
quantify the likelihood and impact of each scenario,
and put controls in place that reduce exposure to
acceptable levels. They are not trying to stop things
from happening. They are trying to make sure the
organization survives when they do.

They think in probability, impact, and residual risk.
They speak in risk registers, heat maps, and control
frameworks. They have a structured methodology for
evaluating new threats and a historical record of
every risk the organization has previously identified,
accepted, mitigated, or transferred. When you bring
them an AI system, they don't see a capability. They
see a new entry for the risk register.

The Risk Practitioner is not the Auditor. The Auditor
looks backward — did this comply? The Risk Practitioner
looks forward — what could go wrong, and are we prepared?
Both perspectives are essential. Neither replaces the other.
A developer who conflates them will satisfy neither.

Bring the Risk Practitioner your threat model before
you bring them your system. Show them you've already
thought about what could go wrong. They will tell you
what you missed — and there will always be something
you missed.

---

### What They Care About
- Complete risk identification — an unidentified risk
  is the most dangerous kind; they would rather have
  a long risk register than a short one with gaps
- Quantified impact — "this could be bad" is not a
  risk assessment; they need likelihood, impact, and
  residual risk after controls are applied
- Control effectiveness — a control that exists but
  doesn't reduce risk is administrative overhead,
  not risk management
- Risk ownership — every risk needs a named owner
  who is accountable for monitoring and remediation;
  diffuse ownership means no ownership
- Emerging risk visibility — AI is generating new
  risk categories faster than most frameworks can
  absorb them; they need early warning, not
  retrospective discovery

---

### What They're Afraid Of
- An AI system that creates risk categories their
  current framework doesn't cover — hallucination
  risk, prompt injection, model drift, and training
  data bias don't map cleanly to traditional
  operational risk taxonomies
- Risks that were identified and accepted at a point
  in time becoming material when the system scales —
  a risk that was acceptable at pilot scale may be
  unacceptable at enterprise scale
- The board asking about AI risk exposure and the
  answer being "we're not sure" — AI risk governance
  is now a board-level conversation in most large
  enterprises
- Cascade failures — an AI system that fails and
  takes adjacent systems or processes down with it
  in ways that weren't anticipated in the risk assessment
- Reputational risk that moves faster than the
  risk management process — a brand or trust incident
  from an AI system can be material before the
  risk committee meets

---

### What "Good" Looks Like for Them
- A developer who arrives with a threat model, not
  just a feature list
- AI-specific risk categories that map to their
  existing framework — or a clear proposal for
  how to extend the framework to accommodate new
  risk types
- Named risk owners for every identified AI risk,
  with monitoring mechanisms that produce evidence
  of control effectiveness
- A system that fails safely — when something goes
  wrong, the failure mode is contained, documented,
  and recoverable
- Residual risk that the organization has explicitly
  accepted, not residual risk that was overlooked

---

### Governance & Compliance Considerations

#### AI Introduces Risk Categories That Don't Exist in Traditional Frameworks
Standard enterprise risk frameworks — COSO, ISO 31000,
NIST — were not designed for AI systems. New risk
categories require explicit framework extension:
model hallucination risk, prompt injection and
adversarial input risk, training data bias risk,
model drift and degradation risk, and third-party
model provider dependency risk. Work with the Risk
Practitioner to map these categories into the existing
framework before deployment. An AI risk that has no
home in the risk register is a risk that no one owns.

#### The EU AI Act Creates Mandatory Risk Assessment Requirements
For systems classified as high-risk under the EU AI Act,
formal risk assessment is not optional — it is a legal
requirement before deployment. The assessment must
cover accuracy, robustness, cybersecurity, and bias.
It must be documented and maintained throughout the
system's lifecycle. Know your system's classification
and whether mandatory risk assessment applies before
architecture is finalized.

#### Third-Party Model Risk Is Enterprise Risk
When your system depends on an external model provider,
their risks become your risks. Model provider outages,
API changes, pricing changes, security incidents,
and regulatory actions against the provider all
create downstream risk for your system. The Risk
Practitioner needs a third-party risk assessment
for every external dependency your system has —
including the model provider, the cloud infrastructure,
and any external data sources. "The vendor has SOC 2"
is a starting point, not a complete risk assessment.

#### Concentration Risk Is Real and Underestimated
If multiple enterprise AI systems depend on the same
model provider, the same cloud region, or the same
data pipeline, a single point of failure creates
enterprise-wide exposure. The Risk Practitioner
needs visibility into the full portfolio of AI
systems to assess concentration risk — which means
shadow AI and undocumented deployments are a risk
management problem, not just an IT governance problem.

#### Residual Risk Requires Explicit Acceptance
Every risk that cannot be fully mitigated becomes
residual risk. Residual risk is not the same as
no risk — it is risk that the organization has
explicitly chosen to accept, with the understanding
that it could materialize. Document residual AI
risks explicitly. Get named executive acceptance
for material residual risks. "We didn't think it
would be a problem" is not a risk acceptance
decision — it is an absence of one.

#### Model Drift Creates Ongoing Risk, Not Just Deployment Risk
AI systems can degrade in ways that are not obvious
until the degradation is significant. Model drift —
where outputs change over time as the model or its
inputs evolve — creates a risk that doesn't exist
at deployment but grows continuously afterward.
Build monitoring that detects output drift and
connects it to the risk management process. A
risk that was acceptable at deployment may become
unacceptable six months later without anyone
noticing.

---

### Model Selection Guidance

**Recommended tier: Small to Large**

- Small for high-volume, structured, low-ambiguity tasks:
  risk register formatting, control assessment
  documentation from structured inputs, standard
  reporting template generation, risk tracking
  and scheduling support
- Medium for structured risk assessment support:
  risk register maintenance with interpretation,
  control testing checklists, risk reporting
  templates, policy gap analysis
- Large for complex risk synthesis: multi-system
  risk correlation, emerging risk landscape analysis,
  board-level risk narrative drafting, scenario
  modeling across interconnected risk domains

**Model mapping:**
- Small — risk register formatting, control assessment
  documentation from structured data, reporting
  template generation, risk tracking support
- Medium — risk register updates, control assessment
  documentation, risk reporting support, policy
  compliance gap analysis
- Large — enterprise risk synthesis, AI-specific
  risk framework development, scenario analysis,
  board and executive risk communication drafting

**Critical:** AI tools used in risk assessment
must themselves be risk-assessed. The Risk Practitioner
will notice — and flag — an AI system used to assess
AI risk that has not been evaluated under the same
framework it is applying to others. Practice what
you build.

---

### The One Thing Developers Get Wrong
They assess risk at deployment and treat it as done.

The risk assessment happens. The controls are documented.
The residual risks are accepted. The system goes live.
And then the risk register entry sits unchanged for
eighteen months while the system evolves, the threat
landscape shifts, and the residual risks that were
acceptable at pilot scale become material at enterprise
scale.

AI risk is not a point-in-time assessment. It is a
continuous monitoring obligation. Model drift, new
attack vectors, regulatory changes, and scale effects
all change the risk profile of a system over its
lifetime. Build monitoring that feeds back into the
risk management process. Schedule risk reassessment
at defined intervals. Connect output anomalies to
risk triggers that escalate automatically.

The Risk Practitioner's job doesn't end at deployment.
Neither does yours.

---

### Fill-in-the-Blank Workflow Starter
```
SYSTEM:
You are a risk management assistant supporting
[DEPARTMENT/TEAM NAME] at [COMPANY NAME].

Your purpose is to [PRIMARY TASK — e.g., "support
enterprise risk assessment workflows by maintaining
the AI risk register, generating control testing
documentation, and drafting risk reporting for
[GOVERNANCE BODY — e.g., the Risk Committee]"].

Risk framework: [FRAMEWORK — e.g., "COSO ERM,
extended with AI-specific risk categories per
[INTERNAL POLICY REFERENCE]"]

Always:
- Classify every risk using [RISK TAXONOMY —
  e.g., "the enterprise risk taxonomy with
  likelihood (1-5), impact (1-5), and residual
  risk after controls"]
- Assign a named risk owner to every identified
  risk before closing the assessment
- Flag risks exceeding [MATERIALITY THRESHOLD —
  e.g., "residual risk score of 15 or above"]
  for escalation to [RISK COMMITTEE/EXECUTIVE]
- Distinguish between [RISK TYPES — e.g.,
  "inherent risk, control effectiveness,
  and residual risk"] in every assessment output
- Include [MONITORING MECHANISM — e.g.,
  "a defined monitoring frequency and metric
  for each accepted residual risk"]

Never:
- Close a risk assessment without [REQUIRED
  ELEMENTS — e.g., "named owner, control
  documentation, residual risk acceptance,
  and next review date"]
- Accept residual risk above [THRESHOLD] without
  [AUTHORIZATION — e.g., "documented executive
  sign-off at the appropriate authority level"]
- Use AI-generated risk assessments as the sole
  basis for [HIGH-STAKES DECISIONS — e.g.,
  "board risk reporting or regulatory submissions"]
  without human practitioner review and sign-off
- Omit [AI-SPECIFIC RISK CATEGORIES — e.g.,
  "model drift, hallucination risk, prompt
  injection, and third-party model dependency"]
  from assessments of AI systems

When a new risk category has no existing framework mapping:
Flag it. Document it as an emerging risk. Route to
[RISK LEAD] for framework extension before proceeding.
Do not force-fit a new risk type into an existing
category that doesn't accurately describe it.

Output format: [RISK TEAM'S PREFERRED FORMAT — e.g.,
"risk ID, category, description, likelihood, impact,
inherent risk score, controls, control effectiveness,
residual risk score, owner, monitoring mechanism,
next review date, acceptance sign-off field"]
```

---

### Adjacent Roles to Consider
When building for Risk Practitioners, also read:
- **Auditor** — risk findings and audit findings
  feed the same governance process; Risk Practitioner
  and Auditor need a shared taxonomy for risk
  classification and a clear handoff between
  risk identification and audit verification
- **Legal/Compliance** — regulatory risk is a
  primary risk category; Legal and Risk need
  aligned definitions of what constitutes
  acceptable residual regulatory exposure
- **IT Administrator** — technical risk categories
  (system availability, security posture, third-party
  dependency) require IT's input to assess accurately;
  Risk Practitioner cannot quantify infrastructure
  risk without IT's knowledge of the environment
- **Security Engineer** — cybersecurity risk is
  a subset of enterprise risk; Security Engineer
  and Risk Practitioner need integrated threat
  modeling that connects technical vulnerabilities
  to business impact

---

*Enterprise Role Playbook for AI Developers | Risk Practitioner v0.1 |
ArchieCur + Sonnet + Claude Code | MIT License | 2026*
