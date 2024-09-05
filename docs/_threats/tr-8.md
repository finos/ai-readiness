---
doc-status: Pre-Draft
sequence: 8
type:
  - Integrity
  - Confidentiality
  - Availability
title: Tampering with the foundational model
external-refs:
  - owasp-llm-top-10:
      - "LLM05: Supply Chain Vulnerabilities"
      - "LLM03: Training Data Poisoning"
---

chat.com is a 3rd party supplier and as such is subject to all typical supply chain, insider, and software integrity
threats. Supply chain attacks on infrastructure and OSS are covered in other frameworks, however supply chains for
foundational models, training data, model updates, and model retraining are all potential targets for attackers.

The underlying firmware of GPUs, the operating system, and the machine learning libraries should be considered as part
of the supply chain too.

