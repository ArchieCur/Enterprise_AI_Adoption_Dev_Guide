# IT Administrator
## Enterprise Role Playbook for AI Developers

---

### Who This Person Is
The IT Administrator is the person your system has to live with
after you leave. They are not your user. They are your landlord.

They manage the infrastructure your system runs on, the identity
and access controls that determine who can touch it, the security
policies that govern what it's allowed to do, and the support
queue that fills up when it breaks at 2am on a Tuesday. They
have seen more vendor implementations promise seamless integration
and deliver undocumented dependencies than they can count. They
are not impressed by demos. They are interested in what happens
six months after the demo.

IT Administrators think in uptime, security posture, patch cycles,
and supportability. They are measured on availability and incident
response, which means every system you add to their environment
is a new way for their metrics to get worse. They are not
obstructionist. They are responsible. There is a difference.

Earn their trust early and you will have an ally who can make
your system work in environments you didn't design for. Ignore
them until deployment and you will discover that your system
doesn't meet their security requirements, isn't on the approved
software list, and can't be supported by their team — all at once,
two days before go-live.

---

### What They Care About
- Security posture — every new system is a new attack surface;
  they need to know exactly what your system does, what it
  connects to, and what data it touches before it goes anywhere
  near production
- Supportability — can their team maintain this system without
  you? If the answer is no, the system is a liability, not
  an asset
- Approved stack compliance — most enterprises maintain an
  approved software and vendor list; a system built on
  unapproved components doesn't get deployed, regardless
  of how well it works
- Integration stability — your system connects to their
  existing infrastructure; they need to know it won't break
  something else when it updates, scales, or fails
- Access control integrity — who can access what, how access
  is provisioned and deprovisioned, and how privileged
  access is managed are non-negotiable requirements,
  not configuration options

---

### What They're Afraid Of
- A security incident that traces back to a system they
  approved for deployment — the accountability is theirs
- Shadow AI — employees using consumer AI tools that
  connect to enterprise data outside of IT's visibility
  or control; this is already happening in most enterprises
  and IT knows it
- Vendor lock-in disguised as integration — a system
  that works beautifully until the vendor changes their
  API, raises their prices, or goes out of business
- An AI system that calls external APIs with enterprise
  data without explicit documentation and approval —
  data leaving the environment without a clear record
  is a compliance and security event
- Being handed a system to support that they had no
  part in designing and don't fully understand

---

### What "Good" Looks Like for Them
- A system they were involved in designing, not handed
  after the fact
- Complete documentation: architecture diagrams, data
  flows, external dependencies, API calls, authentication
  methods, and failure modes
- Clean integration with existing identity and access
  management — SSO, MFA, role-based access control
  that maps to their existing framework
- A support model that doesn't require the original
  developer to be on call — runbooks, monitoring,
  alerting, and escalation paths they can own
- A system that behaves predictably when it fails —
  graceful degradation, clear error states, and logs
  that tell them what happened without requiring them
  to reverse-engineer the architecture

---

### Governance & Compliance Considerations

#### The Approved Stack is Not Negotiable
Enterprise IT maintains approved software, vendor, and
cloud platform lists for security, compliance, and
procurement reasons. A system built on unapproved
components — model providers, vector databases, API
services, open source libraries — will not pass IT
review regardless of technical merit. Validate your
entire dependency list against the approved stack
before you build. Exceptions require a formal review
process that takes time you should plan for.

#### Data Flow Documentation is a Security Requirement
IT needs to know exactly where enterprise data goes.
Every API call your system makes that carries enterprise
data — to a model provider, an external service, a
logging platform — needs to be documented, reviewed,
and approved. "The model provider says they don't
train on API data" is not documentation. It is a
vendor claim. IT needs contractual data processing
agreements and architectural evidence.

#### Identity and Access Management Must Integrate
Your system's authentication cannot be a separate
credential store. Enterprise IT manages identity
through established IAM systems — Active Directory,
Azure AD, Okta, and others. Your system needs to
integrate with the existing IAM infrastructure,
support SSO, enforce MFA where required, and
deprovision access automatically when employees
leave or change roles. A standalone login is a
security gap and an administrative burden.

#### Privileged Access Requires Formal Controls
If your system requires administrative or privileged
access to enterprise systems — databases, file shares,
APIs with elevated permissions — those credentials
need to go through the formal privileged access
management process. Hardcoded credentials, shared
service accounts, and informal access arrangements
are security findings that will stop or reverse
a deployment.

#### AI Systems Create New Log and Monitoring Requirements
Traditional application monitoring doesn't cover
everything an AI system does. Prompt inputs, model
outputs, tool calls, retrieval queries, and agent
actions all generate data that may be required for
security monitoring, compliance audit, or incident
response. Work with IT to define what needs to be
logged, where logs are stored, how long they are
retained, and who can access them — before deployment,
not after an incident.

#### Patch and Update Cycles Need a Plan
AI systems have dependencies — model versions, library
versions, API versions — that change faster than
traditional enterprise software. IT needs a clear
plan for how updates are tested, approved, and deployed
without breaking production. A system with no update
plan is a system that will either fall behind on
security patches or break unpredictably when
dependencies change upstream.

---

### Model Selection Guidance

**Recommended tier: Depends entirely on deployment
architecture — IT Administrator's requirements
constrain the options**

This is the one role where model tier is secondary
to deployment model. Before recommending a model,
answer these questions with IT:

- **Cloud vs. on-premises:** Can the system call
  an external model API, or does data residency
  or security policy require on-premises deployment?
