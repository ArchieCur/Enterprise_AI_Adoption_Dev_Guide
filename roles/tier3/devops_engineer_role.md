# DevOps Engineer
## Enterprise Role Playbook for AI Developers

---

### Who This Person Is
The DevOps Engineer is the person who makes sure your system
actually runs — in production, at scale, under load, after
the third dependency update this month, at 3am when something
breaks and the on-call rotation lands on them. They are not
a deployment mechanism. They are an engineering discipline
that owns the full lifecycle of a system from code commit
to production incident to post-mortem.

They think in pipelines, uptime, mean time to recovery,
deployment frequency, and change failure rate. They have
opinions about your system's architecture because they
are the ones who will have to debug it at 3am without
the original developer on the phone. They value simplicity,
observability, and systems that fail loudly and obviously
over systems that fail quietly and mysteriously.

AI systems have complicated the DevOps Engineer's world
in ways that traditional software did not. A traditional
application behaves deterministically — the same input
produces the same output. An AI system does not. Output
drift, model version changes, prompt sensitivity, retrieval
index staleness, and non-deterministic behavior under load
are operational realities that don't have established
runbooks yet. The DevOps Engineer is building those
runbooks in real time, on live systems, often without
adequate tooling.

Build something they can operate. Document everything
they will need to know when you are not there. A system
that only its creator can maintain is not a production
system — it is a time bomb.

---

### What They Care About
- Deployability — can this system be deployed, rolled
  back, and redeployed reliably without heroic effort?
- Observability — can they see what the system is
  doing, why it is doing it, and what is wrong when
  it breaks — without reading the source code?
- Reliability — does the system degrade gracefully
  under load, handle dependency failures without
  cascading, and recover automatically from transient
  errors?
- Change management — every change to the system —
  model version, prompt update, configuration change,
  dependency update — needs to be tracked, tested,
  and reversible
- Operational handoff — will their team be able to
  operate this system without the developer who built
  it? if the answer is no, the system is not production-ready

---

### What They're Afraid Of
- A model version change upstream that silently changes
  system behavior without triggering any alerts —
  non-deterministic systems fail in ways that don't
  show up in traditional monitoring until something
  is very wrong
- An AI system with no rollback path — if the model
  provider deprecates a version, or a prompt change
  breaks outputs at scale, can the system be restored
  to a known-good state quickly?
- Prompt changes deployed without testing — a prompt
  that works in development can fail at production
  scale, with production data, in ways that weren't
  anticipated
- Runbooks that describe what the system does but
  not what to do when it doesn't — operational
  documentation that doesn't cover failure modes
  is not operational documentation
- Vendor dependency with no fallback — a system
  that goes down when the model provider has an
  outage and has no degraded-mode operation is
  a system with single-point-of-failure risk at
  the infrastructure level

---

### What "Good" Looks Like for Them
- A deployment pipeline that is automated, tested,
  and auditable — not a manual process documented
  in someone's personal notes
- Monitoring and alerting that covers AI-specific
  failure modes — not just the standard application
  metrics that were already in the dashboard
- Runbooks for every identified failure mode,
  written by someone who understands the system,
  validated by the person who will have to use
  them at 3am
- A model versioning strategy that treats model
  updates like dependency updates — tested in
  staging, deployed with a rollback plan, monitored
  after release
- Clear ownership of every component — who is
  responsible for the model, the prompt, the
  retrieval index, the application layer, the
  infrastructure? ambiguous ownership means
  slow incident response

---

### Governance & Compliance Considerations

#### Model Version Control is a Change Management Requirement
When your system's behavior depends on a specific model
version, that version is a dependency that requires
formal change management. Model providers deprecate
versions, release updates, and occasionally change
behavior in ways that are not fully documented. Pin
your model version explicitly. Test model updates
in a staging environment before production deployment.
Document the testing criteria — what outputs are you
validating, against what baseline? Treat a model
update as a significant change event, not a routine
patch.

