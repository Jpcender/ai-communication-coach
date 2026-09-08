# PRODUCT_SPEC.md

**Status:** APPROVED BASELINE — contains explicitly PROPOSED hypotheses where noted
**Product:** AI Communication, Charisma, and Presence Coach
**Version:** V1

## 1. Product Vision

Build a mobile-first AI coach that helps people become more effective communicators through deliberate speaking practice, objective measurement, actionable coaching, repetition, and progress tracking.

The long-term product may support:

* public speaking
* presentations
* interviews
* networking
* storytelling
* persuasion and sales
* dating and social conversations
* difficult conversations
* general confidence
* charisma and presence

Version 1 will not attempt to solve all of these.

The brand, product architecture, and core terminology must remain broad enough to support these future communication scenarios.

## 2. V1 Product Thesis

The smallest commercially useful product is a **solo recorded speaking coach for short, high-stakes spoken responses**.

The core loop is:

**Choose a prompt → speak → receive analysis → fix one thing → speak again → compare**

V1 should prove three things:

1. Users with a real upcoming speaking need will repeatedly practice speaking into their phone.
2. AI-generated coaching is useful enough to change how they speak.
3. Some users will pay for repeated access to structured communication practice.

## 3. V1 Customer

Primary V1 customer:

> **Adults preparing for an upcoming high-stakes speaking situation who want structured solo practice before it happens.**

Examples of qualifying situations include:

* an interview
* a presentation
* a pitch
* a networking interaction
* a difficult question
* an important explanation
* a persuasive conversation
* a prepared story or introduction

The common problem is not the scenario itself.

The common problem is:

> “I need to communicate well soon, and I want a private way to practice, identify weaknesses, and improve before the real situation.”

The product should not be branded around interviews or any other single scenario.

## 4. V1 User Promise

> Practice what you want to say. See exactly what weakens your delivery. Fix the highest-impact problem. Try again.

## 5. Core V1 Experience

### Step 1 — Select Practice

User selects:

* a built-in prompt; or
* a custom prompt

FEATURE-001 uses exactly nine approved built-in starter prompts.

Do not expand the built-in prompt library during FEATURE-001 without separate approval.

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

These prompts focus on transferable communication behaviors rather than creating a large scenario catalog.

The underlying skills transfer across interviews, presentations, networking, leadership, sales, social situations, and other future scenarios.

### Custom Prompt Rules

For FEATURE-001:

* surrounding whitespace is trimmed for validation and accepted stored value
* maximum accepted length is 300 characters after trimming
* empty or whitespace-only input is invalid
* input exceeding 300 characters after trimming is invalid
* invalid custom-prompt edits must never replace the currently valid selected prompt

### Step 2 — Record

User records a response between approximately 30 and 180 seconds.

Show:

* prompt
* recording duration
* stop control

Do not show live coaching while recording.

Recording functionality begins in FEATURE-002.

FEATURE-001 may include one minimal placeholder recording destination solely to verify navigation and selected-prompt state.

That placeholder:

* displays the selected prompt
* supports safe back navigation
* contains no recording functionality
* contains no simulated or fake microphone controls

No other future placeholder destinations should be introduced under FEATURE-001.

### Step 3 — Analyze

Audio is transcribed.

The application calculates objective metrics where technically reliable.

Initial metrics:

* speaking duration
* words spoken
* words per minute
* filler-word count
* fillers per minute
* longest detected pauses
* number of long pauses
* repeated phrases where confidently detectable

The AI evaluates communication quality using an explicit rubric.

Initial rubric:

* clarity
* structure
* concision
* specificity

Scores should use anchored scales such as 1–5.

Do not claim to scientifically measure:

* charisma
* confidence
* attractiveness
* intelligence
* honesty
* personality
* emotional state

### Step 4 — Coach

Results prioritize information in this order:

1. highest-impact improvement
2. what worked
3. what to change
4. delivery metrics
5. transcript

The application should give the user one clear next action rather than overwhelming them with observations.

### Step 5 — Retry

Primary call-to-action:

**Try Again**

The same prompt is immediately available again.

After another attempt, show meaningful comparison where technically justified.

Examples:

* fillers: 8 → 4
* pace: 182 → 161 WPM
* clarity: 3 → 4
* structure: 2 → 4

The retry loop is a core V1 behavior.

## 6. Progress

After authenticated cloud history is introduced, V1 may track:

* sessions completed
* retries completed
* average pace
* filler frequency
* clarity score
* structure score
* concision score
* specificity score

Progress should emphasize trends.

Individual AI-generated scores should not be presented as scientifically precise measurements.

## 7. Monetization

**Status: PROPOSED — REQUIRES VALIDATION**

Initial pricing hypothesis:

> **Approximately $8–15/month, or an equivalent limited-duration practice package. Final pricing and packaging require validation.**

Possible packaging experiments may include:

* limited free analyses followed by paid access
* monthly subscription
* short-duration preparation package
* fixed analysis bundle

V1 should not begin with multiple paid tiers.

Monetization infrastructure should not be implemented until the core practice loop demonstrates sufficient user value.

## 8. V1 Screens

Target approximately:

1. onboarding
2. home / practice selection
3. recording
4. analysis/results
5. progress/history
6. settings/paywall when monetization is implemented

The presence of onboarding in the eventual V1 screen inventory does not authorize onboarding during FEATURE-001. FEATURE-001 remains governed by its own approved feature specification.

Do not add:

* social feeds
* communities
* extensive profile customization
* leaderboards
* unnecessary navigation

## 9. What Is NOT in V1

Explicitly excluded:

* computer vision
* facial-expression analysis
* eye-contact analysis
* body-language analysis
* posture analysis
* attractiveness scoring
* AI video avatars
* live conversational AI
* dating simulations
* multi-person conversations
* real-time coaching while speaking
* meeting monitoring
* Zoom/Teams integrations
* desktop application
* Android launch
* speech therapy
* clinical anxiety treatment
* accent grading
* pronunciation training
* emotion detection
* voice cloning
* community features
* coaching marketplace
* enterprise administration
* team accounts
* user-generated public content
* social sharing
* complex gamification
* complicated achievement systems
* custom AI personalities

## 10. Commercial Validation Criteria

Before materially expanding scope, obtain evidence that the core practice loop works.

Recommended initial validation gate:

* at least 20 external beta users
* at least 60% complete their first analysis after beginning the practice flow
* at least 30% perform an immediate retry
* at least 20% return for another practice session within 7 days
* at least 70% of surveyed users rate coaching usefulness/actionability at 4/5 or higher
* at least 5 users who are not friends or family demonstrate real willingness to pay under tested pricing or packaging

These are initial validation thresholds, not permanent company KPIs.

Failure to meet them should trigger investigation before feature expansion.

## 11. Initial Engineering Targets

**Initial engineering targets — subject to revision after beta measurement.**

Candidate targets:

* ≥98% successful practice submission under normal supported conditions
* ≥99% valid coaching-schema responses after permitted retry handling
* p95 end-to-end analysis time ≤25 seconds after audio upload completes

These targets are provisional.

They should not be treated as fixed product requirements until real beta performance and user expectations are measured.
