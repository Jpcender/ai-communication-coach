AGENTS.md

Status: APPROVED BASELINE

Purpose

This file governs AI coding agents working in this repository.

Repository documentation is the product source of truth.

Required Reading Order

Before a meaningful implementation change, review:

PRODUCT_SPEC.md
CURRENT_STATE.md
DECISIONS.md
ARCHITECTURE.md
DESIGN_SYSTEM.md
the specific docs/FEATURES/FEATURE-XXX.md being implemented

Do not rely on assumptions from previous chats when repository documentation provides an answer.

Product Scope

The long-term product is an AI communication, charisma, and presence coach.

Version 1 is intentionally narrow:

structured solo practice for adults preparing for an upcoming high-stakes speaking situation

Do not reinterpret V1 as:

an interview platform
a dating platform
a public-speaking platform
a sales platform
a conversational AI simulator

Specific scenarios should remain configuration where possible.

Decision Authority

Distinguish:

APPROVED

May be implemented when the relevant feature is active in CURRENT_STATE.md.

PROPOSED

May be discussed or documented but should not automatically be implemented.

If implementation requires a major undocumented product or architecture decision, stop that implementation and document the decision first.

Feature Discipline

Approved implementation sequence:

FEATURE-001 — App shell and prompt selection
FEATURE-002 — Audio recording
FEATURE-003 — Transcription pipeline
FEATURE-004 — Objective speech metrics
FEATURE-005 — AI coaching engine
FEATURE-006 — Results screen
FEATURE-007 — Retry and comparison
FEATURE-008 — Authentication and persistent history
FEATURE-009 — Progress/history view
FEATURE-010 — Monetization

Do not implement later features merely because their requirements are known.

Each feature should be independently implementable and testable.

Validation Gate

FEATURE-001 through FEATURE-007 form the core practice loop.

Do not proceed automatically into:

persistent account infrastructure
progress expansion
monetization
new scenarios

without evaluating the core practice loop.

Monetization infrastructure specifically must not be implemented before sufficient practice-loop validation.

Authentication Rule

Do not introduce required account creation into early prototype flows unless a concrete approved requirement justifies it.

Before FEATURE-008:

local-first state is acceptable
anonymous use is acceptable
no durable user-owned cloud history is assumed

FEATURE-008 introduces authentication because persistent cloud history requires stable user ownership.

Core Architecture Rule

Preserve the distinction between:

Core Practice Engine
record
transcribe
measure
evaluate
coach
retry
track
Scenario Configuration
scenario key
prompt set
rubric
coaching instructions
recommended duration
score weights where justified

Do not create separate implementations for interviews, presentations, networking, storytelling, sales, dating/social, or other scenarios when configuration can reasonably reuse the same engine.

Implementation Philosophy

Prefer:

simple code
explicit code
boring infrastructure
mature dependencies
small changes
testable functions
TypeScript safety
server-side secrets
cross-platform React Native patterns

Avoid:

premature abstractions
microservices
custom infrastructure without demonstrated need
unnecessary native code
dependency proliferation
speculative refactors
features added merely because they are technically possible
Architecture Constraints

Approved technology direction:

React Native
Expo
TypeScript
Supabase
provider-based AI integrations
iOS-first release

Business logic should remain portable to Android.

Avoid Swift-specific implementation unless a documented requirement demands it.

AI Integration Rules

Never expose provider API keys in the client.

Validate structured AI responses server-side.

Separate:

transcription
objective metric calculation
coaching evaluation

Objective calculations should use deterministic code where reliable.

Do not use an LLM to estimate metrics that can be calculated directly from available data.

Coaching Rules

Do not present unsupported psychological conclusions.

Do not classify users as:

confident/unconfident
charismatic/uncharismatic
attractive/unattractive
truthful/deceptive
intelligent/unintelligent

unless a future approved feature establishes a defensible methodology.

Feedback should focus on observable communication behavior.

Data Rules

Collect only data required for product functionality.

Do not send transcripts or recordings to unrelated analytics services.

Raw audio must follow DECISIONS.md.

User-owned persistent cloud records must be protected by authorization and row-level security.

Subscription Rule

Do not implement payment infrastructure before FEATURE-010 is explicitly cleared to begin after validation.

RevenueCat is only:

Preferred candidate for subscription management if justified when monetization is implemented.

Do not treat it as a mandatory dependency.

Dependency Rule

Before adding a dependency:

determine whether existing tools solve the requirement
verify that the dependency is maintained
explain why it is needed
prefer Expo-compatible packages
avoid native complexity without sufficient product value
Change Discipline

For each implementation task:

identify the approved feature
verify dependencies are complete
implement the smallest working change
test it
update documentation if behavior or architecture changed
update CURRENT_STATE.md when project state materially changes

Do not combine unrelated refactors with feature work.

Error Handling

Relevant workflows must explicitly handle:

microphone denial
recording failure
network failure
upload failure
transcription failure
metric-generation failure
coaching failure
malformed model output
authentication failure once authentication exists
purchase failure once monetization exists

Never hide failure behind fabricated success data.

Testing

Critical areas require appropriate tests.

Highest priority:

deterministic metric calculations
structured coaching validation
retry linkage
authorization after FEATURE-008
entitlement enforcement after FEATURE-010
failure states

Do not test AI output by expecting exact wording.

Test:

schemas
field presence
bounds
deterministic surrounding behavior
error behavior
Reliability Targets

Any numerical reliability or latency targets marked as:

Initial engineering targets — subject to revision after beta measurement.

are provisional.

Do not silently promote them into permanent architecture requirements.

Secrets

Never:

commit API keys
hardcode service-role credentials
expose server credentials in mobile bundles
print sensitive user content unnecessarily in production logs
Scope Escalation

The following require a documented decision before implementation:

video analysis
computer vision
live conversation
speech-to-speech AI
new backend infrastructure
new AI provider
Android launch
web application
enterprise features
social features
user-generated public content
major monetization changes
permanent audio storage
health or clinical functionality
Final Rule

When uncertain, choose the implementation that:

satisfies the approved requirement
introduces the least complexity
costs the least to operate
is easiest to test
is easiest to remove or change later
