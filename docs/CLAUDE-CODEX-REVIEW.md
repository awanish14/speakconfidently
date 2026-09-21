# SpeakConfidently — Pre-Development Review Prompt

Use this document as the review brief for Claude/Codex after the repository specification is complete.

## Mission

Review the SpeakConfidently repository as a senior product architect, speech-AI engineer, language-learning researcher, security reviewer and pragmatic startup CTO.

Do not write production code.

## Review objectives

1. Challenge the product thesis.
2. Identify hidden scope.
3. Challenge the V1 boundaries.
4. Audit the architecture.
5. Audit the learner model.
6. Audit the speech/pronunciation design.
7. Audit the evidence and pattern model.
8. Identify places where an LLM is unnecessary.
9. Identify places where deterministic analysis is unsafe or insufficient.
10. Review provider abstraction.
11. Review cost architecture.
12. Review privacy/data handling.
13. Review open-source reference/reuse decisions.
14. Identify licensing risks.
15. Identify evaluation gaps.
16. Identify technical risks that could make the MVP fail.
17. Identify anything that should be removed rather than built.

## Required output

Return:

### A. Critical blockers
Only issues that must be fixed before development.

### B. Architecture changes
Concrete changes with rationale.

### C. Product scope changes
Features to remove, defer or add.

### D. Learner-model critique
Check whether Observation → Pattern → Skill → Intervention → Attempt → Retest is sufficient and where it can fail.

### E. Speech/pronunciation critique
Check feasibility, false positives, accent handling, alignment and evaluation.

### F. Cost critique
Estimate which components are likely to dominate cost and propose cheaper alternatives.

### G. Security/privacy critique
Focus on voice, transcripts and third-party model providers.

### H. Open-source/license audit
For every referenced repository:
- license
- likely commercial compatibility
- code reuse risk
- recommendation: reference / reusable / avoid

Do not assume a repository's license. Verify it.

### I. Build order
Recommend the smallest vertical slice that can prove the product thesis.

### J. Final decision
Classify each major architecture/product decision as:
- KEEP
- MODIFY
- REMOVE
- DEFER

Do not start implementation until the review is complete and accepted.