#### Prompt Changes Require a Deployment Process
A prompt change is a code change. It changes system
behavior, it can introduce regressions, and it needs
to go through the same testing and deployment process
as any other code change. Systems where prompts are
edited directly in production, stored in spreadsheets,
or changed without version control are systems that
will produce unexplained behavioral changes that
no one can trace. Put prompts in version control.
Test prompt changes in staging. Deploy them through
the pipeline with a rollback path.

#### AI-Specific Monitoring Metrics Are Not Optional
Standard application monitoring — latency, error rate,
throughput — is necessary but not sufficient for AI
systems. AI-specific metrics that need monitoring
include: output quality drift over time, prompt
token consumption trends, model provider API latency
and error rates, retrieval relevance degradation,
and anomalous output patterns that may indicate
prompt injection or model manipulation. Work with
the DevOps Engineer to define these metrics before
deployment. A monitoring gap discovered during an
incident is not a monitoring gap — it is a missing
runbook entry.

#### Dependency Failures Need Graceful Degradation Paths
A system that fails completely when the model provider
has an outage is a system with unacceptable availability
risk for most enterprise use cases. Design degraded-mode
operation: what does the system do when the model API
is unavailable? Can it queue requests and retry? Can
it fall back to a simpler model or a cached response?
Can it fail gracefully with a meaningful user message
rather than a 500 error? These are not edge cases —
model provider outages happen, and the DevOps Engineer
will be managing the incident when they do.

#### Infrastructure as Code Applies to AI System Components
Every component of your AI system — the application,
the retrieval index, the vector database, the prompt
configuration, the monitoring setup — should be defined
as code and managed through the same infrastructure
as code practices as the rest of the enterprise
environment. AI systems that require manual configuration
steps, undocumented secrets, or tribal knowledge to
deploy are not production-ready systems. They are
systems that will fail the first time someone other
than the original developer has to deploy them.

#### Post-Mortems for AI Systems Require New Frameworks
When an AI system produces incorrect, harmful, or
unexpected outputs, the post-mortem process needs
to address questions that don't arise in traditional
application incidents: Was it a prompt issue, a
model issue, a retrieval issue, or a data issue?
Was the behavior consistent or intermittent? Can
it be reproduced? Was it a novel failure or a known
failure mode that wasn't caught in testing? Establish
AI-specific post-mortem templates and incident
classification frameworks before the first incident.
Building the framework during an incident is slower
and less thorough than building it in advance.

---

### Model Selection Guidance

**Recommended tier: Small to Medium for operational
workloads, architecture-dependent for the system
being operated**

- The DevOps Engineer's own use of AI tools skews
  toward operational tasks where speed and reliability
  matter more than nuance
- Small for high-volume operational support: log
  parsing, alert summarization, runbook generation
  from structured data, deployment status reporting
- Medium for incident analysis, post-mortem drafting,
  documentation generation, and monitoring configuration
  recommendations

**Model mapping:**
- Small — log analysis, alert triage, deployment
  status summaries, structured runbook generation
- Medium — incident post-mortem drafting, architecture
  documentation, monitoring gap analysis, operational
  playbook development

**On selecting models for the systems DevOps operates:**
The DevOps Engineer does not typically select the
model — they operate whatever was selected. But they
have legitimate operational requirements that should
influence model selection: Is the provider's API
stable and well-documented? Is there a versioning
policy with adequate deprecation notice? Is there
a status page with reliable uptime history? Is there
an SLA that meets the system's availability requirements?
These operational criteria need to be part of model
provider selection, and the DevOps Engineer should
be in the room when that decision is made.

---

### The One Thing Developers Get Wrong
They hand off a system, not a service.

A system is a collection of components that works
when the developer runs it. A service is a system
that works when the developer is on vacation, has
left the company, is unreachable, or is dealing
with a different incident.

The handoff gap looks like this: the system is
built, tested, and deployed. The developer writes
documentation that describes what the system does.
The DevOps Engineer gets paged at 3am because the
system is producing degraded outputs, and the
documentation tells them how the retrieval pipeline
works but not what to do when it breaks, not how
to tell the difference between a model issue and
a data issue, not where the prompt configuration
lives, and not who to call if the model provider
is having an incident.

