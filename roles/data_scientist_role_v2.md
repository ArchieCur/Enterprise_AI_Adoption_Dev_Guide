# Data Scientist
## Enterprise Role Playbook for AI Developers

---

### Who This Person Is
The Data Scientist is the enterprise's applied researcher —
the person who builds the models, runs the experiments, and
translates statistical methodology into business outcomes.
They sit at the intersection of mathematics, software
engineering, and domain expertise, and they are comfortable
with uncertainty in a way that most enterprise roles are not.
Uncertainty, for a Data Scientist, is not a problem to be
eliminated. It is a quantity to be measured, communicated,
and managed.

They think in hypotheses, experiments, and model performance
metrics. They speak in precision, recall, confidence intervals,
and feature importance. They have strong opinions about
methodology because methodology is what separates a finding
that holds up from one that doesn't — and they have seen
enough poorly designed analyses produce confidently wrong
conclusions to be protective of process.

When you are building an AI system that incorporates machine
learning components, the Data Scientist is not your user.
They are your peer. They will have opinions about your
architecture, your training data, your evaluation methodology,
and your deployment approach — and those opinions will
frequently be correct. The developer who treats the Data
Scientist as a domain expert partner will build a better
system than the one who treats them as a requirements source.

They are also, in many enterprises, the person most likely
to notice when your AI system is producing outputs that
look plausible but aren't. They know what model failure
looks like from the inside. Build with them, not around them.

---

### What They Care About
- Model validity — does the model actually measure what
  it claims to measure, and does it generalize beyond
  the training data?
- Reproducibility — can the experiment be run again and
  produce the same result? can another Data Scientist
  follow the methodology and reach the same conclusion?
- Feature integrity — are the input features to the model
  meaningful, available at inference time, and free from
  data leakage?
- Evaluation rigor — is the model being evaluated on
  held-out data, against appropriate baselines, using
  metrics that reflect real-world performance?
- Explainability — can the model's outputs be explained
  to a business stakeholder in terms they can act on,
  and to a regulator in terms that satisfy their requirements?

---

### What They're Afraid Of
- A model deployed to production that was evaluated on
  training data — the most common and most consequential
  methodological error in applied machine learning
- Data leakage — features that contain information about
  the target variable that wouldn't be available at
  inference time, producing evaluation metrics that
  are optimistic by design
- Model drift — a model that was valid at training time
  degrading silently in production as the data distribution
  shifts, with no monitoring in place to detect it
- Pressure to ship before the methodology is sound —
  a Data Scientist who is pushed to deploy a model
  before it is ready knows exactly what will happen
  and will remember it when it does
- Being handed a pre-built model and told to validate
  it — post-hoc validation of a model that was already
  selected is not validation, it is documentation, and
  most Data Scientists know the difference

---

### What "Good" Looks Like for Them
- A well-defined problem statement with clear success
  metrics before any modeling begins
- Access to the data they need — complete, documented,
  and with a clear lineage from source to feature
- An evaluation framework that was designed before
  the model was trained, not after the results came in
- A deployment pipeline that includes model monitoring,
  drift detection, and a retraining trigger
- Organizational trust in their methodology — the ability
  to say "this model isn't ready" and have that finding
  respected rather than overridden

---

### Governance & Compliance Considerations

#### Model Documentation is a Compliance Requirement in Regulated Industries
In financial services, healthcare, and other regulated
industries, models used in consequential decisions require
formal documentation — model cards, risk assessments,
validation reports. The EU AI Act extends this requirement
to high-risk AI systems regardless of industry. Know
your documentation requirements before the model is
built. A model that works but cannot be documented to
the required standard is a model that cannot be deployed.

#### Training Data Provenance Must Be Established
The data used to train a model is a compliance artifact.
Where did it come from? Was it collected with appropriate
consent? Does it contain personal data that requires
a lawful basis for processing? Is it representative of
the population the model will be applied to? These
questions need answers before training begins, not
after a regulatory inquiry arrives. Work with Legal,
Privacy, and the Data Engineer to establish data
provenance documentation as a standard part of the
model development workflow.

#### Bias and Fairness Assessment is Not Optional
Models trained on historical data inherit historical
biases. In consequential use cases — hiring, credit,
healthcare, criminal justice — biased model outputs
can constitute illegal discrimination. Fairness
assessment needs to be part of the evaluation
methodology, not an afterthought. Define the fairness
metrics relevant to your use case before training.
Evaluate against them with the same rigor as performance
metrics. Document the results even when they are
uncomfortable.

#### Model Versioning and Change Management Apply
Every trained model is a versioned artifact. When a
model is retrained — on new data, with new features,
with a different architecture — that is a change event
that requires documentation, validation, and controlled
deployment. A production model that was silently
replaced with a retrained version without going through
change management is a governance gap regardless of
whether the new version performs better.

#### Explainability Requirements Vary by Use Case
Some use cases require that individual model predictions
be explainable — why did the model score this applicant
this way? Others require aggregate explainability —
what features drive the model's predictions overall?
Regulatory requirements for explainability are evolving
rapidly and vary by jurisdiction and use case. Establish
the explainability requirement for your specific
deployment before selecting a modeling approach.
Some model architectures that produce excellent
performance metrics are difficult or impossible to
explain at the level some regulations require.

---

### Model Selection Guidance

**Recommended tier: Small to Large, task-dependent**

- The Data Scientist's relationship with AI models is
  as a builder and evaluator, not primarily as a user;
  the relevant selection question is what foundation
  model or modeling approach best serves the specific
  problem, not what tier handles the task
