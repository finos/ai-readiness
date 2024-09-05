---
doc-status: Pre-Draft
sequence: 3
type:
  - Confidentiality
title: Lack of source data access controls
external-refs:
  - owasp-llm-top-10:
      - "LLM06: Sensitive Information Disclosure"

---

Chat App allows access to corporate data sources (e.g. Confluence, employee databases), however given these sources may have different access control policies, there is the threat that when accessed via chat app a user can access data they are not authorized to see at the source due to the model enforcing auth/z.
