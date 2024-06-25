---
title: Manage data synchronization overview
description: Learn about how to plan and manage data synchronization across various Dynamics 365 applications, including an outline of the types of stakeholders.
author: harshbirla
ms.author: harshbir
ms.topic: article
ms.date: 06/25/2024
---

# Manage data synchronization overview

***Applies to: Dynamics 365***

This article describes why you must plan and manage data synchronization across various Dynamics 365 applications and/or by using external applications and/or even for your business intelligence platform.

In the modern business landscape, data is a critical asset that drives decision-making, operational efficiency, and competitive advantage. For organizations that use Dynamics 365, it's crucial to ensure seamless data synchronization across various Dynamics 365 applications, external applications, and business intelligence systems. If a robust synchronization plan doesn't exist, data silos form and lead to inefficiencies and a fragmented view of business operations.

Dynamics 365 offers several tools and techniques for managing data synchronization. *Dual-write* is an out-of-box infrastructure that provides near-real-time interaction between customer engagement apps and finance and operations apps such as Dynamics 365 Finance. Learn more in [Dual-write home page](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-home-page). With *virtual entities*, you can integrate data that resides in external systems by seamlessly representing that data as entities in Dynamics 365, without replication of data and often without custom code. Learn more in [Virtual entities overview](/dynamics365/fin-ops-core/dev-itpro/power-platform/virtual-entities-overview).

Cross-company data sharing enables sharing of reference and group data across multiple legal entities in Dynamics 365 Finance and Dynamics 365 Supply Chain Management. With main company data sharing, you can share main data across companies. Fabric Link is a new feature that you can use to connect finance and operations apps with Dynamics 365 apps. With Azure Synapse Link for Dynamics 365, you can bring together the power of Dynamics 365 and Azure Synapse Analytics to immediately gain insights into your Dynamics 365 data.

## Stakeholders

Many people across the organization should contribute to the decision-making process and design of the *manage data synchronization* area. The following list provides examples of such stakeholders:

- **Executive leadership stakeholders** include chief executive officers (CEOs), chief financial officers (CFOs), and chief information officers (CIOs). Executive leaders provide strategic oversight and ensure that the data synchronization plan is aligned with organizational goals and priorities. They are important for resource allocation and decision-making in times of crisis.
- **IT management stakeholders** include CIOs, IT directors, and IT managers. IT management plays a key role in identifying critical systems and data, implementing technical aspects of the data move plan, and ensuring that IT resources work well with overall organizational resilience strategies.
- **Program management team** includes project managers from various streams and overall program managers. It's responsible for overseeing successful execution of the data management process. Team members lead the project team, manage the project plan and schedule, and ensure that the project delivers the intended scope on time and within budget.
- **Business process owners** are the individuals who are responsible for specific business processes in the organization. They work with the project team to identify areas where the project is affecting their business processes and ensure that the outcome of the project meets their needs.
- **Business users** are the individuals who use any system that the project delivers. They provide feedback to the project team about the system's usability and functionality, and ensure that the system meets their needs.

## Manage data synchronization process flow

The following diagram illustrates the *manage data synchronization* business process area.

:::image type="content" source="media\administer-to-operate-manage-data-synchronization-overview-1.svg" alt-text="Diagram showing the connection between the manage data synchronization business process area and other administer to operate business areas." lightbox="media\administer-to-operate-manage-data-synchronization-overview-1.svg":::

[!INCLUDE [daf-business-process-flow-def](~/../shared-content/shared/guidance-includes/daf-business-process-flow-def.md)]

1. Start
1. *Administer to operate*
1. *Manage data synchronization*, which has four substeps:

    1. *Manage the initial synchronization of data*, where the initial data synchronization is managed
    1. *Manage the recurring synchronization of data*, where the ongoing, regular synchronization of data is managed
    1. *Monitor data synchronization failures*, where any failures that occur during data synchronization are monitored
    1. *Correct data synchronization failures*, where any issues that are identified during data synchronization are corrected

1. End

The diagram also includes business processes on each side.

- On the left side:

  - Acquire to dispose
  - Case to resolution
  - Concept to market
  - Design to resolution
  - Forecast to plan
  - Hire to retire
  - Inventory to deliver

- On the right side:

  - Order to cash
  - Plan to produce
  - Procure to pay
  - Project to profit
  - Prospect to quote
  - Record to report
  - Service to cash

These business processes are related to the data synchronization steps in the center of the diagram. However, they aren't directly part of the sequential flow that is described.

In addition, the two large, curved arrows indicate that the process is iterative.

## Manage data synchronization benefits

There are many key benefits that can be used to monitor and measure the success of implementing technology to support the management of data synchronization. The following sections outline the key benefits that an organization might monitor and measure for the *manage data synchronization* business process area.