- Small for structured, high-volume, formatting-heavy
  tasks with well-defined inputs and outputs: experiment
  log formatting from structured templates, data
  dictionary entry generation from structured metadata,
  bibliography and citation formatting for literature
  reviews, model card section formatting from structured
  inputs. Note: methodology review, statistical
  interpretation, and evaluation support should begin
  at Medium. Small models applied to analytical reasoning
  tasks can produce outputs that look structured and
  confident while missing the methodological nuance
  that the Data Scientist's workflow depends on — and
  Data Scientist Small-model use cases tend to creep.
  A developer who starts with "format these experiment
  logs" can drift toward "summarize the findings" without
  realizing they have moved into territory where Small
  models will fail them inconsistently.
- Medium for structured analytical tasks where the
  Data Scientist uses AI assistance: literature review,
  code generation for data processing pipelines,
  documentation drafting, experiment logging support
- Large for complex reasoning tasks: methodology
  review, statistical interpretation, multi-framework
  compliance analysis for model governance, technical
  report drafting

**Model mapping:**
- Small — experiment log formatting from templates,
  data dictionary entry generation from structured
  metadata, citation and bibliography formatting,
  model card section formatting from structured inputs
- Medium — experiment documentation, data processing
  code generation, methodology literature review,
  model card drafting from structured inputs
- Large — complex statistical methodology review,
  multi-framework model governance analysis,
  technical report drafting, cross-domain
  feature engineering reasoning

**On foundation models as components:**
When the Data Scientist is evaluating whether to use
a foundation model as a component in a larger system,
the selection criteria shift entirely: task fit,
fine-tuning requirements, inference cost at scale,
explainability constraints, and vendor security
posture all become primary evaluation criteria.
This is a different decision than selecting a model
for Data Scientist productivity support, and it
requires the Data Scientist's full methodology
applied to the evaluation itself.

---

### The One Thing Developers Get Wrong
They deploy the model and call it done.

Model deployment is not the end of the Data Scientist's
work — it is the beginning of the monitoring problem.
A model that performs well on evaluation data in a
controlled environment will encounter the real world
in production, and the real world is messier, more
varied, and more adversarial than any evaluation
dataset. Data distributions shift. User behavior
changes. Edge cases that didn't appear in training
start appearing at scale.

The developer who builds the deployment pipeline
and walks away has built half a system. The other
half is monitoring: tracking model performance over
time, detecting drift before it becomes a problem,
triggering retraining when performance degrades,
and maintaining the feedback loop that keeps the
model valid as the world it operates in changes.

Build the monitoring before you deploy. Define the
drift detection threshold before the model goes live.
Establish the retraining trigger and the retraining
process before the first alert fires. The Data
Scientist knows this. Make sure the deployment
architecture reflects it.

---

### Fill-in-the-Blank Workflow Starter
```
SYSTEM:
You are a data science workflow assistant supporting
[TEAM NAME] at [COMPANY NAME].

Your purpose is to [PRIMARY TASK — e.g., "support
experiment documentation, model card generation,
and methodology review for machine learning projects
in [DOMAIN — e.g., customer churn prediction]"].

Always:
- Apply [METHODOLOGY STANDARD — e.g., "the team's
  standard experiment tracking protocol using
  [PLATFORM — e.g., MLflow]"] to all experiment
  documentation outputs
- Flag any methodology concern involving
  [HIGH-RISK AREAS — e.g., "data leakage, evaluation
  on training data, or fairness metric gaps"] for
  Data Scientist review before proceeding
- Cite data sources with [REQUIRED PROVENANCE FIELDS —
  e.g., "dataset name, version, collection date,
  consent basis, known limitations"]
- Include confidence levels and known limitations
  in all outputs that will be used to inform
  deployment decisions
- Apply [FAIRNESS FRAMEWORK — e.g., "demographic
  parity and equalized odds evaluated across
  [PROTECTED ATTRIBUTES]"] to all model evaluation
  documentation

Never:
- Generate evaluation results or performance metrics —
  these must come from [APPROVED EVALUATION FRAMEWORK]
  run by the Data Scientist on held-out data
- Recommend deployment readiness without [SIGN-OFF
  REQUIREMENT — e.g., "Data Scientist validation
  report and model governance review"]
- Access [RESTRICTED DATA — e.g., "production user
  data outside of approved anonymized exports"]
  outside of formally scoped experiments
- Document a model as explainable without
  [EXPLAINABILITY EVIDENCE — e.g., "SHAP values
  or equivalent feature attribution at the
  required granularity"]

When a methodology question falls outside established
team standards:
Flag it. Route to [DATA SCIENCE LEAD]. Do not
proceed with a non-standard approach without
documented approval.

Output format: [DATA SCIENCE TEAM'S PREFERRED FORMAT —
e.g., "structured experiment log with hypothesis,
data, methodology, results, limitations, and
next steps — flagged for peer review before
any deployment decision"]
```

---

### Adjacent Roles to Consider
When building for Data Scientists, also read:
- **Data Engineer** — the Data Scientist depends
  on the Data Engineer for clean, documented,
  pipeline-ready data; misalignment between these
  two roles is the most common source of feature
  integrity problems in production ML systems
- **Data Analyst** — Data Scientist and Data Analyst
  overlap in organizations where the boundary between
  analytics and machine learning is blurry; understand
  where one ends and the other begins before designing
  the system
- **DevOps Engineer** — model deployment, monitoring,
  and retraining pipelines are DevOps territory;
  the Data Scientist defines what needs to be monitored,
  the DevOps Engineer builds the infrastructure that
  does it
- **Legal/Compliance** — model governance, bias
  assessment, and explainability requirements
  connect Data Science directly to Legal; in
  regulated industries this is not an optional
  relationship

---

*Enterprise Role Playbook for AI Developers | Data Scientist v0.1 |
ArchieCur + Sonnet + Claude Code | MIT License | 2026*
