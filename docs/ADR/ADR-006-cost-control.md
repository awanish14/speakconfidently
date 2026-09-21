# ADR-006: Cost Is an Architectural Requirement

## Decision

Every expensive AI operation must be measurable, routable and replaceable.

## Reason

The consumer product must remain economically viable at realistic speaking volumes.

## Consequence

Use deterministic processing and local/open models wherever practical, cheap models for ordinary reasoning, and stronger models only when justified.
