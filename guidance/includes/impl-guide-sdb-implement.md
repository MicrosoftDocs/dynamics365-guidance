---
author: edupont04
ms.topic: include
ms.date: 11/26/2026
ms.author: edupont
---
In the **Implement phase**, the project team focuses on building the solution according to the agreed-upon solution design and scope. This phase introduces *Implementation reviews* that come from the findings and recommendations of the Solution Blueprint. Implementation Reviews help you more deeply address questions related to the specific aspects of the solution design (data model, security, and integration) and implementation practices (ALM, testing strategy). Implementation reviews are meant to fully address the risks identified during or after the Solution Blueprint Review but before the solution build is too far along.

When building AI-first solutions, include the following in the **Implement** phase:

- **Agent prototyping and evaluation (evals)**: Build and evaluate agent behavior against defined scenarios before integrating into core workflows. Evals should cover accuracy, coverage, safety, and latency.
- **Non-deterministic behavior management**: Account for the non-deterministic nature of AI outputs in your testing strategy. Define acceptable thresholds and fallback paths.
- **Security and access control**: Review data access scope granted to agents, ensure role-based access controls are applied, and audit agent permissions against the principle of least privilege.