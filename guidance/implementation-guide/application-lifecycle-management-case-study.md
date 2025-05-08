---
title: Case study in application lifecycle management strategy
description: Learn from a case study how a transport systems company improved its Dynamics 365 implementation by adopting application lifecycle management (ALM) best practices.
author: abunduc-ms
ms.author: abunduc
ms.date: 01/19/2024
ms.topic: concept-article
ms.custom:
  - ai-seo-date: 01/19/2024
  - ai-gen-docs-bap
  - ai-gen-title
  - ai-gen-desc
content_well_notification: AI-contribution
---

# Case study in ALM strategy

This article shows how a global transport systems company improved its Dynamics 365 implementation by adopting application lifecycle management (ALM) best practices. The company learned from its mistakes and realized that a thorough ALM strategy is essential for a successful implementation.

## The challenge

A global transport systems company wanted to implement Dynamics 365 Sales, Customer Service, and Field Service in phases in multiple regions. It had a tight schedule to achieve a minimum viable product (MVP) go-live.

Before the official project kickoff, the company asked its Dynamics 365 implementation partner to create a rapid prototype of the solution to give business stakeholders a taste of what Dynamics 365 could offer. The prototype team included technical salespeople and consultants who would leave the project after this "Phase 0."

The prototype team didn't focus on governance and quality. They thought that Phase 0 was just a quick demo, not a foundation for the future solution. They made several decisions that affected the application management:

- They staffed Phase 0 with people who wouldn't stay on the project team.
- They developed the prototype using separate, unmanaged solutions with different publishers for each Dynamics 365 app.
- They switched to managed solutions for test and production environments too late in the design phase. They had already deployed unmanaged solutions to these environments during Phase 0.
- They merged the solutions for each Dynamics 365 app into a single "workstream" solution during the build phase.
- They fixed errors too quickly during solution deployments because of pressure from project leaders. They didn't take the time to understand the root causes of the problems. This pressure also led to developers customizing directly in the test environment.

## The consequences

As the project team prepared for go-live on the MVP, the decisions made during Phase 0 caused deployment issues that delayed implementation of the MVP by 12 weeks. Microsoft Support investigated the issues and confirmed that there was no ALM strategy in place. They identified the key issues:

- Unmanaged solutions caused solution-layering issues for testing and production, affecting the integrity and reliability of the environments.
- A prototype solution used for production purposes introduced quality issues.
- The lack of ALM practices such as DevOps caused traceability issues. Developers built functionality that didn't match the customer requirements.
- The code quality was poor because tools such as solution checker weren't used.
- The testing was insufficient and untraceable. Buggy code was deployed to other environments.

The project team realized that they had failed to prepare for a successful implementation. They agreed to attend an ALM refresher training. They also confirmed plans that they should have made at the beginning of the project, such as an environment strategy and a solution management and ALM approach.

## The solution

After the refresher training, the project team started with a "crawl to walk" approach. They implemented the following ALM practices with governance elements:

- They cleaned up their production and test environments and moved from unmanaged to managed solutions.
- They implemented a build process to deploy builds from development to test to production.
- They established a governance process to restrict developer access to production and test environments.
- They added a bug-triaging process that allowed the development team to troubleshoot and fix issues in development environments. They used the build process to deploy fixes in higher-tier environments.
- They required the generation of solution checker reports.

Once these practices were in place, the project team moved toward a partially automated ALM process. They set up Azure Pipelines to automate build deployments and auto-generate solution checker reports.

As this case study shows, an ALM strategy is crucial for the entire implementation&mdash;whether it's a new implementation or a prototype elevated to a solution for use in production.
