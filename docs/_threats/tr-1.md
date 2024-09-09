---
doc-status: Pre-Draft
sequence: 1
type:
 - Confidentiality
title: Information Leaked to Hosted Model
external-refs:
  - owasp-llm-top-10:
    - "LLM06: Sensitive Information Disclosure"
---

In the provided system architecture, sensitive data is transmitted to a SaaS-based Generative AI platform (e.g., chat.com) for inference, posing a risk of information leakage. Sensitive organizational data, proprietary algorithms, and confidential information may be unintentionally exposed due to inadequate control measures within the hosted model. This can occur through several mechanisms unique to Large Language Models (LLMs), as outlined in OWASP's LLM06, such as [overfitting](https://aws.amazon.com/what-is/overfitting/), [memorization](https://arxiv.org/pdf/2310.18362), and [prompt-based attacks](https://owasp.org/www-project-llm-prompt-hacking/).

LLMs can retain data from training processes or user interactions, potentially recalling sensitive information during unrelated sessions, a phenomenon known as "memorization." When data such as Personally Identifiable Information (PII) or proprietary financial strategies enter the model, the risk of inadvertent disclosure rises, particularly when insufficient data sanitization or filtering mechanisms are in place. Additionally, adversarial actors could exploit prompt injection attacks to manipulate the model into revealing sensitive data.

Furthermore, data retention policies or model fine-tuning can exacerbate these risks. When fine-tuning is done on proprietary data without strict access control, sensitive information may inadvertently be disclosed to lower-privileged users, violating principles of least privilege. Without clear Terms of Use, data sanitization, and input validation, the organization loses visibility into how sensitive information is processed by the LLM and where it may be disclosed.

**Unique Considerations:** 

- **Two-Way Trust Boundary**: The client-to-LLM interaction introduces a two-way trust boundary where neither input nor output can be fully trusted. This makes it critical to assume the output could leak sensitive information unintentionally, even when the input appears benign.
- **Model Overfitting and Memorization**: LLMs may retain sensitive data introduced during training, leading to unintentional data leakage in future interactions. This includes potential cross-user leakage, where one user's sensitive data might be disclosed to another.
- **External Inference Endpoint Risks**: Hosted models like chat.com may not provide transparent mechanisms for how input data is processed, retained, or sanitized, increasing the risk of persistent exposure of proprietary data.

This risk is aligned with OWASP’s [LLM06: Sensitive Information Disclosure](https://genai.owasp.org/llmrisk/llm06-sensitive-information-disclosure/), which highlights the dangers of exposing proprietary or personally identifiable information (PII) through large-scale, externally hosted AI systems.