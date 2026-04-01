# Business Owner
## Enterprise Role Playbook for AI Developers

---

### Who This Person Is
The Business Owner has direct P&L responsibility for a product, service 
line, or business unit. Unlike the Business Leader who thinks in 
corporate strategy, the Business Owner thinks in customers, margins, and 
competitive position for their specific domain. They move faster than 
corporate leadership, tolerate more risk, and are often your most 
enthusiastic early adopter — or your most impatient critic.

They're close enough to the work to have opinions about implementation 
and senior enough to override the team. That combination makes them 
uniquely powerful and uniquely dangerous to a deployment.

---

### What They Care About
- Their customers — will this make the customer experience better or worse?
- Their margins — does this reduce cost or increase revenue in their unit?
- Speed to value — they don't want a six-month implementation, they want 
  results this quarter
- Competitive position — are their competitors already doing this?
- Their team's adoption — they'll hear about it immediately if their 
  people hate it

---

### What They're Afraid Of
- A customer-facing failure that damages their brand or their 
  relationships
- Their team working around the system instead of with it
- Committing to something that corporate then defunds or changes
- Being the pilot for something that fails visibly
- Losing control of their domain to a centralized IT solution that 
  doesn't fit their reality

---

### What "Good" Looks Like for Them
- Measurable improvement in their specific metrics within their 
  fiscal timeline
- Their customers notice nothing changed — or notice it got better
- Their team adopted it without a war
- They can point to it as their initiative, not IT's project
- It runs without requiring their constant attention

---

### Governance & Compliance Considerations
- Business Owners often operate across regulatory boundaries — a retail 
  Business Owner may have different compliance requirements than the 
  corporate standard
- Customer data handling requires extra scrutiny — Business Owners are 
  close to customers and may want to use customer data in ways that 
  Legal hasn't approved
- Brand risk lives here — outputs that touch customers need brand 
  review before deployment
- Procurement authority varies — some Business Owners can approve 
  vendor contracts independently, others cannot; know this before 
  your first meeting

---

### Model Selection Guidance

**Recommended tier: Lightweight to Balanced**

- Lightweight for operational workflows: customer communication 
  templates, internal reporting, data summarization
- Balanced when customer-facing quality is critical or when the 
  Business Owner's domain requires nuanced judgment
- Consider cost-per-transaction carefully — Business Owners understand 
  margins and will ask about AI operating costs

**Model mapping:**
- Small — high-volume operational tasks, internal summaries, 
  structured data processing
- Medium — customer-facing content, nuanced analysis, 
  competitive intelligence synthesis
- Large — reserved for high-stakes customer situations or 
  complex strategic analysis

---

### The One Thing Developers Get Wrong
They treat the Business Owner like a Business Leader and move too slowly, 
or they treat them like a Business User and oversimplify.

Business Owners want to be involved in design decisions — they have 
domain expertise that will make your system better if you ask for it 
early. They will also change requirements mid-build if you don't lock 
scope deliberately. Get their domain knowledge. Lock your scope. Move 
at their pace, not corporate IT's pace.

---

### Fill-in-the-Blank Workflow Starter
```
SYSTEM:
You are an AI assistant supporting [BUSINESS UNIT NAME] at [COMPANY NAME], 
owned by [BUSINESS OWNER ROLE — e.g., "the Regional Sales Director"].

Your purpose is to [PRIMARY TASK — e.g., "analyze customer feedback and 
surface actionable insights for the sales team"].

Always:
- Frame outputs in terms of [BUSINESS OWNER'S KEY METRIC — e.g., 
  "customer retention impact"]
- Flag anything that could affect [CRITICAL CONCERN — e.g., 
  "customer relationships or brand perception"]
- Keep [SPECIFIC CONSTRAINT — e.g., "customer PII out of all outputs 
  and logs"]
- Escalate to [CONTACT] when [ESCALATION TRIGGER — e.g., "a customer 
  complaint exceeds severity level 2"]

Never:
- Make commitments on behalf of [BUSINESS UNIT] regarding 
  [RESTRICTED AREA — e.g., "pricing, refunds, or service agreements"]
- Surface outputs to customers without [REVIEW REQUIREMENT — e.g., 
  "human review and approval"]
- [BRAND PROHIBITION — e.g., "use casual language in customer-facing 
  outputs"]

Format: [BUSINESS OWNER'S PREFERRED FORMAT]
```

---

### Adjacent Roles to Consider
When building for Business Owners, also read:
- **Business User** — their team; adoption depends on getting this right
- **Business Leader** — their boss; alignment on success metrics prevents 
  conflicts later
- **Customer Service** — if their domain is customer-facing, these roles 
  overlap significantly

---

*Enterprise Role Playbook for AI Developers | ArchieCur + Sonnet + 
Claude Code | MIT License | v0.1 2026*
