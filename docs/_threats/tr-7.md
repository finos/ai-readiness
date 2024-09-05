---
doc-status: Pre-Draft
sequence: 7
type:
  - Availability
title: Availability of foundational model
external-refs:
  - owasp-llm-top-10:
      - "LLM04: Model Denial of Service"
---

Hosted LLMs typical have usage limits, but often lack the sophisticated controls needed to manage this.

Given the commercial model of LLM services is typically on a per usage basis, there is the risk that significant resources can be expended via Chat App if uncontrolled access is allowed. e.g. DOS, injecting very large contexts, brute forcing to elicit very long responses, etc.
