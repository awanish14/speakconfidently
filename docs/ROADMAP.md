# SpeakConfidently — Development Roadmap

## Phase 0 — Freeze

- complete PRD
- architecture
- learner model
- speech pipeline
- cost model
- reference/reuse matrix
- privacy requirements
- evaluation strategy
- ADRs

**Exit:** Claude/Codex architecture review completed and decisions frozen.

## Phase 1 — Thin vertical slice

Build only:

Onboarding → voice conversation → STT → AI response → TTS → transcript → basic post-session report.

No complex learner intelligence yet.

**Exit:** user can complete a useful conversation end-to-end.

## Phase 2 — Evidence engine

Add:
- observations
- grammar signals
- vocabulary signals
- fluency metrics
- basic pronunciation evidence
- evidence persistence

**Exit:** every session produces structured learning evidence.

## Phase 3 — Learner model

Add:
- skills
- patterns
- confidence
- recurring issue detection
- intervention history
- mastery states

**Exit:** system remembers how the learner speaks.

## Phase 4 — Targeted learning

Add:
- personalised practice
- pronunciation drills
- contextual grammar practice
- daily speaking patterns
- challenge mode

**Exit:** conversations generate targeted learning.

## Phase 5 — Retest and proof

Add:
- skill retesting
- before/after comparisons
- recurring-pattern resolution
- longitudinal progress

**Exit:** product can answer “What have I actually improved?”

## Phase 6 — Cost and reliability hardening

- provider routing
- local model benchmarks
- caching
- usage limits
- cost dashboards
- fallback providers
- privacy controls
- observability

**Exit:** production economics are measurable.

## Development philosophy

Build vertical slices, not a waterfall.

Do not build a large framework before proving the user loop.
