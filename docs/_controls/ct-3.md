---
doc-status: Pre-Draft
sequence: 3
type:
  - Preventative
mitigates:
  - tr-7
  - tr-10
title: User/app/model firewalling/filtering
---

- Detect and prevent prompt injection (user->chat app)
  - Customisable LLMs to detect prompts with suspicious information,
  - LLM as a judge
  - Apply character / input length limits
  - Black list certain words
- API Observability (chat app->LLM, ->Vector, ->Data)
  - “Abundance of paranoia!”
- Toxicity/PII/IP filtering (chat app->user)
  - Library of known-wrong answers into output filtering?
- TLS termination and privacy concerns
