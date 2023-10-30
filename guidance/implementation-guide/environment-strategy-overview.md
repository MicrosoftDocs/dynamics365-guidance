---
title: Environment strategy
description: Environments are containers that store, manage, and share your organization's data. They also store the data model, application metadata, process definitions, and the security constructs to control access to data and apps. The considerations in this article will guide you to define an environment approach that best meets your requirements for data access, isolation, security, governance, and scalability.
author: abunduc-ms
ms.author: abunduc
ms.date: 10/30/2023
ms.topic: conceptual

---

# Environment strategy

Defining your environment strategy is one of the most important steps in the implementation of your business application. Environment-related decisions affect every aspect of the application, from application lifecycle management (ALM) to deployment and compliance.

At a fundamental level, a good environment strategy is about obtaining the right balance with multiple layers of compliance and security, productivity, collaboration, isolation, performance, and maintainability. A strategy to manage environment provisioning and access, and controlling resources within them, is key to:

- Securing data and resource access

- Organizing and structuring solution components

- Governing and managing capacity

We'll explore several deployment and transition scenarios and look at the factors to consider when defining your environment strategy. We'll identify the available patterns that will enable you to confidently deliver an environment plan for your applications.

## Key objectives

- Plan your environment and tenant strategy.

- Identify the key factors affected by the environment strategy.

- Define your environment app strategy.

- Explore deployment scenarios and models.

- Discover different environment lifecycle scenarios.

- Learn how governance and control can affect your environment strategy.

- Discover product-specific guidance for use in operations and customer engagement.

- Review general recommendations for building your environment strategy.

## Tenant strategy

The tenant strategy defines the foundation that a healthy environment strategy builds on.  

A tenant is a logical structure that represents your organization. Every cloud service to which an organization subscribes will be associated with the customer's tenant. A tenant isn't dedicated to a specific service; it has subscriptions for Microsoft services, such as Exchange, Dynamics 365, Power BI, and Azure. Every tenant is given a Microsoft domain, such as `yourorganization.onmicrosoft.com`, but admins can also associate their own custom domains with the tenant. You can also federate access to your tenant via your organization's on-premises Active Directory to enable single sign-on (SSO) across on-premises and cloud services.

[!INCLUDE [azure-ad-to-microsoft-entra-id](~/../shared-content/shared/azure-ad-to-microsoft-entra-id.md)]

The following article [Tenant strategy](environment-strategy-tenant-strategy.md) provides more details of how the different isolation approaches shape the tenant strategy.

## Overview of an environment strategy

Environments are containers that store, manage, and share your organization's data. They also store the data model, application metadata, process definitions, and the security constructs to control access to data and apps. The considerations in the following sections aim at guiding implementation teams to define an environment approach that best meets your requirements for data access, isolation, security, governance, and scalability.

A successful environment strategy defines the core principles and policies for creating, granting access to, and decommissioning environments of different types, along with the necessary governance process. These policies should provide a consistent approach for centrally deployed, IT-driven implementations and for citizen-developed applications for individuals or small business teams.

The project plan plays a crucial role in defining the environment strategy. Some activities could run in parallel, for example training and data migration, as long as there are enough environments available. Constraints such as timeline and cost need to be considered as well.

A data strategy is likely to inform or impose constraints on an environment strategy. For example, an organization could build a unified data platform that different apps and services consume, or there could be a fragmented legacy data estate that must be accounted for in the cloud environment strategy.

The environment strategy isn't the responsibility of a single person or team. It can involve IT admins, the architects responsible for the design and implementation of the solution, the information security and compliance teams, and the business stakeholders.

Environment-related decisions are hard and expensive to change. They can affect how solutions are implemented. This exercise needs to be done at the start of the project, even before beginning implementation, and isn't something that should be left to the end as a part of a go-live plan.

## What is environment planning?

Environment planning is the process of describing the details of all the environments required during and after implementation. It includes procuring and preparing all environments that the team will need to adequately develop and test the Dynamics 365 solution.

