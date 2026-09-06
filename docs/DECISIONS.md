DECISIONS.md

Status: ACTIVE

Decisions become APPROVED only after explicit founder approval and repository update.

D-001 — V1 Wedge

Status: APPROVED

V1 focuses on solo recorded speaking practice for short, high-stakes communication.

The primary V1 customer is:

Adults preparing for an upcoming high-stakes speaking situation who want structured solo practice.

V1 does not begin with live conversational simulation.

Reason

This provides:

clear immediate user need
measurable practice behavior
low technical complexity
reusable architecture
lower operating cost
easier quality evaluation
D-002 — Brand Scope

Status: APPROVED

The product is a broad communication, charisma, and presence coaching product.

Interviews may appear as one practice situation but will not define:

product name
visual identity
architecture
navigation
core terminology
long-term positioning
D-003 — No Computer Vision in V1

Status: APPROVED

V1 uses audio and transcript analysis only.

Video/body-language analysis is deferred until the audio-based coaching loop demonstrates sufficient value.

D-004 — Mobile Technology

Status: APPROVED

Use:

React Native
Expo
TypeScript

Launch iOS first while preserving a practical Android path.

D-005 — Backend Direction

Status: APPROVED

Use Supabase as the current backend direction.

Use it only where needed.

Do not introduce a custom backend stack without a documented requirement.

D-006 — Coaching Engine

Status: APPROVED

Use:

deterministic calculations for objective metrics
structured LLM evaluation for subjective communication quality

Do not ask an LLM to invent objective measurements that can be calculated from available data.

D-007 — Scoring

Status: APPROVED

Do not create one authoritative "charisma score."

Use interpretable communication dimensions and objective delivery metrics.

D-008 — Core Engine and Scenario Configuration

Status: APPROVED

Separate reusable product behavior into:

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

Future scenarios should reuse the same core engine wherever practical.

D-009 — Audio Privacy

Status: APPROVED

Raw audio is temporary server-side processing data.

Persist transcripts, metrics, and coaching results where required.

Permanent raw-audio storage requires a future explicit decision.

D-010 — Pricing Hypothesis

Status: PROPOSED — REQUIRES VALIDATION

Initial pricing hypothesis:

Approximately $8–15/month, or an equivalent limited-duration practice package.

Final:

price
billing structure
free allowance
package size
subscription duration

must be validated.

No specific price is approved.

D-011 — Coaching Priority

Status: APPROVED

Every analysis should identify one highest-impact improvement.

The product should prioritize behavior change over feedback volume.

D-012 — Expansion Rule

Status: APPROVED

No major new communication mode should enter development until the Record → Analyze → Coach → Retry loop demonstrates meaningful user value.

D-013 — Authentication Sequencing

Status: APPROVED

Early practice flow may operate anonymously and local-first.

Authentication should be introduced immediately before persistent user-owned cloud history becomes necessary.

Do not require account creation merely to validate the initial speaking-practice loop.

D-014 — Subscription Infrastructure

Status: APPROVED

Do not build monetization infrastructure before the core practice loop is validated.

When monetization is implemented:

RevenueCat is the preferred candidate for subscription management if justified at that time.

RevenueCat is not a permanent architecture requirement.

D-015 — Reliability Targets

Status: APPROVED

Initial numerical reliability and latency targets are engineering hypotheses.

They must be labeled:

Initial engineering targets — subject to revision after beta measurement.

Beta evidence may tighten, loosen, or replace these thresholds.
