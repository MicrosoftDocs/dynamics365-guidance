---
title: Get guidance for your Dynamics 365 environment strategy
description: Learn about the product-specific resources and considerations that apply to your environment strategy for Dynamics 365 finance and operations apps.
author: abunduc-ms
ms.author: abunduc
ms.date: 01/16/2024
ms.update-cycle: 1095-days
ms.topic: concept-article
ms.custom:
  - evergreen
  - ai-seo-date: 01/16/2024
  - ai-gen-docs-bap
  - ai-gen-title
  - ai-gen-desc
content_well_notification: AI-contribution
---

# Get product-specific guidance for your Dynamics 365 environment strategy

Most concepts related to environment strategy are product-agnostic and apply to most cloud deployments. In this article, we offer some guidance specific to Dynamics 365 finance and operations apps, customer engagement apps, and Power Platform.

## Product-specific guidance: Finance and operations apps

Finance and operations apps include Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Project Operations, and Dynamics 365 Commerce. When you implement these apps, you need environments to develop, test, train, and configure your solution before you go live. These nonproduction environments have different tiers with predefined sizing, topologies, and costs. Understanding these basics is key to designing a good environment plan.

### Environments and project complexity

When you buy Dynamics 365 finance and operations apps from Microsoft, you get two environments. One is the production environment, which is where you run your business operations. It's a robust environment, with high availability and disaster recovery features.

You also get one sandbox environment that's a standard acceptance testing (tier 2) instance for the life of the tenant. It's a nonproduction, multibox instance that you can use for testing, user acceptance testing (UAT), integration, and training. Because it's a basic tier 2 instance, it might not be enough for every type of testing. For example, performance testing needs a bigger instance to handle larger data volumes and more users.

Depending on the project complexity, the production and sandbox environments in the standard subscription might not be enough. For example, the following chart compares the environment requirements of two sample projects, one that's less complex and one that's more complex.

| Environment purpose | Finance and operations tier | Dataverse | Standard subscription | Less complex project | More complex project |
| --- | --- | --- | --- | --- | --- |
| Testing or Training | 2 | Sandbox | ![FO](media/orangeCircle.png) ![Dataverse](media/redCircle.png) | ![FO](media/orangeCircle.png) ![Dataverse](media/redCircle.png) | ![FO](media/orangeCircle.png) ![Dataverse](media/redCircle.png) |
| Production | Sized | Production | ![FO](media/orangeCircle.png) ![Dataverse](media/redCircle.png) | ![FO](media/orangeCircle.png) ![Dataverse](media/redCircle.png) | ![FO](media/orangeCircle.png) ![Dataverse](media/redCircle.png) |
| Development | 1 | Development | | ![FO](media/orangeCircle.png) ![Dataverse](media/redCircle.png) | ![FO](media/orangeCircle.png) ![Dataverse](media/redCircle.png)
| Build | 1 | n/a |  | ![FO](media/orangeCircle.png) | ![FO](media/orangeCircle.png) |
| Golden configuration | 1 or 2 | n/a | | ![FO](media/orangeCircle.png) | ![FO](media/orangeCircle.png) |
| Data migration | 2+ | n/a | | ![FO](media/orangeCircle.png) | ![FO](media/orangeCircle.png) ![Dataverse](media/redCircle.png) |
| Performance testing | 4 or 5 | Sandbox | | ![FO](media/orangeCircle.png) ![Dataverse](media/redCircle.png) | ![FO](media/orangeCircle.png) ![Dataverse](media/redCircle.png) |
| Training | 2 or 3 | Sandbox | | | ![FO](media/orangeCircle.png) ![Dataverse](media/redCircle.png) |
| System integration testing | 2 or 3 | Sandbox | | | ![FO](media/orangeCircle.png) ![Dataverse](media/redCircle.png) |
| Other/ unplanned | n/a | Trial or Sandbox | | | ![FO](media/orangeCircle.png) ![Dataverse](media/redCircle.png) |

![FO](media/orangeCircle.png) Finance and operations environment ![Dataverse](media/redCircle.png) Dataverse environment

For both projects, you can use the out-of-the-box tier 2 sandbox for testing. You'll need development environments, one for each developer, for development activities. These environments have Microsoft Visual Studio installed.

