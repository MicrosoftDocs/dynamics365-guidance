---
title: Monitor and optimize your Dynamics 365 environments
description: Learn how to monitor your Dynamics 365 environments for optimal performance, security, cost, and supportability with Microsoft tools.
author: taksatoms
ms.author: tsato
ms.date: 06/05/2024
ms.topic: conceptual
ms.custom:
 - ai-seo-date: 01/30/2024
 - ai-gen-docs-bap
 - ai-gen-title
 - ai-gen-desc
content_well_notification: AI-contribution
---

# Monitor and optimize your Dynamics 365 environments

To succeed with Dynamics 365, you need to know how healthy your environments are always. You also need to troubleshoot issues quickly and proactively.

You might wonder why you need to monitor your system, since Microsoft rigorously tests Dynamics 365 and Power Platform. The answer is that every implementation has unique usage patterns and customizations that can affect the system's performance, security, cost, and supportability.

For example, you might have:

- Added new fields, forms, logic, or integrations that affect performance.
- More concurrent users or data than usual that increase storage and operational costs.
- Regulatory or compliance requirements that affect how you handle customer data.
- Business intelligence needs that require you to analyze usage patterns and improve processes.

Microsoft provides you with various tools to monitor your system's health and alert you when something goes wrong. This article covers the key areas that you should monitor in your solution:

- Performance
- Licensing and operational cost
- Storage allocation and usage
- API request and service protection
- Security and privacy
- User access and resource usage
- Application logs and errors
- Messages from Microsoft

## Monitor performance

Performance is how fast your system responds to user actions. Poor performance can affect your business efficiency and user adoption.

You should test your system's performance before you deploy it in production. You can use performance testing to measure the impact of your customizations and set a baseline for comparison.

You should also monitor your system's performance in production. Many factors that aren't related to the performance of the Dynamics 365 application itself can influence performance in live production scenarios:

- Network traffic can vary throughout the day, and remote workers who rely on individual Internet connections can have different response times.
- Integrations with other systems might have different response times than in your test environment.
- Workflows and back-office jobs might be running, which can stress the system.

To monitor performance, you need to collect and analyze data from different sources. You can use tools such as:

- [Lifecycle Services)](/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/monitoring-diagnostics) for finance and operations apps
- [Dataverse analytics](/power-platform/admin/analytics-common-data-service) for customer engagement apps and Dataverse
- [Azure Application Insights](/azure/azure-monitor/app/app-insights-overview)

You can set up notifications to warn you when your system's performance falls below a certain range. This way, you can troubleshoot and fix issues faster. [Learn more about performance strategy](performing-solution.md).

## Monitor licensing and operational cost

You should keep track of the licenses that you have and use so that you can plan ahead and adjust your purchasing as needed.

You should also keep track of the operational cost, which depends on your usage volume. Staying aware of changes in your organization's use of the system can help business and IT managers make budget decisions based on usage patterns.

### Related resources

Learn more about monitor licensing and operational costs with the following resources:

- [Review Dynamics 365 licensing requirements](https://go.microsoft.com/fwlink/?LinkId=866544&clcid=0x409)

- [Manage your subscription for customer engagement apps and Power Platform in the Microsoft 365 admin center](/power-platform/admin/use-office-365-admin-center-manage-subscription)

- [Stay compliant with user licensing requirements for finance and operations apps](/dynamics365/fin-ops-core/dev-itpro/sysadmin/stay-compliant-user-license-requirement)

- [View independent software vendor (ISV) license status](/dynamics365/fin-ops-core/dev-itpro/sysadmin/view-isv-license-status)

## Monitor storage allocation and usage

Storage allocation and usage are how much space you have and use for your data. You start with a minimum amount of storage space for your environment. You can add more data as your business grows.

You should be aware of how much storage space you have left and how fast it grows. You can budget for extra storage or free up space by archiving or deleting data. You can also schedule and clean up data regularly.

Different types of data, such as transactions, files, and logs, have different allocations depending on your subscription. Some actions, such as copying and restoring environments, can also affect your storage allocation.

### Related resources

Learn more about monitoring storage allocation with the following resources:

- [Understand and apply the change management discipline effectively and successfully](data-management.md)

- [Verify your Dataverse storage capacity entitlements and usage](/power-platform/admin/capacity-storage)

## Monitor API request and service protection

One of the benefits of using a cloud solution is that it can scale up or down based on your usage. However, to ensure consistent availability and performance for everyone, Microsoft limits how much you can use the APIs that connect your solution to other systems. These limits prevent overuse of resources that can slow down or stop the system.

You should monitor how much you use the APIs and avoid hitting the limits. If you reach a limit, the service might throttle or block your API calls. You can see these errors in your logs when this happens.

You should design your system to use the APIs efficiently and set priorities for different scenarios. For example, you can:

- Use batch operations to group multiple requests into one.
- Use change tracking to get only the data that has changed since the last request.
- Use alternate keys to identify records without querying the database.
- Use asynchronous operations to run tasks in the background without waiting for a response.

To monitor API request and service protection, you can use tools such as:

- [Lifecycle Services](/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/monitoring-diagnostics) for finance and operations apps

    Lifecycle Services also lets you [configure priorities for integrations](/dynamics365/fin-ops-core/dev-itpro/data-entities/priority-based-throttling#configure-priorities-for-integrations).

- [Dataverse analytics](/power-platform/admin/analytics-common-data-service) for customer engagement apps and Dataverse

[Review the service protection API limits](/powerapps/developer/data-platform/api-limits) and learn how to maximize throughput.

## Monitor security and privacy

You should have a security policy that defines who can access your system and what they can do with it. You should also have a compliance policy that meets any regulatory or legal requirements for your industry or region.

You should monitor who is accessing your system and what they're doing with your data. As part of user management, you should also audit user actions and respond to data subject requests (DSRs).

For instance, when an employee changes roles or leaves the company, you need to change or remove their security role and permissions. If a vendor or consultant contract ends, you need to revoke their access to the data they were working with. And if a customer asks to access, modify, or delete their personal data, you need to comply with their request and provide reports.

### Related resources

Learn more about monitor security and privacy with the following resources:

- [Monitor, investigate, and respond to threats with Microsoft 365 security](/microsoft-365/security/).

- [Manage data governance, risk, and compliance in the Microsoft Purview compliance portal](/microsoft-365/compliance/microsoft-365-compliance-center).

- [Identify and troubleshoot service issues in Microsoft 365 service health](/microsoft-365/enterprise/view-service-health).

- [Learn more about security strategy and planning for Dynamics 365](security.md).

## Monitor user access and resource usage

You should understand your users' behavior and expectations. Business sponsors want to know who is using (and not using) the system. They also want to know the frequency of business processes and use cases that are being run. Data on usage patterns gives you clear insights to user adoption, and you can take proven actions to improve it. For example, if a certain capability isn't being used much, query the users to get their feedback on it.

You can also use this information to estimate license needs. For example, you can reassign licenses from users who rarely access the system to new users.

To monitor API request and service protection, you can use tools such as:

- [Lifecycle Services](/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/monitoring-diagnostics) for finance and operations apps

    Lifecycle Services also lets you [configure priorities for integrations](/dynamics365/fin-ops-core/dev-itpro/data-entities/priority-based-throttling#configure-priorities-for-integrations).

- [Dataverse analytics](/power-platform/admin/analytics-common-data-service) for customer engagement apps and Dataverse

- [Azure Application Insights](/azure/azure-monitor/app/app-insights-overview)

## Monitor application logs and errors

You should check your system logs regularly for any issues that might affect your system's health. You should also set up alerts to notify you when something goes wrong.

You can use tools such as:

- [Monitoring and diagnostic tools in Lifecycle Services](/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/monitoring-diagnostics) for finance and operations apps

- [Performance tuning](/power-platform/admin/performance-tuning-and-optimization) for customer engagement apps

- [Trace logging](/powerapps/developer/data-platform/logging-tracing) in Dataverse for plug-in error information

- [Azure Application Insights](/azure/azure-monitor/app/app-insights-overview)

- [Identify and troubleshoot service issues in Microsoft 365 service health](/microsoft-365/enterprise/view-service-health).

## Monitor messages from Microsoft

Messages from Microsoft give you information about the health, updates, and features of your service. You should check the [Microsoft 365 Message center](/microsoft-365/admin/manage/message-center?view=o365-worldwide&preserve-view=true) frequently for new messages. You can set your preferences to receive emails or use the mobile app. You should also give access to the message center to other team members who manage Microsoft services.

## Next steps

- Review how [service updates](service-solution-service-updates.md) work in Dynamics 365 and best practices for readiness
- Learn about the importance of [environment maintenance](service-solution-environment-maintenance.md)
- Find more resources to [continue the business application journey](service-solution-continue-the-business-application-journey.md)
- Read the [case study](service-solution-case-study.md) to understand the impact to an organization when servicing the solution isn't top of mind