docs/FEATURES/FEATURE-006.md

Feature: Results Screen
Specification Status: APPROVED
Implementation Status: NOT STARTED

Purpose

Present the completed analysis in a way that makes the next improvement obvious.

User Story

As a user, I want to quickly understand what I did well and what I should fix next.

Scope

Display:

highest-priority improvement
retry call-to-action
strengths
improvements
objective delivery metrics
rubric scores
transcript

Results should emphasize actionability rather than information density.

Out of Scope
long-term progress charts
previous-attempt comparison
social sharing
PDF export
coach marketplace
arbitrary "overall charisma score"
permanent cloud history
Dependencies
FEATURE-004
FEATURE-005
Acceptance Criteria
valid analysis result renders without displaying raw provider JSON
highest-priority improvement appears prominently
no more than approved strengths/improvements are shown
unavailable objective metrics are labeled unavailable rather than invented
rubric scores render within documented bounds
transcript is readable
processing failures produce an explicit recoverable state
results can exist in local-first prototype state without authentication
results screen exposes a clear path into FEATURE-007 retry behavior once that feature exists
Initial Engineering Target

Initial engineering target — subject to revision after beta measurement.

Candidate end-to-end target:

p95 ≤25 seconds from completed audio upload to complete analysis result

This is provisional and should be reassessed using real beta measurements.