docs/FEATURES/FEATURE-002.md

Feature: Audio Recording
Specification Status: APPROVED
Implementation Status: NOT STARTED

Purpose

Allow the user to record a spoken practice response reliably on-device.

User Story

As a user, I want to record my response to the selected prompt so the application can later analyze how I communicate.

Scope

Implement:

microphone permission request
recording start
elapsed recording timer
stop recording
cancel recording
local recording state
maximum recording duration
clear handling for permission denial
handoff of completed local audio to the future transcription layer

Recommended analysis range:

30–180 seconds.

Out of Scope
transcription
upload
speech metrics
coaching
live feedback
waveform unless trivial and already supported
cloud storage
permanent recording history
Dependencies
FEATURE-001
Acceptance Criteria
first-time microphone permission flow works
denied permission produces a recoverable state
user can begin recording
visible timer advances while recording
user can stop recording manually
user can cancel without creating a completed attempt
recording automatically stops at the approved maximum duration
completed audio is available locally for the next processing step
application remains usable after multiple consecutive recordings
no raw recording is permanently uploaded or stored by this feature