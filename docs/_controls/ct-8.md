---
doc-status: Pre-Draft
sequence: 8
type:
 - Preventative
mitigates:
 - tr-7
 - tr-10
title: QoS/Firewall/DDoS prev
---

LLM endpoints may be abused due to:
  1. attacks to exfiltrate data
  2. jobs coded without the understanding that GPUs are a finite resource

Controls should be in place to ensure that "noisy neighbors" do not interfere with the availability of critical systems.


### API Gateways and Keys

LLM endpoints should require authentication to ensure that only approved use cases can access the LLM. A common approach is to deploy an API gateway and generate API keys specific to each use case. The assignments of keys allows:
  1. revocation of keys on a per use case basis to block misbehaving applications
  2. attribution of cost at the use case level to ensure shared infrastructure receives necessary funding and to allow ROI to be measured
  3. priortizing access of LLM requests when capacity has been saturated and SLAs across all consumers cannot be satisfied


### Modeling and Monitoring

Prioritizing access requires understanding:
   1. expected utilization at various times of day
   2. how to contact the owners when SLAs cannot be met
 
Systems should be in place to:
  - detect anomalous loads
  - throttle loads on a per use case basis to fit the assigned capacity
  - allow intraday reprioritization

### Further reading
- TR-7 Availability of foundational model
- TR-10 Prompt injection
- CT-9 Alerting / DoW spend alert
