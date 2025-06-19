---
title: How an environment strategy affects key factors
description: Learn how an environment strategy affects key factors of a Dynamics 365 implementation, such as security, compliance, and future-proofing.
author: abunduc-ms
ms.author: abunduc
ms.date: 01/16/2024
ms.topic: concept-article
ms.custom:
  - evergreen
  - ai-seo-date: 
  - ai-gen-docs-bap
  - ai-gen-title
  - ai-gen-desc
content_well_notification: AI-contribution
---

# How an environment strategy affects key factors

You need an environment strategy to plan and manage your Dynamics 365 applications. An environment strategy helps you decide how many environments to use, what types of environments to use, and how to configure them. Your environment strategy can affect key factors such as security, compliance, application design, performance, scalability, maintainability, application lifecycle management (ALM), citizen development, and future-proofing. This article explains how these factors relate to your environment strategy and why you should consider them when designing your solution.

## Security and compliance

Security and compliance are essential for any environment strategy. You must ensure that your data is stored and processed according to the laws and regulations of your location and industry. You also need to protect your data from unauthorized access, loss, or corruption.

Before you start your project, you should identify your compliance requirements and involve your security and compliance teams in the strategy review and approval. Some of the common elements that affect compliance are:

- The physical location of the environments, which usually determines data residency
- The features and apps in the scope and their data processing requirements
- The encryption of data at rest and in transit
- The disaster recovery procedures to restore the service and data
- The data retention policies and the ability to back up and restore data
- The standards for protecting personal data and complying with the regulations for your industry and region

## Application design

The application design can influence and be influenced by the environment strategy. For example, you might want to separate or share data and functionality between different departments or business units, depending on your organizational structure and goals. You might also need to integrate your apps with other systems or services, which can affect the compatibility and performance of your solution.

You should design your apps to meet the needs of your users and your business processes. You should also consider how your apps will evolve and grow over time, and how you'll manage changes and updates.

## Performance and scalability

Dynamics 365 online offers high performance and scalability for your cloud solutions. However, you might experience different levels of latency depending on your environment location, user location, device, network, and other factors. Latency is the delay between a user's action and the system's response. High latency can affect the user experience and satisfaction.

We recommend that you create a latency analysis matrix for your solutions that have users in different locations. A latency analysis matrix shows the expected latency for each combination of environment location, user location, device, and network. For example:

| Environment location | User location | Device | Network | Latency | Bandwidth |
| --- | --- | --- | --- | --- | --- |
| North America (NAM) | Canada | Browser | Corporate network | 80 ms| 6.4 Mbps |
| North America (NAM) | Amsterdam | Tablet | Corporate wi-fi | 120 ms| 8 Mbps |

This exercise helps you choose the best environment location for your users and optimize your application design for high-latency scenarios. For example, you can use lightweight forms or reduce the number of records on a page to improve the load time.

You should also choose the right environment types for your workload and capacity needs. For example, trial or low-tier sandbox environments might not provide the same performance as production environments. You might not want to develop or test your solution in these environments.

Scalability is the ability of your solution to handle increasing or varying demands. In the cloud, you can scale your solution by adding more environments, more API capacity, more storage, or more features. However, you should also consider the licensing and service protection limits that apply to your solution.

Following are examples of scalability parameters for a cloud deployment:

- How many parallel connections or concurrent users can you support with one application or in a single environment?
- How many API calls is a user entitled to make?
- What are the limits on workflow or code executions?
- What is the peak transaction volume per hour?
- What is the volume of imported transactions during the peak hour?

The following section explains the difference between scaling up (vertical scalability) and scaling out (horizontal scalability) for finance and operations apps and customer engagement apps.

### Scaling up - vertical scalability

