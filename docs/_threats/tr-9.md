---
doc-status: Draft
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

A malicious actor may tamper with the vectors stored in the client's vector store. 
This data is made available to Chat App users, resulting in unauthorized data access or proliferation of falsities.
There is a possibility of tampering with the client vector store. This could be happen during 
ingesting Confluence by leveraging a known back door in the ingest pipeline by a malicious actor. An adversary could use this
back door to poison the vector store, or use it in other innovative ways to introduce poison data into the vector store.

#### Severity

Low-risk as requires access to clients vector store. This is assumed to be adequately protected as any SaaS would be required to demonstrate as a 3rd party vendor to a financial institution.
