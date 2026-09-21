# ADR-003: Learner Model Is the System of Record

## Decision

Persistent learner state is stored as structured application data.

## Reason

An LLM conversation history is not a reliable learner model.

We need evidence, provenance, confidence, recurrence, skill mapping, intervention history and retest results.

## Consequence

The learner model can survive model/provider changes and supports explainable progress.
