---
doc-status: Pre-Draft
sequence: 4
type:
  - Detective
mitigates:
  - tr-1
  - tr-2
  - tr-3
  - tr-8
  - tr-9
title: System observability
---

- Anomaly detection
- Audit and compliance
  - current/future regulation?
- Drift detection for output (some underlying system change)
  - Underlying data is at risk of changing in various places
  - Or model version
- Output stability
- User prompt stability
- Cost monitoring (denial of wallet: API calls, CPU-lock/scale out, front-end DOS)
  - Finops vs rate limiting etc
- Responsible AI metrics (gather these from another group)


