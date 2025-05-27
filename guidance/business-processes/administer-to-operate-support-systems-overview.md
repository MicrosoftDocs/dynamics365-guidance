---
title: Define support systems overview
description: Learn about support systems, including outlines of how they help increase proactive issue detection, decrease resolution times, and enhance collaboration.
ms.topic: concept-article
author: hasaid
ms.author: hasaid
ms.date: 08/07/2024
---

# Define support systems overview

***Applies to: Dynamics 365***

This comprehensive article about support systems delves into the critical processes of establishing support procedures and policies, managing support subscriptions, handling support incidents, troubleshooting issues, and conducting root cause analysis. With particular emphasis on Dynamics 365 implementations, it explores how these business processes contribute to the smooth functioning and optimization of organizational operations.

Support systems are integral to the success of any organization. They serve as the backbone for ensuring smooth business operations and optimal customer satisfaction. In the context of Dynamics 365 implementations, support processes take on increased significance. The establishment of support procedures and policies lays the groundwork for effective assistance and issue resolution, and ensures that resources are allocated efficiently and consistently across the organization.

Management of support subscriptions allows for seamless access to necessary resources and expertise. Therefore, it facilitates timely assistance and helps reduce downtime. When support incidents occur, swift troubleshooting and resolution are paramount to maintaining operational continuity and preserving customer trust. In addition, root cause analysis not only addresses immediate concerns but also fosters a culture of continuous improvement by driving efficiency and innovation in Dynamics 365 ecosystems.

In essence, these support processes are instrumental in maximizing the value that is derived from Dynamics 365 implementations, bolstering organizational resilience, and enhancing competitive advantage in today's dynamic business landscape.

Many tools can be used to monitor and analyze an issue with Dynamics 365 apps and conduct root cause analysis.

## Increase proactive issue detection by monitoring environments

Implementation of environment monitoring can significantly increase proactive detection of issues in a customer's environment. Dynamics 365 and associated admin centers provide comprehensive monitoring capabilities, including performance metrics, health checks, and alerts.

By continuously monitoring environment health and analyzing telemetry data, teams detect anomalies, identify potential issues, and take proactive measures to prevent downtime or performance degradation. Through real-time insights and automated alerting, monitored environments empower organizations to address issues before they escalate. Therefore, they help ensure optimal performance and reliability of Dynamics 365 apps.

Learn more at [Monitoring and diagnostics tools in Lifecycle Services (LCS)](/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/monitoring-diagnostics) and [Managed Environments overview](/power-platform/admin/managed-environment-overview), respectively.

## Decrease resolution time with Application Insights

Application Insights can decrease the resolution time for issues in Dynamics 365 apps by providing deep insights into application performance and behavior. Application Insights offers advanced monitoring and diagnostics capabilities, including performance metrics, error tracking, and user telemetry.

By analyzing telemetry data in real time and using built-in analytics features, support teams can quickly identify root causes of issues, prioritize resolution efforts, and expedite incident resolution. Additionally, Application Insights allows for proactive alerts and anomaly detection, so that teams can quickly react to emerging issues and minimize downtime.

## Enhance collaboration with Microsoft 365 Service Center

Integration of Microsoft 365 Service Center with Dynamics 365 support systems can enhance collaboration among support teams and stakeholders. Therefore, it can lead to more efficient issue resolution. Microsoft 365 Service Center serves as a centralized hub for managing Microsoft 365 services, including Dynamics 365 apps. It provides a unified view of service health, incidents, and updates.

By using collaboration features such as chat, incident sharing, and knowledge base access, support teams can streamline communication, share insights, and effectively coordinate response efforts. By providing real-time visibility into service status and incident updates, Microsoft 365 Service Center fosters greater transparency and alignment across teams. The results are faster issue resolution and improved customer satisfaction.

## Optimize resource allocation with Azure status

Azure status optimizes resource allocation and prioritizes support efforts for Dynamics 365 apps by providing timely updates about Azure service health and incidents. Azure status offers real-time information about service disruptions, planned maintenance, and operational issues that affect Azure services, including underlying infrastructure that supports Dynamics 365 apps.

By monitoring Azure status updates and assessing their impact on Dynamics 365 app performance, support teams can prioritize resolution efforts, efficiently allocate resources, and minimize the impact of service disruptions on business operations. Additionally, Azure status offers historical data and insights into service reliability trends. Therefore, organizations can proactively identify areas for improvement and enhance overall service resilience.

