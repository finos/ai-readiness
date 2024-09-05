---
doc-status: Pre-Draft
sequence: 2
type:
 - Confidentiality
title: Insufficient access control with vector store
external-refs:
  - owasp-llm-top-10:
      - "LLM06: Sensitive Information Disclosure"
---

Given the immaturity of the products, the vector store may not have capabilities expected of enterprise software (access control, encryption at rest, audit logging etc). Misconfiguration may allow unauthorized access to data. Internal user accesses data and leaks/tampers it.

Q:
- original writing of this threat: just related to maturity of new tooling. Is that a sufficient threat?
- is local vector store poisoning/tampering and/or theft an integrity and confidentiality issue? Is this covered by other frameworks?
- What are the low-level mechanics of poisoning or data extraction from a vector store?
