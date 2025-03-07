---
doc-status: Draft
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

The SaaS-based LLM provider is a 3rd party supplier and as such is subject to all typical supply chain, insider, and software integrity
threats. Supply chain attacks on infrastructure and OSS are covered in other frameworks, however supply chains for
foundational models, training data, model updates, and model retraining are all potential targets for attackers. 
The underlying firmware of GPUs, the operating system, and the machine learning libraries should be considered as part
of the supply chain too.

Whilst fine tuning is out of scope of this framework; it is worth noting that adversarial attacks can be built upon 
model weights for open source models. There could be a possibility of malicious actors using this information to induce unsafe
behaviour in the model.

Similarly, back doors engineered into the model can be triggered through malicious means. This could result in unsafe behaviour
or such tampering could result in removing safe guards around the model.

#### Severity

Given that the LLM is a hosted SaaS the expectation is that the API vendor would have gone through extensive 3rd party checks
before being on-boarded into the financial institution. Therefore, they would have demonstrated adequate quality control measures
in their supply chain. So this is a low-risk threat.
