---
title: TechTalk Service, support, and maintain Dynamics 365 apps 
description: Summary of TechTalk video that talks about how to manage and maintain the Dynamics 365 apps in your business solution.
ms.date: 11/07/2024
ms.topic: conceptual
author: edupont04
ms.author: edupont
ai-usage: ai-assisted
---

# TechTalk: Service, support, and maintain Dynamics 365 apps

The management of the Dynamics 365 apps that are part of a business solution is a complex task that requires a blend of both proactive measures and efficient reactive processes. To ensure smooth functionality and longevity of these apps, it's essential to maintain a robust system for servicing, supporting, and maintaining them. Understanding the intricacies of these elements allow users to achieve optimal performance from their Dynamics 365 apps while minimizing operational risks.

We based this article on [a TechTalk](https://youtu.be/VBvdj7yd_7c) that you can find online in the Dynamics 365 channel on YouTube.  

:::image type="content" source="media/service-support-slide.svg" alt-text="Thumbnail of the first slide in the presentation." link="https://youtu.be/VBvdj7yd_7c":::

> [!TIP]
> The TechTalk session was about finance and operations apps, but this article reflects that the general guidance applies to all solutions with Dynamics 365 apps.

## Servicing Dynamics 365 apps

Servicing Dynamics 365 involves ensuring that the infrastructure, platform, and standard solutions are all kept in a healthy state. Microsoft provides monitoring services around the clock, ensuring that production instances are running smoothly. However, servicing Dynamics 365 isn't solely Microsoft's responsibility. Our customers and implementation partners play a crucial role, particularly when it comes to aspects like identity configuration, user data security, and customization.

The following image outlines the service activity responsibilities within a business solution. It has several segments managed by Microsoft and its implementation partners.

:::image type="content" source="media/service-support-responsibilities.svg" alt-text="Screenshot of a slide with a picture of a circular diagram that is divided into three main segments of ownership that are explained after the image." lightbox="media/service-support-responsibilities.svg":::

Microsoft is responsible for the infrastructure and the application platform with the standard capabilities. Microsoft's customer, meaning the organization that owns the solution, and their implementation partner must manage business processes, including and test thoroughly before deploying new updates. This shared responsibility ensures that both sides can work together to keep systems healthy.

To manage environments, admin centers such as Power Platform admin center and Dynamics 365 Lifecycle Services (LCS) serve as collaboration portals. They're used throughout the onboarding and implementation phases, and later in live environments for monitoring and servicing. Whether deploying new environments, handling database movement operations, or applying package updates, Microsoft provides a suite of self-service actions that streamline many routine servicing tasks. However, for some specific actions that still require manual intervention, you might have to submit support tickets to escalate the process to Microsoft.

Learn more about service responsibilities at [Get support for your Dynamics 365 product](/dynamics365/get-started/support/) and [Help us help you](/dynamics365/get-started/support/support-scope).

## Supporting Dynamics 365 apps

For support, partners and internal teams serve as the first line of defense before reaching out to Microsoft. Business users have access to several channels of support, such as in-app task guides, admin centers, and the content on the [Microsoft Learn](/dynamics365/) site with extensive information about updates, features, and known issues.

Solutions with finance and operations apps use LCS for managing support cases and outages. Power Platform admin center has more tools for all Dynamics 365 apps. Also, the [Microsoft Learn training portal](/training/) provides self-paced training modules to help teams improve their knowledge of Dynamics 365, allowing them to handle minor issues internally. TechTalk sessions and community forums also serve as valuable resources for users looking to stay updated on product news or troubleshoot common issues.

For businesses with more critical support needs, Microsoft offers subscription-based support services, including professional and unified support contracts. These contracts provide more advanced performance monitoring and proactive services, including dedicated customer success managers to assist with complex issues.

Users must ensure they provide detailed information when submitting support tickets, such as the environment where the issue occurred, reproduction steps, and business impact. The more accurate and detailed the information, the faster Microsoft or the partner can resolve the issue.

Find detailed guidance on support contracts at the [Support for business](https://support.serviceshub.microsoft.com/supportforbusiness) website.

## Maintaining Dynamics 365 apps

Maintaining Dynamics 365 apps is a continuous process that involves regular monitoring and diagnostics to ensure everything runs smoothly. Admin centers offer various monitoring functionalities, including activity load analysis, SQL insights, and live views of executing and blocking statements. These features help administrators keep track of system performance, troubleshoot bottlenecks, and ensure that critical business processes are operating as intended.

It's equally important to ensure regular data maintenance. Microsoft provides built-in cleanup routines that help maintain system performance by removing obsolete data, such as batch job history and staging tables. Businesses can customize these routines to meet their specific needs. However, not all data can be deleted. Larger organizations might want to archive data. They can then use Dataverse data archival and Azure Data Lake to store data that is no longer actively used but still needs to be retained for compliance or future reference.

The following image shows a flowchart depicting the process of adjusting Application Lifecycle Management (ALM)  for emergency patching.

:::image type="content" source="media/service-support-adjust-alm.svg" alt-text="Screenshot of a slide with a flowchart depicting the process of adjusting Application Lifecycle Management A L M for emergency situations." lightbox="media/service-support-adjust-alm.svg":::

As more Dynamics 365 apps run on Dataverse, it's essential to use tools such as the Power Platform admin center to monitor telemetry, especially for environments with dual-write enabled. The use of telemetry helps a smooth flow of data between finance and operations apps and Power Platform, minimizing any disruptions in functionality.

Learn more about monitoring and maintaining systems in the [Power Platform admin documentation](/power-platform/admin).

## Staying current with updates

Keeping Dynamics 365 apps current is essential to ensure they're running optimally and to avoid potential issues. Microsoft releases eight updates per year, and while customers can choose to pause updates, they should do so sparingly. Staying on the current or previous version of the software helps make sure Microsoft's support team can address any issues promptly.

If you invest in automated regression testing tools as part of the implementation project, such as the Regression Suite Automation Tool (RSAT), it can greatly reduce the time and effort required for testing updates. This way, businesses can apply updates without the fear of disrupting their critical business processes, helping to keep the system healthy and functioning at its best.

Learn more on how to stay current with updates at [Continuous delivery home page](/dynamics365/fin-ops-core/dev-itpro/dev-tools/continuous-delivery-home-page).

## Conclusion

Effective servicing, supporting, and maintaining of Dynamics 365 apps involve a joint effort between Microsoft and its customers. By using the appropriate tools and resources, staying current with updates, and understanding your responsibilities, businesses can ensure their solutions with Dynamics 365 apps run smoothly, remain secure, and are supported effectively.

Learn more at the [Dynamics 365 community](https://community.dynamics.com/) website.  

### Related resources

You can use the following resources to learn more about Dynamics 365.

- [Service description for finance and operations apps](/dynamics365/fin-ops-core/dev-itpro/get-started/service-description#service-activity-responsibilities)
- [Understanding the infrastructure of Business Central online](/dynamics365/business-central/dev-itpro/administration/tenant-environment-topology)  
- [Technical support for Dynamics 365 Business Central](/dynamics365/business-central/dev-itpro/technical-support)  
- [Get Help + Support in Power Platform admin center](/power-platform/admin/get-help-support)  
- [Support for Microsoft Power Platform and Dynamics 365 apps](/power-platform/admin/support-overview)  
- [What are the Dynamics 365 TechTalk videos?](../roles/techtalk-videos.md)
- [TechTalk on the Dynamics Community website](https://community.dynamics.com/videos/)
- [Dynamics 365 channel on YouTube](https://www.youtube.com/channel/UC5QxCcXhFFixs1nfmOpJlvQ)
