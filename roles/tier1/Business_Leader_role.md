# Business Leader
## Enterprise Role Playbook for AI Developers

---

### Who This Person Is
The Business Leader sets strategy, owns outcomes, and is accountable to the 
board, investors, or executive team. They don't use AI directly — they make 
decisions about whether AI gets deployed, how much it costs, and whether it 
delivered value. They measure everything in business outcomes: revenue, risk, 
efficiency, competitive position. If your AI system can't be explained in 
those terms, it won't get funded, and if it gets funded without those terms, 
it won't get renewed.

They are not your user. They are your deployment's survival condition.

---

### What They Care About
- Return on investment — not capability, not accuracy, not latency. Value.
- Competitive advantage — are we ahead of the market or catching up?
- Risk exposure — what happens if this goes wrong and whose name is on it?
- Strategic alignment — does this support where we're going or distract from it?
- Board-level explainability — can I defend this decision in a meeting I 
  didn't prepare for?

---

### What They're Afraid Of
- A headline with their company's name and the word "AI" and something bad
- Committing budget to something that becomes obsolete in six months
- Being responsible for a decision an AI made that harmed someone
- Their competitors doing this better and faster
- Not understanding what they approved well enough to answer questions about it

---

### What "Good" Looks Like for Them
- A dashboard that shows business impact in their language — not model metrics
- Evidence of ROI within a timeframe they committed to
- No surprises — they want to know about problems before they become visible
- A system their team actually uses, not one that was built and abandoned
- Something they can point to as a strategic win

---

### Governance & Compliance Considerations
- They are often the named accountable party in AI governance frameworks — 
  make sure they know this before deployment, not after an incident
- Board-level AI governance policies are increasingly required — your 
  deployment may need to be documented at that level
- Make vs. buy decisions often live here — your system may be competing 
  against a vendor solution they're also evaluating
- Budget cycles matter — if your deployment spans a fiscal year boundary, 
  renewal approval is not automatic

---

### Model Selection Guidance

**Recommended tier: Not applicable — this role doesn't interact with 
the model directly**

The Business Leader's AI interaction is through dashboards, summaries, 
and briefings produced by systems built for other roles. Your design 
decision here is not model selection — it's output design.

**What this means for you:**
- Every system you build for other roles will eventually produce outputs 
  a Business Leader sees
- Design executive-facing outputs from the beginning — summary views, 
  impact metrics, exception reports
- Never surface raw model output to this role — always through an 
  interpretive layer that translates to business language

---

### The One Thing Developers Get Wrong
They build for the user and forget the approver.

A system that works perfectly for the team using it can still get shut 
down because the Business Leader couldn't explain it, couldn't measure 
it, or couldn't defend it when something went sideways. Build the 
executive layer into the system from the start — not as an afterthought 
dashboard nobody maintains.

---

### Fill-in-the-Blank Workflow Starter

This role rarely needs a direct AI workflow. What they need is a 
reporting layer from other workflows. Use this template for executive 
briefing summaries generated from other systems:
```
SYSTEM:
You are an executive briefing assistant for [COMPANY NAME].

Your purpose is to synthesize operational AI system outputs into 
executive-level summaries for [ROLE — e.g., "the Chief Operating Officer"].

Always:
- Lead with business impact, not technical performance
- Quantify outcomes in [METRIC TYPE — e.g., "time saved, cost reduced, 
  revenue influenced"]
- Flag exceptions and anomalies that require leadership attention
- Keep summaries to [LENGTH — e.g., "one page or less"]
- Use [COMPANY'S PREFERRED FORMAT — e.g., "situation, implication, 
  recommended action"]

Never:
- Use technical AI terminology without plain language explanation
- Present model confidence scores without business context
- Omit negative findings or system limitations
- Make strategic recommendations outside your defined scope

Format: [EXECUTIVE PREFERRED FORMAT — e.g., "bullet summary with 
headline metrics at top, exceptions section at bottom"]
```

---

### Adjacent Roles to Consider
When building for or reporting to Business Leaders, also read:
- **Business Owner** — if they have direct P&L ownership, risk tolerance 
  is higher and decision speed is faster
- **Risk Practitioner** — they brief Business Leaders on AI risk; 
  alignment between your system and their risk framework is essential
- **Solution Architect** — they translate your technical decisions into 
  language Business Leaders can evaluate

---

*Enterprise Role Playbook for AI Developers | ArchieCur + Sonnet + 
Claude Code | MIT License | v0.1 2026*
