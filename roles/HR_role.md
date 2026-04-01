# HR (Human Resources)
## Enterprise Role Playbook for AI Developers

---

### Who This Person Is
The HR professional is the enterprise's most paper-heavy operational
role — and simultaneously its highest-stakes one. Their day runs on
process: benefits enrollment, onboarding documentation, leave requests,
policy notifications, offboarding checklists, compliance filings. A
significant portion of HR's work is moving structured information
through defined workflows, which makes it look like a natural fit for
automation.

It isn't simple. Every one of those workflows touches the most sensitive
personal data in the enterprise — compensation, medical accommodations,
disciplinary history, immigration status, performance records. The
forms are operational. The data inside them is not.

HR professionals know this. They work under a compliance burden that
most developers don't fully see: employment law, EEOC requirements,
FMLA, ADA, HIPAA for benefits data, SOX implications for compensation
records, and state-level regulations that vary by where employees
actually work. They are not bureaucrats who love paperwork. They are
practitioners managing legal exposure through documentation, every day.

Build for their operational reality without forgetting what's inside
the forms.

---

### What They Care About
- Accuracy above all — an error in a benefits enrollment or a
  termination notice has direct legal and human consequences
- Compliance — they are personally accountable when HR processes
  fail regulatory requirements
- Employee trust — HR's credibility with the workforce depends on
  confidentiality and fairness; anything that threatens that is
  existential to their function
- Cycle time on administrative work — open enrollment, onboarding
  waves, and offboarding all have hard deadlines and high volume
- Consistency — the same process must produce the same outcome
  regardless of who runs it

---

### What They're Afraid Of
- A data breach involving employee PII — compensation, medical,
  disciplinary — on their watch
- An AI output that creates legal liability: a termination notice
  with discriminatory language, a benefits explanation that
  contradicts the plan document, a hiring communication that
  runs afoul of EEOC guidelines
- Employees finding out their personal data was handled by a
  system they didn't consent to
- Losing auditability — if a regulatory body asks how a decision
  was made, HR needs a paper trail that holds up
- Building dependency on a system that Legal or IT later shuts down

---

### What "Good" Looks Like for Them
- Faster cycle time on high-volume administrative work without
  sacrificing accuracy
- Consistent outputs that don't require manual review every time
- A system they can explain to an employee who asks: "Did AI
  touch my records?"
- Audit trails that satisfy both internal compliance and
  external regulators
- Outputs that stay within the boundaries of approved policy
  language — not paraphrases of it

---

### Governance & Compliance Considerations

#### Employment Law Exposure is Structural
HR's workflows are governed by a layered compliance stack: federal
employment law, state-specific requirements, and company policy.
A system that works correctly for employees in one state may produce
a non-compliant output for employees in another. Know which
jurisdictions are in scope before you build.

#### PII Classification is Stricter Than You Think
HR data is not generic PII. Compensation records, performance
history, medical accommodations, disciplinary actions, and
immigration documentation carry heightened protection requirements.
Understand exactly which data categories your system will touch
and what data handling obligations apply to each before you write
a line of code.

#### HIPAA Applies to Benefits Data
If your system touches anything related to health benefits —
enrollment, claims, accommodations — HIPAA compliance is not
optional. This is a separate compliance track from general
employment law and requires its own legal review.

#### AI-Generated Employment Communications Carry Legal Risk
Any output that goes to an employee about their employment —
offer letters, termination notices, performance improvement plans,
leave approvals — carries legal weight. AI-generated language
that deviates from approved policy language, even subtly, can
create liability. Human review of these outputs is not a
nice-to-have; it is a legal requirement in most enterprise contexts.

#### Consent and Transparency Requirements are Emerging
Regulations in several jurisdictions now require employers to
disclose when AI is used in employment decisions. This is a
rapidly evolving area. Build disclosure and consent mechanisms
in from the start. Retrofitting them is expensive.

#### The Audit Trail is Non-Negotiable
HR decisions are subject to regulatory audit, internal review,
and legal discovery. Every output your system produces that
touches an employment decision needs to be logged, traceable,
and explainable in plain language. "The model said so" is not
an acceptable audit response.

---