### Stakeholders

Many people across the organization should contribute to the decision-making process and design of the *support systems* area. The following list provides examples of such stakeholders:

- **Executive leadership** stakeholders include chief executive officers (CEOs), chief financial officers (CFOs), and chief information officers (CIOs). Executive leaders provide strategic oversight to ensure that support systems are aligned with organizational goals and priorities.
- **IT management** stakeholders include CIOs, IT directors, and IT managers. IT management plays a pivotal role in identifying critical systems and data by selecting the appropriate support plans and tools to ensure the integration of IT resources with overall organizational support strategies.
- **System administrators** are responsible for configuring and maintaining the support system infrastructure. They collaborate with other stakeholders to ensure that support systems are properly integrated with existing IT infrastructure, meet security requirements, and adhere to compliance standards.
- **Technical support engineers** specialize in troubleshooting technical issues and providing solutions. Their expertise is crucial in designing support workflows, establishing escalation procedures, and implementing tools for effective incident resolution.
- **Change management team** professionals facilitate the adoption of new support systems by assessing the impact on users, effectively communicating changes, and addressing resistance to change. Their involvement is essential for ensuring a smooth transition and maximizing user acceptance of support system enhancements.
- **Quality assurance (QA) teams** ensure the reliability and performance of support systems by testing various scenarios, identifying potential issues, and validating the effectiveness of support procedures. Their feedback informs improvements to support processes and ensures a consistent user experience.
- **Business process owners** are responsible for defining and optimizing support processes so that they are aligned with organizational objectives. They collaborate with other stakeholders to identify areas for improvement, streamline workflows, and implement best practices for delivering efficient and effective support services.

### Define support systems process flow

The following diagram illustrates the *administer to operate* business process area.

:::image type="content" source="media/administer-to-operate-support-systems-overview-1.svg" alt-text="Business process area map showing the connection between the administer to operate business process area and other processes." lightbox="media/administer-to-operate-support-systems-overview-1.svg":::

[!INCLUDE [daf-business-process-flow-def](~/../shared-content/shared/guidance-includes/daf-business-process-flow-def.md)]

1. Start

    An unshown branch from Start connects to the Forecast to plan end-to-end process, which connects to Define strategic and operational plans, which also connects to 3. Establish support procedures and policies.

1. Administer to operate

    1. A parallel branch connects to uptake software releases.
    1. Define business continuity plan
    1. Monitor systems, environments, and capacity

    A, B, and C have parallel branches that connect to 3. Establish support procedures and policies.

1. Establish support procedures and policies

    A parallel branch connects to define business continuity plan, which is shown under the administer to operate business process area and also connects to 8. End.

1. Establish support subscription
1. Manage support incidents
1. Troubleshoot reported incidents and conduct root cause analysis, which connects to define business continuity plan and 8. End
1. Train users and increase adoption
1. End

## Establish support procedures and policies

Before you deploy Dynamics 365, you should define your support procedures and policies to ensure a smooth and consistent user experience. The following list describes some of the aspects that you should consider:

- Who will be responsible for providing support to your users, and how will those individuals be trained?
- What are the channels and tools that users can use to report issues and request assistance?
- What are the service level agreements (SLAs) and escalation paths for different types of issues?
- How will you document and communicate your support procedures and policies to your users and stakeholders?

## Establish a support subscription

To access the official Microsoft support for Dynamics 365, you must have a valid support subscription. Different types of support subscriptions are available, depending on your needs and budget. The following list describes some of the benefits of a support subscription:

