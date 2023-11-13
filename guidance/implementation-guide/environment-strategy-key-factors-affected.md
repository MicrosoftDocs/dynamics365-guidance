---
title: Key factors affected by an environment strategy
description: In this article, we explore the key factors directly affected by an environment strategy, including security and compliance, ALM, operations, and functional and nonfunctional aspects of the solution. Considering these key factors will help you define an environment strategy that meets the needs of your organization, and set the direction for the future growth of these applications to meet evolving business requirements.
author: abunduc-ms
ms.author: abunduc
ms.date: 04/12/2023
ms.topic: conceptual

---

# Key factors affected by an environment strategy

In this article, we explore the key factors directly affected by an environment strategy. Factors include security and compliance, application lifecycle management (ALM), operations, and functional and nonfunctional aspects of the solution. Considering these key factors will help you define an environment strategy that meets the needs of your organization, and set the direction for the future growth of these applications to meet evolving business requirements.

## Compliance

Security and compliance are critical considerations for an environment strategy. Each organization must make sure that data is stored and processed in accordance with local or regional laws.

At the onset of the project, your organization must determine your environment's compliance requirements. Requirements can vary widely depending on the industry, regulations, business type, and user base. Your internal security and compliance teams will want to review and approve the strategy.

The most common elements affecting compliance are:

- The physical location of the environment(s), which usually determines data residency

- The specific features and apps in the scope and their data-processing requirements

- The encryption (at rest and in transit for confidential information)

- The disaster recovery procedures to restore the service and data

- The data-retention policies, and the ability to back up and restore data

- The personally identifiable information (PII) standards for data protection, and ensuring the service is compliant with the regulatory requirements for the industry and region

## Application design

The environment strategy can affect the application design. Conversely, the needs of an application can drive the environment requirements, and it's not uncommon for IT systems within an organization to reflect the actual structure of the organization. Depending on your organization's strategy for data isolation, collaboration, and security between different departments, you could choose to have a single shared environment or create isolated environments. For example, in customer engagement apps, a bank might allow data sharing and collaboration between commercial and business banking divisions while isolating the personal banking division. This data flow reflects the bank's application design and environment strategy.

App integrations also play a key role, as multiplexing with different environments may not work. For example, a user may not be able to simultaneously sync emails to several environments.

## Performance and scalability

Microsoft cloud services provide a high degree of scalability and performance. Globally distributed users can experience higher latencies when accessing cloud solutions due to a range of factors. Such factors include network latency, firewalls, network traffic monitoring, organizational proxies, and routing by internet service provider (ISP). We recommend creating a latency analysis matrix for solutions that have a globally distributed user base.

| Environment location | User location | Device | Network | Latency | Bandwidth |
| --- | --- | --- | --- | --- | --- |
| North America (NAM) | Canada | Browser | Corporate network | 80 ms| 6.4 Mbps |
| North America (NAM) | Amsterdam | Tablet | Corporate wi-fi | 120 ms| 8 Mbps |

This exercise gives a fair idea of how the network latency will affect the user experience based on the location of your environment. This information can be used to make a balanced choice so most users have an acceptable level of latency, and application design can be optimized for users in high-latency locations. For example, using lightweight forms or reducing the number of records shown on a page can enable faster loads.

Choose the environment types carefully, based on the workload and the capacity needed. Trial or low tier sandbox environments won't deliver the same level of performance as production environments, for example. In many cases, you'll prefer to not develop or test the solution on a trial or low tier sandboxes.

Scalability of the cloud platform is a critical consideration for business applications. In on-premises deployments, you would scale up by adding more servers or more CPU, memory, or storage capacity to existing servers. In a cloud world with elastic scale and microservice architecture, you'll replace the server with an environment, and the compute and data transfer units with the API capacity. That wording was just an analogy and not a one-to-one mapping where one environment corresponds to a server in the cloud infrastructure.  

Examples of the scalability parameters for a cloud deployment include the following list:

- How many parallel connections or concurrent users can you support with one application or in a single environment?

- How many API calls is a user entitled to make?

- What are the limits on workflow or code executions?

- What is the peak transaction volume per hour?

- What is the volume of imported transactions during the peak hour?

The following section provides a perspective of the cloud interpretation for scale-up/ vertical and scale-out/ horizontal scalability for finance and operations apps, as well as customer engagement apps.

### Scale-up - vertical scalability

Organizations commonly operate single environments supporting thousands of users and multiple applications. The environment's storage grows as more users and applications store their data. Dynamics 365 online is built on a scalable cloud infrastructure that can store terabytes of data to meet the requirements for large enterprises. However, the entitlements and licenses acquired by the organization, including service protection limits, govern the concrete requirements. The [License Guide](https://dynamics.microsoft.com/pricing/) contains up-to-date information about how to license Dynamics 365.