What about the build environment? The build process uses the tier 1 build environment to produce code packages that you can apply to sandbox and production environments. Alternatively, you can use Microsoft-hosted build agents to do the builds instead of having a dedicated build environment. The limitations of this approach are that you can't run unit tests and a monthly time limit applies. Assess the limitations and decide whether you need a dedicated build environment.

The "[Golden configuration](/dynamics365/fin-ops-core/dev-itpro/database/dbmovement-scenario-goldenconfig)" environment is for configurations that are fully tested and that you want to keep and transfer to other sandboxes and production environments.

You might need a data migration environment to move data from legacy systems. For performance testing, you'll want to use a higher tier (4 or 5) environment.

More complex projects might need even more environments. For example, you might want more than one testing environment if multiple teams are developing and testing parallel workstreams, or sandbox environment that mirrors the production environment for training users.

### Environments in Dynamics 365 Lifecycle Services

For Dynamics 365 finance and operations apps, all environments for a solution are contained in one project on the Microsoft Dynamics 365 Lifecycle Services portal. This *Dynamics 365 Lifecycle Services project* is hosted in one Microsoft Entra ID tenant, and includes all the environments you use for the implementation.

[!INCLUDE [azure-ad-to-microsoft-entra-id](~/../shared-content/shared/azure-ad-to-microsoft-entra-id.md)]

Typically, an implementation project has only one production environment and one Dynamics 365 Lifecycle Services project for each Microsoft Entra ID tenant. But this isn't always the case. For instance, an organization might have multiple production environments and thus multiple Dynamics 365 Lifecycle Services projects. Other examples are if one instance of a solution doesn't meet a global implementation's requirements for data residency, latency, or data volume, or when different business units are implementing the product separately as independent applications.

Each Dynamics 365 Lifecycle Services project must meet the minimum licensing requirement. The project team must distribute the total licenses at the tenant level to the individual Dynamics 365 Lifecycle Services projects, making sure that the number of licenses assigned across all projects doesn't exceed the total number of licenses purchased. To do so, after you determine the allocation, open the [Subscription estimator](/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/subscription-estimator) tool for each implementation project, and edit the active subscription estimate to allocate the licenses for that project.

[Learn more about using multiple Dynamics 365 Lifecycle Services projects](/dynamics365/fin-ops-core/dev-itpro/get-started/implement-multiple-projects-aad-tenant).

### Production environment and go-live assessment

When you're [preparing to go live](/dynamics365/fin-ops-core/fin-ops/imp-lifecycle/prepare-go-live), the first thing you need is access to your production environment. A production environment is deployed after all customizations are code-complete, UAT is done, the customer has signed off, and no blocking issues remain.

For a Finance, Supply Chain Management, and Commerce project, you won't have access to this environment on day one. Microsoft needs to complete a few prerequisites, including a go-live assessment, before we can release the production environment.

In a go-live assessment, a solution architect is assigned to review the project and provide an assessment of potential risks, best practices, and recommendations for a successful go-live. The solution architect might highlight risk factors and ask for a mitigation plan. When the assessment is done, the solution architect indicates that you're ready to request the production environment in Dynamics 365 Lifecycle Services.

> [!IMPORTANT]
> The production environment is used only for running your business operations. You shouldn't use it for testing. Moreover, the production environment isn't available until the go-live assessment is done, a stage in which most of the testing should already be done. You'll be able to perform the cutover and, if planned, "mock" the cutover in production.

### General recommendations

- Plan for environments early in the project because of the impact on the project's budget and timeline. Revisit the plan at regular intervals.

- Define a consistent naming standard for your environments. For example, a gold environment should have "gold" in the name.

- Have a regular schedule to deploy updates and import fresh data if needed.

- Keep all environments in the same region if your business is in one region. For example, avoid having a test environment in one geographical location and production in another.

- Deploy environments by using an unnamed account, such as `dynadmin@your\_organization\_name.com`. Assign the environments to an owner who is responsible for their status and maintenance. We strongly recommend using the same dedicated admin account in all environments.

### Test environments

- Consider the number of testing environments you'll need throughout the project. A lack of environments might prevent planned concurrent testing activities from taking place and delay the project.

### Training environments

- Make sure all users have access with appropriate roles and permissions, which should be the same roles and permissions they'll have in production.

- Plan for downtime and have a communication plan to alert users. Zero downtime is the eventual goal.

- Ensure all integrations are set up and working, so that users can experience the end-to-end cycle of a business process.

