---
title: Case study in go-live review and readiness
description: Learn from a case study how to prepare your Dynamics 365 project for a smooth go-live, including outlines on the decision made and lessons learned.
ms.date: 01/30/2024
ms.topic: concept-article
author: vaniusca
ms.author: vaniaf
ms.custom:
  - evergreen
  - ai-seo-date: 01/30/2024
  - ai-gen-docs-bap
  - ai-gen-title
  - ai-gen-desc
  - bap-template
content_well_notification: AI-contribution
---

# Case study in go-live readiness

A toy company wanted to replace its old on-premises enterprise resource planning and customer relationship management (CRM) systems with Dynamics 365. The new cloud solution would automate and improve the company's processes, increase its revenue, profitability, and scalability, and make its employees happier. But changing from a system it had used for years was a big deal, and it needed to manage the change well.

It planned to move all its financial data and the CRM system to the cloud by the end of the year, its busiest time. By late October, the implementation team was excited and a little nervous about the approaching go-live. They had migrated all the company's processes and integrated them with Power Apps and Power BI. They had completed system integration testing and were finishing user acceptance testing (UAT) and performance testing. The system wasn't perfect, but the team decided that it was good enough for production.

## The go-live review reveals problems

Four weeks before go-live, the implementation team started to check if the company was ready for the change. They used a go-live checklist and asked themselves some questions: Was the system ready? Were the users ready? Was all the infrastructure ready? Were all the systems up to date? Was there a plan for mock cutover? Did the solution from a partner software development company work well?

The go-live review showed some risks and issues that worried them. For example, they found out that mail and other services were in another tenant. They had to move them to the same tenant so that employees could use single sign-on. They also learned that Microsoft would release a new version of Dynamics 365 before go-live. They had to update their environments to the new version and test to make sure that the software development company still worked with it. They had some open transactions that they couldn't close in the old system, so they had to create them again in the new one. Their data migration plan was weak. The system didn't perform as well as they hoped.

The implementation team was busy with UAT, fixing code and bugs, and dealing with new requirements from testing. They missed important deadlines. The business stakeholders had to make a go/no-go decision.

## The decision is made

It was a tough decision, but the stakeholders realized the company wasn't ready to go live. Even though the implementation team had done a lot of work, they didn't have a plan for mock cutover, which was needed to finish the readiness process.

The time was tight. The company had three choices:

- Go live with what it had. This choice risked stopping operations in the middle of the company's busiest season.
- Move the go-live date to January. This choice wasn't possible because the company needed the new system for the holidays.
- Hire more people and work longer hours to try to deliver on time. This choice risked having to train new people and work during the November holidays.

It was clear that going live all at once in a "big bang" as the team had envisioned wasn't a good idea.

## Lessons learned

What could the team have done differently? They couldn't delay the implementation. The system needed to be ready for the holidays. But they could have planned for an earlier go-live date, giving them more time to get ready and deal with delays and issues. They could also have started the go-live review sooner, when UAT was almost done.

The team learned some important lessons from their experience:

- It's vital to schedule the readiness review with enough time and resources to fix any problems.
- It's vital to start the readiness review on time.
- It's vital to have a solid support plan for production.

Don't underestimate the importance of go-live preparation in your implementation plan. Make sure you have enough time to address any issues and risks.
