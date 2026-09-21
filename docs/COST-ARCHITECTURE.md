# SpeakConfidently — Cost Architecture

## 1. Objective

Keep consumer pricing viable by avoiding unnecessary LLM and speech API calls.

Target economics are hypotheses, not commitments. Actual cost must be measured during prototype testing.

## 2. Cost principle

**Do not use an LLM when deterministic processing can reliably do the job.**

## 3. Processing tiers

### Tier 0 — deterministic
- word counts
- speaking rate
- pauses
- repetition
- vocabulary lookup
- pattern frequency
- basic grammar rules where reliable

### Tier 1 — local/open models
- STT where hardware economics permit
- phoneme/alignment models
- selected NLP tasks

### Tier 2 — inexpensive cloud models
- ordinary conversation
- explanations
- classification
- lesson generation

### Tier 3 — stronger model
Only for:
- ambiguous diagnosis
- difficult semantic analysis
- quality-control sampling
- exceptional conversation needs

## 4. Cost telemetry

Every AI operation should emit:
- provider
- model
- operation
- duration
- input units/tokens
- output units/tokens
- estimated cost
- user/session id
- success/fallback status

## 5. Product metrics

Track:

```
AI cost / conversation
AI cost / speaking minute
AI cost / active user / month
AI cost by provider
AI cost by feature
AI cost by subscription tier
```

## 6. Cost controls

- summarise conversation history
- send structured learner state instead of full history
- cap unnecessary context
- cache stable content
- use concise TTS responses
- batch post-session analysis
- route by confidence
- avoid repeated analysis of identical material
- allow provider fallback

## 7. Pricing principle

Do not promise unlimited usage until actual heavy-user cost is understood.

The product should measure cost before commercial limits are finalised.
