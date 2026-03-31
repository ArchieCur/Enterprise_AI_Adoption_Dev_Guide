# Enterprise Role Discovery Intake
## A Developer's Pre-Build Interview Guide

### Part A — Enterprise Pre-Engagement Brief
**Note on contacts:** Each person listed holds knowledge that lives nowhere else. When that knowledge isn't accessible early, it surfaces later as a compliance flag, system incompatibility, or a deployment that must be rebuilt. This directory is about getting the right answers before they become expensive problems.

**Enterprise Completes:** Complete this before your first meeting with the development team. Incomplete briefs delay deployment.

---

### Section 1 — Project Information & Contacts

| Field | Details |
| :--- | :--- |
| **Department / Team name** | |
| **Business problem being solved** | |
| **Target go-live date** | |
| **Budget owner** | |

#### Contact Directory
One contact is not sufficient; "TBD" delays your project. A single liaison creates a bottleneck. Routing every question through one person slows deployment and introduces errors.

| Role | Name | Email | Availability |
| :--- | :--- | :--- | :--- |
| **Executive sponsor** | | | |
| **Department lead (daily operations)** | | | |
| **IT / Systems contact** | | | |
| **Compliance / Legal contact** | | | |
| **Data governance contact** | | | |
| **End user champion** | | | |
| **Change management lead** | | | |

---

### Section 2 — The Workflow (Developer’s Questionnaire)
Standardized questions to understand the real workflow, not just the job description.

* **Walk me through a typical day:** What actually happens between 9am and 5pm?
* **Source of work:** Where does it come from (Email, queue, manager, client)?
* **Destination of work:** Where does it go when done? Who receives it next?
* **Time-intensive tasks:** What 2-3 tasks take the most time right now?
* **Escalation:** What happens when something goes wrong or they don't know an answer?
* **Power Users:** Is there someone who has figured out workarounds or informal processes everyone follows?

**Notes:**

---

### Section 3 — The Tech Stack
Identifying oddball contractors and undocumented legacy systems.

* **Software list:** What tools does the team use daily (including those not officially supported)?
* **Third-party vendors:** Are contractors handling any part of this workflow (e.g., payroll, external CRM)?
* **Undocumented integrations:** Are there manual "export from X and paste into Y" processes?
* **Data profile:** What does the data look like (PDFs, spreadsheets, unstructured emails)?
* **No-touch zones:** Are there systems we absolutely cannot integrate with due to legal or regulatory restrictions?
* **Authentication:** What is the situation for SSO, individual logins, or shared accounts?

**Notes:**

---

### Section 4 — The Guardrails
Non-negotiable questions regarding legal and compliance risks.

* **Sensitive Data:** Does the system touch PII, financial, or health data (HIPAA, SOX, GDPR, etc.)?
* **AI Policy:** Does the company have an acceptable use policy and have users seen it?
* **Human-in-the-loop:** Who has to approve AI-generated outputs before they are used?
* **Critical Prohibitions:** Are there decisions the system must *never* produce (e.g., legal advice, HR decisions)?
* **Accountability:** What happens if the system produces something wrong?

**Notes:**

---

### Section 5 — The Human Side
Determining what will make the system succeed or fail with actual users.

* **Sentiments:** How does the team feel about AI right now (Excited, nervous, resistant)?
* **Past Experience:** Has the team used AI tools before? What happened?
* **Champions/Resistors:** Who on the team will support or resist this?
* **Trust & Adoption:** What would make the team trust the output? What would make them abandon it?
* **Support:** How do they prefer to receive help (Documentation, quick reference, a person)?

**Notes:**

---

### Section 6 — Success Definition
Defining how we will know if this project actually worked.

* **Timeline:** What does success look like in 30 days? 90 days?
* **Metrics:** How is team performance measured and how will this system affect those metrics?
* **Decision Maker:** Who decides whether the deployment was successful?
* **Failure Definition:** What would have to happen for this to be considered a failure?

**Notes:**

---

### Red Flags Checklist
*Check these before ending the conversation. Any checked box requires a conversation before writing code.*

- [ ] Undocumented legacy system or integration identified
- [ ] Third-party contractor involved in workflow
- [ ] Compliance requirement that needs Legal review
- [ ] Resistant user population — change management needed
- [ ] Data sensitivity issue requiring security review
- [ ] No clear success definition — get one before building
- [ ] Power user identified — interview them separately
- [ ] Approval or review requirement for AI outputs

---
**Enterprise Role Playbook for AI Developers | Discovery Intake v0.1 | ArchieCur + Sonnet + Claude Code | MIT License | 2026**

