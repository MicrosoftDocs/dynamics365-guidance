---
title: Plan your environment strategy for Dynamics 365
description: Learn how to plan your environment strategy to balance compliance, security, productivity, and performance for your Dynamics 365 apps.
author: abunduc-ms
ms.author: abunduc
ms.date: 01/16/2024
ms.update-cycle: 1095-days
ms.topic: concept-article
ms.custom:
  - evergreen
  - ai-seo-date: 01/16/2024
  - ai-gen-docs-bap
  - ai-gen-title
  - ai-gen-desc
content_well_notification: AI-contribution
---

# Plan your environment strategy for Dynamics 365

Defining your environment strategy is one of the most important steps in implementing your Dynamics 365 solution. Your environment strategy affects every aspect of your app, from application lifecycle management (ALM) to deployment and compliance.

A good environment strategy helps you find the right balance of compliance and security, productivity, collaboration, isolation, performance, and maintainability. You need a strategy to manage how you create, access, and control resources in your environments. This strategy is key to:

- Secure data and resource access
- Organize and structure solution components
- Govern and manage capacity

You should decide on your environment strategy before you start implementing your app. Changing your environment strategy later can be hard and expensive. It can also affect how your solutions work. Don't wait until the end of the project to plan your environment strategy.

This article explores several deployment and transition scenarios. It helps you consider the factors and patterns that can help you plan your environment strategy. It also guides you on how to plan for the different environments you'll need during and after implementation. Finally, it provides a checklist to help you plan your environment strategy.

## Key objectives

- Plan your environment and tenant strategy.
- Identify the key factors that your environment strategy affects.
- Define your environment app strategy.
- Explore deployment scenarios and models.
- Learn about environment lifecycle scenarios.
- Learn how governance and control can affect your environment strategy.
- Discover product-specific guidance for finance and operations apps and customer engagement apps.
- Review general recommendations for planning your environment strategy.

## Start with the tenant strategy

The first step in planning your environment strategy is to determine your tenant strategy. Your tenant strategy defines the structure of your organization's Microsoft Entra ID (formerly Azure Active Directory) tenant and how you use it to manage access to your Dynamics 365 business app.

A *tenant* is a logical structure that represents your organization. Every cloud service that you subscribe to, such as Exchange, Dynamics 365, Power BI, and Azure, is associated with your tenant. Every tenant has a Microsoft domain, such as `yourorganization.onmicrosoft.com`, but admins can associate a custom domain with the tenant. You can federate access to your tenant using your organization's on-premises Microsoft Entra ID for single sign-on (SSO) across on-premises and cloud services.

[!INCLUDE [azure-ad-to-microsoft-entra-id](~/../shared-content/shared/azure-ad-to-microsoft-entra-id.md)]

[Learn how different isolation approaches shape the tenant strategy](environment-strategy-tenant-strategy.md).

## Overview of an environment strategy

*Environments* are containers that store, manage, and share your organization's data. They also store the data model, app metadata, process definitions, and the security constructs to control access to data and apps. The considerations in the following sections help you plan an environment approach that meets your requirements for data access, isolation, security, governance, and scalability.

A successful environment strategy defines the core principles and policies for creating, accessing, and decommissioning environments of different types, along with the necessary governance process. These policies should provide a consistent approach for centrally deployed, IT-driven implementations and for citizen-developed apps for individuals or small business teams.

The project plan plays a crucial role in planning your environment strategy. Some activities, such as training and data migration, could run in parallel as long as you have enough environments. The project plan should consider constraints such as timeline and cost as well.

The data strategy might inform or impose constraints on your environment strategy. For example, your organization might build a unified data platform that different apps and services consume, or it might have a fragmented legacy data estate that you must account for in your cloud environment strategy.

The environment strategy isn't the responsibility of a single person or team. It can involve IT admins, the architects who design and implement the solution, the information security and compliance teams, and the business stakeholders.

## What is environment planning?

Environment planning is the process of describing the details of all the environments that you need during and after implementation. It includes procuring and preparing all environments that the team needs to develop and test the Dynamics 365 solution. The plan lists the type, topology, deployment option, and due date for each environment. It's a living document that you should revisit after each project milestone.

