# SpeakConfidently — Evaluation Strategy

## 1. Why evaluation matters

The product makes claims about speech and language. False corrections can reduce learner trust.

## 2. Evaluation layers

### Speech recognition
Measure transcription quality on representative accents, speaking rates and noisy environments.

### Pronunciation
Use a labelled test set with:
- correct productions
- common substitutions
- varied accents
- different recording conditions

Track false-positive and false-negative rates.

### Grammar
Create a curated benchmark of learner utterances with expert labels.

### Pattern detection
Test whether repeated observations are correctly grouped and whether unrelated observations are kept separate.

### Intervention
Evaluate whether the recommended exercise actually targets the detected skill.

### Retest
Measure whether the system detects improvement in spontaneous use.

## 3. LLM evaluation

Every LLM prompt that affects learner state should have regression cases.

Do not allow an LLM response to directly mutate high-impact learner state without validation.

## 4. Human review

During MVP:
- sample sessions
- review pronunciation findings
- review grammar findings
- compare system diagnosis with human judgement
- record false corrections

## 5. Release gates

No production release of a major analysis component until:
- benchmark exists
- baseline exists
- regression tests exist
- known failure modes are documented
- confidence thresholds are documented
