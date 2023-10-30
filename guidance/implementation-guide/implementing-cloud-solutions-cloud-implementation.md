---
title: Cloud implementation considerations
description: Learn how Dynamics 365 helps you with security, scalability, performance, data isolation, limits, and capacity before you start an implementation project.
author: taksatoms
ms.author: tsato
ms.date: 05/16/2023
ms.topic: conceptual
---

# Cloud implementation considerations

Implementing solutions from online apps such as Dynamics 365 can reduce management overhead and allow you to deliver business value more quickly by focusing on the application layer. Fundamental application considerations, however, still apply to online applications. Security, scalability, performance, data isolation, limits, and capacity are still critical, but could have a different approach when compared to an application deployed on-premises. This section focuses on some of these considerations for online apps.

> [!TIP]
> Dynamics 365 offers deep integration with Azure DevOps with [build tools](/power-platform/alm/devops-build-tools) to help [automate your deployment pipeline](/dynamics365/fin-ops-core/dev-itpro/dev-tools/hosted-build-automation) and effectively manage the application lifecycle.

:::image type="content" source="media/implementing-cloud-solutions-alm-by-devops.png" alt-text="ALM powered by Azure Devops" :::

## Security readiness

The responsibility for security in cloud solutions is shared by the service provider and the customer. That means your existing security policies might not be suitable to meet the security requirement in the cloud. The service provider processes customer data and is responsible for aspects such as securing the backend infrastructure and data encryption in transit and at rest. As a data controller, the customer is still responsible for securing access to environments and application data.

The IT information security team should clearly understand the boundaries of these shared responsibilities to meet the following goals:

- The service provider meets the organizational security, privacy, and compliance requirements. It's usually done in the beginning to approve the platform for use supported by a regular review or audit process to ensure continued compliance.

- The security team is aware of the controls and configurations required to govern access to data and fulfill the customer security responsibility. Configurations might include defining the data loss prevention policies, access control policies, and environment management policy. They usually have a default setup with a process to manage deviations for specific apps.

- The governance process makes sure the application-level security requirements are met. This is primarily managed by the application teams and driven by business requirements for each app deployment. You might have more checks before deployment to ensure compliance.

A good example is compliance and privacy laws. Here, the service itself might be fully compliant from a data processor standpoint, but the customer is still responsible for implementing data controller processes, such as a "forget me" request or managing marketing consent for contacts.

