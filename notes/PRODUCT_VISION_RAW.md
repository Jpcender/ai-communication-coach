Status: NON-AUTHORITATIVE — FOUNDER VISION / BACKLOG

Purpose

Preserve strategically valuable founder ideas without converting them into approved product requirements.

Nothing in this document is approved for implementation merely because it appears here.

The authoritative sources remain:

PRODUCT_SPEC.md
DECISIONS.md
ARCHITECTURE.md
DESIGN_SYSTEM.md
CURRENT_STATE.md
approved docs/FEATURES/*.md

To move an idea from this backlog into implementation:

review the idea against current product evidence
validate where necessary
make an explicit founder/product decision
update DECISIONS.md if materially architectural or strategic
create or revise an approved feature specification
update CURRENT_STATE.md when implementation may begin
1. Event Preparation
Concept

Allow a user to tell the product:

“I have something important coming up.”

Examples:

interview Thursday
presentation tomorrow
client pitch Friday
networking event
difficult conversation
speech
important social interaction

The system could generate a short preparation plan leading up to the event.

Why Preserve It

This strongly matches the approved V1 customer's underlying need and could become a major bridge between the narrow initial product and broader communication coaching.

Potential Architecture

Prefer:

Event context
→ Scenario Configuration
→ generated practice sequence
→ existing Core Practice Engine

Avoid building a separate practice engine.

Status

POST-V1 — STRONG IDEA

Requires validation and explicit future approval.

2. Personalized Communication Model
Concept

Build a longitudinal model of the user's communication patterns.

Potential inputs:

recurring weaknesses
strongest skills
scenario-specific weaknesses
practice history
recent scores
improvement rate
interventions that helped
neglected skills
difficulty progression

Example:

A user may speak at an appropriate pace generally but consistently rush during interview-style answers.

The product should eventually detect the contextual pattern rather than treating pace as one universal trait.

Why Preserve It

Potentially one of the strongest long-term differentiators.

The moat is not simply:

“AI gives feedback.”

It is:

“The product learns how this person communicates, where they struggle, and which coaching changes their behavior.”

Status

POST-V1 — STRONG IDEA

Material long-term architecture implications.

3. Communication Profile
Concept

A persistent view of communication development across supported skill dimensions.

Potential future dimensions may include:

Delivery
pacing
pausing
articulation
vocal variety
Message
clarity
concision
structure
storytelling
Interaction
listening
questioning
improvisation
conversation flow

Only dimensions with defensible measurement should be included.

Guardrails

Avoid:

universal charisma score
pseudo-scientific precision
unsupported psychological traits
too many numbers without actionable meaning
Status

POST-V1

Requires validated longitudinal data and stable scoring.

4. Before vs Now
Concept

Allow users to compare current performance with an older attempt.

Potential experience:

First attempt from three months ago
versus
current attempt

Could include:

objective metrics
rubric changes
transcript differences
audio playback if future storage is explicitly approved
Why Preserve It

Actual evidence of improvement may be more emotionally compelling than synthetic progression mechanics.

Architecture Impact

Historical audio playback would conflict with the current temporary-audio policy.

Permanent recording storage would require:

explicit user consent
privacy review
storage policy
deletion controls
new approved decision
Status

POST-V1 — STRONG IDEA

5. Scenario Builder
Concept

Allow a user to describe a real communication situation in natural language.

Example:

“I need to tell my manager that my workload is becoming unreasonable without sounding confrontational.”

The system could generate:

scenario context
prompts
target skills
rubric
coaching instructions
recommended difficulty
Architecture Principle

Prefer generating or selecting Scenario Configuration that reuses the Core Practice Engine.

Status

POST-V1 — STRONG IDEA

6. Content Generation Framework
Concept

Create a scalable configuration model for exercises.

Potential fields:

scenario
target skill
difficulty
recommended duration
prompt type
expected behavior
coaching rubric
scoring weights where justified
Why Preserve It

Could allow the product to expand practice content without manually coding each exercise.

Risk

Do not build a generalized content-management system before content scale exists.

Status

POST-V1

7. Multi-Turn AI Roleplay
Concept

Future conversational simulations such as:

interviewer
customer
networking contact
skeptical buyer
difficult coworker
social/date scenario
Architecture Impact

Likely requires:

conversation state
turn management
role behavior
additional latency controls
additional inference cost
potentially speech synthesis

Reuse:

transcription
metrics
coaching
user-history components

where practical.

Status

POST-V1

Material architecture expansion requiring explicit approval.

8. Real-World Missions
Concept

Extend training beyond simulated practice.

Examples:

initiate one conversation
ask three follow-up questions
deliberately tell a structured story
practice pausing during an actual conversation
introduce yourself to someone new
Why Preserve It

Could improve transfer from practice behavior to real-world behavior.

Risk

Verification is weak and may initially rely on self-report.

Status

POST-V1 / NEEDS VALIDATION

9. Daily Arena
Concept

Short unpredictable communication exercises intended to create repeat practice.

Potential characteristics:

brief
varied
skill-focused
immediately actionable
Risk

The approved V1 customer may be episodic rather than daily.

Do not assume Duolingo-style daily behavior.

Status

POST-V1 / EXPERIMENT

10. Skill Progression and Adaptive Difficulty
Concept

Gradually increase difficulty as demonstrated ability improves.

Potential factors:

response complexity
time pressure
scenario ambiguity
persuasive resistance
required structure
audience difficulty
Risk

Difficulty must be meaningfully defined before automation.

Status

POST-V1 / NEEDS VALIDATION

11. Gamification

Potential future experiments:

XP
streaks
levels
personal bests
achievements
skill mastery
boss challenges
Guardrail

Gamification must reinforce practice rather than replace intrinsic improvement.

Avoid:

arbitrary overall development score
manipulative streak loss
excessive reward animations
childish presentation
engagement mechanics disconnected from communication outcomes
Status

EXPERIMENT / NEEDS VALIDATION

Not assumed to be part of the long-term product.

12. Weekly Recap
Concept

Summarize:

practice volume
recurring weakness
strongest improvement
useful metric trends
suggested next focus
Status

POST-V1 / NEEDS VALIDATION

Do not build until weekly usage actually exists.

13. Personal Bests
Concept

Highlight genuine improvements in objective behaviors.

Examples:

lowest filler rate
best pacing range
longest structured response within target duration

Prefer objective metrics over unstable AI-generated records.

Status

POST-V1 / EXPERIMENT

14. Advanced Voice Metrics

Potential future measurements:

speech-to-silence ratio
pitch variation
volume variation
speaking consistency
articulation characteristics
vocal variety
Architecture Impact

Some may require direct audio-signal processing rather than transcript/timestamp analysis.

Status

POST-V1 / NEEDS VALIDATION

Do not silently expand FEATURE-004.

15. Evidence-Based AI Feedback
Concept

AI-assessed feedback should be supported by observable evidence.

Prefer:

“Your answer became less direct after the opening because you repeated the same qualification three times.”

Over:

“You sound unconfident.”

Status

The underlying principle is already aligned with approved coaching rules.

More sophisticated evidence presentation remains a future refinement.

16. Commercial Event Packages
Concept

Instead of assuming permanent subscription use, test short-duration preparation products.

Examples:

interview preparation package
presentation preparation package
sales pitch preparation package
networking preparation package

Potential model:

Pay for a focused preparation period around one upcoming event.

Why Preserve It

The V1 user has a time-bound need.

Episodic willingness to pay may be stronger than long-term subscription retention.

Status

COMMERCIAL HYPOTHESIS — STRONG

Requires market validation.

17. Subscription Model

Current hypothesis remains approximately:

$8–15/month
or equivalent limited-duration package

Possible experiments:

first useful result free
paywall after retry
analysis bundle
monthly subscription
annual subscription
event package
Status

COMMERCIAL HYPOTHESIS

No pricing or packaging model is approved here.

18. Personalized Practice Recommendations
Concept

Eventually recommend the next exercise based on:

recent weaknesses
neglected skills
upcoming event
historical response to coaching
difficulty progression
Status

POST-V1 — STRONG IDEA

Depends on sufficient history and validated personalization signals.

19. Social Features

Possible ideas:

friend challenges
practice accountability
comparative challenges
leagues
percentile rankings
Risk

These may:

distract from private deliberate practice
require normative scoring
create privacy concerns
add substantial product complexity
Status

EXPERIMENT / LOW PRIORITY

No social architecture should be introduced without strong evidence.

20. Long-Term Principle

The strongest future direction is not:

more features.

It is:

progressively better understanding of what this individual needs to improve, followed by the smallest useful practice intervention that changes their real communication behavior.

Future ideas should be evaluated against:

Does this improve real communication ability?
Does it create useful practice?
Can the improvement be measured credibly?
Does it reuse the Core Practice Engine?
Does user evidence justify the complexity?
Does it strengthen the product rather than simply increase engagement?