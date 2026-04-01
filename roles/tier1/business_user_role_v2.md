# Business User
## Enterprise Role Playbook for AI Developers

---

### Who This Person Is
The Business User is the most common human your AI system
will serve and the most underestimated. They are not
technical. They did not choose to work with AI — AI
arrived in their tools and they are adapting. They measure
success by whether their day got easier, not by whether
the model performed well.

They are not trying to understand the system. They are
trying to finish their work. Every moment of friction —
a prompt that doesn't produce what they expected, an
output that needs significant editing, an interface that
requires learning before it helps — is a moment where
they conclude the system doesn't work. They will not
file a bug report. They will route around the system
quietly and tell their manager it didn't work.

If your system makes them feel stupid, they'll abandon
it quietly and tell their manager it didn't work. Design
for the actual user, not the ideal one.

---

### What They Care About
- Getting their actual work done faster — not learning
  a new tool
- Outputs they can use immediately without editing
  or second-guessing
- Not looking foolish in front of colleagues or leadership
- Knowing when to trust the output and when to check it

---

### What They're Afraid Of
- Sending something AI-generated that turns out to be
  wrong — and being blamed for it
- Their job becoming redundant
- Being asked questions about how the AI works that
  they cannot answer
- Accidentally sharing something confidential with
  an AI system

---

### What "Good" Looks Like for Them
- The output is ready to use or needs only minor editing
- The system tells them clearly when it is uncertain
- They do not need to understand how it works to use
  it well
- It fits inside tools they already use — email, Teams,
  their existing workflow

---

### Governance & Compliance Considerations

#### Data Sensitivity
Business Users often don't know what's confidential.
Your system needs guardrails, not just warnings. A
warning that appears after the user has already pasted
customer names into a prompt is not a guardrail — it
is a regret. Build the prevention into the architecture.

#### Output Transparency
In many organizations, outputs need to be disclosed as
AI-generated. Build that disclosure into the workflow.
Do not leave it to the user to remember, understand,
or correctly apply a policy they may have never read.
A Business User who doesn't know they're supposed to
disclose AI assistance cannot be expected to do so
consistently.

#### Acceptable Use Policies
Most enterprises have them. Most Business Users haven't
read them. Your system should enforce the boundaries
those policies establish — not assume that user awareness
is sufficient. If the policy says no customer PII in
AI prompts, the system should prevent or intercept it,
not rely on the user to self-regulate.

#### No PII in Prompts
Business Users will paste customer names, employee
details, and financial figures into a prompt unless
the system prevents or warns them before they do it.
This is not a failure of judgment — it is the natural
behavior of someone focused on completing a task, not
on data governance. Design for this behavior as a
given, not as an exception.

---

### Model Selection Guidance

**Recommended tier: Small to Medium**

- Small is sufficient for structured tasks:
  summarization, drafting from a template,
  reformatting data, answering questions from
  a known document set
- Medium when inputs are unstructured or ambiguous:
  open-ended questions, synthesis across multiple
  documents, nuanced tone requirements
- Large is not appropriate for standard Business
  User workflows — the cost is not justified and
  the complexity does not serve them

**Model mapping:**
- Small — structured summarization, template-based
  drafting, data reformatting, FAQ-style responses
  from known document sets
- Medium — open-ended drafting, multi-document
  synthesis, tone-sensitive communications,
  ambiguous or unstructured inputs

**Critical:** Response time matters more to this
user than to almost any other role. A slow response
feels like failure even if the output is excellent.
Optimize for latency in Business User deployments —
a fast, good-enough response will be adopted over
a slow, excellent one every time.

---

### The One Thing Developers Get Wrong
They build for how Business Users should use AI,
not for how they actually use it.

Business Users will write vague prompts. They will
paste sensitive data. They will trust outputs they
shouldn't and distrust outputs they should. They will
use the system in ways that were never anticipated —
not because they are careless, but because they are
focused on the work, not on the system. That is exactly
what they should be focused on.

The developer's job is to build a system that works
for the actual user — vague prompts, sensitive data
paste, unpredictable use patterns and all. Guardrails
are not condescending. They are good design. A system
that only works when the user behaves correctly is a
system that will fail in production at the rate that
users don't behave as expected — which is constantly.

---

### Fill-in-the-Blank Workflow Starter
```
SYSTEM:
You are an AI assistant helping [ROLE/TEAM NAME]
at [COMPANY NAME].

Your purpose is to [PRIMARY TASK — e.g., "draft
professional email responses to customer inquiries"].

Always:
- [KEY BEHAVIOR 1 — e.g., "keep responses under
  200 words unless asked for more"]
- [KEY BEHAVIOR 2 — e.g., "flag when you are
  uncertain rather than guessing"]
- [KEY BEHAVIOR 3 — e.g., "use the company's
  standard sign-off format"]

Never:
- Include information you cannot verify from
  the provided context
- [CRITICAL PROHIBITION — e.g., "make promises
  about pricing, timelines, or policy without
  explicit instruction"]
- Request or repeat personally identifiable
  information

When the request is outside your scope:
[ESCALATION PATH — e.g., "politely explain what
you can help with and suggest they contact
[TEAM/PERSON] for this request"]

Output format: [PREFERRED FORMAT — e.g.,
"professional email, subject line included,
no bullet points unless specifically requested"]
```

---

### Adjacent Roles to Consider
When building for Business Users, also read:
- **Business Leader** — the Business User's work
  product reaches leadership through summaries
  and dashboards; outputs need to translate up
  without the user having to reformat them manually
- **Business Owner** — in many deployments the
  Business Owner is the Business User's direct
  sponsor; what the Owner considers success
  determines whether adoption is celebrated
  or ignored
- **Customer Service / Support** — Business Users
  are often the customers that Support serves;
  when an AI tool creates confusion or errors,
  Support absorbs the fallout; align these two
  roles before deployment
- **Data Analyst** — Business Users consume AI
  outputs; Data Analysts validate them; when they
  share a system, output format needs to serve both

---

*Enterprise Role Playbook for AI Developers | Business User v0.1 |
ArchieCur + Sonnet + Claude Code | MIT License | 2026*
