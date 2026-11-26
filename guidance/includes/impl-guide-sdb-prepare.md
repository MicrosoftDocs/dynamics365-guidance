---
author: edupont04
ms.topic: include
ms.date: 11/26/2026
ms.author: edupont
---
By the **Prepare phase**, the project team built and tested the solution and is preparing for the final round of user acceptance testing (UAT) and training. Also, the project team granted all necessary customer approvals, completed information security reviews, defined the cutover plan (including go/no-go criteria), scheduled mock go-lives, readied the support model, and completed the deployment runbook with tasks, owners, durations, and dependencies defined. At this point, the project team uses the Success by Design Go-live Readiness Review to identify any remaining gaps or issues.

For AI-enabled solutions, Go-live readiness should additionally confirm:

- **Pre-production validation**: Validate agents against production-representative data and scenarios, not just development or test datasets.
- **Responsible AI sign-off**: Document and approve Responsible AI review and residual risk acceptance by accountable business stakeholders.
- **Monitoring and observability readiness**: Set up telemetry, logging, and alerting for agent outputs before go-live.
- **Incident response plan**: The support team understands how to detect, triage, and respond to agent behavioral anomalies post-deployment. For example, use telemetry queries to distinguish a single task failure from a broader pipeline stoppage.