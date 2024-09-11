---
doc-status: Pre-Draft
sequence: 6
type:
  - Integrity
title: Non-deterministic behaviour
external-refs:
  - owasp-llm-top-10:
      - "LLM09: Overreliance"
      - "LLM08: Excessive Agency"
---
**Outline**


A fundamental property of LLMs is the non-determinism of their response. This is because LLMs generate responses by predicting the probability of the next word or token in a given context, meaning different prompts equating to the same request can produce different responses from the models. [This method also means that LLMs can tend towards winding or unintelligible outputs when the outputs being produced are larger.](https://arxiv.org/pdf/2203.11370) LLMs also make use of sampling methods like top-k sampling during text generation or have an internal state or seed mechanisms which can cause distinct responses from the same prompt used in different requests.This can make it difficult or impossible to reproduce results, and may result in different (and potentially incorrect) results being returned occasionally and in a hard to predict manner. 

One danger of this is as users get differing responses when they use the system at different times or get different answers than a colleague asking the same question leading to the confusion in the user and the overall trust in the system may degrade until users no longer want to use the tool at all.

This behaviour can also increase the difficulty of evaluating your system as you may be unable to reproduce what you thought was a bug, or consistently produce evaluation metrics to see if you are improving or degrading the system as you make changes.

**Severity**

This is not a hugely severe risk in the context of this RAG chatbot as it is presenting information that the user can access elsewhere, and may already have a passing familiarity with which should help with their understanding of the system's outputs. 

However even though the non-determinism risk of LLMs is reduced in RAG systems, there is a risk of not providing the same response or information source to similar queries due to the internal data source having intersecting information about the wanted topic and the system may produce different results with different citations.

**Also Read**

[The Non-determinism of ChatGPT in Code Generation](https://arxiv.org/abs/2308.02828)