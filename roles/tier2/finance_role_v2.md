# Finance
## Enterprise Role Playbook for AI Developers

---

### Who This Person Is
The Finance professional is the enterprise's institutional skeptic.
Their entire function is built around a single premise: every number
must be defensible. Not approximately right. Not directionally
accurate. Defensible — to auditors, to regulators, to the CFO,
to the board, and in some organizations, to the SEC.

Finance operates on closing cycles, reconciliation deadlines, and
audit schedules that don't move for anyone. Their work is governed
by accounting standards — GAAP, IFRS, SOX — that carry legal weight.
They have seen more software implementations promise efficiency and
deliver chaos than any other function in the enterprise. They are
not cynical. They are experienced.

When a Finance professional pushes back on your system, it is not
obstruction. It is due diligence. Build for someone who needs to
be able to explain every output to an external auditor, and you
will earn their trust. Build for speed without defensibility, and
you will not get past the first review.

**A note on Finance sub-functions:** This profile primarily addresses
Accounting and Controllership — the close cycle, reconciliation,
audit trail, and regulatory reporting functions. Finance is not
monolithic. A developer building for FP&A (Financial Planning &
Analysis) will find a user with more tolerance for approximation,
more need for scenario modeling and forward-looking projections,
and less focus on audit trail completeness. Treasury has different
concerns again: cash positioning, counterparty risk, and payment
processing. Use this profile as your foundation, then validate
which Finance sub-function you are actually building for before
finalizing your architecture.

---

### What They Care About
- Accuracy — a rounding error that cascades through a financial
  model is not a minor issue; it is a material misstatement
- Auditability — every figure needs a traceable source; every
  calculation needs a documented method
- Close cycle performance — month-end, quarter-end, and year-end
  close have hard deadlines; anything that slows the cycle
  is a problem, anything that accelerates it without sacrificing
  accuracy is genuinely valuable
- Regulatory compliance — SOX, GAAP, IFRS, and industry-specific
  requirements are not negotiable constraints, they are the
  operating environment
- Control integrity — Finance owns internal controls; any system
  that touches financial data must fit within the existing
  control framework or replace it with something demonstrably better

---

### What They're Afraid Of
- A material misstatement in a financial report that traces
  back to an AI output — the liability is personal, not just
  organizational
- An audit finding that references an AI system they can't
  fully explain or document
- Losing control of the audit trail — if a regulator asks
  how a number was produced, "the AI calculated it" is
  not an acceptable answer
- Variance they can't explain — Finance reconciles everything;
  an AI output that doesn't match the expected figure without
  a clear reason will stop a workflow cold
- Shadow systems — AI tools adopted by business units that
  touch financial data without Finance's knowledge or approval

---

### What "Good" Looks Like for Them
- Every output is traceable to source data with a documented
  calculation method
- The system accelerates close cycle work without introducing
  reconciliation problems downstream
- Outputs fit within existing control frameworks — they don't
  require Finance to rebuild their audit documentation
- Variance explanations are built in — when a number looks
  unexpected, the system explains why before being asked
- The CFO can sign off on work product that passed through
  the system without a separate manual verification step

---

### Governance & Compliance Considerations

#### SOX Compliance is an Architecture Decision
If your system touches financial reporting for a public company,
Sarbanes-Oxley compliance is not a feature you add later. SOX
requires documented internal controls over financial reporting,
separation of duties, and audit trails that satisfy external
auditors. Design your access controls, logging, and approval
workflows to SOX standards before you write application logic.

#### GAAP and IFRS Are Not Style Guides
Accounting standards govern how numbers are calculated, categorized,
and reported. An AI system that produces financial outputs must
operate within the applicable standard. A calculation that is
mathematically correct but violates GAAP is wrong in every way
that matters to Finance. Understand which standards apply before
you build any calculation or reporting logic.

#### The Audit Trail Must Satisfy External Auditors
Internal logging is not enough. Financial audit trails need to
meet the evidentiary standards of external auditors who are
specifically looking for gaps. Every financial output your system
produces needs: source data reference, calculation methodology,
timestamp, user authorization, and change history. Design for
the auditor who has never seen your system and is specifically
trying to find a hole in it.

#### Separation of Duties Cannot Be Automated Away
Finance maintains separation of duties as a fraud prevention
and compliance control. A system that allows the same user to
initiate and approve a financial transaction — even inadvertently —
breaks a control that auditors will flag. Map your user roles
and approval workflows against the existing separation of duties
framework before deployment.

#### Data Residency and Retention Have Regulatory Teeth
Financial records have mandatory retention periods — seven years
under many jurisdictions, longer in others. Understand where your
system stores data, how long it retains it, and whether that
meets the applicable regulatory requirements. Also understand
data residency requirements for multinational organizations;
financial data crossing certain jurisdictions triggers additional
compliance obligations.

