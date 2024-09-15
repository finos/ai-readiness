---
doc-status: Draft
sequence: 7
type:
  - Availability
title: Availability of foundational model
external-refs:
  - owasp-llm-top-10:
    - "LLM04: Model Denial of Service"
  - FFIEC IT Handbook: Business Continuity Management 
  - FFIEC Appendix J:
    - "Strengthening the Resilience of Outsourced Technology Services"
---

RAG systems are proliferating due to the low barrier of entry compared to traditional chatbot technologies. RAG has applicability for internal users as well as supporting customer-related use cases.

Many LLMs require GPU compute infrastructure to provide an acceptable level of responsiveness. Furthermore, some of the best-performing LLMs are proprietary. Therefore, the path of least resistance is to call out to a Technology Service Provider (TSP).

However, applications that index sensitive information may use on-prem GPUs because:

1. The risks associated with data leakage are too high.
2. The administrative barriers for getting approval to use a cloud provider are too high.

Using on-prem GPU puts the onus on the system owner to ensure that VRAM exhaustion does not occur. Current GPUs use soldered VRAM to achieve maximum memory bandwidth and are not expandable. Most LLM libraries will fail when a memory allocation fails.

# Key Risks

-	**Denial of Wallet (DoW)**: Over-usage that results in slowdowns, unexpected costs, or outages. Examples include:
    - Unexpectedly long prompts due to large chunk sizes or many chunks packed into the prompt.
        - This could be exacerbated by systems that work with multimedia content.
        - LLM attacks to exfiltrate training data may also generate the maximum number of tokens.
    - Scripts which repeatedly hit API endpoints without built-in throttling.
        - This may result from Strats searching for new sources of "signal".
    - Agentic systems which may generate additional LLM / search calls that were not taken into account in the initial design / capacity planning. 
-	**TSP Outages**:
    - Some LLM providers might not have sufficient technical maturity to provide uptime to meet target SLA.
    - Inability to fail over to an equivalent LLM back end due to proprietary model / lack of capacity at other TSPs. (FFIEC Appendix J).
- **On-Prem Capacity**:
    - Long lead time to add GPUs to data centers may result in prolonged performance degredation.
    - BCP site may not have equivalent GPU capacity.
    - Load testing new LLM serving libraries and settings.
- **VRAM Exhaustion**:
    - VRAM utilization can increase for a variety of reasons:
        - new release of LLM library has a memory leak
        - new caching techniques to improve throughput at the cost of VRAM
        - setting a longer context length
        - etc.

# Recommendations:

- LLM utilization modeling and monitoring:
    - Predict expected load with enough lead time to build capacity.
    - Detect when an SLA cannot be satisfied.
- Gateways in front of LLM endpoints that can:
    - ensure that the most critical systems get priority access to LLMs
    - revoke access to "noisy neighbors" who are impacting performance of critical systems
- Ensure that VRAM is sufficient for new LLM libraries and / or configuration changes.

# Further reading:
- CT-4 System observability
- CT-8 QoS/Firewall/DDoS prev
- CT-9 Alerting / DoW spend alert
- https://www.prompt.security/blog/denial-of-wallet-on-genai-apps-ddow
- https://ithandbook.ffiec.gov/
- https://www.ffiec.gov/%5C/press/PDF/FFIEC_Appendix_J.pdf
