---
title: Monitor the health of your environments to keep system performances at optimal levels
description: Learn the importance of monitoring various aspects of the health of your Dynamics 365 services to ensure a healthy system. Be proactive to address any potential issues through monitoring.
author: taksatoms
ms.author: tsato
ms.date: 03/31/2023
ms.topic: conceptual

---

# Monitor the health of your environments to keep system performances at optimal levels

A key principle for a successful onboarding experience to Dynamics 365 is knowing the health of your environments always. Your team must be able to troubleshoot issues right away.

Dynamics 365 and the Power Platform have gone through rigorous testing, so why do customers need to check that it's running smoothly? It's because of each organization's unique usage patterns and the extensibility of the platform.

Just about every implementation contains customizations to their Dynamics 365 environment. It can be small changes, such as adding new fields and forms. Maybe your business requires heavy customizations with complex logic or performance-impacting integrations with other systems. Or maybe your organization has more concurrent users than the typical use case, so data management needs are also growing at a rapid pace.

Another reason to monitor your system is to understand usage patterns for better business intelligence. Through this analysis, business stakeholders can pinpoint where to invest and prioritize improvements and focus areas for training.

Microsoft highly recommends monitoring service health and provides you with the tools to do so. That way, you know when irregularities are found and action is needed.

As administrators and power users of Dynamics 365, you can focus on several key areas when monitoring usage. These areas impact performance, security, cost, and supportability, all central to keeping the system performance at optimal levels.

This article addresses key areas for monitoring the solution:

- Performance monitoring

- Licensing and operational cost

- Storage allocation and usage

- API request and service protection

- Security and privacy

- User access and resource usage

- Application logs and errors

- Messages from Microsoft

## Performance monitoring

Microsoft recommends that Dynamics 365 project teams consider adding performance testing to the project's test cycle. Performance testing is an effective way to gauge the impact that your customizations may have on the baseline Dynamics 365 solution.

Performance testing is typically conducted in a simulated environment. It provides insight into changes in solution design or configuration prior to production rollout at scale. By conducting performance testing early, Dynamics 365 administrators have a baseline performance expectation of the new system that can be used as comparison over time.

Many factors can influence how performance is affected in live production scenarios:

- Integrations with other production systems have fluctuating response times that are different than in the simulated tests

- Workflows such as back-office jobs could be running, which stresses the systems

- The network traffic can vary throughout the day depending on an organization's usage patterns

- For remote workers, reliance on individual internet connections could cause different outcomes for each user

Ultimately, the responsiveness that user experience comes from a mix of multiple factors that aren't limited to the performance of the Dynamics 365 application itself.

To understand the performance impact in these scenarios, proper end-to-end logging and collection of telemetry is required. You get a complete picture of how long each step of the pipeline takes to complete. This information can reduce the time required to triage and fix any issues.

As this data is collected, monitor the performance of the solution and set up notifications to warn you when performance of any aspect of the solution varies from a defined range.

A solution that performs poorly can affect the operational efficiency of a business and create barriers to user adoption. But you can stay ahead of such issues through proper monitoring and alerts.

> [!NOTE]
> The article [A performing solution, beyond infrastructure](performing-solution.md) covers the importance of having a performance strategy that includes elements such as defining performance requirements, establishing baseline metrics, and ongoing performance testing.

> [!NOTE]
> You can use many different tools to monitor performance. For finance and operations apps, [Lifecycle Services (LCS)](/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/monitoring-diagnostics) is the first place to go for performance monitoring. Also, tools such as the Optimization advisor suggest best practices for module configuration and identifies business data that is obsolete or incorrect. 

> [!NOTE]
> For customer engagement apps and Dataverse, wide breadth of your organization's metrics is available in [Dataverse analytics](/power-platform/admin/analytics-common-data-service). With it you can gauge and monitor performance from within the Power Platform Admin center. Organizations are also encouraged to regularly use the Solution Checker to identify customization issues and get links to recommended resolutions.  

> [!NOTE]
> You can also use extensions such as [Azure Application Insights](/azure/azure-monitor/app/app-insights-overview) to monitor applications like Dynamics 365 for custom telemetry needs.

## Licensing and operational cost

As your solution matures and new users are onboarded, it becomes more important to keep track of the licenses used. Insight on the number of available licenses will help you plan ahead and adjust your purchasing as needed.

Another aspect is the operational cost. With solutions that include cloud computing, usage volume heavily impacts this expense. Staying aware of any changes in your organization's usage will help business and IT managers make key budget decisions.

> [!NOTE]
> [Stay compliant with user licensing requirements](/dynamics365/fin-ops-core/dev-itpro/sysadmin/stay-compliant-user-license-requirement) and view the [independent software vendor (ISV)](/dynamics365/fin-ops-core/dev-itpro/sysadmin/view-isv-license-status) license status for finance and operations apps for more information.