Users of customer engagement apps have a defined API entitlement based on the license type assigned. For workflow automation, you might define any number of Power Automate flows in each environment. Each flow might have thousands of steps performed per day, which can be further scaled using appropriate license types and add-ons. There are no hard limits on the number of apps in each environment, but you can't have multiple first-party apps of the same type in the same environment.

finance and operations apps have [priority-based throttling](/dynamics365/fin-ops-core/dev-itpro/data-entities/priority-based-throttling) that prevents over-utilization of resources to preserve the system's responsiveness and ensure consistent availability and performance for the environments.

### Scale-out - horizontal scalability

With horizontal scalability, organizations can have several separate environments, with any number of Power Automate flows on the tenant. There are no native sync capabilities between environments, and you still need to take license entitlements into consideration, especially when it comes to tenant-wide storage and API entitlement.

## Maintainability

Maintainability measures the ease and speed of maintaining a solution, including service updates, bug fixes, and rolling out change requests and new functionality.

If you have several applications sharing common components in the same environment, you should consider maintainability when upgrading or deploying a new release. It's also important to invest in automation testing so you can run regression tests and quickly identify any dependencies that could cause issues.

The effort to maintain the solution is directly proportional to the number of environments involved. For example, testing a release wave or analyzing the impact of deprecations is easier when there's just one production environment with the Dynamics 365 Sales app and the Dynamics 365 Customer Service app, compared to a solution that uses different production environments for the Sales and Customer Service apps.

## Application lifecycle management

Application lifecycle management (ALM) includes the tools and processes that manage the solution's lifecycle and can affect the long-term success of a solution. When following the ALM of a solution, consider the entire lifespan of the solution, along with maintainability and future-proofing. Changes to your environment strategy will directly affect the ALM (and vice versa), but it's important to be clear that environments aren't the repository of your code and customizations.

Environments can be used to separate business functions or for different purposes, such as development, testing, and production. Typically, at least three environments are necessary to support a mature release-management process.

### Types of environments

Production environments are meant to support the business. By default, production environments are more protected for operations that can cause disruption, such as copy and restore operations. Sandbox environments can be used to develop, test, and delete as required. The following list provides more detailed descriptions of the different purposes for each type of environment.  

- Development

  One or more development environments are usually required, depending on the customization requirements and time available. Development environments should be set up with proper DevOps to allow for smooth CI/CD. Learn more at [Application lifecycle management](application-lifecycle-management.md).  

- Quality assurance (QA)

  Allows for solution testing from both a functionality and deployment perspective before the solutions are given to the business teams in a user acceptance testing (UAT) environment. Only managed solutions should be deployed here. Depending on project requirements, there can be multiple testing environments, including regression testing, performance testing, and data-migration testing.

- user acceptance testing (UAT)

  Generally the first environment that business users will have access to. It will allow them to perform UAT testing before signing off deployment to production environment for go live.

- Training

  With a dedicated training environment, business users can practice in a simulated environment without the risk of interfering with live data.  

- Production

  The live system for business users.  

## Citizen development

Power Platform enables people who aren't professional developers to build apps and create solutions to solve their own problems. The central IT crew still has governance responsibility and creates guidelines to secure data with DLP policies. However, business users can build apps and automate their work while accessing data in a secure way. This organic growth of applications by business users facilitates digital transformation at a massive scale. Thousands of organizations have adopted this "citizen developer" philosophy to quickly roll out hundreds of apps across the organization. In this way, they get a community of engaged employees who are helping realize the vision of an agile business that can evolve to meet customer needs in days or weeks instead of months or years.

For finance and operations apps, business users can take advantage of the integration with Power Platform to access a set of tools and services such as dual write, virtual entities, and business and data events. As such, the topic of citizen development should be an attention point for these implementations as well.

The environment strategy that enables this kind of organic growth will be different from a traditional IT-developed solution. It's crucial to deliver an agile and automated process where business users can request environments to enable the maker experience and connect to data in a secure way while conforming to the standards for data modeling and application design set by the organization.

## Future-proofing

Future-proofing is the process of developing methods to minimize any potential negative effects in the future. It can also be referred to as resilience of the solution to future events.

Your environment strategy needs to take into consideration any future phases and roll-outs of the solution, and allow you to deal with changing requirements and build a solution that won't limit the business or take away necessary control. As an example, consider country/region-specific needs, as well as variations to and deviations from the standard process.

## Next steps

- Review recommendations for Azure Active Directory at [Tenant strategy](environment-strategy-tenant-strategy.md)  
- Check out the [Global deployment scenarios](environment-strategy-global-deployment-scenarios.md)  
- Get an overview at [Environment strategy](environment-strategy-overview.md)  
