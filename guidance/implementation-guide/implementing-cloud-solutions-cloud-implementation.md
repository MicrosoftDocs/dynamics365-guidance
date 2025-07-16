---

title: Cloud implementation considerations for implementation projects
description: Before you start a cloud implementation project, learn how Dynamics 365 can help you with security, scalability, performance, data isolation, limits, and capacity.
author: taksatoms
ms.author: edupont
ms.date: 01/10/2024
ms.update-cycle: 1095-days
ms.topic: concept-article
ms.custom:
  - evergreen
  - ai-seo-date: 01/10/2024
  - ai-gen-docs-bap
  - ai-gen-title
  - ai-gen-desc
content_well_notification: AI-contribution
ai-usage: ai-assisted
---

# Cloud implementation considerations and how they apply to implementation projects

Cloud solutions like Dynamics 365 can help you reduce management overhead and deliver business value faster by focusing on the application layer. But you still need to consider some fundamental aspects of online applications, such as security, scalability, performance, data isolation, limits, and capacity. These aspects might differ from an on-premises deployment. This article explains some of these differences and how to plan for them.

> [!TIP]
> Dynamics 365 integrates with Azure DevOps and [build tools](/power-platform/alm/devops-build-tools) to help you [automate your deployment pipeline](/dynamics365/fin-ops-core/dev-itpro/dev-tools/hosted-build-automation) and manage the application lifecycle effectively.

## Prepare for security in the cloud

Security in cloud solutions is a shared responsibility between the service provider and the customer. That means your existing security policies might not suit the cloud environment. The service provider handles the back-end infrastructure and data encryption, while the customer controls access to environments and application data.

Your IT security team should understand these boundaries and meet these goals:

- The service provider meets your organizational security, privacy, and compliance requirements. You should verify this before using the platform and review it regularly.
- The security team knows how to configure and manage access to data and environments. For example, you might need to define data loss prevention policies, access control policies, and environment management policies.
- The governance process ensures that the application-level security requirements are met. The application teams should follow the business requirements for each app deployment and check for compliance before deployment.

For instance, the service might comply with the data processor regulations, but you still need to implement data controller processes, such as deleting personal data or managing marketing consent.

You should review your security policies and make sure they're cloud-ready before the app deployment cycle. You should also work closely with your cloud software as a service (SaaS) provider to meet your security needs. Microsoft publishes the details of how we secure data on the [Microsoft Trust Center](https://www.microsoft.com/trust-center). There, you can find our security and privacy policies, as well as the certificates of compliance for various standards and regulations.

## Scale your cloud solution

The scalability of the SaaS platform is another key factor for business applications. You want to be able to scale out and scale up to support seasonal workloads or spikes in user activity, which can affect the user experience and the effectiveness of business processes.

The cloud scalability parameters in SaaS are different from a traditional on-premises system. Instead of adding more servers or increasing the power of machines, these parameters could be translated as available API capacity. You shouldn't assume that the cloud has infinite scale and computing power. You still need to follow the best practices for coding and design, but you might need to adapt them to the cloud. Although managing and scaling cloud services is complex, you can adjust your data storage, processing power, and networking requirements easily. In many cases, you can do this automatically or with simple configuration changes. The microservices architecture, including capacity-based routing and storage management, is transparent to Microsoft customers. The SaaS cloud lets you scale horizontally and vertically to support thousands of concurrent users. By adopting the capacity-based model for resource consumption, you can build optimized applications and plan your operating costs better.

## Optimize your performance

Many factors can affect the performance of your application, such as network latency, user device and browser, application design, configuration, data composition, and customizations. Cloud services are scalable, have vast compute power, and are available from multiple locations. But that doesn't guarantee performance if the solution is poorly designed, or if users access the service from slow networks.

Research shows that a few milliseconds of latency can cause a significant drop in page load times. For e-commerce companies, this can mean a loss of user attention and sales revenue. Low latency isn't just good, it's crucial for your brand and reputation. The same applies to back-office business applications in the cloud. User experience and productivity can suffer in a high-latency environment.

Your cloud applications run on hundreds of virtualized hardware pieces in Azure datacenters around the world. A critical decision you must make is which datacenter to use for your application, so that all users get a reasonable level of latency. Learn more in [Environment Strategy](environment-strategy-overview.md).