### Improved data accuracy and consistency

One of the primary benefits of implementing technology to manage data synchronization in Dynamics 365 is the enhancement of data accuracy and consistency. By automating the synchronization process, organizations can ensure that data across all applications and systems is uniform and up to date. As a result, there is less likelihood of discrepancies that can arise from manual data entry or delayed updates. Accurate and consistent data enables more reliable reporting and analytics, and therefore supports better decision-making and strategic planning.

### Enhanced operational efficiency

Effective management of data synchronization can lead to significant improvements in operational efficiency. With synchronized data, employees can access the information that they need without switching between systems or dealing with outdated data. This seamless access to accurate information streamlines workflows and reduces the time that is spent on administrative tasks. For example, sales teams can better manage customer relationships by using real-time data from both customer relationship management (CRM) and enterprise resource planning (ERP) systems. The results are faster response times and more productive engagements.

### Enhanced data security and compliance

With Dynamics 365, organizations can sync data securely and reliably across systems. Because data synchronization can involve sensitive information, data must be safe while it's being moved and stored. Dynamics 365 encrypts all data at rest. Dynamics 365 security frameworks control user access to your data. In addition, when you use technologies such as dual-write and virtual tables, the source application's business logic applies across applications to keep data consistent.

### Improved decision making and business intelligence

Effective data synchronization supports better decision-making by ensuring that business intelligence (BI) tools have access to the most current and accurate data. Dynamics 365 facilitates the integration of data from multiple sources into BI platforms. In this way, it allows for comprehensive analysis and reporting through technologies such as Microsoft Fabric link and Azure Synapse Link for Dynamics. Decision makers can use this consolidated data to gain actionable insights, identify trends, and make informed strategic choices. For example, synchronized sales and financial data can reveal patterns in revenue generation and therefore help optimize pricing strategies and sales tactics.

## Next steps

If you want to implement Dynamics 365 solutions to assist with your *manage data synchronization* business processes, you can use the following resources and steps to learn more. (Links are added, when the articles are ready.)  

1. [Define a business continuity plan](administer-to-operate-define-business-continuity-plan-overview.md)
1. *Manage licensing and entitlements*
1. *Administer system features*
1. [Manage system access and security](administer-to-operate-manage-system-access-security.md)  
1. [Train users and increase adoption](administer-to-operate-train-users-increase-adoption-overview.md)
1. *Monitor systems, environments, and capacity*
1. *Manage background jobs*
1. *Manage notifications alerts*
1. *Uptake software releases*
1. *Manage data synchronization* (the page that you're currently reading)
1. [Manage system compliance](administer-to-operate-manage-system-compliance.md)  
1. [Support systems](administer-to-operate-support-systems-overview.md)

## Related resources

You can use the following resources to learn more about the *manage data synchronization* process in Dynamics 365.

- [Dual-write overview](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-overview)
- [Get started with virtual tables (entities) (Microsoft Dataverse)](/power-apps/developer/data-platform/virtual-entities/get-started-ve)
- [Virtual entities overview](/dynamics365/fin-ops-core/dev-itpro/power-platform/virtual-entities-overview)
- [Cross-company data sharing overview](/dynamics365/fin-ops-core/dev-itpro/sysadmin/srs-overview)
- [Create an Azure Synapse Link for Dataverse with your Azure Synapse Workspace](/power-apps/maker/data-platform/azure-synapse-link-synapse)
- [Choose finance and operations data in Azure Synapse Link for Dataverse](/power-apps/maker/data-platform/azure-synapse-link-select-fno-data)
- [Link your Dataverse environment to Microsoft Fabric and unlock deep insights](/power-apps/maker/data-platform/azure-synapse-link-view-in-fabric)
- [Integration between finance and operations apps and third-party services](/dynamics365/fin-ops-core/dev-itpro/data-entities/integration-overview)
- [Integrate your Dynamics 365 apps with other solutions](../implementation-guide/integrate-other-solutions.md)

<!--## Tags

*Industries:* Agriculture (01-09), Mining (10-14), Construction (15-17), Manufacturing (20-39), Transportation and Public Utilities (40-49), Wholesale Trade (50-51), Retail Trade (52-59), Finance, Insurance, Real Estate (60-67), Services (70-89), Public Administration (91-99)

*Stakeholders:* Administrative, Audit, Engineering, IT, Project Management

*Products:* Dynamics 365 -->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [Harsh Birla](https://www.linkedin.com/in/harsh-birla-2519714/) \| Principal Solutions Architect

Other contributors:

- [Rachel Profitt](https://www.linkedin.com/in/rachelprofitt) \| Principal Program Manager