#### Materiality Has a Threshold
Finance thinks in terms of materiality — the level at which an
error is significant enough to affect decisions. Build your
error handling and exception flagging to surface issues at the
materiality threshold relevant to the organization. An AI system
that flags everything equally is noise. One that understands
what size of variance matters is a tool Finance will actually use.

---

### Model Selection Guidance

**Recommended tier: Small to Medium, with strict constraints**

- Small for structured, high-volume financial operations:
  transaction categorization, invoice matching, data extraction
  from structured financial documents, report formatting
- Medium for analysis, variance explanation, and financial
  communication drafting where judgment and nuance matter
- Large only for complex multi-standard compliance analysis,
  cross-jurisdictional reporting, or unstructured financial
  data synthesis — and always with human review and
  documented sign-off

**Model mapping:**
- Small — transaction processing, data extraction, invoice
  routing, structured report generation from clean data
- Medium — variance analysis, close cycle support, financial
  narrative drafting, budget versus actual commentary
- Large — complex regulatory analysis, multi-entity
  consolidation reasoning, audit response drafting

**Critical:** Financial outputs that flow into regulated
reporting require human review and documented authorization
regardless of model tier. Speed is valuable. Defensibility
is non-negotiable. When the two conflict, defensibility wins.

---

### The One Thing Developers Get Wrong
They build for efficiency and Finance rejects it for
defensibility.

The system works. The numbers are right. The cycle time
drops by forty percent. And Finance won't approve deployment
because the audit trail has a gap, or the calculation
methodology isn't documented, or the approval workflow
doesn't preserve separation of duties.

Efficiency is not Finance's primary optimization target.
Defensibility is. A slower process that survives an audit
is better than a faster one that doesn't. Build the audit
trail first. Build the approval workflow first. Build the
control documentation first. Then build the efficiency.

Finance will adopt a system that makes their close cycle
faster and keeps them out of audit findings. They will
reject a system that does the first without guaranteeing
the second — every time, without exception.

---

### Fill-in-the-Blank Workflow Starter
```
SYSTEM:
You are a financial operations assistant supporting
[DEPARTMENT/TEAM NAME] at [COMPANY NAME].

Your purpose is to [PRIMARY TASK — e.g., "support month-end
close by extracting variance explanations from actuals versus
budget data and drafting commentary for the CFO package"].

Always:
- Cite the specific data source, version, and timestamp
  for every figure referenced
- Document the calculation methodology for every derived
  figure in [FORMAT — e.g., "a footnote visible to the
  reviewer before output is finalized"]
- Flag variances exceeding [MATERIALITY THRESHOLD —
  e.g., "$50,000 or 5% of budget line, whichever is less"]
  for human review before inclusion in any report
- Apply [ACCOUNTING STANDARD — e.g., "US GAAP"] to all
  calculations and categorizations
- Route all outputs requiring authorization to
  [APPROVER ROLE] before delivery

Never:
- Produce a final financial output without documented
  human review and authorization
- Allow the same user to [SEPARATION OF DUTIES CONSTRAINT —
  e.g., "initiate and approve the same transaction or
  journal entry"]
- Access [RESTRICTED DATA — e.g., "payroll records,
  executive compensation, or M&A-related financial data"]
  outside of explicitly authorized workflows
- Round, estimate, or approximate figures without flagging
  the deviation from source data explicitly
- Retain financial data beyond [RETENTION POLICY —
  e.g., "the active session; all source data references
  must point to the system of record, not local copies"]

When a figure cannot be traced to an approved source:
Stop. Flag the gap. Route to [FINANCE CONTACT/ROLE]
before proceeding. Do not estimate.

Output format: [FINANCE TEAM'S PREFERRED FORMAT — e.g.,
"structured data table with source citations, followed
by narrative commentary, followed by reviewer sign-off
field"]
```

---

### Adjacent Roles to Consider
When building for Finance, also read:
- **Auditor** — Finance's work product is the auditor's
  input; build as if the auditor is the secondary user
  of everything Finance touches
- **Legal/Compliance** — SOX and regulatory requirements
  need Legal review before deployment; Finance cannot
  self-certify compliance on a system that touches
  regulated reporting
- **IT Administrator** — access controls, separation of
  duties enforcement, and audit logging are infrastructure
  decisions; IT needs to be at the table before
  architecture is finalized
- **Business Leader** — Finance serves the whole
  organization's reporting needs; executive sponsors
  need to understand what the system can and cannot
  certify before it goes near regulated outputs

---

*Enterprise Role Playbook for AI Developers | Finance v0.1 |
ArchieCur + Sonnet + Claude Code | MIT License | 2026*
