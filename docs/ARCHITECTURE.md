# SpeakConfidently — Architecture

## 1. System overview

```
Learner
  │
  ▼
Web / Mobile Voice UI
  │
  ▼
Conversation Gateway
  │
  ├── Speech-to-Text
  │      ├── transcript
  │      └── timestamps
  │
  ├── Conversation Engine
  │      └── model provider abstraction
  │
  └── Text-to-Speech
         │
         ▼
Session Analyzer
  │
  ├── Speech Analysis
  │    ├── phonemes
  │    ├── pronunciation
  │    ├── pauses
  │    ├── rate
  │    ├── stress
  │    └── fluency
  │
  └── Language Analysis
       ├── grammar
       ├── vocabulary
       ├── meaning
       ├── naturalness
       └── CEFR signals
              │
              ▼
        Evidence Store
              │
              ▼
        Pattern Engine
              │
              ▼
        Learner Model
              │
              ▼
        Learning Planner
              │
              ▼
        Next Conversation
```

## 2. Service boundaries

### Web
User interface, audio capture, reports, practice and progress.

### Conversation service
Session lifecycle, turn orchestration, scenario state, model routing and safety.

### Speech service
STT, alignment, phoneme analysis and acoustic metrics.

### Learner model
Skills, observations, patterns, interventions, attempts and mastery.

### Language engine
Grammar, vocabulary, semantic and naturalness analysis.

### Evaluation package
Offline test datasets, scoring and regression evaluation.

## 3. Provider abstraction

The application must never directly depend on one AI provider.

Interfaces should include:

- `SpeechToTextProvider`
- `TextToSpeechProvider`
- `ConversationModelProvider`
- `ReasoningModelProvider`
- `PronunciationProvider`

Provider selection is configuration, not product logic.

## 4. Model routing

Use a cost-aware escalation strategy:

1. deterministic/rule-based analysis where reliable
2. local/open model where practical
3. low-cost cloud model for ordinary reasoning
4. stronger model only for ambiguous/high-value cases

## 5. Recommended initial technology direction

This is a proposal, not yet an implementation lock:

- Web: Next.js + TypeScript
- API/services: Python/FastAPI or TypeScript service layer
- Database: PostgreSQL
- Cache/queues: Redis
- Object storage: S3-compatible storage
- Realtime: WebSocket/WebRTC as appropriate
- Speech: provider abstraction + local Whisper/faster-whisper evaluation
- LLM: provider abstraction
- TTS: provider abstraction
- Observability: structured logs + cost telemetry

Final stack is an ADR decision after prototype benchmarks.

## 6. Data flow

Raw audio should not automatically become permanent storage. Retention must be configurable. Derived evidence should be stored separately from raw audio.

## 7. Failure strategy

The system must degrade gracefully:
- STT unavailable → retry/fallback provider
- LLM unavailable → fallback provider or scripted scenario
- pronunciation analysis unavailable → conversation can continue and report the missing analysis
- TTS unavailable → browser/device fallback where possible

## 8. Security

- encrypt sensitive data in transit and at rest
- explicit consent for voice recording/storage
- configurable retention/deletion
- minimise raw audio retention
- provider data-use policies must be reviewed before production
- separate personally identifiable account data from learning evidence where practical
