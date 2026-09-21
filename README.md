# SpeakConfidently

SpeakConfidently is a speaking-first language learning product built around one core idea:

> **Your conversations become your curriculum.**

The product lets learners speak naturally with an AI conversation partner, analyses what they actually said—including pronunciation, grammar, vocabulary and fluency—detects recurring patterns over time, teaches targeted improvements, and then verifies improvement in later conversations.

## Current status

**Phase:** Product definition / architecture freeze  
**Implementation:** Not started  
**Repository:** `awanish14/speakconfidently`

## Core loop

Speak → Analyse → Identify patterns → Teach → Practice → Re-speak → Measure improvement → Update learner model.

## Architectural principle

LLMs are a reasoning component, not the system of record. Speech analysis, learner state, evidence, pattern detection and progress should be represented as structured product data so that expensive model calls are minimized and providers can be changed without rewriting the product.

## Build principle

This is a new repository and a clean implementation. Existing open-source projects are research/reference sources. Code is reused only after explicit license and dependency review.
