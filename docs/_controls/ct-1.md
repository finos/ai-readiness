---
doc-status: Draft
sequence: 1
type:
  - Detective
mitigates:
  - tr-1
title: Data Leakage Canaries & Fingerprinting
---

To address the potential for data leakage when proprietary information is processed by an external LLM (e.g., chat.com), a detective control using [data leakage canaries](https://www.ischool.berkeley.edu/projects/2023/llm-canary-open-source-security-benchmark-tool) and/or [data fingerprinting](https://arxiv.org/abs/2401.12255) can be implemented. This technique aims to monitor and detect unauthorized disclosure of sensitive information by embedding uniquely identifiable markers (canaries) into the data streams or queries sent to the hosted model.

Key components of this control include:

- **Canary Data Injection**: Canary data consists of artificial or uniquely identifiable tokens embedded within the proprietary data sent to the hosted model. These tokens do not have legitimate business value but are crafted to detect leaks when exposed. For instance, queries containing unique strings can be planted during interactions with the LLM, and if these tokens appear in unauthorized contexts (e.g., responses from the model, external logs, or internet forums), it would indicate a potential breach.
- **Data Fingerprinting**: Proprietary data can be fingerprinted using cryptographic hashing techniques to create unique signatures. By monitoring the hosted service (e.g., chat.com) or conducting external reconnaissance, organizations can detect if these fingerprints appear in unauthorized locations, signaling a data breach or leakage.
- **Plugin Architecture Integration**: Implementing canary and fingerprint detection mechanisms into the plugin architecture of the chat.com extension ensures that data leakage detection is embedded into the system at multiple touchpoints, providing continuous monitoring across interactions.
- **Detection and Response Workflow**: Once a canary token is detected in an unauthorized environment, the system triggers an immediate alert, initiating the incident response process. This includes identifying the source of the breach, determining the extent of the leakage, and implementing remedial actions, such as ceasing further interaction with the compromised model.

This control is particularly effective in detecting unauthorized use or exposure of internal proprietary information processed by external systems. By embedding canaries and fingerprints, organizations can maintain a degree of oversight and control, even when data is processed beyond their direct infrastructure. 
