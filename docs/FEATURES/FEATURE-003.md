docs/FEATURES/FEATURE-003.md

Feature: Transcription Pipeline
Specification Status: APPROVED
Implementation Status: NOT STARTED

Purpose

Convert a completed practice recording into reliable transcript and timing data.

User Story

As a user, I want my spoken response transcribed so the application can analyze what I said and how I delivered it.

Scope

Implement:

temporary audio upload
secure server-side transcription request
provider integration
transcript retrieval
duration metadata
word/segment timing data where available
processing state
transcription failure handling
temporary raw-audio deletion after successful processing
server-side secret handling

Early prototype use may remain anonymous.

Out of Scope
speech metrics beyond raw transcription metadata
coaching
persistent cloud attempt history
authentication requirement
permanent raw-audio storage
multi-provider failover architecture
Dependencies
FEATURE-002
approved backend foundation
Acceptance Criteria
valid completed recording can be submitted for transcription
provider secret does not exist in the mobile client bundle
successful request returns transcript text
timing information is returned where supported by the selected provider
transcription errors return an explicit failure state
retry behavior does not silently create duplicate attempts
temporary raw audio is deleted after successful processing
failed deletion is logged for remediation
identical stored transcription input can be passed unchanged into later deterministic processing
Initial Engineering Targets

Initial engineering targets — subject to revision after beta measurement.

Candidate target:

≥98% successful submission/transcription completion under normal supported conditions

This is not a permanent product requirement.