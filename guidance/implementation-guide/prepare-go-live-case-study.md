---
title: A case study for Dynamics 365 implementation projects’ prepare phase
description: Review the readiness of a toy company to go live with Microsoft Dynamics 365 to learn the importance of the prepare phase in an implementation project.
ms.date: 06/06/2023
ms.topic: conceptual
author: vaniusca
ms.author: vaniaf
ms.custom:
  - ai-gen-docs-bap
  - ai-gen-desc
  - ai-seo-date:08/22/2023
  - bap-template
---

# A case study for the prepare phase of Dynamics 365 implementation projects

**A toy company reviews its readiness to go live with a new cloud solution.**

A toy company had embarked on a months-long project to replace its on-premises enterprise resource planning and customer relationship management (CRM) systems with Dynamics 365. Employees looked forward to moving to a system that would automate and improve their previously manual, inefficient processes. Leadership anticipated increased revenue growth, profitability, and scalability. But the impact of changing from a system that had been in place for many years would be huge, and change management was critical for success.

The company targeted the transfer of all financial data and the CRM system to the cloud by the end of the year, its busiest time. At the end of October, the team was excited and a little nervous about the approaching go-live. All processes were migrated and integrations with Power Apps and Power BI were in place. System integration testing was complete. With user acceptance testing (UAT) and performance testing nearly done, the system seemed to perform well enough. Although not optimal, it was considered ready for production.

## The go-live review raises concerns

With go-live four weeks away, the implementation team began to assess the company's readiness for the implementation. As they prepared the go-live checklist, they asked themselves the following questions: Was the system ready? Were the users ready? Was all the infrastructure ready? Were all the systems up to date? Was the mock cutover planned? Were the independent software vendor solutions (ISVs) working well?

The go-live review revealed some risks and issues that raised concerns. For instance, the implementation team discovered that mail and other services resided in another tenant. They needed to perform a tenant move so that employees could use single sign-on. They learned that Microsoft was releasing a new version of Dynamics 365 by the go-live date. They had to update their environments to the new version, which required another smoke test to verify the ISVs worked correctly with the update. Open transactions weren't ready to be closed in the old system, so they needed to be recreated in the new one. The data migration plan wasn't solid. The system didn't perform as well as expected.

With the implementation team focused on UAT, troubleshooting code and making fixes, and addressing new requirements identified during the testing phase, they missed important dates. Business stakeholders made a go/no-go decision.

## The verdict comes in

It wasn't an easy decision, but stakeholders realized the company wasn't ready to go live. Despite all the heavy lifting the implementation team had done, they didn't have a mock cutover plan, which was necessary to complete the readiness process.

The timelines were tight. The company had three choices:

- Go live with what it had. This choice risked stopping operations in the middle of the busiest season.

- Move the go-live date to January. Delaying the implementation wasn't a viable option, however.  

- Hire more resources and work more hours to try to deliver on time. This choice risked scheduling ramp-up during the November holidays.

It was obvious that the "big bang" go-live the team had envisioned wasn't optimal under the circumstances.

## Lessons learned

What could the team have done differently? They couldn't push back the implementation. The system needed to be ready for the holidays. But they could have planned for an earlier go-live date, giving them more time for ramping up and addressing delays and issues. They could also have started the go-live review earlier, with UAT almost complete.

The team learned several important lessons from their experience.

- It's critical to schedule the readiness review with sufficient time and resources to address any concerns.
- It's critical to start the readiness review on time.
- It's crucial to have a solid support plan for production.

Don't underestimate the importance of the Prepare phase in your implementation plan. Build in enough time to mitigate any issues and risks.