- **Approved vendors:** Which model providers are
  on the approved vendor list?
- **Data classification:** What is the classification
  of data the system will process, and does that
  classification permit external API calls?

**Model mapping once deployment architecture is confirmed:**
- Small — high-volume operational tasks where
  on-premises or private cloud deployment is
  feasible; latency and cost matter at scale
- Medium — standard enterprise workflows where
  an approved cloud provider meets security
  requirements
- Large — complex reasoning tasks where the
  security and data residency requirements
  have been cleared through IT and Legal

**Critical:** Do not select a model provider before
confirming they are on the approved vendor list
and that their data processing agreements meet
the enterprise's security and compliance requirements.
Rebuilding on an approved provider after development
is complete is expensive and demoralizing.

---

### The One Thing Developers Get Wrong
They treat IT Administrator as a deployment step
instead of a design partner.

The conversation with IT that should happen at the
whiteboard happens instead at the deployment gate.
The system is built. The model provider isn't on
the approved vendor list. The authentication uses
a standalone credential store. The external API
calls aren't documented. The logs don't meet
the security monitoring requirements.

None of these are small fixes. All of them were
preventable with a one-hour conversation before
architecture was finalized.

IT Administrator knows the environment your system
has to live in better than you do. They know which
integrations have failed before, which vendors
have had security incidents, which compliance
requirements will trigger a formal review, and
which parts of the infrastructure are fragile
in ways that aren't documented anywhere. That
knowledge is available to you for free if you
ask early. It costs significantly more if you
discover it at deployment.

Bring the architecture diagram to IT before you
build it. Leave with a list of requirements.
Build to those requirements. Come back with
documentation. That is how enterprise AI systems
get deployed.

---

### Fill-in-the-Blank Workflow Starter
```
SYSTEM:
You are an IT operations assistant supporting
[DEPARTMENT/TEAM NAME] at [COMPANY NAME].

Your purpose is to [PRIMARY TASK — e.g., "support
IT service desk operations by triaging incoming
requests, routing to the appropriate team, and
drafting initial response communications"].

Deployment architecture:
- Authentication: [IAM INTEGRATION — e.g.,
  "Azure AD SSO with MFA required"]
- Data classification: [CLASSIFICATION LEVEL —
  e.g., "Internal use only; no customer PII
  or regulated data"]
- Approved model provider: [VENDOR — e.g.,
  "confirmed on approved vendor list as of
  [DATE]; data processing agreement on file"]
- External API calls: [LIST ALL — e.g.,
  "model inference API only; no other external
  calls; all data stays within approved
  cloud boundary"]

Always:
- Log all inputs and outputs to [LOGGING SYSTEM]
  with [REQUIRED FIELDS — e.g., "timestamp,
  user ID, request type, response generated,
  ticket ID if applicable"]
- Route requests involving [SENSITIVE SYSTEMS —
  e.g., "privileged access, security incidents,
  or data classification questions"] to
  [IT CONTACT/ROLE] immediately
- Apply [ACCESS CONTROL RULE — e.g., "role-based
  permissions; users can only query systems
  they are authorized to access"]
- Follow [CHANGE MANAGEMENT PROCESS] for any
  action that modifies system configuration

Never:
- Execute commands or make configuration changes
  without [AUTHORIZATION REQUIREMENT — e.g.,
  "explicit approval from the requesting user's
  manager and IT lead"]
- Access [RESTRICTED SYSTEMS — e.g., "production
  databases, security infrastructure, or
  privileged credentials"] outside of approved
  workflows
- Retain sensitive system information beyond
  [RETENTION POLICY — e.g., "the active session;
  no caching of credentials, access tokens,
  or system configuration data"]
- Call external services not on the
  [APPROVED SERVICES LIST]

When a request involves an unapproved system
or tool:
Stop. Log the request. Route to [IT CONTACT/ROLE].
Do not attempt to fulfill the request through
an alternative path.

Output format: [IT TEAM'S PREFERRED FORMAT —
e.g., "structured ticket format with priority,
category, assigned team, and suggested response
— flagged for human review before sending"]
```

---

### Adjacent Roles to Consider
When building for IT Administrators, also read:
- **Security Engineer** — IT Administrator and
  Security Engineer share the attack surface your
  system creates; security requirements need both
  perspectives before architecture is finalized
- **Legal/Compliance** — data residency, vendor
  agreements, and regulatory requirements for
  system logging connect IT directly to Legal;
  these conversations need to happen in parallel,
  not sequentially
- **Developer** — if the enterprise has an internal
  development team, IT Administrator's infrastructure
  requirements need to be communicated directly
  to the developers building on top of it; don't
  let requirements travel through intermediaries
- **Business Leader** — IT Administrator controls
  deployment; Business Leader controls budget
  and priority; when these two are misaligned,
  systems stall; make sure executive sponsorship
  includes explicit support for IT's requirements,
  not just the business outcome

> **See also:** *Unified Logging Architecture for
> Enterprise AI Systems* (appendix) — IT Administrator,
> Security, DevOps, Privacy, and Auditor each require
> different logging outputs from the same system.
> IT Administrator owns the access layer: who can
> see the logs, where they are stored, how long they
> are retained, and what classification they carry.
> Design one logging architecture that satisfies all
> five before deployment.

---

*Enterprise Role Playbook for AI Developers | IT Administrator v0.1 |
ArchieCur + Sonnet + Claude Code | MIT License | 2026*
