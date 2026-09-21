# SpeakConfidently — Privacy and Data

## 1. Data categories

Potentially sensitive:
- account information
- voice recordings
- transcripts
- learning history
- pronunciation analysis
- behavioural learning patterns

## 2. Principles

- collect only what is needed
- obtain explicit consent for recording/storage
- make retention understandable
- allow deletion
- minimise permanent raw-audio storage
- encrypt data in transit and at rest
- avoid sending unnecessary personal information to model providers
- document provider data-use policies

## 3. Audio retention

Default architecture should permit:
- ephemeral processing
- configurable retention
- permanent deletion
- derived evidence retained independently from raw audio

## 4. Provider boundaries

Each AI provider must be documented with:
- data sent
- reason
- retention policy
- whether data is used for provider training
- regional processing where relevant
- fallback provider

Production launch requires provider-policy review.
