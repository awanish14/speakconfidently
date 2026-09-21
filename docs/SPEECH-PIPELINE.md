# SpeakConfidently — Speech Pipeline

## 1. Principle

Pronunciation must be evaluated using actual speech signals and dedicated speech analysis wherever possible. An LLM should not be treated as the authoritative pronunciation scorer.

## 2. Pipeline

```
Audio
 ↓
VAD / segmentation
 ↓
STT + timestamps
 ↓
forced alignment
 ↓
phoneme representation
 ↓
pronunciation analysis
 ↓
word/sound-level evidence
 ↓
fluency analysis
 ↓
learner model
```

## 3. Pronunciation dimensions

Track separately:

### Accuracy
How closely the produced sounds match the target.

### Intelligibility
Whether speech is understandable.

### Naturalness
Stress, rhythm, connected speech and pronunciation patterns.

Do not frame the product as eliminating a learner's native accent.

## 4. Useful signals

- phoneme substitutions
- omitted sounds
- added sounds
- word endings
- syllable stress
- sentence stress
- speaking rate
- pause duration
- filler frequency
- hesitation
- repeated self-correction
- rhythm/intonation signals where technically reliable

## 5. Recurring pronunciation example

```
Conversation 1:
"think" → /tɪŋk/-like production

Conversation 2:
"three" → repeated /t/ substitution

Conversation 3:
"through" → repeated substitution

Pattern:
TH sound production
Confidence: high
       ↓
Targeted practice
       ↓
New contextual conversation
       ↓
Retest
```

## 6. Technical reference projects

See `REFERENCE-SOURCES.md` for Cadence and Echoic.

The implementation must remain our own abstraction so speech providers/models can be changed.

## 7. Evaluation requirement

Pronunciation analysis must be evaluated against a labelled internal test set before being used for strong learner claims.

False positives are especially harmful: the product must not repeatedly tell a learner they pronounced something incorrectly when the evidence is uncertain.
