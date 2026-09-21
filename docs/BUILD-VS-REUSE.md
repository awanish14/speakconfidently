# SpeakConfidently — Build vs Reuse Matrix

## Product/application layer

| Component | Decision |
|---|---|
| UI | Build from zero |
| Conversation UX | Build from zero |
| Scenario system | Build from zero |
| Learner dashboard | Build from zero |
| Progress reporting | Build from zero |
| Pattern engine | Build from zero |
| Learner model | Build from zero |
| Learning planner | Build from zero |
| Intervention engine | Build from zero |
| Product analytics | Build from zero |

## Infrastructure/commodity layer

| Component | Decision |
|---|---|
| Database | Use mature open-source/managed technology |
| Authentication | Use mature library/provider |
| Payments | Use payment provider |
| Object storage | Use mature provider |
| Queue/cache | Use Redis or equivalent |
| STT | Evaluate provider and local/open model |
| TTS | Evaluate provider and local/device option |
| LLM | Provider abstraction |
| Phoneme model | Evaluate existing open model/library |
| Forced alignment | Evaluate existing open model/library |

## Product intelligence that must remain ours

- observation schema
- evidence confidence
- pattern promotion
- skill graph
- intervention selection
- retest logic
- mastery calculation
- adaptive conversation objectives
- learning progress evidence
- cost-aware model routing

## No blind forking rule

Do not fork Cadence, Echoic, FreeLingo or any other reference project as the product base.

Create a clean implementation in `awanish14/speakconfidently`.
