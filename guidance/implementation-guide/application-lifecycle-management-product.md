---
title: Best practices for ALM in Dynamics 365 applications
description: Learn how to use application lifecycle management (ALM) tools and best practices to develop, test, and deploy Dynamics 365 solutions.
author: abunduc-ms
ms.author: abunduc
ms.date: 01/19/2024
ms.topic: conceptual
ms.custom:
  - ai-seo-date: 01/19/2024
  - ai-gen-docs-bap
  - ai-gen-title
  - ai-gen-desc
content_well_notification: AI-contribution
---

# Best practices for ALM in Dynamics 365 applications

Do you want to create and maintain high-quality Dynamics 365 apps that meet your business needs? If so, you need a good application lifecycle management (ALM) strategy. ALM is the process of planning, developing, testing, and deploying your apps. It helps you improve every aspect of your apps, from design and functionality to performance and security.

In this article, you'll learn about the tools and best practices for ALM in Dynamics 365. You'll discover how to use solutions, environments, Azure DevOps, and other tools to manage your apps efficiently and effectively. You'll also find out how to apply ALM to different types of apps, such as finance and operations apps and customer engagement apps.

## Team responsibility

ALM involves various team members with different roles and responsibilities, such as the project manager, the developer, the tester, and the customer. Each team member should own and maintain the processes and tools they use for ALM. For instance, the project manager should own and maintain the project plan, and the tester should own and maintain the test plan. You should also collaborate with other teams to ensure consistent and effective ALM practices.

### Azure DevOps

Azure DevOps is a cloud-based platform that provides services and tools for ALM. You can use Azure DevOps to manage your ALM practices and processes, such as work items, source code, version control, build automation, release pipelines, project management, test management, and bug tracking. Azure DevOps includes standard templates that you can use to manage your projects. You can also build custom templates to meet your specific needs.

## Finance and operations apps

Finance and operations apps are enterprise resource planning (ERP) apps that help you manage your finances, operations, and supply chain. This section offers recommendations and considerations for implementing ALM for finance and operations apps.

### Dynamics 365 Lifecycle Services

Dynamics 365 Lifecycle Services is a cloud-based solution that helps you manage your finance and operations apps throughout their lifecycle. Lifecycle Services lets you collaborate with your team members, partners, and Microsoft. You can use Lifecycle Services to manage your project from presales through implementation to the operate phase. Lifecycle Services provides various checklists and tools to help you manage your project efficiently, such as:

- A single location for all your projects
- [Project onboarding](/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/project-onboarding)
- [Project methodologies](/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/create-methodology)
- [Azure DevOps configuration](/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/project-onboarding#configure-azure-devops)
- [Business process modeler](/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/bpm-overview)
- [Cloud-hosted environments](/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/ax-2012/cloud-hosted-environments-lcs)
- [Data application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/database/dbmovement-operations)
- [Management of Microsoft support](/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/cloud-powered-support-lcs)
- [Customization analysis](/dynamics365/fin-ops-core/dev-itpro/dev-tools/customization-analysis-report)<!--Subscription estimator-->
- [Issue search](/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/issue-search-lcs)
- [Continuous updates](/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/download-hotfix-lcs)
- [Service requests to Dynamics Service Engineering](/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/submit-request-dynamics-service-engineering-team)
- [Environment monitoring and diagnostics](/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/monitoring-diagnostics)
- [Asset library](/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/asset-library)

The goal of Lifecycle Services is to deliver the right information, at the right time, to the right people. It helps you ensure repeatable, predictable success with each rollout of an implementation, update, or upgrade.

### Business process modeler

Business process modeler (BPM) is a tool that helps you define, view, and edit the business processes of your finance and operations apps. Business processes are the underlying foundation for app configuration and development. BPM lets you review your processes, track the progress of your project, and sync your business processes and requirements to Azure DevOps. You can use BPM to model your business processes based on the out-of-the-box processes provided by Dynamics 365, or customize them according to your specific needs.

### Development

The development phase of ALM involves writing, testing, and merging source code for your customizations and independent software vendor (ISV) solutions. You can use Microsoft Visual Studio as the development environment for your finance and operations apps. The development lifecycle includes the following steps:

- Each developer uses their own development environment.
- Developers write source code and check in their code to Azure DevOps.
- Developers also sync code from source control to get source code from other developers.
- Source code can be merged to working branches depending on the branching strategy.
- The build takes the source code from Azure DevOps, uses the build definition, and creates a deployable package.
- The build pipeline pushes the deployable package to the Lifecycle Services asset library.
- Azure release pipelines work with Visual Studio to simplify deploying packages to user acceptance testing (UAT).
- When UAT is complete, the deployable package is marked as a release candidate to deploy to production.
- The marked release candidate is deployed to production as a self-service action.

The following diagram illustrates the finance and operations app development lifecycle, with developer, build, testing, and production environments, and Azure DevOps and Lifecycle Services as the tools for ALM:

:::image type="content" source="media/application-lifecycle-management-fo-development-lifecycle.svg" alt-text="Diagram of the finance and operations apps development lifecycle." lightbox="media/application-lifecycle-management-fo-development-lifecycle.svg":::

### Version control

Version control is the process of storing and maintaining source code for your customizations and ISV solutions. You can use Azure Repos as the version control management tool for your code. Version control helps you track changes, resolve conflicts, and collaborate with other developers. Here are some recommendations for version control branching:

- Consider using the minimum branching option.
- Consider the following recommended branching strategy:
  - **Development**: Developer check-in and testing with development data (Trunk/Dev)
  - **Test**: Deploying to the tier 2+ and testing with current production data (Trunk/Main)
  - **Release or Release XX**: Retesting in the tier 2+ and deploying to production (Trunk/Release) or v-next (Trunk/Release XX)
- Run the Customization Analysis Report tool to check best practices and resolve errors and warnings.
- Use the shelve command or suspend changes to keep work safe.
- Request a code review to ensure code quality.
- Check in code when a feature is complete.
- Merge each feature in a separate changeset.
- Don't check in code directly to the test or release branches.
- Don't check in changes for more than one feature in a single changeset.
- Don't mark deployable packages from the development and test branches as release candidates.
- Don't merge untested features into the release branch.

The following figure illustrates a recommended branching strategy, with a branch for each release, a development branch, and a code upgrade branch all branching from the main branch:

:::image type="content" source="media/application-lifecycle-management-fo-branching.svg" alt-text="Diagram of finance and operations apps branching." lightbox="media/application-lifecycle-management-fo-branching.svg":::

[Learn more about developing and customizing apps](/dynamics365/fin-ops-core/dev-itpro/dev-tools/developer-home-page).

### Build automation

Build automation is the process of creating deployable packages from source code automatically and regularly. Build automation helps you speed up your implementation and ensure consistent and reliable results. You can use Azure DevOps to create and configure build definitions and triggers for your finance and operations apps. The Azure DevOps build system provides the following triggers for builds:

- Scheduled builds, such as nightly at 6:00 PM
- Continuous integration, such as starting a build as soon as code is checked in and gated check-in
- Manual builds (on demand)

Here's a checklist to ensure your build goes smoothly:

- Make sure the code compiles without errors.
- Don't use build environments for development activities.
- Create a build definition for each branch and for each build trigger.
- Consider using continuous integration or gated check-in build triggers.
- Perform automated testing after successful builds.
- Create a single deployable package that contains all packages.
- Don't use Visual Studio to create a deployable package, for the following reasons:
  - Deployable packages contain all the code on the development machine, including experimental code and incomplete features.
  - Deployable packages might not include all the modified packages, which means they're not independent and testing results could vary.
- Create a deployable package with a build machine so it's self-contained and contains all applicable modules.
- Make sure to keep service updates on the build machine less than or equal to production.
- Follow a consistent naming convention for your deployable package.

To learn more about build automation, check out the following guides:

- [Deploy and use a continuous build and test automation environment](/dynamics365/fin-ops-core/dev-itpro/perf-test/continuous-build-test-automation)
- [Create a build automation that uses Microsoft-hosted agents and Azure Pipelines](/dynamics365/fin-ops-core/dev-itpro/dev-tools/hosted-build-automation)
- [Update model versions in an automated build](/dynamics365/fin-ops-core/dev-itpro/dev-tools/version-models-build)
- [Create deployable packages in Azure Pipelines](/dynamics365/fin-ops-core/dev-itpro/dev-tools/pipeline-create-deployable-package)

### Automated testing

Automated testing is the process of running tests on your finance and operations apps without manual intervention. Automated testing helps you reduce the time and cost of testing, improve the quality and reliability of your apps, and keep up with the innovation and changes in your solution. You can use different tools and frameworks to perform automated testing for your finance and operations apps, such as:

- Unit and component-level testing using the SysTest framework
- Automated testing using [automation testing solutions](testing-regression-tooling.md)

To perform automated testing, you need to create test cases, test scripts, test data, and test plans. You also need to integrate your testing tools with Azure DevOps and Lifecycle Services to run and monitor your tests. You can use the BPM tool to generate test cases and test scripts from your business processes.

[Learn more about testing and validation](/dynamics365/fin-ops-core/dev-itpro/perf-test/testing-validation).

### Deployment

Deployment is the process of applying deployable packages to your environments. Deployable packages are units of deployment that contain the customizations and ISV solutions for your apps. Deployment can be manual or automated, depending on the type of environment and the tools you use. Here are some of the key concepts and best practices for finance and operations apps deployment:

- Deployable package: A unit of deployment that can be applied in an environment

- Deployment runbook: A series of steps that are generated to apply the deployable package to the target environment

- AX Installer: Creates a runbook that enables installing a package

You can deploy a package manually or through automated deployment. (Automated deployment doesn't apply to production environments.) We recommend the following steps when you deploy finance and operations apps:

- Consider using automated deployment to achieve continuous deployment.
- Make sure that the deployable package that should be applied is valid.
- Make sure that the package is applied in a sandbox environment before it's applied in the production environment.
- If you want to apply multiple packages, create a merged all-in-one package that can be applied first in a sandbox environment and then in the production environment.
- Production deployment is manual. After successful UAT, mark the deployable package as a release candidate and schedule a service request with the Dynamics Service Engineering team.
- Clean up the old deployable package periodically from the Lifecycle Services asset library.

For more information about deployment, see the following guides:

- [Create deployable packages in Azure Pipelines](/dynamics365/fin-ops-core/dev-itpro/dev-tools/pipeline-create-deployable-package)
- [Apply updates to cloud environments](/dynamics365/fin-ops-core/dev-itpro/deployment/apply-deployable-package-system)
- [Troubleshoot package application issues](/dynamics365/fin-ops-core/dev-itpro/deployment/deployable-package-troubleshooting)
- [Uninstall a package](/dynamics365/fin-ops-core/dev-itpro/deployment/uninstall-deployable-package).

### One Version service updates

One Version is the service update model for finance and operations apps that ensures all customers are on the same version of Dynamics 365, with access to the latest capabilities and bug fixes. One Version eliminates the need for large and costly upgrades and helps you stay current and compliant with your apps. You can use Lifecycle Services to manage your service updates and schedule them according to your preferences and business needs.

[Learn more about One Version service updates](/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/oneversion-overview). [Read the One Version service updates FAQ](/dynamics365/fin-ops-core/fin-ops/get-started/one-version).

## Customer engagement apps

Customer engagement apps are customer relationship management (CRM) apps that help you manage your sales, service, marketing, and other customer-facing activities. To implement ALM for customer engagement apps, you need to use solutions, environments, Azure DevOps, and other tools. Here are some of the key aspects of ALM for customer engagement apps:

### Solutions

Solutions are the mechanism for implementing ALM in Power Platform apps. They're vehicles that distribute components across different environments. A component represents what can be customized within the solution, such as site maps, applications, the components of the data model, forms, charts, and plug-ins.

### Solution publishers

Solutions have a [publisher](/power-platform/alm/solution-concepts-alm#solution-publisher) associated with them. The publisher defines the prefix associated with newly created components and allows you to easily recognize who developed them. You should use one custom publisher for all components and give it a meaningful name, such as your company's initials. You should avoid using the default solution and create your own instead.

Often, solution boundaries are defined based on functional needs, such as a sales solution or a service solution that depend on a common core solution. Sometimes, you might need to move components between these solutions. For example, you might want to move a component from the service solution to the core solution. The best practice is to create a common core solution and move the shared components to it. If different solution publishers have been used between the solutions, you can't share the component without deleting and recreating the component.

Consider the following structure:

| Solution | Managed Solution Publisher | Entity | Entity |
|-|-|-|-|
| Service (v 1.0.0.0) | Service Team (prefix: svc) | svc_X1 | svc_X2 |
| Sales (v 1.0.0.0) | CompanyA (prefix: cpya) | cpya_Y1 | cpya_Y2
| Core (v 1.0.0.0) | CompanyA (prefix: cpya)| Account | Contact

The core solution extends the Account and Contact entities. Both the sales and service solutions depend on these components. The service solution has a unique publisher. If you want to move component `svc\_X2` to the core solution, you can't do it directly, because the service solution still references it. You also can't create an identical component in the core solution, because the different publisher would cause a conflict on import.

The only option left is to create a new component within the core solution, using a holding solution technique to delete the original component from the service solution and optionally migrate the data between the two components.

You might also need to remove and create relationships to the entity being moved, which can be a complex process to maintain data integrity within a live production environment.

The sales solution uses the same publisher as the core solution. You can easily move component `cpya\_Y2` as an unmanaged component to the core solution and remove it from the sales solution within the development environment. The solutions can then be reimported into production. The component continues to exist because the solution publisher keeps a reference count of one or more to the component throughout the process.

The best practice is to keep the number of publishers to a minimum.

### Managed vs. unmanaged solutions

Solutions can either be managed or unmanaged. Use unmanaged solutions in development environments while changes are still underway. Use managed solutions to deploy to any environment that isn't a development environment.

The following table highlights some of the important differences between unmanaged and managed solutions.

| Unmanaged solution | Managed solution |
|-------------------------|-------------------------|
| Acts as a container of customizations that exist on top of the system and other managed solutions | A "version complete" unmanaged solution that has been exported as managed |
| "Open" | "Closed" |
| Allows direct customization of components | The identity of the solution can't be modified |
| Holds references to customization and components but doesn't own them | Components can't be added or removed |
| Doesn't delete or remove components if the solution is deleted | Can be uninstalled (deleted) and deletes components that it directly owns |
|| Can be upgraded and serviced as discrete layers, enabling ISVs or multiple departments to provide multiple applications to a shared environment |
|| Merges with other layers and the system layers to present application behavior to the user |
|| Exists within its own discrete layer |

Managed solutions create layers on a per-component basis. They can also extend and take dependencies on other managed solutions. Both the import order and the dependencies between managed solutions influence the layering order of the managed solutions.

Unmanaged solutions don't create any layers. They're simply containers to logically group unmanaged component customizations and when imported, add the contained unmanaged component customizations to the unmanaged layer. Unmanaged component customizations override any equivalent managed component customization introduced by managed solutions that layer beneath them.

### Solution layering

Layering occurs on import of solutions when a specific component is affected by change within one or more solutions. Layers describe the dependency chain of a component from the root solution that introduces it, through each solution that extends or changes the component's behavior. Layers are created through extension of an existing component (taking a dependency on it) or through creation of a new component or version of a solution. Examples include:

- Extending a managed Dataverse component, which takes a dependency on the component
- Extending a managed component from a Microsoft app, which takes a dependency on the component from the solution that represents the app
- Extending a managed component from an ISV solution or custom solution or app
- Introducing a new custom component in a custom managed solution, which creates the component and so the root layer for that component
- Amending properties of an existing component within a different managed solution

In the following example, the column length was originally 1,024. When Managed Solution A was imported, the column was truncated to 128. After importing Managed solution B, the column was increased to 4,096. The unmanaged solution layer was then updated to 65,536, which is what the user experiences.

:::image type="content" source="media/application-lifecycle-management-ce-solution-layering.svg" alt-text="Illustration of the effect of solution layering." lightbox="media/application-lifecycle-management-ce-solution-layering.svg":::

The example is only meant as an illustration that column lengths shouldn't be changed frequently in the solutions, because it can cause data to be truncated. Also, the unmanaged layer shouldn't be directly updated. Managed solutions should be deployed instead.

Use [connection references](/powerapps/maker/data-platform/create-connection-reference) and [environment variables](/powerapps/maker/data-platform/environmentvariables) to define information about a connector or to store parameter keys and values. This streamlines the process of migrating the solutions between environments.

You should have a good understanding of solution concepts in Power Platform. The solution is the baseline for the components across their lifecycle. [Learn more about solution concepts](/power-platform/alm/solution-concepts-alm).

### Environment strategy

The number of solutions that are used to deliver an app affects the number of Dynamics 365 environments you need to build and maintain them. You also need to consider that after an app is live, you need to support the next version of the app in parallel with the current version. This might require more environments. [Learn more about environment strategy for Dynamics 365 apps](environment-strategy-overview.md).

Consider the scenario where an app consists of a single solution. Version 1 of the app is implemented and released to production, as shown in the following illustration.

:::image type="content" source="media/application-lifecycle-management-ce-solution-release1.svg" alt-text="Illustration of Solution A version 1 released as a managed solution from a development environment to production." lightbox="media/application-lifecycle-management-ce-solution-release1.svg":::

The development environment is preserved to support any necessary patching of the live app. In parallel, another development environment is required to start work on version 2 of the app. Patches to version 1 are incorporated with enhancements for version 2 by propagating as unmanaged changes between development environments, as shown in the following illustration.

:::image type="content" source="media/application-lifecycle-management-ce-solution-release2.svg" alt-text="Illustration of Solution A version 1 and version 2 released to production." lightbox="media/application-lifecycle-management-ce-solution-release2.svg":::

When version 2 of the app is complete and released to production, the development environments are rotated. Dev\_2 is preserved to support any necessary patching of the live app and Dev\_1 is recycled to start work on version 3 of the app in parallel.

Let's expand the scenario to consider an app that consists of two solutions, one dependent on the other. In this case, you'll need four development environments. For example, you have a core solution, with a regional variant solution dependent on the core solution. The previous single solution example showed that two development environments are required to maintain version 1 of the core solution in production, while version 2 is being implemented in parallel. Since the regional solution has a dependency on the core solution, a third environment is required to support the dependency by importing the managed version of the core solution, as shown in the following illustration.

:::image type="content" source="media/application-lifecycle-management-ce-solution-release3.svg" alt-text="Illustration of the release of a solution with dependencies." lightbox="media/application-lifecycle-management-ce-solution-release3.svg":::

Finally, the regional variations might be implemented on a different timeline than the core solution. This introduces a need for a fourth environment to support version 2 of the regional solution to be implemented while version 1 is maintained in live use.

### Tools

Dynamics 365 and Power Platform offer several tools that can help you automate and streamline the ALM process for your customer engagement apps. These tools can help you increase efficiency, reduce manual work, and avoid human errors when working with solutions throughout their lifecycle.

For instance, the [ALM Accelerator for Makers](https://github.com/microsoft/coe-starter-kit/tree/main/ALMAcceleratorForMakers) can expedite your ALM setup. It's a prebuilt application that provides a starting point for automating your solution version control and migrations between environments.

Tools such as Azure DevOps and GitHub provide developer services that support the activities required to plan, store, collaborate, build, and deploy. This includes synchronization of solution metadata between development environments and your version control system, generating build artifacts, deploying to downstream environments, provisioning or deprovisioning environments, and performing static analysis checks against your solution using the Power Apps checker service. Consider using the [Power Apps Build tools](/power-platform/alm/devops-build-tools) or [GitHub actions](/power-platform/alm/devops-github-actions) as building blocks in creating your pipelines.

Other tools include:

- A version control system is a software tool that helps you record changes to files by keeping track of changes committed to software code. A version control system is a database of changes, which contains all the edits and historical versions of a software project. Version control systems allow you to maintain a single source of truth and recall specific versions when needed. Git and GitHub are popular examples of version control applications.

- The configuration migration tool lets you [move configuration and reference data across environments](/power-platform/admin/manage-configuration-data). Configuration and reference data is data that is stored as records in Dataverse but that supports various aspects of the app, such as currencies, portal configuration, and lookup values.

- The package deployer lets you [deploy comprehensive packages](/powerapps/developer/common-data-service/package-deployer/create-packages-package-deployer) of relevant assets to Dataverse environments. Packages can consist of not only solution files, but also flat files, custom code, and HTML files. You can automate the execution of the package deployer with the [DevOps build tools task Deploy package](/power-platform/alm/devops-build-tool-tasks#solution-tasks).

-The solution packager can [unpack or pack a compressed solution file](/power-platform/alm/solution-packager-tool) into multiple XML files and other files or vice versa, so that they can be easily managed by a source control system or be deployed to an environment from source control. You can automate the execution of this tool with [DevOps build tools tasks](/power-platform/alm/devops-build-tool-tasks#solution-tasks).

- The [Power Apps CLI](/powerapps/developer/common-data-service/powerapps-cli) is a simple, single-stop developer command-line interface for creating code components. You can also use this interface to automate the deployment of portal configurations.

- [PowerShell cmdlets](/powershell/powerapps/overview) for administrators, app makers, and developers allow you to automate monitoring, management, and quality assurance tasks that are possible through the Power Apps admin center user interface.

- [Test Studio](/powerapps/maker/canvas-apps/test-studio) helps you ensure the quality of your canvas apps.

- Use [automated regression solutions](testing-regression-tooling.md) to generate test scripts that can be used to regression test changes to your model-driven apps.

- Use [performance insights](/power-platform/admin/analyze-improve-data-query-performance) to analyze runtime user data and provide recommendations.

## Next steps

- Plan your ALM strategy with the [ALM workshop](application-lifecycle-management-workshop.md)
- Review the [ALM Success by Design checklist](application-lifecycle-management-checklist.md)
- Read a [case study](application-lifecycle-management-case-study.md) about a global transport systems company that found its ALM strategy to be a cornerstone of implementation

### See also

- [Microsoft Power Platform build tools for Azure DevOps](/powerapps/developer/common-data-service/build-tools-overview)
- [Power Apps build tools for Azure DevOps](https://devblogs.microsoft.com/premier-developer/power-apps-build-tools-for-azure-devops/)
- [Key concepts for new Azure Pipelines users](/azure/devops/pipelines/get-started/key-pipelines-concepts)