Scaling up means increasing the capacity of a single environment to support more users, data, or features. For example, you can have one environment with thousands of users and multiple apps. You can also increase the storage of your environment to store terabytes of data. Dynamics 365 online has a scalable cloud infrastructure that can support large enterprises. However, you must follow the licensing and entitlement rules for Dynamics 365. [Find the latest information on how to license Dynamics 365 in the License Guide](https://dynamics.microsoft.com/pricing/).

Users of customer engagement apps have a defined API entitlement based on their license type. API calls are requests to the system to perform an action or retrieve data. For workflow automation, you can create any number of Power Automate flows in each environment. Each flow can have thousands of steps per day, which you can scale further with the appropriate license types and add-ons. There are no hard limits on the number of apps in each environment, but you can't have multiple Microsoft apps of the same type in the same environment.

Finance and operations apps have [priority-based throttling](/dynamics365/fin-ops-core/dev-itpro/data-entities/priority-based-throttling) that prevents overuse of resources and ensures consistent availability and performance for the environments.

### Scaling out - horizontal scalability

Scaling out means adding more environments to support more users, data, or features. For example, you can have several separate environments for different purposes or business units. You can also have multiple Power Automate flows in your tenant. A tenant is a container for your environments and data. However, you still need to consider the licensing and service protection limits that apply to your tenant, especially for storage and API capacity.

There are no native sync capabilities between environments, so you need to manage the data and code transfer between them. You should also follow the best practices for data modeling and application design set by your organization.

## Maintainability

Maintainability is the ease and speed of maintaining your solution, including service updates, bug fixes, and rolling out change requests and new features. You want to keep your solution up to date and secure, as well as meet the changing needs of your users and business.

Your environment strategy can affect your maintainability in several ways. For example, if you have multiple apps sharing common components in the same environment, you need to consider the impact of upgrading or deploying a new release on all the apps. You also need to invest in automation testing to quickly identify and resolve any issues or dependencies.

The number of environments you have can also affect your maintainability. For example, testing a release wave or analyzing the impact of deprecations is easier when you have fewer environments to manage.

## Application lifecycle management

Application lifecycle management (ALM) is the process of managing the development, deployment, and maintenance of your solution. ALM includes the tools and methods you use to create, test, and update your solution. ALM can affect the long-term success, maintainability, and future-proofing of your solution.

Your environment strategy can affect your ALM and vice versa. For example, you might use different environments for different stages of your solution lifecycle, such as development, testing, and production. Typically, you need at least three environments to support a mature release-management process.

### Types of environments

There are two main types of environments: production and sandbox. Production environments are meant to support your business operations. They have more protection and restrictions than sandbox environments. Sandbox environments are meant for development, testing, and training. You can create, delete, and restore them as needed. The following list describes the different purposes of each type of environment.

- **Development**: You use development environments to create and customize your solution. You might need one or more development environments, depending on your requirements and timeline. You should set up proper DevOps to enable smooth continuous integration and continuous delivery (CI/CD). Learn more at [Application lifecycle management](application-lifecycle-management.md).

- **Quality assurance (QA)**: You use QA environments to test your solution from both a functionality and deployment perspective before you move it to a user acceptance testing (UAT) environment. You should only deploy managed solutions to QA environments. You might need multiple testing environments for different purposes, such as regression testing, performance testing, and data migration testing.

- **User acceptance testing (UAT)**: You use UAT environments to let your business users test and approve your solution before you deploy it to a production environment. UAT environments are usually the first environments that business users have access to.

- **Training**: You use training environments to train your business users on how to use your solution. Training environments let users practice in a simulated environment without affecting live data.

- **Production**: You use production environments to run your solution for your business users. Production environments are the live systems that support your business operations.

## Citizen development

Power Platform lets people who aren't professional developers build apps and create solutions to solve their own problems. The central IT team still has governance responsibility and creates guidelines to secure data with data loss prevention policies. However, business users can build apps and automate their work while accessing data in a secure way.

This organic growth of applications by business users enables digital transformation at a large scale. Thousands of organizations have adopted this "citizen developer" approach to quickly roll out hundreds of apps across the organization. They also get a community of engaged employees who help the business evolve to meet customer needs faster and better.

For finance and operations apps, business users can use the integration with Power Platform to access tools and services such as dual-write, virtual entities, and business and data events. You should consider citizen development for these implementations as well.

Your environment strategy should support this kind of organic growth and enable the maker experience for business users. You should provide an agile and automated process for users to request environments and connect to data in a secure way while following the standards for data modeling and application design set by your organization.

## Future-proofing

Future-proofing is the process of developing methods to minimize any potential negative effects in the future. It can also be called resilience of the solution to future events.

Your environment strategy should consider any future phases and roll-outs of your solution, allow you to deal with changing requirements, and build a solution that won't limit the business or take away necessary control. For example, you should think about country- and region-specific needs, as well as variations and deviations from the standard process.

## Next steps

- Learn about [global deployment scenarios](environment-strategy-global-deployment-scenarios.md)
- Learn about [environment lifecycle scenarios](environment-strategy-lifecycle-scenarios.md)
- Get [product-specific guidance](environment-strategy-guidance-product.md)
- Follow the [environment strategy checklist](environment-strategy-checklist.md)
- Read a [case study](environment-strategy-case-study.md) of a company that learned the importance of a good environment strategy
