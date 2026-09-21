# SpeakConfidently — Product Requirements Document

**Status:** Freeze candidate  
**Version:** 0.1  
**Date:** 2026-09-21

## 1. Product thesis

Most AI language products can already let a learner talk to an AI, correct mistakes, practise pronunciation and generate personalised lessons. SpeakConfidently should therefore not compete on “AI conversation” alone.

The product differentiator is a **persistent model of how the learner actually speaks**.

> **Your conversations become your curriculum.**

A single mistake is an observation. A repeated mistake is a pattern. A pattern points to an underlying skill gap. The product intervenes and then verifies whether the learner can use the skill later in a natural conversation.

## 2. Target learner

V1 focuses on adults learning **English speaking** who can understand some English but want to speak more confidently, clearly and naturally.

Primary goals:
- everyday conversation
- workplace communication
- interviews
- travel
- social confidence
- clearer pronunciation

V1 is not designed for children, academic language certification, or complete beginner literacy instruction.

## 3. Product promise

After regular use, the learner should be able to answer:

**“What have I actually improved?”**

The product should show evidence from real conversations rather than only streaks, XP or lesson completion.

## 4. Core product loop

1. Learner speaks.
2. Speech is transcribed and analysed.
3. Language and speech observations are created.
4. Observations are linked to skills.
5. Repeated observations become patterns after confidence/evidence thresholds.
6. The intervention engine selects a small number of high-value targets.
7. The learner receives a focused explanation and practice.
8. A later conversation naturally tests the same skill.
9. Results update the learner model.
10. Progress is shown longitudinally.

## 5. V1 scope

### Included

- onboarding
- learner goal and approximate level
- 3–5 minute diagnostic conversation
- 5–10 minute voice conversations
- free conversation
- real-life scenarios
- workplace scenarios
- transcript
- grammar observations
- vocabulary observations
- pronunciation observations
- fluency metrics
- naturalness suggestions
- recurring-pattern detection
- personalised practice
- pronunciation drills
- contextual grammar practice
- useful daily speaking patterns
- re-test conversation
- learner progress history
- evidence-backed improvement report
- configurable AI/model providers
- usage/cost telemetry

### Explicitly out of scope for V1

- 100+ languages
- full Duolingo-style curriculum
- social network/community
- human tutor marketplace
- live multiplayer
- certification
- children/parent product
- complex gamification
- fundraising or unrelated verticals
- custom foundation-model training

## 6. Conversation modes

### Free Talk
Natural conversation with minimal interruption.

### Scenario
Examples: restaurant, hotel, doctor, airport, shopping, neighbour, work meeting, client call, interview, networking.

### Challenge Me
The engine deliberately creates opportunities to test a known weak skill.

### Practice
Short targeted interaction around one learning objective.

The conversation should not feel like an exam. The engine should quietly collect evidence.

## 7. Feedback principles

- Prioritise, do not dump corrections.
- Distinguish understandable from natural.
- Explain the reason, not only the correction.
- Avoid accent-shaming.
- Pronunciation goals are clarity, intelligibility and naturalness.
- Use evidence from multiple conversations before declaring a recurring pattern.
- Show uncertainty where the analysis is uncertain.
- Prefer examples taken from the learner's own speech.

## 8. Post-session report

A default report should contain:
- 1 strength
- up to 3 recurring/high-value language patterns
- up to 3 pronunciation targets
- 1 fluency observation
- 3 useful expressions
- recommended practice
- what will be tested next

## 9. Success metrics

### Product
- first conversation completion
- second conversation completion
- practice completion
- week-4 retention
- conversations/user/month

### Learning
- recurring-pattern resolution rate
- successful re-use of corrected structures
- pronunciation target improvement
- reduction in repeated errors
- learner-reported confidence change

### Economics
- AI cost/minute
- total variable cost/user/month
- LLM calls/conversation
- average input/output tokens
- speech-processing cost/minute
- TTS cost/minute
- storage cost/user
- gross margin by usage tier

## 10. Non-negotiable architectural principles

1. New repository; no blind fork.
2. Provider-independent AI interfaces.
3. LLM is not the learner model.
4. LLM is not the pronunciation source of truth.
5. Structured evidence is persisted.
6. Every recurring pattern has provenance.
7. Expensive models are routed only when justified.
8. Speech, language and learning intelligence remain separate services/modules.
9. Every major AI operation has measurable cost.
10. The product must remain usable if the premium LLM provider changes.