### Gold environment

- Make sure no transactions happen in a gold environment. You should have a process to bring tested configurations into the gold environment.

### Data migration environments

- Assess whether you need a dedicated environment for data migration, which is a disruptive task that can't generally coexist with other types of test activities. Multiple data migration environments might be needed to avoid conflicts if multiple parties are migrating data concurrently.

- Account for data migration performance in environment planning. Depending on the size of the data migration task, it might be necessary to use a tier 3 or higher environment to perform data migration testing.

### Pre-production environments

- Assess whether you need a separate environment to test code or configuration changes before they're applied to production.

- If development of the solution will continue after you go live, you might need a separate pre-production environment to support concurrent hotfix and hotfix test activities. This environment should have the same code base and data as production, so a like-for-like comparison can be performed for any new changes before they're applied to production.

### Performance testing environments

- Plan a specific environment for performance testing, or you won't be able to do performance testing activities in parallel with other test activities.

- Don't use a cloud-hosted environment for performance testing.

- Avoid doing performance testing in the production environment or lower tier environments.

- Use of tier 2 or tier 3 environments typically won't provide the resources required to perform a performance test. Limitations on the number of threads and database resources available in these environments don't allow for modeling of most concurrent workload profiles.

### Developer environments

- Ensure each developer has an independent development environment.

### Production environment

- If not available through self-service actions, raise production environment requests through support, because you don't have direct access to this environment.

## Product-specific guidance: Customer engagement apps

This section focuses on product-specific resources and considerations that apply to [Power Platform](/power-platform/admin/admin-mode) and [customer-engagement apps](/power-platform/admin/manage-apps).

### Environments and Dataverse in Power Platform

The resources of an environment that's created under a Microsoft Entra ID tenant can only be accessed by users within that tenant. An environment is bound to a geographic location, such as the United States. When you create an app in an environment, that app is routed only to datacenters in that geographic location. Any items that you create in that environment, including connections, gateways, and flows using Power Automate, are also bound to their environment's location. Every environment can have one Microsoft Dataverse database, which provides storage for your apps.

In the following example, Contoso Corp has chosen to have a production environment for each geography where it has a legal entity. Each production environment contains a Dataverse instance and the apps that employees of that legal entity need. User D is the only employee who has access to all three production environments.

:::image type="content" source="media/environments-dataverse-tenant.svg" alt-text="Organization chart under Microsoft Entra ID tenant, Contoso Corp, with three environments that contain a Dataverse database each." lightbox="media/environments-dataverse-tenant.svg":::

### Environment app strategy

If you're deploying multiple business apps on the Dynamics 365 platform, you need to decide on an environment strategy. Should all apps be deployed in the same environment? Or should each app have an environment of its own?

But environment policies shouldn't be created in isolation. If you don't consider the business requirements or understand the underlying data and integration dependencies, you might create a generic organization-wide policy, such as "Every application should use a separate environment" or "All applications should share a single environment," leading to unnecessary complexity and fragmentation. The data store for an application and the supporting business process plays a key role in your decision.

For instance, if multiple apps for different departments can benefit from using each other's data, a single environment with integrations can improve consistency and collaboration. The user experience can be tailored using dedicated apps for different personas and secure data access using the security model.

No standard answer or blanket approach will work for all apps within your organization. The best approach for you is the one that facilitates collaboration and cross-pollination of information between apps, while also reducing data silos and meeting your organization's security, compliance, and data protection requirements.

#### Multiple-app environment

In a multiple-app environment, a single production environment is used for multiple apps. For example, the production environment might have the Dynamics 365 Sales and Customer Insights - Journeys apps to facilitate collaboration between the marketing and sales teams and quick transfer of qualified leads to sales representatives. Similarly, having the Sales and Customer Service apps in the same environment gives the sales team insights into customer support experiences, which could affect ongoing deals.

The following diagram illustrates Contoso's choice to have one production environment with several Dynamics 365 apps installed:

:::image type="content" source="media/environments-multi-app.svg" alt-text="Diagram of a production environment for Contoso and bubbles with the names of five Dynamics 365 apps." lightbox="media/environments-multi-app.svg":::

With a multiple-app deployment, the app data, security models, and data models are in a common repository, allowing the apps to reuse any integrations. The security model design limits access to data for each app, with the individual apps defining the user experience. For example, the Sales and Customer Insights apps might use the same lead table, but security roles and the app definition control access to records, fields, and processes.

