# Data Analyst
## Enterprise Role Playbook for AI Developers

---

### Who This Person Is
The Data Analyst lives at the intersection of data and decisions. They 
transform raw data into insights that inform business strategy, 
operational improvements, and performance measurement. They're technical 
enough to build queries and models but positioned as a business 
function, not an engineering function. They understand data quality 
issues intimately and are often the first person to notice when 
something is wrong with an AI system's outputs — because they know what 
the data actually looks like.

They are your best internal ally and your most rigorous critic. Treat 
them as a partner, not a user.

---

### What They Care About
- Data accuracy — they will catch errors your QA missed
- Reproducibility — can they explain how this output was produced?
- Access to underlying data — they don't just want answers, 
  they want to interrogate the reasoning
- Speed without sacrificing correctness — faster is only better 
  if the answer is still right
- Not being replaced — they've watched "AI will do analytics" 
  headlines for three years and they're paying attention

---

### What They're Afraid Of
- Presenting AI-generated insights to leadership that turn out 
  to be wrong — their credibility is on the line, not the model's
- Black-box outputs they can't validate or explain
- AI being used to bypass their function entirely
- Data governance violations they didn't know about until after 
  the fact
- Bias in training data producing systematically wrong insights 
  in their domain

---

### What "Good" Looks Like for Them
- Outputs they can validate against source data
- Transparency about confidence levels and data sources
- A system that accelerates their work, not one that replaces 
  their judgment
- Explainable outputs — they need to present these findings and 
  defend them
- Integration with their existing tools — not another platform 
  to manage

---

### Governance & Compliance Considerations
- Data lineage matters — outputs need to be traceable to 
  source data for audit purposes
- PII in datasets requires explicit handling protocols — 
  Data Analysts often work with sensitive data as a matter 
  of course
- Model outputs used in business decisions may require 
  documentation under emerging AI governance frameworks
- Data retention policies affect what training data can be 
  used and how long outputs can be stored
- Statistical significance — in regulated industries, AI-generated 
  insights used in decisions may need to meet the same evidentiary 
  standards as traditional analysis

---

### Model Selection Guidance

**Recommended tier: Balanced to Frontier**

- Balanced for structured data analysis, report generation, 
  and pattern identification in known datasets
- Frontier when analysis requires complex reasoning across 
  unstructured data sources, or when outputs inform 
  high-stakes business decisions
- This role has higher tolerance for model cost than Business 
  Users — they understand the value of accuracy and will 
  advocate for the right tool

**Model mapping:**
- Medium — standard analytics workflows, structured 
  data summarization, report drafting
- Large — complex multi-source synthesis, 
  unstructured data analysis, high-stakes insight generation
- Consider function calling capabilities for direct 
  data tool integration

---

### The One Thing Developers Get Wrong
They build outputs Data Analysts can consume but can't interrogate.

A Data Analyst who can't trace an AI output back to source data 
can't use it professionally. Build explainability in from the 
start — not as a feature, as a requirement. Show your work. 
Every insight needs a data lineage the analyst can follow.

---

### Fill-in-the-Blank Workflow Starter
```
SYSTEM:
You are a data analysis assistant for [TEAM/DEPARTMENT] at 
[COMPANY NAME].

Your purpose is to [PRIMARY TASK — e.g., "analyze sales performance 
data and surface insights for weekly business reviews"].

Always:
- Cite the specific data source and time period for every insight
- Flag data quality issues, gaps, or anomalies you observe
- Distinguish between [CERTAINTY LANGUAGE — e.g., "confirmed 
  trends vs. patterns that require further investigation"]
- Present confidence levels when drawing conclusions from 
  incomplete data
- Format numerical outputs to [PRECISION STANDARD — e.g., 
  "two decimal places, thousands separated by commas"]

Never:
- Present conclusions without supporting data references
- Smooth over data quality issues to produce cleaner-looking output
- Make causal claims when the data only supports correlation
- Access or reference [RESTRICTED DATASETS — e.g., 
  "HR compensation data, customer PII beyond anonymized IDs"]

When data is insufficient to answer the question:
State clearly what data would be needed and why the current 
dataset cannot support the requested conclusion.

Output format: [ANALYST'S PREFERRED FORMAT — e.g., 
"executive summary paragraph, followed by supporting data 
table, followed by methodology notes"]
```

---

### Adjacent Roles to Consider
When building for Data Analysts, also read:
- **Data Engineer** — they build the pipelines your analyst 
  depends on; misalignment here causes data quality problems
- **Data Scientist** — adjacent role with deeper ML focus; 
  understand where one ends and the other begins in this org
- **Business Leader** — Data Analysts often present directly 
  to leadership; build outputs that translate up

---

*Enterprise Role Playbook for AI Developers | ArchieCur + Sonnet + 
Claude Code | MIT License | v0.1 2026*