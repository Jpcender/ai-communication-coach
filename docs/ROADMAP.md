ROADMAP.md

Status: APPROVED BASELINE

Principle

The roadmap is validation-gated rather than feature-gated.

Do not build later phases merely because they appear here.

Phase 0 — Product Definition

Deliverables:

PRODUCT_SPEC.md
ROADMAP.md
ARCHITECTURE.md
DESIGN_SYSTEM.md
DECISIONS.md
CURRENT_STATE.md
FEATURE-001 through FEATURE-010
AGENTS.md

Exit condition:

Founder approves the core V1 product and architecture decisions.

Status: COMPLETE

Phase 1 — Anonymous Practice Shell

Features:

FEATURE-001 — App shell and prompt selection
FEATURE-002 — Audio recording

Characteristics:

no required account
local-first state
no persistent cloud history
no monetization

Exit condition:

A user can select a prompt and reliably record a practice response on the target iPhone environment.

Phase 2 — Analysis Pipeline

Features:

FEATURE-003 — Transcription pipeline
FEATURE-004 — Objective speech metrics
FEATURE-005 — AI coaching engine
FEATURE-006 — Results screen

Characteristics:

practice may remain anonymous
recordings are processed server-side
raw audio remains temporary
completed results may remain local-first during prototype testing
cloud user history is not yet required

Exit condition:

A real recording consistently produces understandable transcription, deterministic metrics, structured coaching, and a usable result.

Phase 3 — Core Improvement Loop

Feature:

FEATURE-007 — Retry and comparison

Exit condition:

A user can:

practice
receive coaching
retry the same prompt
compare relevant changes

This completes the minimum core practice loop:

Record → Analyze → Coach → Retry

Phase 4 — Core Loop Validation

Run a small external beta before building account/history or monetization complexity.

Measure:

first-analysis completion
immediate retry rate
feedback usefulness
failure rate
analysis latency
return intent
actual repeat behavior
qualitative willingness to pay

Gate:

Do not proceed automatically.

If the practice loop is not useful enough to cause repeated practice, improve the core experience before expanding infrastructure.

Phase 5 — Identity and Persistent History

Features:

FEATURE-008 — Authentication and persistent history
FEATURE-009 — Progress/history view

Authentication is introduced at this point because persistent cloud history now requires stable user identity.

Before this phase:

anonymous/local-first use is acceptable
no permanent cloud history is required

After this phase:

user attempts may sync to their account
history survives reinstall/device changes where supported
progress may be calculated from persisted attempts

Exit condition:

Authenticated users can securely access their own persistent practice history and progress.

Phase 6 — Monetization Validation and Implementation

Feature:

FEATURE-010 — Monetization

Precondition:

The core practice loop has demonstrated sufficient user value to justify adding payment infrastructure.

Activities may include:

price interviews/tests
package testing
paywall experimentation
purchase implementation
entitlement enforcement

Preferred subscription management candidate:

RevenueCat, if justified at implementation time.

RevenueCat is not a permanent architecture requirement.

Exit condition:

A validated commercial model can be purchased and access rights behave correctly.

Phase 7 — Private Paid Beta / Launch Readiness

Verify:

critical bugs resolved
analytics operational
crash reporting operational
privacy policy
terms
account deletion
payment restoration where applicable
production cost controls
App Store assets
support contact
Phase 8 — V1 Launch

Launch only after:

practice loop is useful
core reliability is acceptable
privacy behavior is understood
pricing/package has evidence
monetization works where applicable
Post-V1 Candidates

Not commitments.

Potential future directions:

expanded prompt/scenario configurations
personalized practice recommendations
stronger progress analytics
longer-form presentation practice
conversational roleplay
sales/persuasion simulations
dating/social simulations
video/body-language feedback
Android
web/desktop
teams/enterprise

Every major addition requires a documented decision before implementation.
