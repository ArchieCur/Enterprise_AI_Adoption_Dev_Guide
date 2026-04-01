# Marketing
## Enterprise Role Playbook for AI Developers

---

### Who This Person Is
Marketing is the enterprise's most enthusiastic early adopter
of AI — and that enthusiasm is exactly what makes them
interesting to build for and genuinely dangerous to deploy for
without guardrails.

They move fast. They test constantly. They have already been
using consumer AI tools for months before your enterprise
system arrives, which means they have established workflows,
strong opinions, and a low tolerance for systems that slow
them down. They will adopt your system faster than any other
function in the enterprise. They will also push it further
than you designed it to go — and they will do it cheerfully,
creatively, and at scale.

Marketing thinks in campaigns, audiences, and brand voice.
They are measured on engagement, pipeline, and revenue
influence. They live in deadlines that don't move because
the campaign launch date is already in the market. They are
collaborative, iterative, and comfortable with ambiguity in
a way that Finance and Legal are not.

They are also sitting on top of the brand. Every output your
system produces that touches a customer is a brand event.
A compliance failure in Finance is an internal problem until
it isn't. A brand failure in Marketing is public the moment
it posts.

Build for their speed. Protect the brand they're sitting on.

---

### What They Care About
- Campaign performance — clicks, conversions, pipeline,
  revenue influence; they are measured on outcomes,
  not outputs
- Brand consistency — every piece of content that leaves
  Marketing carries the brand; inconsistency at scale
  is a brand problem
- Speed to market — campaign windows are real; a system
  that produces good content slowly loses to a system
  that produces good enough content fast
- Creative quality — they have taste, and they will notice
  when AI output is generic, flat, or off-brand before
  any other function in the enterprise
- Audience insight — they want to know what resonates,
  with whom, and why; systems that help them understand
  their audience are systems they will champion

---

### What They're Afraid Of
- A brand-damaging output that goes live before anyone
  catches it — at campaign scale, one bad piece of
  content can become a PR incident before the team
  finishes their morning coffee
- AI-generated content that is detectably generic —
  audiences can feel when content was written by a
  model that was handed a brief and left alone; brand
  credibility erodes quietly and quickly
- Losing the brand voice — tone, vocabulary, personality,
  and values are carefully constructed assets; a system
  that drifts from brand voice at scale does damage
  that takes months to repair
- Regulatory exposure in content — FTC disclosure
  requirements for AI-generated content, advertising
  standards, and industry-specific restrictions
  (financial services, healthcare, pharma) create
  compliance obligations Marketing may not fully own
  but will be blamed for
- The system becoming a crutch — Marketing leaders
  worry that AI tools will flatten creative output
  across the industry, eroding the differentiation
  they've spent years building

---

### What "Good" Looks Like for Them
- Content that sounds like the brand wrote it, not
  like a model was handed the style guide
- Faster brief-to-draft cycles without sacrificing
  the creative iteration that produces the best work
- A system that learns brand voice well enough that
  the team spends their time on strategy and judgment,
  not on rewriting AI output to sound human
- Compliance guardrails that are invisible to the
  workflow — they don't want to think about FTC
  disclosures on every output; they want the system
  to handle it
- Performance data that closes the loop — content
  generation connected to engagement analytics so
  the system gets smarter about what actually works

---

### Governance & Compliance Considerations

#### FTC Disclosure Requirements Are Evolving Rapidly
The Federal Trade Commission has issued guidance on AI-generated
content and endorsements that is actively being updated.
Depending on your system's outputs — sponsored content,
influencer materials, testimonials, product claims —
disclosure requirements may apply. Build disclosure
flagging into the workflow. Marketing should not be
making FTC compliance decisions at campaign velocity
without systematic support.

#### Industry-Specific Advertising Restrictions Apply
Financial services, healthcare, pharmaceutical, and
alcohol marketing operate under advertising restrictions
that govern what can be claimed, how it must be
qualified, and what disclosures are required. A general-
purpose content generation system deployed in a regulated
industry without industry-specific guardrails will
produce non-compliant content. Know the industry before
you build the content layer.

