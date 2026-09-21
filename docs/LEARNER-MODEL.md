# SpeakConfidently — Learner Model

## 1. Principle

The learner model is the product's long-term memory.

The LLM may reason about a learner, but the learner model owns persistent state.

## 2. Hierarchy

```
Observation
    ↓
Evidence
    ↓
Pattern
    ↓
Skill
    ↓
Intervention
    ↓
Attempt
    ↓
Retest
    ↓
Mastery update
```

## 3. Core entities

### Learner
Identity, language profile, goals, preferences.

### Skill
Examples:
- present perfect
- articles
- prepositions
- TH pronunciation
- word stress
- hesitation
- sentence formulation
- conversational turn-taking

### Observation
One piece of evidence from a conversation or practice attempt.

Fields:
- type
- source
- evidence
- confidence
- timestamp
- conversation_id
- skill_id

### Pattern
A recurring behaviour supported by multiple observations.

Fields:
- observation_ids
- frequency
- severity
- confidence
- first_seen
- last_seen
- status
- skill_id

Suggested statuses:
- observed
- emerging
- confirmed
- improving
- mastered
- dormant

### Intervention
A teaching action:
- explanation
- example
- exercise
- target skill
- difficulty

### Attempt
The learner's response to an intervention.

### Conversation
Transcript, turns, audio references, analysis and evidence.

## 4. Pattern promotion

An observation should not immediately become a persistent problem.

A pattern should require configurable evidence such as:
- repeated occurrence
- sufficient confidence
- occurrence across different contexts
- no strong contradictory evidence

Example:

```
"I am working here since five years."
       ↓
Observation #1

"I am living here since 2020."
       ↓
Observation #2

"She is working there since 2019."
       ↓
Observation #3

Pattern:
Using present progressive + since for continuing states
       ↓
Intervention
       ↓
Later conversation
       ↓
Correct spontaneous usage
       ↓
Pattern status = improving
```

## 5. Mastery

Mastery should not be a single LLM-generated score.

Use evidence from:
- practice accuracy
- spontaneous conversation
- recurrence frequency
- context diversity
- time since last error
- pronunciation consistency
- successful re-use

The system should be able to explain why a skill is considered improving.

## 6. Progress language

Prefer:
- improving
- recurring
- recently resolved
- needs practice
- consistently strong

Avoid presenting false precision such as “you are 87.4% fluent.”
