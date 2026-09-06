DESIGN_SYSTEM.md

Status: APPROVED BASELINE

1. Design Principle

The product should feel like a serious personal coach, not a corporate training portal and not a game.

Desired attributes:

calm
focused
modern
credible
private
actionable

Avoid interview imagery such as résumés, suits, briefcases, or hiring-related branding.

Avoid cliché charisma imagery such as flames, crowns, alpha symbols, or attractiveness meters.

2. Core UX Principle

Every analysis screen should answer:

What should I fix next?

The application should prioritize action over information density.

3. Visual Hierarchy

Results:

highest-priority coaching action
retry button
improvement comparison
key delivery metrics
detailed coaching
transcript

Do not lead with a giant arbitrary score.

4. Proposed Color Tokens

Primary:
#315CF5

Background:
#F7F8FA

Surface:
#FFFFFF

Primary text:
#16181D

Secondary text:
#667085

Border:
#E4E7EC

Success:
#16835D

Warning:
#B86E00

Error:
#C73535

These remain working visual tokens and may change during UI validation without changing product architecture.

5. Typography

Use native/system typography initially.

No custom font dependency is required for V1.

Hierarchy:

Display
H1
H2
Body
Supporting
Metric

Prioritize readability over branding novelty.

6. Spacing

Use an 8-point spacing system.

Common values:

4
8
16
24
32
48
7. Components

Keep component vocabulary small:

PrimaryButton
SecondaryButton
TextButton
Card
MetricCard
ScoreRow
PromptCard
RecordingControl
ProgressIndicator
FeedbackSection
TranscriptSection
ErrorState
EmptyState

Do not create abstractions for components used once unless required for consistency.

8. Recording Screen

Must minimize distraction.

Show:

prompt
timer
waveform only if technically trivial
stop control

Do not display:

WPM
filler count
live scores
AI suggestions

The user should focus on speaking.

9. Feedback Language

Coaching must be:

specific
concise
behavior-based
nonjudgmental
actionable

Prefer:

"Your main point arrives late. State the conclusion in your first two sentences."

Avoid:

"You lack confidence."

10. Accessibility

Minimum requirements:

44×44 point minimum touch targets
sufficient text contrast
screen-reader labels
no meaning conveyed by color alone
scalable text where practical
microphone denial state that remains navigable
11. Motion

Use motion only for:

recording state
processing state
progress changes
screen transitions

No decorative animation system in V1.
