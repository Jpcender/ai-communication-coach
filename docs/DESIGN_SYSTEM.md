DESIGN_SYSTEM.md

Status: APPROVED BASELINE

1. Design Principle

The product should feel like a serious personal performance coach, not a corporate training portal and not a game.

Desired attributes:

calm
focused
modern
credible
private
actionable
performance-oriented

Avoid interview-specific imagery such as:

résumés
suits
briefcases
hiring iconography

Avoid cliché charisma imagery such as:

flames
crowns
alpha symbols
dominance imagery
attractiveness meters

Avoid styling that makes the product feel:

childish
excessively gamified
cyberpunk
neon-heavy
visually aggressive
2. Core UX Principle

Every analysis screen should answer:

What should I fix next?

The application should prioritize action over information density.

3. Visual Direction

The approved initial visual direction is:

Dark-first graphite surfaces with an indigo primary accent family.

The interface should feel intentionally dark rather than simply applying a black background to standard components.

Use:

layered graphite surfaces
strong text contrast
restrained indigo accents
minimal decorative color
clear emphasis for the primary action

Exact colors remain implementation/design tokens rather than fixed founder decisions.

They may change during visual testing without requiring a product-scope decision.

4. Working Color Tokens

The following are working implementation tokens only.

They are not permanent founder-approved hex values.

Example starting tokens:

Primary:
#6C63FF

Primary emphasized:
#7C74FF

Background:
#0D0F12

Surface:
#15181E

Elevated surface:
#1B1F27

Primary text:
#F5F7FA

Secondary text:
#A5ACB8

Muted text:
#747C89

Border:
#292E38

Success:
#35B987

Warning:
#D99A3E

Error:
#E05A66

These values may be adjusted for:

accessibility
OLED appearance
contrast
visual hierarchy
brand refinement
platform behavior
5. Visual Hierarchy

For future results screens:

highest-priority coaching action
retry button
improvement comparison
key delivery metrics
detailed coaching
transcript

Do not lead with a giant arbitrary score.

6. Typography

Use native/system typography initially.

No custom font dependency is required for V1.

Preferred iOS behavior should naturally align with system typography.

Hierarchy:

Display
H1
H2
Body
Supporting
Metric

Prioritize readability over branding novelty.

7. Spacing

Use an 8-point spacing system.

Common values:

4
8
16
24
32
48

Exact spacing values remain implementation tokens where appropriate.

8. Components

Keep component vocabulary small.

Potential shared components include:

PrimaryButton
SecondaryButton
TextButton
Card
PromptCard
MetricCard
ScoreRow
RecordingControl
ProgressIndicator
FeedbackSection
TranscriptSection
ErrorState
EmptyState

Do not create abstractions for components used once unless consistency or testability justifies them.

9. Primary Action Principle

Prefer one obvious primary action per screen.

Secondary actions should not visually compete with the action that advances the core practice flow.

For FEATURE-001, the interface should make the path from prompt selection toward speaking obvious.

Do not add permanent navigation merely to make the application appear more complete.

10. FEATURE-001 Navigation Direction

FEATURE-001 should implement only navigation necessary for:

Prompt selection → future recording route

Do not introduce:

Today tab
Practice tab
Progress tab
onboarding flow
account destination
permanent bottom navigation
placeholder screens for future features

Navigation architecture may expand later when multiple approved product destinations actually exist.

11. Recording Screen

When FEATURE-002 is implemented, the recording screen should minimize distraction.

Show:

prompt
timer
stop control

Waveform may be included only if it is technically trivial and does not distract from speaking.

Do not display:

WPM
filler count
live scores
AI suggestions

The user should focus on speaking.

12. Feedback Language

Coaching should be:

specific
concise
behavior-based
nonjudgmental
actionable

Prefer:

"Your main point arrives late. State the conclusion in your first two sentences."

Avoid:

"You lack confidence."

13. Accessibility

Minimum requirements:

44×44 point minimum touch targets
sufficient text contrast
screen-reader labels
no meaning conveyed by color alone
scalable text where practical
microphone-denial state that remains navigable

Dark-first design does not reduce accessibility requirements.

14. Motion

Use motion only where it supports:

state changes
recording state
processing state
progress changes
screen transitions

No decorative animation system is required for V1.

15. Token Authority

Founder-approved design decisions define broad direction.

Implementation tokens define details.

Changes to:

exact hex values
spacing increments
corner radii
shadow values
animation durations

do not require founder-level architectural approval unless they materially change product identity or usability.