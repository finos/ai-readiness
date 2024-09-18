---
doc-status: Draft
sequence: 3
type:
  - Confidentiality
title: Lack of source data access controls
external-refs:
  - owasp-llm-top-10:
      - "LLM06: Sensitive Information Disclosure"

---

Chat App allows access to corporate data sources (e.g. Confluence, employee databases), however given these sources may have different access control policies, there is the threat that when accessed via chat app a user can access data they are not authorized to see at the source, due to the architecture not honoring source access controls.

The threat posed here is the loss of data access controls in building a traditional RAG application. The access control restrictions in place in Confluence, for example, will
not be replicated in the Vector database or at the model level.

Examples of important things to consider:

- loss of access control data when data is ingested
- limitations of system prompt designed to obey corporate access controls