> [!NOTE]
> Review the [business subscriptions and billing documentation](/microsoft-365/commerce/?view=o365-worldwide&preserve-view=true) for Microsoft 365 and the [Microsoft 365 admin center to manage your subscription](/power-platform/admin/use-office-365-admin-center-manage-subscription) for customer engagement apps and Power Platform.

> [!TIP]
> The [Dynamics 365 Licensing Guide](https://go.microsoft.com/fwlink/?LinkId=866544&clcid=0x409) provides details on licensing requirements.

## Storage allocation and usage

With a Dynamics 365 subscription, you start with a set minimum amount of storage space for your environment.

Depending on your needs, you can add more data to suit your business size and expected growth.

Administrators must be mindful of the amount of storage that is available for the organization's subscription as usage grows. Different data classifications (such as transactions, files, and logs) have different allocations depending on your subscription.

Users and integrations aren't the only cause of storage growth. Logs from system jobs, indexes created to help performance, and more application data added from new modules also contribute to storage growth. Another scenario that impacts storage allocation is in the copy and restore operations of an environment. Depending on the type of copy, the size of the database can be different. As an administrator, you need to be mindful of who can create new instances and what their true needs are to minimize impact on the storage allocation as these copies are being restored.

Administrators should monitor the volume of storage that is currently used as well as its growth rate. This information will help you budget for any extra storage needs or look into data archiving and deletion to free up space. Scheduling and cleaning up data from time to time will help as well. Learn more at [Environment maintenance](service-solution-environment-maintenance.md).

> [!IMPORTANT]
> Refer to the article [Data management](data-management.md) for details on storage entitlements, segmentation, and impact to allocations when backing up and restoring instances.

> [!NOTE]
> For information on storage capacity for finance and operations apps, see the Dynamics 365 Licensing Guide. Note that [Dataverse storage capacity entitlements and usage changed in 2019](/power-platform/admin/capacity-storage). This resource also provides instructions on verifying your storage capacity and usage.

## API request and service protection

One of the advantages of choosing a cloud solution over on-premises software is that your application is scalable. Among other things, you can adjust the amount of processing and memory resources based on the usage. But to provide consistent availability and performance for everyone, Microsoft monitors and applies some limits to how APIs are used. These limits are designed to detect when client applications are making extraordinary demands on server resources.

The intent is to prevent over-utilization of resources to preserve the system's responsiveness and performance for environments running Dynamics 365. When an API limit is hit, the service may be throttled or even prevent API calls from running. Error logging shows you when these limits are exceeded.

As an admin, you can pull historical telemetry reports to see if any areas of the application are at risk of hitting these limits. Then, work with the implementation team to make appropriate design changes. Or better yet, use tools like Azure Application Insights to set thresholds on these API calls. This way, the admin is notified before the limit is reached, so that they can mitigate the risk of throttling or being shut down.

> [!NOTE]
> For finance and operations apps, use LCS to monitor API usage. For more information, review [priority-based throttling and how to configure priorities](/dynamics365/fin-ops-core/dev-itpro/data-entities/priority-based-throttling#configure-priorities-for-integrations) for special circumstances such as integrations.

> [!NOTE]
> For customer engagement apps, use the Dataverse analytics available in the Power Platform Admin center. Refer to the [service protection API limits](/powerapps/developer/data-platform/api-limits) and the ways to maximize throughput to avoid hitting these limits.

## Security and privacy

From a security perspective, you want to prevent unwanted access to your system, applications, and data. The unified Microsoft 365 security center combines protection, detection, investigation, and response to threats for your Dynamics 365 system, all in a central portal.

At the solution level, you need strategic planning to create a robust security policy that can be implemented during deployment. As the administrator who services this solution, you must also monitor and act upon other aspects of security.

Take a scenario in which an employee changes roles or leaves the company. You need a process to change the security role and permissions for that user. When a vendor is granted access to a system as a consultant, they often continue to have access to it even when they're no longer working with the company. Microsoft recommends that you have a process to address these scenarios.

"Who has access to my customer data?" may seem like a simple question, but as the number of users and system usage grows, it can be daunting to keep track. You need to be able to identify who is accessing the system and what they're doing with the data.

Depending on the industry or the region of the organization, you may also have regulatory or compliance-related requirements. You might need to provide reports about customer data handling or delete customer data upon request.

Microsoft recommends that you have a proper auditing strategy to capture the information needed to track user actions so that you can satisfy these types of requests. Most common areas are covered by Dynamics 365. Because auditing takes up more storage and potentially impacts performance, administrators need to turn some of these capabilities on where they may not be by default.

> [!TIP]
> Refer to the article [Security](security.md) for details on security strategy and planning. Review the Microsoft security portals and admin centers overview and the Microsoft 365 compliance center overview for more details. The Microsoft 365 security center provides the ability to search through Dataverse activity logging for customer engagement apps.

> [!NOTE]
> Your organization may be subject to rules that give users specific rights to their personal data. You may need to respond to [data subject requests](https://servicetrust.microsoft.com/ViewPage/GDPRDSR) (DSRs) to delete a user's personal data.

## User access and resource usage

For any application or solution, it's important to understand your organization's resource usage patterns. Business sponsors want to know who is using (and not using) the system. They'll also want to know the frequency of business processes and use cases that are being run.

Telemetry on usage patterns gives you clear insights to user adoption, and you can take proven actions to improve adoption. For example, if a certain capability isn't being used much, query the users to get their feedback on it. By using telemetry to identify the areas that are most important to the user group, the project team can work with business sponsors to prioritize features.

> [!TIP]
> Monitoring and Diagnostic tools in LCS provide telemetry for usage patterns for finance and operations apps.

> [!TIP]
> Microsoft Dataverse analytics provides user access and usage pattern telemetry for customer engagement apps and the Power Platform.

You can also use this information when estimating license needs. For example, some licenses may be assigned to users who rarely access the system; you can reassign the licenses to someone new. Insights provided by the telemetry are readily available in Dynamics 365. Use this data to help improve business processes and allocate resources in the right areas to maximize your investment.

The platform is constantly adding functionality to the standard usage reports. If you have any gaps between your needs and these options, you can tailor tools such as Azure Application Insights to your usage pattern tracking requirements. By using reporting and analytics tools such as Power BI, organizations can create reports based on custom usage tracking needs.

## Application logs and errors

Typically, system errors are found by users who report issues through an IT service management (ITSM) process. But you may have unreported issues that can only be found in the application logs.

Turning to notifications and application logs to proactively look for entries is a good way to find trouble spots and address them before they impact users.

You can use tools such as Azure Application Insights for Dynamics 365 and other applications and services that are part of the overall IT solution for your organization. Application Insights lets you collect telemetry both in and outside of Dynamics 365.

For example, if a user in Dynamics 365 initiates a process that calls on an integrated, but external system, Application Insights can still detect performance and exceptions at different stages of the execution pipeline. You can see these issues whether they occur at the user interface level, in Dynamics 365, or the external system. The admin monitors alerts to react quickly the moment the exceptions surface. They also have immediate access to information on the source of the issue.

> [!IMPORTANT]
> Monitoring and Diagnostic tools in LCS allow administrators to monitor and query logs for issues detected in the system for finance and operations apps.

> [!IMPORTANT]
> For customer engagement apps, Performance Insights in the Power Platform Admin center analyzes runtime user data and provides a prioritized list of recommendations to help improve performance of model-driven apps. [Trace logging](/powerapps/developer/data-platform/logging-tracing) in Dataverse provides plugin error information for customer engagement apps and the Power Platform.

> [!TIP]
> You can also use [Microsoft 365 service health](/microsoft-365/enterprise/view-service-health) to identify service issues, and administrators can be notified via email or through the mobile app.

## Messages from Microsoft

Microsoft provides ample information about the health of your service, upcoming release information, service exceptions and interruptions, and other important details. The [Microsoft 365 Message center](/microsoft-365/admin/manage/message-center?view=o365-worldwide&preserve-view=true) is the central location for technical and licensing communications with our customers. As an administrator of your solution, the message center is an important area to frequently check for new messages.

Typically, organizations have multiple people who manage Microsoft services. You may want to provide appropriate team members with access to these messages.

You can also configure your preferences on receiving emails. A mobile app is available to manage these communications.

As we've described, it's key to know when to act by having the information needed to understand the health of your system. Multiple tools are available to monitor your solution, which can feel daunting. But with tools to alert administrators when services are running less than optimal, the task will be much more manageable.

Key alerts you can receive from Microsoft include the service updates to your Dynamics 365 solution. In the next section, we discuss when and how Dynamics 365 is updated and what you can do as an administrator to take advantage of the predictable nature of the service updates.

## Next steps

- Understand the importance to service the solution by reviewing the [overview](service-solution.md)
- Review how [Service Updates](service-solution-service-updates.md) work in Dynamics 365 and best practices for readiness  
- Learn about the importance of [environment maintenance](service-solution-environment-maintenance.md)
- Find more resources to [continue the business application journey](service-solution-continue-the-business-application-journey.md)
- Read the [case study](service-solution-case-study.md) to understand the impact to an organization when servicing the solution isn't top of mind