A sample environment plan (Environment-Plan-Sample-DYN879PAL.xlsx) is provided in the [Environment Planning for finance and operations implementations](https://community.dynamics.com/blogs/post/?postid=d3606de6-90b7-42c3-9211-d98479d620fc)  TechTalk. The matrix format lists the type, topology, deployment option, and due date for each environment. This plan is a living document that should be revisited after each milestone of the project.

### The importance of environment planning

Implementing an enterprise resource planning (ERP) and a customer relationship management (CRM) project typically requires collaboration among multiple teams that will need to access the apps for different reasons: to develop, build, test, and train. So, part of your plan should cover making environments available for different teams to ensure they can deliver their respective tasks on time. Also, if you plan for all needed environments early, you'll know what the costs are going to be throughout the project and at which stages you need the funds, and you'll avoid project delays from last-minute discoveries of missing environments.

To get started with creating an environment strategy, ask the following questions:

- Where are my users physically located?

- What are my organization's data compliance and residency requirements?

- What types of environments are required, and when?

- What are the different roles (such as developers, testers, admins, business analysts and trainers), and which environments do they need access to?

- Do I have overlapping activities in my project plan that will require an environment (such as training, testing, data migration)?

- Is there enough time allocated in my plan for preparing an environment for a specific use (such as refresh and restore operations before training)?

- What's the access procedure for an environment?

- Which apps will be installed in the environment?

- Will the solution require more than one production environment?

- Which services and third-party applications do I need to integrate with?

## Key factors affected by an environment strategy

The environment strategy influences a series of key factors of a solution. Key factors include security and compliance, ALM, operations, and functional and nonfunctional aspects of the solution. Take these key factors into consideration early to help you define an environment strategy that meets the needs of your organization, and set the direction for the future growth of these applications to meet evolving business requirements.

In the article [Key factors affected by the environment strategy](environment-strategy-key-factors-affected.md), we explore the key factors directly affected by an environment strategy.

## Global deployment scenarios

Global deployment scenarios for Dynamics 365 refer to the different ways in which you can deploy and use the application across different geographies and regions. These scenarios have a direct impact on the environment strategy. There are two main global deployment scenarios for Dynamics 365:

- Global single-environment implementation is just one environment deploying an app that users across the globe access. All the data, processes, code, customizations reside in a single environment. Based on the app's security requirements and regional data-sharing policies, your organization will have to manage access via security roles. It's the most common approach, as it enables strong global collaboration and a unified view of data and processes across different regions, business units, and legal entities.

- Multiple-environment scenarios support different business units, departments, teams, countries/regions, or other structures inside an organization.  

  Each environment has its own database, and data isn't shared across environments. The approach provides a physical security aspect on top of logical, out-of-the-box security based on security roles. In separating environments by region or country, solutions included in each environment can support local business and compliance requirements.

The article [Global deployment scenarios](environment-strategy-global-deployment-scenarios.md) evaluates the pros and cons of each of these two strategies, to help you find the best option for your deployment.

## Environment lifecycle scenarios

Environments transition through various states before they're decommissioned. Some of these transitions are natural to support ALM, but there could be business, compliance, and technical reasons that trigger these transitions. As described earlier, environment-related changes are complex, and they require significant planning and (usually) downtime.

These environment lifecycle activities are essential to make sure that Dynamics 365 environments are properly configured, maintained, and secured throughout their lifecycle. By following best practices and performing these activities in a systematic and thorough manner, IT admins and developers can help to ensure that environments are stable, reliable, and meet the needs of the organization.

In the article [Environment lifecycle scenarios](environment-strategy-lifecycle-scenarios.md), we dive into the various activities that might be performed throughout the lifecycle of an environment.

## Governance and control

Establishing a center of excellence (CoE) for business applications that is responsible for defining guidelines, creating best practices, and nurturing organic growth plays a fundamental role in driving business innovation.

Good governance is critical during deployment and for long-term system operation. But the governance and control processes for a centrally deployed and managed IT solution might be vastly different from processes used to deliver a secure ecosystem of business-user-developed applications.

A CoE helps enforce security and policies, but also fosters creativity and innovation across the organization. It empowers users to digitize their business processes, while maintaining the necessary level of oversight.

With the changing technology landscape and evolution of security mechanisms, organizations should review and update policies on a continuing basis. The better organizations understand the service architecture, the greater the opportunity to fine-tune the controls, rather than creating overly restrictive policies.

To define a robust environment governance policy:

- Examine your organization's usage, application types, user personas and location, data confidentiality, and access control.

- Identify how environments need to comply with the different requirements, such as access rules or the data sensitivity level that they can store. Is data obfuscation needed?

- Evaluate your capacity needs in terms of storage, API calls, and other factors.

- Understand the release and rollout strategy, and how it affects the environment lifecycle.

- Enforce audit requirements at the environment and application levels.

- Ensure DLP policies apply tenant-wide.

- Define admin roles and processes to obtain admin privileges.

- Monitor deployment and usage.

## Product-specific guidance

Throughout this article, we have discussed concepts related to environment strategy that are product-agnostic and apply to most cloud deployments.

There are a series of concepts that are specific to the finance and operations apps like Dynamics 365 Finance, Dynamics 365 Supply Chain Management, and Dynamics 365 Commerce. A team implementing a project with these apps requires environments to develop, test, train, and configure before production. These nonproduction environments come in a range of tiers with pre-defined sizing, topologies, and costs. Understanding these basics is key to charting out a well-designed environment plan.

Environments and Dataverse in Power Platform are dedicated instances used for developing, testing, and deploying solutions built on the Power Platform. Power Apps is a suite of apps, services, connectors, and a data platform that provides an app-development environment where you can quickly build custom business apps that connect to your business data stored in either the underlying data platform (Dataverse) or online and on-premises data sources. Customer-engagement apps such as Sales and Customer Service are first-party Power Apps developed by Microsoft.

Dynamics 365 and the Power Platform make it easier to create apps and share data across all Dynamics 365 applications. The combination also creates a set of purpose-built intelligent apps to connect front office and back office functions through shared data. Rich analytical capabilities provide organizations with deep insights into each functional area of their business.

The article [Product specific guidance](environment-strategy-guidance-product.md) explores the distinct characteristics of the finance and operations apps and Power Platform environments.

## On-premises to online migration services

The [Dynamics 365 migration program](/dynamics365/get-started/migration/migration-overview) enables on-premises customers to simplify and accelerate their move to the cloud. The migration program also features access to a dedicated team of migration advisors, no-charge migration assessments, pricing offers, tools (including a [CRM platform assessment tool](/dynamics365/get-started/migration/assessment-tool)), and migration support for customers.

## Conclusion

As we've seen throughout this article, defining an environment strategy for your organization is a critical step when planning for deployment. Decisions made about environment strategies are hard to change and could be costly later in the program lifecycle. The wrong environment strategy can create unnecessary data fragmentation and increase the complexity of your solutions. Early environment planning aligned to your organization's digital roadmap is fundamental to success.

## Next steps

- Review the case study at [Timely environment planning is a critical factor to success](environment-strategy-case-study.md)  

- Learn more about recommendations for your Azure Active Directory tenant at [Tenant strategy](environment-strategy-tenant-strategy.md)  

- Access the checklist at [Environment strategy Success by Design checklist](environment-strategy-checklist.md)
