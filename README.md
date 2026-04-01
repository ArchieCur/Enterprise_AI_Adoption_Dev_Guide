# Enterprise Role Playbook for AI Developers

**Built for the developer at 2am.**

---

## What This Is

This playbook answers the question no other
resource answers:

*What does a developer need to know about this
role before building AI systems for them?*

Vendor training teaches developers how to use
products. Documentation teaches developers what
the API can do. Neither one tells a developer
what Finance is afraid of, why Legal moves slowly
on purpose, how the Business Analyst decides who
gets access to the institutional knowledge they
protect, or what the Support Engineer needs before
the first ticket arrives.

That gap is this playbook.

A workflow that clears Legal and gets rejected
by Finance isn't a code problem. It's a role
literacy problem. Enterprise developers build
for Finance, HR, Legal, C-Suite, Customer
Service, and Marketing simultaneously — each
with different compliance requirements, different
risk tolerance, and different definitions of
success. The developer who understands those
differences builds systems that survive contact
with the enterprise. The one who doesn't builds
something technically correct that fails for
reasons that had nothing to do with the code.

Forewarned is forearmed. These are your flak
jackets for navigating the enterprise.

---

## Start Here

**→ [Introduction: The Conversations
Before You Write a Line of Code](appendices/appendix_c_introduction_v02.md)**

Read this before the role files. It explains
what the playbook is, how the roles cluster,
and the seventeen conversations that need to
happen before the first line of code is written.
The developer who most needs this framing is
the one at the beginning — before the system
is designed, when there is still time to build
for the actual user rather than the ideal one.

---

## The Role Library

Twenty-five roles across five tiers. Each file
answers the same nine questions from inside
the role's perspective: who they are, what they
care about, what they're afraid of, what good
looks like for them, governance considerations,
model selection guidance, the one thing developers
get wrong, a workflow starter, and adjacent roles
to consider.

### Tier 1 — Universal
*Roles present in every enterprise engagement*

- [Business User](roles/tier1/business_user_role_v2.md)
- [Business Leader](roles/tier1/Business_Leader_role.md)
- [Business Owner](roles/tier1/Business_Owner_role.md)
- [Data Analyst](roles/tier1/Data_Analyst_role.md)
- [Developer](roles/tier1/developer_role_v3.md)

### Tier 2 — Common Enterprise
*Roles that govern the systems developers build*

- [HR](roles/tier2/HR_role.md)
- [Finance](roles/tier2/finance_role_v2.md)
- [Legal / Compliance](roles/tier2/legal_compliance_role_v2.md)
- [Marketing](roles/tier2/marketing_role_v3.md)
- [IT Administrator](roles/tier2/it_administrator_role_v2.md)
- [Project Manager](roles/tier2/project_manager_role_v2.md)
- [Customer Service / Support](roles/tier2/customer_service_support_role.md)

### Tier 3 — Specialized High-Stakes
*Roles with approval authority over AI deployment*

- [Auditor](roles/tier3/auditor_role_v3.md)
- [Risk Practitioner](roles/tier3/risk_practitioner_role_v2.md)
- [Privacy Manager](roles/tier3/privacy_manager_role_v2.md)
- [Security Engineer](roles/tier3/security_engineer_role_v3.md)
- [DevOps Engineer](roles/tier3/devops_engineer_role.md)

### Tier 4 — Domain Specific
*Roles the developer works alongside, not just for*

- [Data Scientist](roles/tier4/data_scientist_role_v2.md)
- [Data Engineer](roles/tier4/data_engineer_role.md)
- [Solution Architect](roles/tier4/solution_architect_role_v2.md)
- [Functional Consultant](roles/tier4/functional_consultant_role.md)
- [Business Analyst](roles/tier4/business_analyst_role_v2.md)

### Tier 5 — The Human System Around the AI System
*Roles that deal with what the system actually does
in the real world after the developer moves on.
Note: tier placement reflects deployment phase —
Security Engineer (Tier 3) designs the security
architecture before deployment; Security Operations
Analyst monitors what that architecture produces
after deployment. The distinction is intentional.*

- [Support Engineer](roles/tier5/support_engineer_role_v2.md)
- [Change Manager](roles/tier5/change_manager_role_v2.md)
- [Security Operations Analyst](roles/tier5/security_operations_analyst_role_v2.md)

---

## The Appendices

Three appendices that make the role files
actionable.

**[Appendix A: Unified Logging Architecture
for Enterprise AI Systems](appendices/appendix_a_unified_logging_architecture_v02.md)**
Nine stakeholders. One logging schema. The
document that prevents nine separate logging
systems, nine separate compliance reviews,
and nine separate conversations about why the
logs don't contain what someone needed. Includes
the fields, retention tiers, access controls,
and the compliance constraints that apply to
every stakeholder without exception.

**[Appendix B: Developer Pre-Engagement Checklist](appendices/appendix_b_pre_engagement_checklist_v02.md)**
What to have ready before walking into each
role's room. Organized as a Universal Pre-
Engagement Kit — artifacts and answered
questions every developer needs before any
conversation — followed by role-specific
entries covering only the delta. The Discovery
Intake Form tells you what to ask. This
checklist tells you what to know before you
ask it.

