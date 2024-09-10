---
doc-status: Draft
sequence: 2
type:
 - Confidentiality
title: Insufficient access control with vector store
external-refs:
  - owasp-llm-top-10:
      - "LLM06: Sensitive Information Disclosure"
---

In this system architecture, where a [Retrieval-Augmented Generation (RAG)](https://cloud.google.com/use-cases/retrieval-augmented-generation) model relies on a vector store to retrieve relevant organizational knowledge, the immaturity of current vector store technologies poses a significant confidentiality risk. Vector stores, which hold embeddings of sensitive internal data, may lack enterprise-grade security controls such as robust access control mechanisms, encryption at rest, and audit logging. Misconfigurations or incomplete implementations can lead to unauthorized access to sensitive embeddings, enabling data tampering, theft, or unintentional disclosure. 

It is important to understand that, unlike traditional databases that store human-readable text, vector databases store embeddings, which are not directly interpretable by humans. With that being said, there are still integrity and confidentiality risks, particularly if unauthorized access or tampering occurs.

While it is unlikely that an adversary could easily reverse-engineer embeddings to retrieve precise, human-readable information (e.g., in plain-text), there is a potential for creative attack vectors that could exploit embeddings in novel ways, especially as these technologies evolve.

One of the primary threats involves data poisoning, where an attacker with access to the vector store could inject malicious or misleading embeddings into the system (see: [PoisonedRAG](https://arxiv.org/html/2402.07867v1) for an example). These compromised embeddings could degrade the quality or accuracy of the LLMs responses, leading to integrity issues that are difficult to detect. Since embeddings are dense numerical representations, spotting malicious alterations is not as straightforward as it would be with traditional data.

Given the nascent nature of vector store products, they may not adhere to enterprise security standards, leaving gaps that could be exploited by malicious actors or internal users. For example:

- **Misconfigured Access Controls**: Lack of role-based access control (RBAC) or overly permissive settings may allow unauthorized internal or external users to retrieve sensitive embeddings, bypassing any intended security measures.
- **Encryption Failures**: Without encryption at rest, embeddings that contain sensitive or proprietary information may be exposed to anyone with access to the storage layer. This can lead to data breaches or data tampering, threatening both confidentiality and integrity.
- **Audit Deficiencies**: The absence of robust audit logging makes it difficult to detect unauthorized access, modifications, or data exfiltration, allowing breaches to go unnoticed for extended periods.

This risk is aligned with OWASP’s [LLM06: Sensitive Information Disclosure](https://genai.owasp.org/llmrisk/llm06-sensitive-information-disclosure/), which highlights the dangers of exposing proprietary or personally identifiable information (PII) through large-scale, externally hosted AI systems.