Write the runbooks. Document the failure modes.
Make the prompt configuration findable. Establish
the escalation path. Define what "degraded but
acceptable" looks like versus "stop and roll back."
Build the monitoring before you leave.

The system that runs reliably without you is the
only system that is actually done.

---

### Fill-in-the-Blank Workflow Starter
```
SYSTEM:
You are a DevOps operations assistant supporting
[DEPARTMENT/TEAM NAME] at [COMPANY NAME].

Your purpose is to [PRIMARY TASK — e.g., "support
incident response by summarizing system alerts,
identifying probable root cause categories, and
drafting initial investigation steps for on-call
engineer review"].

System context:
- Model provider: [PROVIDER — e.g., "confirmed on
  approved vendor list; model version pinned to
  [VERSION]; deprecation date [DATE]"]
- Model version policy: [POLICY — e.g., "updates
  require staging validation against the output
  baseline test suite before production deployment"]
- Prompt location: [LOCATION — e.g., "version
  controlled in [REPO PATH]; changes require PR
  review and staging deployment"]
- Known failure modes: [LIST — e.g., "retrieval
  latency spikes under load, output quality
  degradation when context window exceeds 80%
  capacity, model provider API rate limits
  during peak hours"]

Always:
- Classify incidents using [CLASSIFICATION FRAMEWORK —
  e.g., "P1/P2/P3/P4 severity with AI-specific
  subcategories: model issue, prompt issue,
  retrieval issue, infrastructure issue"]
- Reference the current runbook version [VERSION]
  for all standard incident response steps
- Log all actions taken during incident response
  with [REQUIRED FIELDS — e.g., "timestamp, engineer
  ID, action taken, system state before and after,
  outcome"]
- Flag any incident involving [HIGH-IMPACT SCENARIOS —
  e.g., "data exfiltration indicators, prompt
  injection patterns, or model provider outage"]
  for immediate escalation to [CONTACT]
- Document post-mortem inputs in [FORMAT] within
  [TIMEFRAME — e.g., "24 hours of incident resolution"]

Never:
- Execute [RESTRICTED OPERATIONS — e.g., "production
  database modifications, model version rollbacks,
  or infrastructure scaling changes"] without
  human engineer authorization
- Modify [PROTECTED CONFIGURATIONS — e.g., "prompt
  files, model version pins, or monitoring thresholds"]
  outside of the approved change management process
- Retain [SENSITIVE CONTENT — e.g., "raw log data
  containing PII or authentication tokens"] beyond
  [RETENTION LIMIT — e.g., "the active incident
  session; full logs stored in the approved
  logging system only"]

When a failure mode has no existing runbook entry:
Document the symptoms, system state, and actions
taken. Flag for post-mortem inclusion. Route to
[ENGINEERING CONTACT] for runbook development
before the incident is closed.

Output format: [DEVOPS TEAM'S PREFERRED FORMAT —
e.g., "incident ID, severity, classification,
probable cause, current system state, recommended
next action, escalation status, engineer assignment"]
```

---

### Adjacent Roles to Consider
When building for DevOps Engineers, also read:
- **Security Engineer** — security controls need
  to be built into the deployment pipeline; DevOps
  and Security need to collaborate on security gates,
  vulnerability scanning, and AI-specific threat
  detection before the pipeline is finalized
- **IT Administrator** — infrastructure decisions
  affect deployment architecture; DevOps Engineer
  needs IT Administrator's requirements for
  access controls, network configuration, and
  approved tooling before the pipeline is designed
- **Developer** — the developer who built the system
  is the DevOps Engineer's primary knowledge source
  for failure modes and operational requirements;
  the handoff between these two roles is where
  most operational gaps are created
- **Risk Practitioner** — operational risk —
  availability, recovery time, dependency failure —
  needs to be included in the enterprise risk
  register; DevOps Engineer and Risk Practitioner
  need shared definitions of acceptable operational
  risk and escalation thresholds

---

*Enterprise Role Playbook for AI Developers | DevOps Engineer v0.1 |
ArchieCur + Sonnet + Claude Code | MIT License | 2026*
