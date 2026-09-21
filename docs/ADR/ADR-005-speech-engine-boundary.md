# ADR-005: Separate Speech Intelligence from Language Intelligence

## Decision

Speech analysis and language analysis are separate components.

## Reason

Pronunciation requires audio, alignment and acoustic evidence. Grammar and naturalness primarily require language/text evidence.

## Consequence

Neither component needs to pretend the other can be solved by a general LLM.