Let's examine some of the pros and cons of the multiple-app deployment model.

Pros of a multiple-app deployment model:

- It enables stronger collaboration between business teams by decreasing data silos.

- It reduces the number of environments to manage and the amount of effort needed for platform updates.

- It allows reuse of integrations, and its simpler design lowers API consumption while avoiding the need to sync data across environments.

- It simplifies reporting and the business intelligence architecture.

Cons of a multiple-app deployment model:

- Its security model could become complex, depending on access restrictions.

- Its ALM and release process needs to be coordinated for each app and will require full regression testing when changing shared components, making automation testing even more critical.

- Its capacity utilization for individual apps is more difficult to track.

- Its security, data models, or integrations, if poorly designed for one app, can affect other apps.

- It might have limitations on deploying several apps of the same type in a single environment. For example, you can't have several Power Apps portals with the same template in a single environment.

- It can't be used if you need to segregate the environments for a globally distributed user base due to performance, compliance regulations, or process differences.

#### Per-app environment

In a per-app deployment model, every application gets its own production environment, with a separate set of environments to support the underlying ALM and release process. The data, schema, and security model are completely isolated. A per-app environment might seem simpler from a deployment perspective, but it can create data silos that prevent business processes from easily benefiting from sharing information. This can lead to extra effort in building complex integrations.

The following diagram illustrates Contoso's choice to have three production environments and install a single Dynamics 365 app in each of them:

:::image type="content" source="media/environments-single-app.svg" alt-text="Diagram with three production environments for Contoso and a single Dynamics 365 app listed for each environment." lightbox="media/environments-single-app.svg":::

Since the security model is defined for each environment, you can't use the platform security constructs to define which data from one environment will be accessible to a user in a different environment.

Consider an example where the Sales and Customer Service apps are deployed in separate environments, and core customer records must be synchronized between them. Providing sales representatives with visibility into support experiences will require some level of integration, either by copying over the data periodically or integrating the visual user interface.

This approach might be more relevant for isolated functions that don't need data sharing and collaboration. For example, an internal HR ticketing system for employees has little to do with the sales process.

Network latency, compliance, and region-specific requirements could mandate the use of per-app environments, but will introduce data-replication challenges, integration redundancy, and increased costs for storage, integration, and maintainability.

Let's examine some of the pros and cons of the per-app deployment model.

Pros of a per-app deployment model:

- Its security model is separately managed for each app, which simplifies configuration when there's no need for data sharing between environments or development of custom security components.

- Its ALM and release process for each app can be independent.

- Its capacity utilization for individual apps can be tracked easily for cross-charging within the business.

- Any design issues in one app won't directly affect other apps.

- It's the preferred approach if you need to segregate the environments for a globally distributed user base due to network latency, compliance regulations, or process differences.

Cons of a per-app deployment model:

- It can create data silos between business units and departments, potentially reducing collaboration and value to the business.

- It means a linear increase in the number of environments to support ALM and the administration effort for platform updates for each app.

- It largely prevents reuse of integrations and is a potentially complex solution requiring data sync and complex custom security logic. In some cases, integrations aren't possible across several environments. For example, you can't sync users' Exchange mailboxes to several environments at the same time.

- It potentially brings higher API and storage costs due to data and integration redundancy.

- Its reporting and intelligence architecture will be more complex and require data unification in an external data store, such as a data lake.

### Administration and governance

The [Power Platform admin center](https://admin.powerplatform.microsoft.com/) provides a unified portal for administrators to [create and manage environments](/power-platform/admin/create-environment), including [sandbox environments](/power-platform/admin/sandbox-environments), [backing up and restoring environments](/power-platform/admin/backup-restore-environments), and [copying an environment](/power-platform/admin/copy-environment). Admins can also manage settings for Power Apps and Power Automate.

The [Microsoft Power Platform Center of Excellence (CoE) Starter Kit](/power-platform/guidance/coe/starter-kit) is a collection of components and tools to help you get started with developing a strategy for adopting and [administrating](/power-platform/admin/admin-documentation) Power Platform.

## Next steps

- Follow the [environment strategy checklist](environment-strategy-checklist.md)
- Read a [case study](environment-strategy-case-study.md) of a company that learned the importance of a good environment strategy