#### Personalization at Scale Triggers Data Privacy Obligations
Personalization — dynamic content, audience segmentation,
and individualized messaging — is one of the most powerful
and most commonly requested Marketing AI use cases. It is
also where the most significant data privacy exposure lives.
Feeding audience behavioral data, engagement signals, and
individual interaction history into a content system
triggers GDPR, CCPA, and similar obligations that go well
beyond standard content compliance. Before building any
personalization capability, confirm with Legal which data
categories can be used, under what consent framework, and
with what retention limits. Personalization built without
this foundation is a data privacy incident waiting to happen
at campaign scale.

#### Audience Data Used to Train or Tune the System Requires Separate Review
Using audience engagement data to improve system outputs —
whether through fine-tuning, retrieval augmentation, or
feedback loops — is a different data processing activity
than using it to generate a single campaign. It requires
its own legal review, its own consent framework, and its
own data governance controls. Do not assume that consent
to receive personalized content is consent to have
behavioral data used for model improvement.

#### Brand Voice is Intellectual Property
The brand voice, tone guidelines, messaging frameworks,
and campaign assets you feed into your system are
proprietary intellectual property. Understand how
your model provider handles training data, fine-tuning,
and data retention. Feeding proprietary brand assets
into a system that uses them for model improvement
without authorization is an IP exposure Legal needs
to review.

#### AI Content Disclosure is Becoming a Legal Requirement
Several jurisdictions are moving toward mandatory
disclosure of AI-generated content in advertising and
public communications. Build the infrastructure to
track which content was AI-generated, AI-assisted,
or human-created. Retrofitting content provenance
tracking after deployment is expensive and often
incomplete.

#### Social Media Platform Policies Govern Distribution
Major social media platforms have their own policies
on AI-generated content that are separate from and
sometimes stricter than regulatory requirements.
Content that complies with FTC guidance may still
violate platform terms of service. Marketing needs
platform policy review built into their publishing
workflow, not bolted on after the content is ready
to post.

#### Copyright in AI-Generated Content is Unsettled
The copyright status of AI-generated content is
actively being litigated and legislated. Content
generated entirely by AI may not be protectable
under current copyright law in some jurisdictions.
For Marketing, this means AI-generated assets —
images, copy, video scripts — may not carry the
same IP protection as human-created work. Legal
needs to advise on how to structure content
creation workflows to preserve protectability.

---

### Model Selection Guidance

**Recommended tier: Small to Large, brand-tuned**

- Small for high-volume, structured, low-ambiguity
  content operations where brand voice is not the
  primary output: meta descriptions, alt text,
  SEO metadata, internal content tagging, social
  post scheduling copy, asset categorization,
  internal routing and categorization of campaign
  assets
- Medium for standard content production: social
  copy, email subject lines, ad variations,
  email campaigns, content repurposing
- Large for brand-critical outputs: campaign hero
  copy, executive communications, thought leadership,
  content that will represent the brand in high-
  visibility channels
- Consider fine-tuning or system prompt investment
  heavily for this role — a generic model producing
  generic content defeats the purpose; brand voice
  configuration is not optional, it is the product

**Model mapping:**
- Small — meta descriptions, alt text, SEO metadata,
  content tags, asset categorization, social post
  scheduling copy, internal content routing,
  internal summaries from structured inputs
- Medium — social media variations, email campaigns,
  ad copy testing, content repurposing, landing pages
- Large — campaign strategy narratives, brand voice-
  critical long-form content, executive thought
  leadership, high-stakes customer communications

**Critical:** Marketing will push volume through your
system faster than any other function. Model cost
per output compounds quickly at campaign scale.
Build cost awareness into the architecture and
establish volume thresholds before deployment.
A system that works beautifully in testing can
become expensive in production when Marketing
runs a global campaign through it.

---

### The One Thing Developers Get Wrong
They build a content machine and forget they were
supposed to build a brand asset.

The system generates content. Marketing uses it.
Volume goes up, cycle time goes down, the metrics
look good. And six months later someone pulls a
brand audit and the content produced by the system
sounds like everyone else's content produced by
the same model with a different logo on it.