- You can submit support requests online or by phone, and get a response within a specified time frame.
- You can access the [Microsoft Dynamics 365 Community](https://community.dynamics.com/), where you can find answers, tips, and best practices from other users and experts.
- You can access [Dynamics 365 content on the Microsoft Learn site](/dynamics365/), where you can find training courses, videos, and certifications to enhance your skills and knowledge.
<!-- Eva: Commenting out because I have no idea what has replaced that portal - You can access the Microsoft Dynamics 365 Update Portal, where you can find information about the latest updates, features, and fixes for Dynamics 365. -->

## Manage support incidents

When you encounter an issue with Dynamics 365, you should follow these steps to manage the support incident:

1. Try to troubleshoot the issue yourself by using the available resources, such as [the Dynamics 365 hub on Microsoft Learn](/dynamics365/) and [the Dynamics 365 Community](https://community.dynamics.com/)<!--, and the Dynamics 365 Learning Portal-->.
2. If you can't fix the issue yourself, submit a support request to Microsoft or your partner, depending on your support subscription and agreement. Provide as much detail as possible about the issue, such as the error message, the steps that are needed to reproduce it, the impact, and the urgency.
3. Monitor the status of your support request, and communicate with the support engineer who is assigned to your case. Provide any additional information or feedback as requested.
4. After the issue is fixed, close the support request, and evaluate the support experience. Provide feedback to Microsoft or your partner about how they can improve their support service.

Learn more at [Get support for your Dynamics 365 product](/dynamics365/get-started/support/).  

### Troubleshoot reported incidents and conduct root cause analysis

After you resolve a support incident, you should conduct root cause analysis to identify the underlying cause of the issue and prevent it from recurring. The following list describes some of the steps that you should take:

- Analyze the symptoms and the resolution of the issue. What was the issue, and how was it fixed?
- Identify the factors that contributed to the issue. What were the triggers, conditions, and dependencies that caused it?
- Determine the corrective and preventive actions that will help you avoid the issue in the future. What are the changes, improvements, or recommendations that you can implement to prevent the issue from happening again?
- Document and share your findings and actions with your users and stakeholders. How will you communicate the lessons learned and the best practices from the issue?

These benefits highlight the synergy between Dynamics 365, Azure, and effective business continuity planning. They emphasize the tangible advantages of using Microsoft's cloud services for a resilient and responsive organizational infrastructure.

## Next steps

If you want to implement Dynamics 365 solutions to assist with your *administer to operate* business processes, you can use the following resources and steps to learn more. (Links are added when the articles are ready.)

1. [Implement solutions overview](administer-to-operate-implement-solutions.md)  
1. [Define business continuity plan](administer-to-operate-define-business-continuity-plan-overview.md)  
1. *Manage licensing and entitlements*  
1. [Administer system features](administer-to-operate-administer-system-features.md)  
1. [Manage system access and security](administer-to-operate-manage-system-access-security.md)  
1. [Train users and increase adoption](administer-to-operate-train-users-increase-adoption-overview.md)  
1. *Monitor systems, environments, and capacity*  
1. *Manage background jobs*  
1. *Manage notifications alerts*  
1. *Uptake software releases*  
1. [Manage data](administer-to-operate-manage-data-synchronization-overview.md)  
1. [Manage system compliance](administer-to-operate-manage-system-compliance.md)  
1. *Support systems* (the article you're currently reading.)  

    1. *Establish support procedures and policies*  
    1. *Establish support subscription*  
    1. *Develop support transition strategy*  
    1. *Manage support incidents*  
    1. *Troubleshoot reported incidents*  
    1. *Conduct root cause analysis*  

## Related information

You can use the following resources to learn more about the *support systems* processes with Dynamics 365.

- [Get support for your Dynamics 365 product](/dynamics365/get-started/support)
- [Help us help you](/dynamics365/get-started/support/support-scope)
- [Monitoring and diagnostics tools in Lifecycle Services (LCS)](/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/monitoring-diagnostics)
- [Monitoring and telemetry using Application Insights](/dynamics365/fin-ops-core/dev-itpro/sysadmin/monitoring-and-telemetry-appinsights)
- [Analyze model-driven apps and Dataverse telemetry with Application Insights](/power-platform/admin/analyze-telemetry)
- [Azure status](https://azure.status.microsoft/status)
- [Environment Telemetry in the Business Central administration center](/dynamics365/business-central/dev-itpro/administration/tenant-admin-center-telemetry)

<!--## Tags

*Industries:* Agriculture (01-09), Mining (10-14), Construction (15-17), Manufacturing (20-39), Transportation and Public Utilities (40-49), Wholesale Trade (50-51), Retail Trade (52-59), Finance, Insurance, Real Estate (60-67), Services (70-89), Public Administration (91-99)

*Stakeholders:* Administrative, Audit, Human Resources, IT, Operations, Production,

*Products:* Dynamics 365 -->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [Haytham Said](https://www.linkedin.com/in/haytham-said-9016a312/) \| Senior Program Manager

Other contributors:

- [Rachel Profitt](https://www.linkedin.com/in/RachelProfitt/) \| Principal Program Manager
