---
doc-status: Pre-Draft
sequence: 6
type:
  - Integrity
title: Non-deterministic behaviour
external-refs:
  - owasp-llm-top-10:
      - "LLM09: Overreliance"
      - "LLM08: Excessive Agency"
---

A fundamental property of LLMs is their non-determinism of response. This can make it difficult or impossible to reproduce inference results, and may result in different (and potentially incorrect) results being returned occasionally and in a hard to predict manner.


Qs:
-  what about stochastic elements of training preventing model reproducibility?