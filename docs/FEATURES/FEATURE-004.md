docs/FEATURES/FEATURE-004.md

Feature: Objective Speech Metrics
Specification Status: APPROVED
Implementation Status: NOT STARTED

Purpose

Calculate reproducible delivery metrics from transcript and timing data without relying on subjective LLM estimation.

User Story

As a user, I want objective information about my speaking patterns so I can identify concrete delivery habits to improve.

Scope

Initial metrics:

duration
word count
words per minute
configured filler-word count
fillers per minute
pause count above defined threshold
longest detected pause

Repeated-phrase detection may be added only if technically reliable and still small enough for this feature.

Metric calculations should be deterministic.

Out of Scope
confidence score
charisma score
emotion detection
attractiveness
personality inference
accent scoring
pronunciation grading
AI-generated estimates of objective metrics
Dependencies
FEATURE-003
Acceptance Criteria
duration is calculated from approved timing data
word count follows one documented token-counting rule
WPM follows one documented formula
filler dictionary is centrally configurable
filler count follows documented context-handling rules
pause threshold is centrally configurable
pause metrics derive from timing data rather than LLM inference
identical input produces identical metric output
automated tests cover each deterministic metric
malformed/incomplete timing data produces a defined fallback or explicit unavailable state rather than fabricated values