# docs/FEATURES/FEATURE-001.md

**Feature:** App Shell and Prompt Selection
**Specification Status:** APPROVED
**Implementation Status:** READY

## Purpose

Create the smallest usable application shell from which a user can choose a practice prompt and proceed toward a speaking session.

FEATURE-001 establishes only the navigation and interaction required for the beginning of the core practice flow.

## User Story

As a user preparing to practice speaking, I want to choose a practice prompt so I can begin a focused speaking session with minimal friction.

## Scope

Implement:

* minimal application shell
* prompt-selection screen
* exactly nine approved built-in prompts
* custom prompt entry
* selected-prompt state
* navigation from prompt selection into one minimal placeholder recording destination
* basic empty/error states required by this flow

No additional prompt content or future product destinations are included.

## Approved Built-In Prompt Set

FEATURE-001 includes exactly these nine prompts.

### Explain

1. Explain a complicated idea simply.
2. Describe a project you are proud of.
3. Explain why something matters.

### Story

1. Tell a memorable story.
2. Describe a challenge you overcame.
3. Describe a mistake and what you learned.

### Persuade

1. Convince someone to support an idea.
2. Recommend something you believe in.
3. Make the case for a decision.

Do not expand, generate, substitute, or add to this built-in prompt set during FEATURE-001 without separate approval.

## Custom Prompt Rules

A custom prompt is valid only when all of the following are true:

* surrounding whitespace has been trimmed
* at least one non-whitespace character remains
* trimmed length is no greater than 300 characters

Therefore:

* empty input is invalid
* whitespace-only input is invalid
* input exceeding 300 characters after trimming is invalid

When a valid custom prompt is accepted, the trimmed value becomes the selected prompt.

### Selection-State Protection

Invalid custom-prompt edits must never replace or clear a currently valid selected prompt.

Example:

1. user selects a valid built-in prompt
2. user begins editing a custom prompt
3. custom input is empty, whitespace-only, or exceeds 300 characters
4. existing valid built-in selection remains selected

Likewise:

1. user has a valid custom prompt selected
2. user edits the custom input into an invalid state
3. the previously valid selected prompt remains intact until another valid selection is explicitly accepted

Invalid draft input and valid selected-prompt state must therefore be treated as distinct concepts.

## Minimal Recording Placeholder

FEATURE-001 may include exactly one future-route placeholder solely to verify:

* navigation
* selected-prompt transfer
* safe return navigation

The placeholder recording destination must:

* display the currently selected prompt
* allow the user to navigate safely back to prompt selection
* contain no microphone access
* contain no audio-recording logic
* contain no recording timer
* contain no waveform
* contain no simulated microphone control
* contain no fake Record button
* contain no fake Stop button
* contain no disabled recording controls intended to imitate future functionality

The placeholder should communicate only enough information to make its development purpose clear.

This is the **sole approved exception** to the rule against implementing future placeholder destinations during FEATURE-001.

No other future screens may be added as placeholders under this feature.

## Navigation Constraint

Navigation must remain deliberately minimal.

FEATURE-001 supports only:

**Prompt selection → minimal recording placeholder → safe back navigation**

Do not create permanent application navigation until additional approved destinations exist.

## Out of Scope

FEATURE-001 explicitly does not include:

* onboarding
* communication-goal questionnaire
* personalized onboarding
* Today tab
* Practice tab
* Progress tab
* permanent bottom-tab navigation
* permanent multi-destination app navigation
* actual microphone recording
* microphone permission requests
* audio capture
* transcription
* objective speech metrics
* AI coaching
* accounts
* authentication
* cloud history
* progress
* subscriptions
* paywall
* scenario marketplace
* prompt generation
* prompt-library expansion
* daily curriculum
* streaks
* XP
* gamification
* personalization engine
* event-preparation system
* additional placeholder screens

No founder-note idea becomes part of FEATURE-001 unless separately approved.

## Design Direction

Use the approved dark-first design direction:

> graphite surfaces + indigo primary accent family

Exact:

* hex values
* shades
* spacing
* border radii
* component-detail tokens

remain adjustable implementation/design choices under DESIGN_SYSTEM.md.

The shell should feel:

* focused
* minimal
* credible
* modern
* private

Avoid decorative complexity.

## Dependencies

Required:

* approved React Native + Expo + TypeScript direction
* approved DESIGN_SYSTEM.md
* approved D-016
* approved D-017

No backend dependency is required for FEATURE-001.

No authentication dependency is required.

## Acceptance Criteria

### Application Shell

* application launches successfully on the target iOS development environment
* initial screen renders without requiring authentication
* application uses the approved dark-first visual direction
* no permanent tab navigation is present

### Built-In Prompts

* exactly nine built-in prompts are present
* exactly three prompts appear under Explain
* exactly three prompts appear under Story
* exactly three prompts appear under Persuade
* prompt wording matches the approved prompt set
* no additional built-in prompts are introduced
* user can select exactly one built-in prompt

### Custom Prompt Validation

* surrounding whitespace is trimmed before validating an accepted custom prompt
* empty input is invalid
* whitespace-only input is invalid
* trimmed input of 1–300 characters may be accepted
* trimmed input exceeding 300 characters is invalid
* invalid input produces a clear recoverable state
* invalid input does not crash the application

### Selection State

* selected built-in prompt is stored in local application state
* valid custom prompt can become the selected prompt
* accepted custom prompt is stored in trimmed form
* only one valid prompt is active for the upcoming practice session
* invalid custom-prompt edits never replace the currently valid selected prompt
* invalid custom-prompt edits never clear the currently valid selected prompt
* switching to another valid prompt produces predictable selected state

### Minimal Recording Placeholder

* exactly one placeholder recording destination exists
* placeholder displays the selected prompt exactly as provided by selected state
* placeholder supports safe back navigation
* returning to prompt selection does not corrupt valid selected-prompt state
* placeholder contains no microphone functionality
* placeholder contains no recording functionality
* placeholder contains no simulated/fake recording controls

### Navigation

* user can navigate from prompt selection to the placeholder only when a valid selected prompt exists
* selected prompt is available at the placeholder destination
* navigation does not depend on authentication
* navigation does not depend on cloud persistence
* navigation does not require Today, Practice, or Progress tabs

### Scope Protection

No implementation is included for:

* onboarding
* real recording
* progress
* accounts
* subscriptions
* long-term navigation
* additional placeholder destinations
* founder backlog ideas

unless separately approved through repository documentation.