A sample environment plan (Environment-Plan-Sample-DYN879PAL.xlsx) is provided in the [Environment planning for finance and operations implementations](https://community.dynamics.com/blogs/post/?postid=d3606de6-90b7-42c3-9211-d98479d620fc) TechTalk.

### The importance of environment planning

Implementing an enterprise resource planning (ERP) and a customer relationship management (CRM) project typically requires collaboration among multiple teams that need to access the apps for different reasons: to develop, build, test, and train. Part of your plan should cover making environments available for different teams so that they can deliver their tasks on time. Also, if you plan for all needed environments early, you'll know what the costs will be throughout the project and at which stages you need the funds, and you'll avoid project delays from last-minute discoveries of missing environments.

To get started with creating an environment strategy, ask the following questions:

- Where are my users physically located?
- What are my organization's data compliance and residency requirements?
- What types of environments do I need, and when?
- What are the roles (such as developers, testers, admins, business analysts, and trainers), and which environments do they need access to?
- Do I have overlapping activities in my project plan that will require an environment, such as training, testing, and data migration?
- Is enough time allocated in my plan for preparing an environment for each specific use?
- What's the access procedure for an environment?
- Which apps will be installed in the environment?
- Will the solution require more than one production environment?
- Which services and non-Microsoft apps do I need to integrate with?

## Key factors affected by an environment strategy

The environment strategy influences several key factors of a solution. Key factors include security and compliance, ALM, operations, and functional and nonfunctional aspects of the solution. Consider these key factors early to help you plan an environment strategy that meets the needs of your organization and sets the direction for the future growth of these apps to meet evolving business requirements.

[Learn about the key factors that your environment strategy affects](environment-strategy-key-factors-affected.md).

## Global deployment scenarios

Global deployment scenarios for Dynamics 365&mdash;the different ways that you can deploy and use the app across different geographies and regions&mdash;have a direct impact on your environment strategy. Global deployment scenarios for Dynamics 365 fall into two main categories:

- In *global single-environment implementations*, you deploy an app in one environment that users everywhere access. All the data, processes, code, and customizations reside in that one environment. Based on the app's security requirements and regional data-sharing policies, your organization has to manage access using security roles. A single-environment implementation is the most common approach, because it makes global collaboration and a unified view of data and processes across different regions, business units, and legal entities easier.

- In *multiple-environment implementations*, each environment has its own database, and data isn't shared across environments. This approach adds physical security to logical, out-of-the-box security based on security roles. In separating environments by region or country, solutions that are included in each environment can support local business and compliance requirements. Organizations often use this approach to support different business units, departments, teams, countries/regions, or other structures.

[Learn about the pros and cons of each type of global deployment scenario](environment-strategy-global-deployment-scenarios.md).

## Environment lifecycle scenarios

Environments transition through various states before you decommission them. Some of these transitions are natural to support ALM, but business, compliance, and technical reasons can also trigger them. As mentioned earlier, environment-related changes are complex, and they require significant planning and usually downtime.

Environment lifecycle activities are essential to make sure that Dynamics 365 environments are properly configured, maintained, and secured throughout their lifetimes. By following best practices and performing these activities in a systematic and thorough manner, IT admins and developers can help make sure that environments are stable, reliable, and meet the needs of your organization.

[Learn about environment lifecycle activities](environment-strategy-lifecycle-scenarios.md).

## Governance and control

A center of excellence (CoE) that's responsible for defining guidelines, creating best practices, and nurturing organic growth of business apps plays a fundamental role in driving business innovation.

Good governance is critical during deployment and for long-term system operation. The governance and control processes for a centrally deployed and managed IT solution might be vastly different from processes used to deliver a secure ecosystem of apps developed by business users. A CoE helps enforce security and policies, but also fosters creativity and innovation across your organization. It empowers users to digitize their business processes, while maintaining the necessary level of oversight.

With the changing technology landscape and evolution of security mechanisms, your organization should review and update policies on a continuing basis. The better your organization understands the service architecture, the greater the opportunity to fine-tune the controls rather than creating overly restrictive policies.

To define a robust environment governance policy:

- Examine your organization's usage, app types, user personas and location, data confidentiality, and access control.
- Identify how your environments need to comply with different requirements, such as access rules or the data sensitivity level that they can store. Do you need data obfuscation?
- Evaluate your capacity needs in terms of storage, API calls, and other factors.
- Understand the release and rollout strategy, and how it affects the environment lifecycle.
- Enforce audit requirements at the environment and app levels.
- Make sure that data loss prevention policies apply tenant-wide.
- Define admin roles and processes to obtain admin privileges.
- Monitor deployment and usage.

## Product-specific guidance

In this article, we discussed concepts related to environment strategy that don't depend on the product and apply to most cloud deployments. Other concepts are specific to finance and operations apps like Dynamics 365 Finance, Dynamics 365 Supply Chain Management, and Dynamics 365 Commerce. A team that's implementing a project with these apps needs environments to develop, test, train, and configure before production. These nonproduction environments come in a range of tiers with predefined sizing, topologies, and costs. Understanding these basics is key to charting out a well-designed environment plan.

[Learn about the distinct characteristics of Dynamics 365 finance and operations apps and Power Platform environments](environment-strategy-guidance-product.md).

## On-premises to online migration services

The Dynamics 365 migration program helps on-premises customers simplify and accelerate their move to the cloud. The migration program offers access to a dedicated team of migration advisors, no-charge migration assessments, pricing offers, and tools such as a [CRM platform assessment](/dynamics365/get-started/migration/assessment-tool).

Learn more at [Migrate to Dynamics 365 online from Dynamics on-premises products](../migrate/overview.md).

## Conclusion

Planning your environment strategy for your organization is a critical early step in planning for deployment. Decisions that you make about environments are hard and costly to change later. The wrong environment strategy can create data fragmentation and increase the complexity of your solutions. Early environment planning that's aligned to your organization's digital roadmap is fundamental to success.

## Next steps

- Define the right [tenant strategy](environment-strategy-tenant-strategy.md)
- Learn about the [key factors that are affected by an environment strategy](environment-strategy-key-factors-affected.md)
- Learn about [global deployment scenarios](environment-strategy-global-deployment-scenarios.md)
- Understand [environment lifecycle scenarios](environment-strategy-lifecycle-scenarios.md)
- Get [product-specific guidance](environment-strategy-guidance-product.md)
- Follow the [environment strategy checklist](environment-strategy-checklist.md)
- Read a [case study](environment-strategy-case-study.md) of a company that learned the importance of a good environment strategy