Organizations need to review their information security policies and ensure that they're cloud ready. Doing this exercise earlier, before the app deployment cycle, will help avoid delays. It's important to closely work with your cloud SaaS service provider to ensure all your security requirements are met. Microsoft publishes the details of how this shared responsibility of securing data is fulfilled from a data processor perspective on the [Microsoft Trust Center](https://www.microsoft.com/trust-center). There, you find detailed information on our security and privacy policies, as well as the certificate of compliance for various regulatory norms and internal standards.

## Scalability

The scalability of the SaaS platform is another key consideration for business applications. Being able to scale out and scale up to support seasonal workloads or spikes in user activity impact the overall user experience (both staff and customers) and effectiveness of business processes.

The cloud scalability parameters available in SaaS differ from a traditional on-premises system. Instead of adding more servers or increasing the power of machines, these parameters could be translated as available API capacity. You also shouldn't assume that cloud means infinite scale and computing power that can process everything thrown at it. The good old coding and design best practices are still relevant, but might need to be adapted. Although managing and scaling cloud services is complex, increasing or decreasing your data storage, processing power, and networking requirements can be done seamlessly. In many cases, you can do so automatically or with simple configuration changes. This microservices architecture, including capacity-based routing to resources and storage management, is transparent to Microsoft customers. The SaaS cloud offers the flexibility to scale horizontally and vertically to support thousands of concurrent users. Embracing the capacity-based model for resource consumption in the cloud helps not only build optimized applications but also a better plan for operating cost post deployment.

## Performance

Several contributing factors can impact application performance, including network latency, user device and browser, application design, configuration, data composition, and customizations. Cloud services are inherently scalable, have vast compute power, and are available from multiple locations around the world. But that doesn't necessarily guarantee performance if the solution is poorly designed, or if users access the service from environments with high network latency.

Research shows that a few milliseconds of latency lead to a significant percentage drop-in page load times. For e-commerce companies, it might be a sizable drop in user attention and therefore sales revenue. Low latency isn't  just good, it's a critical deciding factor in an enterprise's brand and reputation. The same applies to back office business applications operating in the cloud, user experience and productivity can be impacted in a high-latency environment.

Your cloud applications are powered by hundreds of pieces of virtualized hardware running on Azure datacenters sprinkled around the world. A crucial decision you must make the datacenter to deploy your application so that all users of the application get an acceptable level of latency. Learn more at [Environment Strategy](environment-strategy-overview.md)

One option for businesses looking for more network reliability and security is to use a private connection. Cloud providers offer dedicated channels, for example [Azure ExpressRoute](https://azure.microsoft.com/services/expressroute/). These connections can offer more reliability, consistent latencies, and higher security than typical connections over the internet.

Performance also can suffer because of a poorly designed application. There are three typical scenarios for this issue:

- You make custom code changes in Dynamics 365 online  
- You deploy custom applications in a platform as a service (PaaS) environment  
- You deploy custom applications in an infrastructure as a service (IaaS) environment  

In those cases, your team must design a high-performing application and carry out proper performance tests. Only then do you deploy to production.

To summarize, here are key takeaways:

- Performance must be a key consideration for business applications  
- Give due attention to performance during the implementation projects  

Performance not only impacts the user experience and adoption. It can directly impact business goals and key performance indicators (KPIs) of project success.

> [!TIP]
> You can test latency using the Azure Latency Test and Azure Speed Test 2.0 for each datacenter.

## Isolation in the shared cloud

The cloud operates on a shared common infrastructure across different businesses, which leads to economies of scale. But although the infrastructure and processing may be shared in public clouds, you have data isolation, which means one customer's data isn't shared with others. Microsoft takes security and data use policies seriously. For us, it's imperative that we maintain the highest data and security standards. Trusted third-party organizations audit and certify these standards and practices regularly. Security isn't an afterthought. It's ingrained into how we develop applications, so that the computing infrastructure is shared and other security related aspects are isolated.

The other aspect of sharing resources and infrastructure in the cloud is the possibility of monopolizing resources or becoming a noisy neighbor. While rare, these cases often happen due to to poorly developed runaway code, and not due to a legitimate business use case. Automated monitoring and protection throttles are built into the Dynamics 365 platform to prevent such situations. It's important to understand and comply with these service boundaries and throttles when you design for cloud platforms. For more information, read [Priority-based throttling](/dynamics365/fin-ops-core/dev-itpro/data-entities/priority-based-throttling) and [Service protection API limits](/powerapps/developer/data-platform/api-limits).

## Service protection and a capacity-based model

Service protection and limits are used in cloud services to ensure consistent availability and performance for users. The thresholds don't impact the normal user operations. They're designed to protect from random and unexpected surges in request volumes that threaten the user experience, and the availability and performance characteristics of the platform or solution. It's crucial to understand the protection limits and design for them with the appropriate patterns, especially around high-volume workloads like integrations and batch processing.

The cloud provides us with the scalability to deal with large workloads, but a shared public cloud doesn't mean you have unlimited capacity or computing power. In many cases, these capacity limits are enforced via licensing. You have to embrace this capacity-based model of cloud infrastructure and plan to operate within the entitlements, taking into account usage profile, data volumes, and integration patterns. Understanding these protections and service boundaries that apply to a specific service helps bring clarity on available resources. It also drives the right behavior when it comes to design and development. As a result, the solution is optimized to operate within the allocated capacity. More capacity is procured to meet the requirements in advance.

Learn more at [Service the solution](service-solution.md)  

> [!TIP]
> Plan for the daily peak and the monthly maximum order transaction volumes expected to ensure that the service is licensed to satisfactorily support the peak as well as the total maximum expected volumes. Also, plan and prioritize for integrations and Open Data Protocol (ODATA) requests based on the volumes, so they're honored and not throttled due to request limits. These checks and balances prevent overutilizing resources, preserve the system's responsiveness, and ensure consistent availability and performance for environments running Dynamics 365 apps.

## Integration with on-premises systems

The cloud might be the preferred approach for new applications, but in most enterprise solutions, you could still have on-premises elements. Therefore, it's common to build integrations with these on-premises systems. It's important to establish these integration patterns in compliance with your internal security policies while allowing cloud applications to authenticate and connect to on-premises services. You often need allow-listing URLs and IP ranges on your firewall. Or you might use the Microsoft Entra Application Proxy or an on-premises gateway that allows such integrations without having to open inbound connections into your customer's corporate network.

[!INCLUDE [azure-ad-to-microsoft-entra-id](~/../shared-content/shared/azure-ad-to-microsoft-entra-id.md)]

Even from a design standpoint, patterns that worked on-premises could be challenging in the cloud, due to latency and other security restrictions imposed. An example is the encryption of traffic leaving a customer network or routing via a peering network.

## Cloud and edge

The public cloud is the default and recommended choice of deployment for most Dynamics 365 customers. However, you may want to extend the cloud to unlock important capabilities for key scenarios where connectivity is an issue. Your industry may need a solution on the ground, such as brick and mortar commerce, field service, a manufacturing execution system (MES), warehouse operations, and project operations.

These implementations are called cloud and edge, where cloud is the system of intelligence and edge is the system of record.

For example, Dynamics 365 Commerce customers use the cloud and edge model. Here, the store operations run on-premises (edge), while the main instance handles centralized back office functions like finance, data management (such as products and customers), and analytics (cloud).

Cloud and edge deployments provide business continuity for mission-critical functions like point of sales, warehousing, and manufacturing. We want you to be able to continue running operations when disconnected from the cloud. If there's a network outage, Dynamics 365 Point of Sales can sustain itself with basic operations and keep data generated locally. When connectivity resumes, data is synchronized to the cloud. Also, whenever throughput is high and more heavy processes are run in parallel, user productivity may be impacted. We want to enable you to scale out and run manufacturing and warehouse processes in isolation so high user productivity is always supported.

Another reason is internet connectivity. Regions with poor internet connectivity see more occurrences of on-premises deployments. Organizations operating in such regions go with an edge model to mitigate the risk to their business from poor connectivity. They also want to maintain a stable user experience for their staff.

## Next steps

- Understand the importance of implementing cloud solutions reviewing the [overview](implementing-cloud-solutions.md)
- Understand how to [adopt a cloud mindset](implementing-cloud-solutions-adopt-cloud-mindset.md)
- Learn how to [customize and extend cloud applications](implementing-cloud-solutions-customize-extend-cloud-applications.md)
- Learn how to successfully [operate in the cloud](implementing-cloud-solutions-operate-in-cloud.md)
- Review the [evergreen cloud](implementing-cloud-solutions-evergreen-cloud.md) approach and the model of continuous updates
- Understand best practices to [upgrade from on-premises to the cloud](implementing-cloud-solutions-upgrade-from-onpremises-to-cloud.md) 
- Review the [checklist](implementing-cloud-solutions-checklist.md) to help with best practices in implementing cloud solutions
- Read the [case study](implementing-cloud-solutions-case-study.md) to see how adopting a cloud mindset and putting together proper strategy can help your organization
