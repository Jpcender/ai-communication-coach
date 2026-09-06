ARCHITECTURE.md

Status: APPROVED BASELINE

1. Architecture Goals

Optimize for:

low complexity
low operating cost
reliability
fast AI-assisted development
iOS-first launch
future Android compatibility
replaceable AI providers
scenario expansion without major rewrites

Avoid premature scale engineering.

2. Client

Approved direction:

React Native + Expo + TypeScript

Use Expo-managed tooling unless a required capability justifies otherwise.

Likely major components:

Expo Router
Expo Audio
React Native
TypeScript
EAS Build

Reason:

A shared codebase minimizes implementation burden while preserving a practical future path to Android.

3. Backend

Approved current backend direction:

Supabase

Use where justified for:

authentication
PostgreSQL
temporary audio storage
server-side functions
row-level security
persistent cloud data

Do not create a dedicated custom application server unless a documented requirement cannot be cleanly satisfied by the existing backend direction.

4. Authentication Sequencing

Authentication is not required for the earliest practice prototype.

Before Persistent Cloud History

The application may operate:

anonymously
local-first
without a user account

Practice state and temporary result state may remain on-device.

Server-side analysis services may process anonymous requests with appropriate abuse controls.

No durable per-user cloud history is required.

When Persistent Cloud History Is Introduced

Authentication must be introduced immediately before durable user-owned cloud history is required.

At that point:

attempts become associated with authenticated user IDs
row-level security protects user-owned records
history may persist across sessions/devices
progress may be calculated from cloud history

This avoids making account creation a prerequisite for validating the core speaking experience.

5. Core Practice Engine

The application will treat the following as the reusable core product engine:

record
transcribe
measure
evaluate
coach
retry
track

These capabilities should remain as scenario-independent as practical.

Record

Capture the user's spoken attempt.

Transcribe

Convert audio into transcript and timing data.

Measure

Calculate deterministic objective metrics.

Evaluate

Apply an appropriate communication rubric.

Coach

Return prioritized actionable feedback.

Retry

Allow another attempt against the same practice objective.

Track

Compare attempts and, once persistence exists, track longer-term trends.

6. Scenario Configuration

Scenario-specific behavior should preferably be represented as configuration rather than separate application implementations.

A scenario configuration may contain:

scenario key
prompt set
rubric
coaching instructions
recommended duration
score weights where justified

Possible future scenarios include:

interviews
public speaking
dating/social
networking
storytelling
sales/persuasion

Where those scenarios use the same solo-speaking practice model, they should reuse the same Core Practice Engine.

Conceptual relationship:

Core Practice Engine

Record
→ Transcribe
→ Measure
→ Evaluate
→ Coach
→ Retry
→ Track

Scenario Configuration

Interview configuration
Public-speaking configuration
Networking configuration
Storytelling configuration
Sales configuration
Dating/social configuration

A future scenario should not create a separate transcription system, metrics pipeline, coaching response format, retry system, or progress architecture without a documented technical reason.

Some future interaction modes, such as true multi-turn conversational roleplay, may require additional orchestration. Those capabilities should extend or wrap reusable core components rather than replace them unnecessarily.

7. AI Pipeline

Conceptual flow:

Mobile application
↓
temporary audio upload
↓
server-side processing
↓
speech-to-text provider
↓
deterministic metric calculation
↓
scenario configuration
↓
LLM coaching evaluation
↓
structured-result validation
↓
local result or authenticated persistence
↓
mobile results screen

API secrets must never exist in the mobile client.

8. AI Provider Abstraction

Do not scatter provider-specific assumptions throughout the application.

Separate conceptually:

Speech Transcription

Input:

audio

Output:

transcript
duration
timing data where supported
Communication Coaching

Input:

transcript
objective metrics
prompt
scenario configuration
rubric configuration

Output:

validated structured coaching result

Provider substitution should primarily affect backend integration code.

Do not build complex multi-provider orchestration in V1.

9. Coaching Schema

Coaching should return a stable structured schema.

Conceptual fields:

schema version
rubric version
scenario key
overall summary
highest-priority improvement
strengths
improvements
clarity score
structure score
concision score
specificity score
examples where useful
suggested retry goal

The UI should render validated fields.

It should not depend on arbitrary free-form model prose.

10. Data Model

Keep V1 small.

Local Prototype State

Before authentication:

selected prompt
temporary attempt
temporary transcript
temporary analysis result
retry linkage where needed

This may be stored on-device.

profiles

Introduced when authentication/persistence is required.

Possible fields:

id
created_at
onboarding_status
selected_communication_goal
prompts

Possible fields:

id
scenario_key
prompt_text
difficulty
active_status
attempts

Introduced for persistent cloud history.

Possible fields:

id
user_id
prompt_id or custom_prompt
previous_attempt_id
created_at
duration
transcript
objective_metrics
coaching_result
rubric_version
scenario_key
processing_status

Avoid additional tables until justified.

11. Raw Audio Retention

Approved direction:

Audio is temporary server-side processing data.

After successful processing, raw audio should be deleted.

Persist where required:

transcript
objective metrics
coaching result

Do not permanently retain raw recordings by default unless a future approved feature demonstrates that stored playback provides enough user value to justify the additional privacy, security, and storage burden.

12. Subscription Architecture

Do not implement subscription infrastructure during early core-loop development.

When monetization is justified:

RevenueCat is the preferred candidate for subscription management if justified when monetization is implemented.

It is not a permanent architecture decision.

The implementation decision should be reassessed based on:

required platforms
pricing model
subscription versus practice packages
App Store requirements
operating cost
implementation complexity
13. Analytics

Track product events, not sensitive speech content.

Examples:

practice_started
recording_completed
analysis_completed
analysis_failed
retry_started
retry_completed
authentication_completed
history_viewed
paywall_viewed
purchase_started
purchase_completed

Do not send complete transcripts or raw audio to general-purpose analytics services.

14. Reliability

AI operations must have:

timeout handling
safe retry behavior
schema validation
graceful failure states
cost logging
provider-failure logging

Never silently manufacture coaching when upstream processing fails.

Initial Engineering Targets

Initial engineering targets — subject to revision after beta measurement.

Possible early targets:

≥98% successful practice submission under normal supported conditions
≥99% valid coaching-schema responses after allowed retry behavior
p95 ≤25 seconds from completed audio upload to complete analysis result

These are provisional engineering targets rather than permanent acceptance requirements.

15. Security

Minimum V1 direction:

server-side secret management
HTTPS
row-level security once user-owned cloud records exist
authenticated users may access only their own persistent attempts
no AI API keys in client code
minimal personal-data collection
account deletion once accounts exist
data deletion support
16. Android

Do not launch Android simultaneously with the initial iOS release unless evidence justifies it.

However:

avoid iOS-only application architecture
avoid unnecessary Swift-specific business logic
keep shared business logic in TypeScript
prefer cross-platform Expo libraries

Android should primarily become a distribution and QA expansion rather than a ground-up rewrite.
