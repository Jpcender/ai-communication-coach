docs/FEATURES/FEATURE-005.md

Feature: AI Coaching Engine
Specification Status: APPROVED
Implementation Status: NOT STARTED

Purpose

Turn the user's transcript and objective metrics into concise, structured, actionable communication coaching.

User Story

As a user, I want feedback that tells me the most important thing to improve so my next attempt is better.

Scope

Implement:

scenario/configuration input
fixed initial communication rubric
structured LLM request
structured response schema
schema validation
one highest-priority improvement
up to two strengths
up to three improvements
one retry goal
rubric scores for:
clarity
structure
concision
specificity
safe retry behavior for malformed provider responses

Initial V1 coaching configuration may use a single general high-stakes-speaking scenario configuration.

Out of Scope
arbitrary free-form coaching output
conversational roleplay
live coaching
emotion inference
personality inference
charisma score
attractiveness judgments
multiple specialized scenario engines
automatic clinical or psychological conclusions
Dependencies
FEATURE-003
FEATURE-004
approved coaching schema
approved initial scenario configuration
Acceptance Criteria
coaching request includes transcript
coaching request includes deterministic metrics
coaching request includes selected prompt
coaching request includes scenario/rubric configuration
model response must pass schema validation before display
result contains exactly one highest-priority improvement
result contains no more than two strengths
result contains no more than three improvements
result contains exactly one retry goal
required rubric scores remain within documented bounds
malformed response triggers defined retry/error behavior
provider failure never produces fabricated coaching
model API secret is never included in mobile client code
Initial Engineering Targets

Initial engineering targets — subject to revision after beta measurement.

Candidate target:

≥99% valid coaching-schema responses after permitted retry handling

This is provisional and should be recalibrated from beta data.