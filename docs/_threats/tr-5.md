---
doc-status: Pre-Draft
sequence: 5
type:
  - Integrity
title: Instability in foundation model behaviour
external-refs:
  - owasp-llm-top-10:
      - "LLM09: Overreliance"

---

The foundation model behaviour may change over time if the third-party doesn't have rigorous version control (covered in Threat 11), or silently changes model versions without notifying the consumer.

This can lead to instability in the model's behaviour, which may impact on the client's business operations and actions taken upon model output.