Brand voice is not a style guide you paste into
a system prompt. It is a living set of decisions
about how the organization sounds, what it values,
and what it refuses to say. It requires ongoing
investment — examples, feedback loops, human review
of outputs that are drifting, and a process for
updating the voice configuration as the brand evolves.

Build the feedback loop from day one. Give Marketing
a way to flag off-brand outputs and feed that signal
back into the system. The content machine that learns
the brand is a competitive asset. The one that doesn't
is a commodity.

---

### Fill-in-the-Blank Workflow Starter
```
SYSTEM:
You are a marketing content assistant for [BRAND NAME]
at [COMPANY NAME].

Your purpose is to [PRIMARY TASK — e.g., "draft campaign
copy across email, social, and digital channels that
reflects [BRAND NAME]'s voice and drives [PRIMARY
METRIC — e.g., pipeline, engagement, conversion]"].

Brand voice: [BRAND VOICE DESCRIPTION — e.g., "Direct
and confident, never corporate. We use plain language.
We lead with customer outcomes, not product features.
We never use [PROHIBITED TERMS/PHRASES]."]

Always:
- Apply brand voice guidelines consistently across
  all output formats
- Flag any claim about [SENSITIVE AREAS — e.g.,
  "product performance, competitive comparisons,
  or regulatory compliance"] for human review
  before use
- Include [REQUIRED DISCLOSURES — e.g., "AI-assisted
  content disclosure language"] when required by
  [PLATFORM/CHANNEL]
- Produce [NUMBER] variations when generating
  copy for testing
- Format outputs for [CHANNEL SPECIFICATIONS —
  e.g., "LinkedIn: 150 words max; email subject:
  50 characters max; paid social: headline +
  body + CTA"]
- Flag any content that uses [AUDIENCE DATA TYPES —
  e.g., "behavioral signals, engagement history,
  or individual interaction data"] for privacy
  review before personalization is applied

Never:
- Make product claims that are not in [APPROVED
  CLAIMS SOURCE — e.g., "the current approved
  messaging framework"]
- Use competitor names in [RESTRICTED CONTEXTS —
  e.g., "direct comparisons without Legal review"]
- Generate content for [RESTRICTED CHANNELS —
  e.g., "regulated markets including healthcare
  and financial services verticals"] without
  compliance review
- Produce content that could be perceived as
  [BRAND PROHIBITIONS — e.g., "political, divisive,
  or inconsistent with our stated brand values"]
- Use audience behavioral data for personalization
  without confirming [CONSENT FRAMEWORK — e.g.,
  "active opt-in under the current privacy policy
  and applicable data regulations"]

When a request falls outside approved messaging:
Flag the gap and route to [MARKETING CONTACT/ROLE]
before generating content that could misrepresent
the brand.

Output format: [MARKETING TEAM'S PREFERRED FORMAT —
e.g., "channel label, word/character count, copy,
compliance flags if any, suggested A/B variant"]
```

---

### Adjacent Roles to Consider
When building for Marketing, also read:
- **Legal/Compliance** — FTC requirements, industry
  advertising restrictions, audience data privacy
  obligations, and AI content disclosure requirements
  make Legal a required partner, not an optional
  reviewer; Marketing moves fast enough that
  compliance gaps scale before anyone notices
- **Business Leader** — brand decisions at scale
  require executive visibility; a system producing
  high-volume customer-facing content needs leadership
  awareness and sign-off on the guardrails before
  deployment
- **Business Owner** — if Marketing serves specific
  business units, the Business Owner's domain expertise
  and customer knowledge should inform the content
  configuration; generic brand voice applied to a
  specialized domain produces content that sounds
  like it came from the wrong company
- **Customer Service** — Marketing creates the
  promise; Customer Service lives with the gap
  between that promise and reality; align their
  perspectives before your content system goes live

---

*Enterprise Role Playbook for AI Developers | Marketing v0.1 |
ArchieCur + Sonnet + Claude Code | MIT License | 2026*