One option for more reliable and secure networks is to use a private connection. Cloud providers offer dedicated channels, such as [Azure ExpressRoute](https://azure.microsoft.com/services/expressroute/). These connections can provide more reliability, consistent latencies, and higher security than typical Internet connections.

Performance can also suffer because of a poorly designed application. Three scenarios are common:

- You customize Dynamics 365 with code changes  
- You deploy custom applications in a platform as a service (PaaS) environment  
- You deploy custom applications in an infrastructure as a service (IaaS) environment  

In these cases, your team should design a high-performing application and test it properly before deploying it to production.

Performance not only influences the user experience and adoption. It can also affect your business goals and key performance indicators (KPIs) of project success.

> [!TIP]
> You can test latency using the Azure Latency Test and Azure Speed Test 2.0 for each datacenter.

## Isolate your data in the shared cloud

The cloud uses a shared common infrastructure across different businesses, which leads to economies of scale. But even though the infrastructure and processing might be shared in public clouds, your data is isolated, which means it's not shared with others. Microsoft takes security and data use policies seriously. We maintain the highest data and security standards, and we get them audited and certified by trusted third parties regularly. Security isn't an afterthought. It's part of how we develop applications, so that the computing infrastructure is shared and other security aspects are isolated.

Another aspect of sharing resources and infrastructure in the cloud is the possibility of monopolizing resources or becoming a noisy neighbor. This can happen due to poorly developed code that consumes too much resources, and not due to a valid business use case. The Dynamics 365 platform has automated monitoring and throttling mechanisms to prevent such situations. You should understand and comply with these service boundaries and throttles when you design for cloud platforms. For more information, see [Priority-based throttling](/dynamics365/fin-ops-core/dev-itpro/data-entities/priority-based-throttling) and [Service protection API limits](/powerapps/developer/data-platform/api-limits).

## Protect your service and use a capacity-based model

Service protection and limits are used in cloud services to ensure consistent availability and performance for users. The thresholds don't affect the normal user operations. They're designed to protect from random and unexpected surges in request volumes that threaten the user experience, and the availability and performance of the platform or solution. You should understand the protection limits and design for them with the appropriate patterns, especially for high-volume workloads like integrations and batch processing.

The cloud gives you the scalability to handle large workloads, but a shared public cloud doesn't mean you have unlimited capacity or computing power. In many cases, these capacity limits are enforced via licensing. You should embrace this capacity-based model of cloud infrastructure and plan to operate within the entitlements, taking into account usage profile, data volumes, and integration patterns. Understanding these protections and service boundaries that apply to a specific service helps you clarify the available resources. It also drives the right behavior when it comes to design and development. As a result, the solution is optimized to operate within the allocated capacity. You should procure more capacity to meet your requirements in advance.

Learn more at [Service the solution](service-solution.md).

> [!TIP]
> Plan for expected daily peak and monthly maximum order transaction volumes to ensure that the service is licensed to support them. Also, plan and prioritize your integrations and Open Data Protocol (ODATA) requests based on the volumes, so they're not throttled by request limits. These checks and balances prevent overusing resources, preserve the system's responsiveness, and ensure consistent availability and performance for environments running Dynamics 365 apps.

## Integrate with on-premises systems

The cloud might be the preferred option for new applications, but you might still have on-premises elements in your enterprise solution. Therefore, you might need to build integrations with these on-premises systems. You should establish these integration patterns in compliance with your internal security policies while allowing cloud applications to authenticate and connect to on-premises services. You might need to allow-list URLs and IP ranges on your firewall. Or you might use the Microsoft Entra Application Proxy or an on-premises gateway that allows such integrations without opening inbound connections into your network.

[!INCLUDE [azure-ad-to-microsoft-entra-id](~/../shared-content/shared/azure-ad-to-microsoft-entra-id.md)]

Even from a design standpoint, patterns that worked on-premises might be challenging in the cloud, due to latency and other security restrictions. An example is the encryption of traffic leaving your network or routing via a peering network.

## Use cloud and edge for offline scenarios

The public cloud is the default and recommended choice of deployment for most Dynamics 365 customers. However, you might want to extend the cloud to support key scenarios where connectivity is an issue. Your industry might need a solution on the ground, such as retail, field service, manufacturing, warehousing, and project operations. These implementations are called *cloud and edge*, where *cloud* is the system of intelligence and *edge* is the system of record.

For example, Dynamics 365 Commerce customers use the cloud and edge model. Here, the store operations run on-premises (edge), while the main instance handles centralized back-office functions like finance, data management, and analytics (cloud).

Cloud and edge deployments provide business continuity for mission-critical functions. You can keep running operations when disconnected from the cloud. If there's a network outage, Dynamics 365 Point of Sales can operate locally and store data generated offline. When connectivity resumes, data is synchronized to the cloud. Also, when throughput is high and many processes run in parallel, user productivity might be affected. You can scale out and run manufacturing and warehouse processes in isolation to support high user productivity.

Another reason for using a cloud and edge implementation is Internet connectivity. Regions with poor Internet connectivity might prefer on-premises deployments. Organizations operating in such regions use an edge model to reduce the risk to their business from poor connectivity. They also want to maintain a stable user experience for their staff.

## Next steps

- Learn why it's important to implement cloud solutions by reviewing the [overview](implementing-cloud-solutions.md)
- Learn how to [adopt a cloud mindset](implementing-cloud-solutions-adopt-cloud-mindset.md)
- Learn how to [customize and extend cloud applications](implementing-cloud-solutions-customize-extend-cloud-applications.md)
- Learn how to [operate in the cloud](implementing-cloud-solutions-operate-in-cloud.md)
- Review the [evergreen cloud](implementing-cloud-solutions-evergreen-cloud.md) approach and the model of continuous updates
- Learn best practices to [upgrade from on-premises to the cloud](implementing-cloud-solutions-upgrade-from-onpremises-to-cloud.md)
- Review the [checklist](implementing-cloud-solutions-checklist.md) to help you with best practices in implementing cloud solutions
- Read the [case study](implementing-cloud-solutions-case-study.md) to see how adopting a cloud mindset and putting together a proper strategy can help your organization
