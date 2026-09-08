docs/FEATURES/FEATURE-001.md

Feature: App Shell and Prompt Selection
Specification Status: APPROVED
Implementation Status: READY

Purpose

Create the smallest usable application shell from which a user can choose a practice prompt and proceed toward a speaking session.

FEATURE-001 should establish only the navigation and interaction required for the beginning of the core practice flow.

User Story

As a user preparing to practice speaking, I want to choose a practice prompt so I can begin a focused speaking session with minimal friction.

Scope

Implement:

minimal application shell
prompt-selection screen
small built-in prompt set
custom prompt entry
selected-prompt state
navigation from prompt selection into the future recording route
basic empty/error states required by this flow

Built-in prompts should support transferable categories such as:

Explain
Story
Persuade

The future recording route may exist only as the minimum destination or placeholder necessary to prove navigation.

Do not implement recording behavior in this feature.

Navigation Constraint

Navigation must remain deliberately minimal.

FEATURE-001 should support only:

Prompt selection → future recording route

Do not create permanent application navigation until additional approved destinations exist.

Out of Scope

FEATURE-001 explicitly does not include:

onboarding
communication-goal questionnaire
personalized onboarding
Today tab
Practice tab
Progress tab
permanent bottom-tab navigation
permanent multi-destination app navigation
microphone recording
transcription
objective speech metrics
AI coaching
accounts
authentication
cloud history
progress
subscriptions
paywall
scenario marketplace
large prompt library
daily curriculum
streaks
XP
gamification
personalization engine
event-preparation system

No founder-note idea becomes part of FEATURE-001 unless separately approved.

Design Direction

Use the approved dark-first design direction:

graphite surfaces + indigo primary accent family

Exact:

hex values
shades
spacing
border radii
component-detail tokens

remain adjustable implementation/design choices under DESIGN_SYSTEM.md.

The shell should feel:

focused
minimal
credible
modern
private

Avoid decorative complexity.

Dependencies

Required:

approved React Native + Expo + TypeScript direction
approved DESIGN_SYSTEM.md
approved D-016
approved D-017

No backend dependency is required for FEATURE-001.

No authentication dependency is required.

Acceptance Criteria
Application shell
application launches successfully on the target iOS development environment
initial screen renders without requiring authentication
application uses the approved dark-first visual direction
no permanent tab navigation is present
Built-in prompts
user can view the approved small built-in prompt set
prompts are organized clearly enough to distinguish available practice choices
user can select exactly one built-in prompt
Custom prompt
user can enter a custom prompt
custom prompt enforces a documented character limit
whitespace-only input is rejected
invalid custom input produces a clear recoverable state
invalid input does not crash the application
Selection state
selected built-in prompt is stored in local application state
valid custom prompt can become the selected prompt
switching selections produces predictable state
only one prompt is active for the upcoming practice session
Navigation
selected prompt is available to the future recording route
user can navigate from prompt selection to that route
navigation does not depend on authentication
navigation does not depend on cloud persistence
navigation does not require Today, Practice, or Progress tabs
user can return to prompt selection without corrupting selected-prompt state
Scope protection

FEATURE-001 is not complete merely because additional speculative UI has been added.

No implementation should be included for:

onboarding
recording
progress
accounts
subscriptions
long-term navigation
founder backlog ideas

unless separately approved through repository documentation.