---
doc-status: Pre-Draft
sequence: 9
type:
  - Integrity
  - Confidentiality
title: Tampering with the vector store
external-refs:
  - owasp-llm-top-10:
      - "LLM03: Training Data Poisoning"
      - "LLM05: Supply Chain Vulnerabilities"
      - "LLM06: Sensitive Information Disclosure"
---

A malicious actor may tamper with the vectors stored in the client's vector store. This data is made available to Chat App users, resulting in unauthorized data access or proliferation of falsities.

Poisoning Confluence or source data are covered in , insider threat, externally ingested data. Indirect prompt injection and friends.