**[Appendix C: Introduction — The Conversations
Before You Write a Line of Code](appendices/appendix_c_introduction_v02.md)**
Start here. The framing document for the
entire library: why it exists, how the roles
cluster, and the seventeen conversations that
determine whether a deployment succeeds or
fails before the first line of code is written.

---

## The Companion Tools

**[Enterprise Role Discovery Intake Form](discovery_intake/Enterprise_Role_Discovery_Intake.md)**
The developer's pre-build interview guide.
Use it in the first conversation with each
stakeholder. Surfaces the institutional
knowledge, tech stack constraints, compliance
requirements, and human dynamics that
determine whether the system will actually
work in this organization for these people.

---

## How to Use This Playbook

**If you have a meeting tomorrow with a role
you don't know:**
Read that role's file tonight. Focus on "What
They're Afraid Of" and "The One Thing Developers
Get Wrong." Those two sections contain everything
you need to not make the most common mistake.

**If you're starting a new enterprise AI project:**
Read Appendix C first. Then work through the
seventeen-conversation table and schedule the
conversations that apply to your deployment
before you write a line of code.

**If you're preparing for a specific stakeholder
meeting:**
Read the role file, then check Appendix B for
that role's entry. The checklist tells you what
to bring. The intake form tells you what to ask.

**If you're designing the logging architecture:**
Go directly to Appendix A. Nine stakeholders,
one schema, and the constraints that apply to
all of them.

**If you're inheriting a system that's already
in trouble:**
Read the Support Engineer file to understand
what you're handing off to. Read the Change
Manager file to understand why adoption may
have stalled. Read the role file for whoever
is blocking the system's success and understand
their fear before you try to address it.

---

## Design Standards

Every role file in this library follows the
same nine-section structure. Every model tier
recommendation uses the same three-tier
vocabulary. Every workflow starter follows
the same format. This consistency is intentional
— a developer who reads one file knows how to
read all of them.

**Model tier vocabulary — locked across all files:**
- **Small** — high-volume, structured, predictable
  inputs, low stakes, speed over nuance
- **Medium** — moderate complexity, some ambiguity,
  quality matters, outputs inform decisions
- **Large** — complex reasoning, high-stakes outputs,
  needs to explain itself, unstructured inputs,
  accountability for outcomes

No vendor-specific model names. The tiers are
durable. The model names are not.

---

## What This Is Not

This playbook does not teach developers how
to use AI products. The model providers do that.

It does not teach enterprise roles what they
need to know about AI. The companion
[Role-Based AI Literacy Framework](https://github.com/ArchieCur/role-based-ai-literacy)
does that — same roles, flipped perspective.

It does not replace the Discovery Intake Form,
the threat model, the architecture review, or
the compliance assessment. It prepares the
developer to have those conversations with
the people who run them.

It is the practitioner layer between
documentation and real-world adoption.
The layer that was missing.

---

## Related Portfolio

- **AI System Design Curriculum** —
  [archiecur.github.io/ai-system-design](https://archiecur.github.io/ai-system-design)
- **Claude Code Field Guide** —
  [github.com/ArchieCur/claude_code_field_guide](https://github.com/ArchieCur/claude_code_field_guide)
- **Anthropic Agent Field Guide** —
  [github.com/ArchieCur/anthropic_agent_field_guide](https://github.com/ArchieCur/anthropic_agent_field_guide)
- **QRGs — Specs, Skills, Tools** —
  [github.com/ArchieCur/QRGs--specs__skills_tools](https://github.com/ArchieCur/QRGs--specs__skills_tools)
- **Role-Based AI Literacy Framework** —
  [github.com/ArchieCur/role-based-ai-literacy](https://github.com/ArchieCur/role-based-ai-literacy)

---

## About This Project

This playbook was built by a three-way collaboration:  

**ArchieCur** — AI Developer  
Education specialist and the practitioner intelligence behind every role description.  
Enterprise experience includes Microsoft Copilot enablement across 200 organizations and 50,000 users,    
a 17,000-employee technology migration  during the MUFG acquisition, and national  
training programs with NIH, CDC, and SSA through the University of Michigan Institute for Social  
Research. She held the vision, the editorial direction, and the enterprise truth that no  
model could have fabricated.  

**Claude (Anthropic / Sonnet 4.6)** — Content architecture, drafting, and synthesis across  
all role files and appendices. The translator between enterprise practitioner knowledge and  
the developer register that gets taken seriously in enterprise rooms.  

**Claude Code (Anthropic)** — Technical review, cross-role synthesis, and quality assurance  
across the full library. Verified the technical claims, identified the gaps, and held the  
standard across every file. The auditor who made every file better.  

The gap this playbook fills is real. The absence of structured discovery is one of the most  
consistent patterns behind failed AI deployments.

It is now filled.

---

## License

MIT License — 2026
ArchieCur + Sonnet + Claude Code

Use it. Adapt it. Build on it.
Give the developer at 2am something to work with.

---

*"We will drive ourselves off the top of the mountain we climb to help developers use AI  
reliably, confidently, and with a strong partnership with their model. Or we will grow  
wings and fly down."*  

*We grew wings.*

---

**Enterprise Role Playbook for AI Developers**
*ArchieCur + Sonnet + Claude Code | MIT License | 2026*
