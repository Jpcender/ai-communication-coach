docs/FEATURES/FEATURE-001.md

Feature: App Shell and Prompt Selection
Specification Status: APPROVED
Implementation Status: READY

Purpose

Create the smallest usable application shell from which a user can begin a practice session.

User Story

As a user preparing to practice speaking, I want to choose a practice prompt so I can start a focused session.

Scope

Implement:

basic application navigation
home/practice-selection screen
small built-in prompt set
custom prompt entry
selected-prompt state
transition into the future recording screen
basic empty/error states

Built-in prompts should support transferable categories such as:

Explain
Story
Persuade
Out of Scope
microphone recording
transcription
AI coaching
accounts
cloud history
progress
subscriptions
scenario marketplace
large prompt library
Dependencies

None beyond approved project setup and design-system direction.

Acceptance Criteria
application launches successfully on the target iOS development environment
user can view built-in prompts
user can select exactly one prompt
user can enter a custom prompt
custom prompt enforces an approved character limit
selected prompt is available to the next practice step
application does not require authentication
no cloud persistence is required
invalid/empty custom input is handled without crashing