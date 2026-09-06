CURRENT_STATE.md

Status: ACTIVE

Current Phase

Product definition approved.

The project may proceed into implementation planning and FEATURE-001 development.

Application code should be implemented only against approved feature documentation and approved architectural decisions.

Current Product Direction

Approved V1:

A mobile speaking coach for adults preparing for an upcoming high-stakes speaking situation who want structured solo practice.

Core behavior:

Choose → Record → Analyze → Coach → Retry

Long-term scope remains broader communication, charisma, and presence coaching.

The application is not an interview-specific product.

Current Architecture Direction

Approved:

iPhone first
React Native
Expo
TypeScript
Supabase as current backend direction
speech-to-text provider abstraction
LLM coaching provider abstraction
deterministic objective-metrics layer
scenario configuration layered over a reusable core practice engine
Current Sequencing Direction
Early Prototype
anonymous/local-first use permitted
prompt selection
audio recording
transcription
metrics
coaching
results
retry/comparison
no persistent cloud history required
no monetization infrastructure
After Core Practice Validation

Introduce:

authentication
persistent cloud history
progress/history

Authentication appears immediately before persistent cloud ownership becomes necessary.

After Commercial Value Validation

Implement monetization if justified.

RevenueCat is currently only the preferred candidate for subscription management.

Approved Product and Architecture Decisions

Approved:

narrow V1 customer
broad non-interview-specific brand
no computer vision in V1
React Native + Expo + TypeScript
iOS-first / Android-portable architecture
Supabase backend direction
deterministic objective metrics
structured LLM coaching output
no single charisma score
Core Practice Engine / Scenario Configuration separation
temporary raw-audio retention
one prioritized coaching action
validation before major expansion
anonymous/local-first prototype sequencing
authentication before persistent cloud history
no monetization infrastructure before core-loop validation
RevenueCat only as a preferred future candidate
engineering reliability numbers remain provisional
FEATURE-001 through FEATURE-010 implementation sequence
Still Unvalidated
exact pricing
subscription versus limited-duration package
free usage allowance
exact payment provider choice
commercial validation thresholds
final engineering reliability thresholds
initial rubric effectiveness
filler-word rules
pause thresholds
exact authentication method
permanent raw-audio playback/storage value
Not Started
Expo project implementation
application code
backend configuration
audio recording implementation
transcription implementation
metric calculations
coaching integration
authentication
persistent history
analytics implementation
subscriptions
App Store configuration
beta recruitment
Immediate Next Step

Begin implementation with:

FEATURE-001 — App Shell and Prompt Selection

Do not ask Codex to build the entire MVP.

The implementation sequence is:

FEATURE-001
FEATURE-002
FEATURE-003
FEATURE-004
FEATURE-005
FEATURE-006
FEATURE-007
validate the core loop
FEATURE-008
FEATURE-009
validate commercial model
FEATURE-010 if justified
Important Constraint

The GitHub repository is the authoritative source of truth.

If any chat guidance conflicts with newer approved repository documentation, the approved repository documentation wins.