### Model Selection Guidance

**Recommended tier: Small to Medium**

- Small for high-volume structured workflows: deadline
  notifications, document routing, enrollment reminders,
  status updates from structured data
- Medium for anything requiring policy interpretation, employee
  communication drafting, or outputs that will be reviewed
  before going to an employee
- Large only for complex, high-stakes situations: accommodation
  analysis, multi-jurisdictional compliance questions, or
  sensitive case documentation — and always with human review

**Model mapping:**
- Small — form routing, deadline notifications, data extraction
  from structured HR documents, status confirmations
- Medium — benefits communication drafts, onboarding content,
  policy summaries for employee consumption
- Large — accommodation and leave analysis, sensitive case
  documentation, compliance questions spanning multiple
  regulatory frameworks

**Critical:** No HR system should produce final employment
communications without human review. Model tier affects quality
and nuance, not the requirement for human sign-off.

---

### The One Thing Developers Get Wrong
They solve the workflow problem and miss the consent problem.

HR's operational workflows are genuinely automatable. The volume
is real, the structure is real, the efficiency gains are real.
Developers build the system, it works, and then Legal asks one
question that stops the deployment: "Did employees consent to
AI processing their records?"

Build consent, transparency, and disclosure into the architecture
from day one. Know which employment decisions your system
influences — not just the outputs it produces. Understand that
in HR, the difference between "AI-assisted" and "AI-decided"
is a legal distinction with real consequences. Design for
human-in-the-loop at every step that touches an individual
employee's record or status.

The workflow problem is solvable. The consent problem, retrofitted
after deployment, is expensive. Sometimes it kills the deployment
entirely.

---

### Fill-in-the-Blank Workflow Starter
```
SYSTEM:
You are an HR operations assistant supporting [DEPARTMENT/TEAM NAME]
at [COMPANY NAME].

Your purpose is to [PRIMARY TASK — e.g., "draft employee
communications for open enrollment and route documents
through the onboarding workflow"].

Always:
- Use only approved policy language from [POLICY SOURCE —
  e.g., "the current Employee Handbook, version [X]"]
- Flag any request that involves [SENSITIVE CATEGORIES —
  e.g., "medical accommodations, disciplinary history,
  or compensation data"] for human review before proceeding
- Include a human review checkpoint before any output
  is sent to an employee
- Log all outputs with [REQUIRED FIELDS — e.g.,
  "timestamp, employee ID (anonymized), action taken,
  reviewer name"]
- Apply [JURISDICTION — e.g., "federal FMLA requirements
  and [STATE] state leave law"] to all leave-related outputs

Never:
- Make or imply employment decisions [e.g., "hiring,
  termination, promotion, or disciplinary action"]
  without explicit human authorization
- Access or output [RESTRICTED DATA — e.g.,
  "compensation records, medical documentation,
  or immigration status"] outside of approved workflows
- Generate communications that have not been reviewed
  against [COMPLIANCE STANDARD — e.g.,
  "current EEOC guidelines and company policy"]
- Retain employee PII beyond [RETENTION POLICY —
  e.g., "the active session; no logging of personal data"]

When a request falls outside approved workflows:
Route to [HR CONTACT/ROLE] and confirm receipt before
taking any further action.

Output format: [HR TEAM'S PREFERRED FORMAT — e.g.,
"plain language summary for employee, followed by
compliance notes for HR reviewer"]
```

---

### Adjacent Roles to Consider
When building for HR, also read:
- **Legal/Compliance** — employment law exposure means Legal
  needs to review before deployment, not after; treat this
  as a required dependency, not a courtesy review
- **IT Administrator** — HR systems hold the enterprise's
  most sensitive data; access controls, SSO, and data
  residency requirements need IT's involvement from day one
- **Business Leader** — HR serves the whole organization;
  executive sponsors need to understand AI's role in
  employment processes before deployment, not during
  an incident
- **Data Analyst** — if your system produces workforce
  analytics or reporting, bring a Data Analyst in to
  validate outputs before they inform business decisions

---

*Enterprise Role Playbook for AI Developers | HR v0.1 |
ArchieCur + Sonnet + Claude Code | MIT License | 2026*
