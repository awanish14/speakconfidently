# ADR-002: LLM Provider Abstraction

## Decision

All model calls go through internal interfaces rather than provider-specific calls scattered throughout the application.

## Reason

- cost optimisation
- provider switching
- local model experimentation
- fallback
- evaluation
- commercial flexibility

## Consequence

Model/provider configuration is infrastructure. Product logic consumes capabilities such as conversation, explanation and classification.
