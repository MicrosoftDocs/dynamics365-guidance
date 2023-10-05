---
title: ALM strategy for Dynamics 365 solutions
description: Get guidance for aspects of the application lifecycle management (ALM) strategy specific to Dynamics 365 applications.
author: abunduc-ms
ms.author: abunduc
ms.date: 03/31/2023
ms.topic: conceptual

---

# ALM strategy for Dynamics 365 solutions

Application lifecycle management (ALM) can improve every aspect of your Dynamics 365 solution. Dynamics 365 offers various tools to achieve a successful ALM in your implementation.

## Team responsibility

Various team members are involved in an implementation, with separate roles and responsibilities. Multiple teams such as the customer, partner, and ISV work are involved and must work together.

Every team member, either directly or indirectly involved, should own the ALM maintenance of the processes and tools they're using. For example, the project manager owns and maintains the project plan, and the tester owns and maintains the test plan. You should also have cross-team collaboration for maintaining ALM practices.

## Azure DevOps

Microsoft recommends using Azure DevOps or GitHub as the tool for managing or maintaining your ALM practices and processes. For some areas of Dynamics 365 (such as finance and operations apps), Azure DevOps is the only version control tool.

In addition to the standard templates in Azure DevOps, you can build your own custom templates according to your business needs. Azure DevOps lets you store all your work items, including features, user stories, requirements, tasks, bugs, and more.

A standard lifecycle is available for each work item, and you can build your own custom states and rules for each type of work item.

Dynamics 365 also recommends Azure Repos as the version control management tool for your code. You can achieve build automation and release pipelines using build definitions and release definitions.

You can also use Azure DevOps for project management, test management, bug tracking, release management, and many more aspects of your implementation.

## Finance and operations apps

In this section, we provide some of the finance and operations apps recommendations to achieve an efficient ALM in your solution. We'll cover things such as Microsoft Dynamics Lifecycle Services, business process modeling, development, and version control.

### Dynamics 365 Lifecycle Services

Dynamics 365 Lifecycle Services is a cloud-based solution in which all participants (customer, partner, and Microsoft) work collaboratively. You manage your implementation from pre-sales, through implementation, and finally the *Operate* phase. Lifecycle Services provides various checklists and tools to help you manage your project efficiently:

- A single location for all your projects

- [Project onboarding](/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/project-onboarding)

- [Project methodologies](/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/create-methodology)

- [Azure DevOps configuration](/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/project-onboarding#configure-azure-devops)

- [Business process modeler (BPM)](/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/bpm-overview)

- [Cloud-hosted environments (CHE)](/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/ax-2012/cloud-hosted-environments-lcs)

- [Data application lifecycle management (DataALM)](/dynamics365/fin-ops-core/dev-itpro/database/dbmovement-operations)

- [Management of Microsoft support](/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/cloud-powered-support-lcs)

- [Customization analysis](/dynamics365/fin-ops-core/dev-itpro/dev-tools/customization-analysis-report)<!--Subscription estimator-->

- [Issue search](/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/issue-search-lcs)

- [Continuous updates](/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/download-hotfix-lcs)

- [Service requests to Dynamics Service Engineering (DSE)](/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/submit-request-dynamics-service-engineering-team)

- [Environment monitoring and diagnostics](/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/monitoring-diagnostics)

- [Asset library](/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/asset-library)

The goal of Lifecycle Services is to deliver the right information, at the right time, to the right people. It helps ensure repeatable, predictable success with each rollout of an implementation, update, or upgrade.

### Business process modeler

Business process modeler (BPM) provides abstract explanations of your solution's business processes. Business processes are the underlying foundation for application configuration and application development.

Effective ALM provides defined, documented, and templated processes to follow in your implementation. Model your business processes in Dynamics 365 finance and operations apps with the BPM tool.

Use the BPM tool to define, view, and edit the finance and operations apps out-of-box business processes (in the form of libraries). Then, use the information in future implementations. The tool helps you review your processes, track the progress of your project, and sync your business processes and requirements to Azure DevOps.

Every business is different in some ways; this tool helps you align your business processes with your industry-specific business processes and best practices. BPM libraries provide a foundation for your business process, and you can add, remove, and edit your processes according to your solution requirements.

### Development

In finance and operations apps, Microsoft Visual Studio is used as the development environment. The development lifecycle includes the following steps:

- Each developer uses their own development environment

- Developers write source code and check in their code to Azure DevOps

- Developers also sync code from Source Control to get the source code from other developers

- Source code can be merged to respective branches depending on the branching strategy

- The build takes the source code from Azure DevOps, uses the build definition, and creates a deployable package

- The build pipeline also pushes the deployable package to the Lifecycle Services asset library

- Azure release pipelines work with Visual Studio to simplify deploying packages to UAT

- When UAT is complete, the deployable package is marked as a release candidate to deploy to production

<!-- The original text is not correct anymore - see below>
- The Dynamics Service Engineering (DSE) team deploys it to production using a service request from Lifecycle Services
<-->

- The marked release candidate is deployed to production as a Self-service action

:::image type="content" source="media/application-lifecycle-management-fo-development-lifecycle.png" alt-text="Finance and operations apps development lifecycle." lightbox="media/application-lifecycle-management-fo-development-lifecycle.png":::

### Version control

The primary purpose of version control is storing and maintaining source code for customizations and ISV solutions. You develop against local, XML-based files (not the online database), which are stored in version control tools such as Azure DevOps. The following are recommendations for version control branching:

- Consider using minimum branching option

- Consider the following recommended branching strategy:
  
  - Development Developer check-in and testing with development data (Trunk/Dev)
  - Test Deploying to the tier 2+ and testing with current production data (Trunk/Main)
  - Release or Release XX Retesting in the tier 2+ and deploying to production (Trunk/Release) or v-next (Trunk/Release XX)

- Run Customization Analysis Report (CAR) tool to check best practices and resolve errors and warnings

- Use the shelve command or suspend changes to keep work safe

- Request a code review to ensure code quality

- Check in code when a feature is complete, and include changes from one feature in each changeset

- Merge each feature in a separate changeset

- Don't check in code directly to the test or release branches

- Don't check in changes for more than one feature in a single changeset

- Don't mark deployable packages from the development and test branches as release candidates

- Don't merge untested features into the release branch

Figure below illustrates a recommended branching strategy.

:::image type="content" source="media/application-lifecycle-management-fo-branching.png" alt-text="Finance and operations apps branching.":::

For more information, check the [Develop and customize home page](/dynamics365/fin-ops-core/dev-itpro/dev-tools/developer-home-page).

### Build automation

Speed is essential for rapid implementation, and build automation is the key to achieving this speed.

The build process is mandatory for any code to run. This process involves compiling the source code and producing binary files (assemblies). A database sync also requires a build first because the schema is retrieved from the assemblies (and not the XML files).

The Azure DevOps build system provides the following triggers for builds:

- Scheduled builds, such as nightly at 6 PM

- Continuous integration, such as:

  - Starting a build as soon as code is checked in
  - Gated check-in

- Manual builds (on demand)

Here's a checklist to ensure your build goes smoothly:

- Make sure the code compiles without errors

- Don't use build environments for development activities

- Create a build definition for each branch and for each build trigger

- Consider using continuous integration or gated check-in build triggers

- Perform automated testing after successful builds

- Create a single deployable package that contains all packages

- Don't use Visual Studio to create a deployable package, for the following reasons:

  - Deployable packages contain all the code on the development machine, including experimental code and incomplete features
  - Deployable packages may not include all the modified packages, which means they're not independent and testing results could vary

- Create a deployable package with a build machine so it's self-contained and contains all applicable modules

- Make sure to keep service updates on the build machine less than or equal to production

- Follow a consistent naming convention for your deployable package

To learn more about build automation, check out our guides on how to:

- [Deploy and use a continuous build and test automation environment](/dynamics365/fin-ops-core/dev-itpro/perf-test/continuous-build-test-automation)

- [Create a build automation that uses Microsoft-hosted agents and Azure Pipelines](/dynamics365/fin-ops-core/dev-itpro/dev-tools/hosted-build-automation)

- [Update model versions in an automated build](/dynamics365/fin-ops-core/dev-itpro/dev-tools/version-models-build)

- [Create deployable packages in Azure Pipelines](/dynamics365/fin-ops-core/dev-itpro/dev-tools/pipeline-create-deployable-package)

### Automated testing

As part of development ALM, testing automation should be in place to achieve fast-moving code from development to deployment. In finance and operations apps, you can integrate testing and validation two different ways:

- Unit and component level testing using SysTest framework

- Automated testing using **Task recorder** and the **Regression suite automation tool** (RSAT)

To keep up with innovation and constant changes in your solution, it's critical to invest and build in continuous validation. It takes different components as shown below.

:::image type="content" source="media/application-lifecycle-management-automated-testing.png" alt-text="Finance and operations apps automated testing.":::

The RSAT significantly reduces the time and cost of UAT for finance and operations apps. RSAT lets functional super users record business tasks by using Task recorder and converting the recordings into a suite of automated tests, without having to write source code.

Learn more at the following tutorials in the product docs:  

- [Testing and validations](/dynamics365/fin-ops-core/dev-itpro/perf-test/testing-validation)  
<!--- [Using the regression suite automation tool](/dynamics365/fin-ops-core/dev-itpro/perf-test/rsat/rsat-overview)  
- [Acceptance test library resources](/dynamics365/fin-ops-core/dev-itpro/perf-test/acceptance-test-library)  -->

### Deployment

Let's review the key concepts for finance and operations apps deployment:

- Deployable package:  

  A unit of deployment that can be applied in an environment

- Deployment runbook  

  A series of steps that are generated to apply the deployable package to the target environment

- AX Installer  

  Creates a runbook that enables installing a package

You can deploy a package manually or through automated deployment (which isn't applicable to production). We recommend the following steps when you deploy finance and operations apps:

- Consider using automated deployment to achieve continuous deployment.

- Make sure that the deployable package that should be applied is valid.

- Make sure that the package is applied in a sandbox environment before it's applied in the production environment.

- If you want to apply multiple packages, create a merged all-in-one package that can be applied first in a sandbox environment and then in the production environment.

- Production deployment is manual. After successful UAT, mark the deployable package as a release candidate and schedule a service request with the DSE team.

- Clean up the old deployable package periodically from the Lifecycle Services asset library.

For more information about automated testing, we offer tutorials on [Download assets by using Azure Pipelines](/dynamics365/fin-ops-core/dev-itpro/dev-tools/pipeline-asset-download), [All-in-one deployable packages](/dynamics365/fin-ops-core/dev-itpro/dev-tools/aio-deployable-packages) and [Deploy assets by using Azure Pipelines](/dynamics365/fin-ops-core/dev-itpro/dev-tools/pipeline-deploy-asset).

### One Version (Continuous Updates)

Some years ago, there were concerns regarding how to keep the environment up to date with the latest features and bug fixes. Customers were using different versions and upgrading to latest version was a hefty task. Now, once you're live in production, you no longer have large upgrade implementations ahead of you.

With One Version, all customers benefit from being on the same version with access to the latest capabilities available, and no one is stuck on less capable older versions.

Learn more at [One Version service updates overview](/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/oneversion-overview). Find many of your questions answered here: [One Version service updates FAQ](/dynamics365/fin-ops-core/fin-ops/get-started/one-version).

## Customer engagement apps

When organizations implement their cloud solution, some level of customization and extensibility typically exists. The goal is to provide more value and adjust the functionalities to specific business or industry needs.

The following concepts are important to understanding ALM when using the Power Platform.

### Solutions

Solutions are the mechanism for implementing Dev ALM in Power Platform apps. They're vehicles that distribute components across different environments.

A component represents what can be customized within the solution, such as site maps, applications, the components of the data model, forms, charts, or plug-ins.

### Solution publishers

Solutions have a [publisher](/power-platform/alm/solution-concepts-alm#solution-publisher) associated with them. The publisher defines the prefix associated with newly created components and allows you to easily recognize who developed the components. One custom publisher should be used for all components and should have a meaningful name such as the company's initials. It's best not to use the default solution but instead to create your own.

Often solution boundaries are defined based on functional need, for example a sales solution, a service solution both taking a dependency on a common core solution. Sometimes there's a need for components to be moved between these solutions. For example, a component in the Service solution is also needed in the Sales solution. The best practice is to create a Common Core solution and move the shared components to this solution. If different solution publishers have been used between the solutions, they can't share the component without deleting and recreating the component. Consider the following structure:

:::image type="content" source="media/application-lifecycle-management-multiple-publishers.png" alt-text="Three components with two different publishers.":::

The Core solution extends the Account and Contact entities. Both the Sales and Service solutions depend on these components.

The Service solution has a unique publisher. Assuming component `svc\_X2` was determined to be common, you can't move it directly into the Core solution, because the Service solution maintains a reference to it. You can't create an identical component directly in the Core solution as it would flag a conflict on import due to the fact it was introduced by a different publisher.

The only approach remaining is to introduce a new component within the core solution, using a holding solution technique to delete the original component from the service solution and "optionally" conduct a data migration between the two components.

> [!NOTE]
> It's likely there would be more work to remove any relationships to the entity being removed and to create new relationships to the entity being created. This way, it's a complex process to maintain data integrity within a live production environment.

The Sales solution uses the same publisher as the Core solution. `cpya\_Y2` can then easily be moved as an unmanaged component to the core solution and be removed from the Sales solution within the development environment. The solutions can then be reimported into production. The component will continue to exist given the solution publisher maintains a reference count of one or greater to the component throughout the process. The best practice is to keep the number of publishers to a minimum.

### Managed vs. unmanaged solutions

Solutions can either be managed or unmanaged. Use unmanaged solutions in development environments while changes are still underway. Use managed solutions to deploy to any environment that isn't a development environment. The table below highlights some of the important differences between unmanaged and managed solutions:

| Unmanaged solution | Managed solution |
|-------------------------|-------------------------|
| Acts as a container of customizations that exist on top of the system and other managed solutions| A "version complete" unmanaged solution that has been exported as managed|
| Unmanaged solutions are "Open"| Managed solutions are "Closed"|
| They allow direct customization to components| The identity of the solution can't be modified|
| They hold references to customization and components but don't own them | Components can't be added or removed|
| They don't delete or remove components if the solution is deleted | They exist within their own discrete layer|
|| They can be upgraded and serviced as discrete layers enabling ISV's or multiple departments to provide multiple applications to a shared environment|
||They merge with other layers and the system layers to present application behavior to the user|
||They can be uninstalled (deleted) and they do delete components that they directly own|

Managed solutions create layers on a per-component basis. They can also extend and take dependencies upon other managed solutions. Both the import order and the dependencies between managed solutions will influence the layering order of the managed solutions.  

> [!IMPORTANT]
> Note when two or more managed solutions with no interdependencies contain a reference to a common component. In such circumstances, the import order may change the layering order, potentially leading to unintended application behavior.

Unmanaged solutions don't create any layers. They're simply containers to logically group unmanaged component customizations and when imported, will add the contained unmanaged component customizations to the unmanaged layer. Importantly, unmanaged component customizations override any equivalent managed component customization introduced by managed solutions that layer beneath them.

Component customizations can't be deleted through deletion of an unmanaged solution. They can continue to mask further updates to those components that are imported through an updated version of an existing managed solution. You can import a managed solution and specify that unmanaged customizations should be overridden. This process essentially updates the managed solution layer and applies the same updated component customizations to the existing unmanaged customizations.

### Solution layering

Layering occurs on import of solutions when a specific component is affected by change within one or more solutions. Layers describe the dependency chain of a component from the root solution introducing it, through each solution that extends or changes the component's behavior. Layers are created through extension of an existing component (taking a dependency on it) or through creation of a new component or version of a solution. Examples include:

- Extending a managed Dataverse component – which takes a dependency on the component

- Extending a managed component from a first-party app (Microsoft App) – which takes a dependency on the component from the solution that represents the app

- Extending a managed component from an ISV solution or custom solution/app

- Introducing a new custom component via a custom managed solution – which creates the component and so the root layer for that component.

- Amending properties of an existing component within a different managed solution

In this example below, the column length was originally 1024. When Managed Solution A was imported, the column was truncated to 128. After importing Managed solution B, the column was increased to 4096. The unmanaged solution layer was then updated to 65,536, which is what the user experiences. The example is only meant as an illustration that column lengths shouldn't be changed frequently in the solutions as truncation of data could occur. Also, the unmanaged layer shouldn't be directly updated as managed solutions should be deployed instead.

:::image type="content" source="media/application-lifecycle-management-ce-solution-layering.png" alt-text="Solution layering":::

Use [connection references](/powerapps/maker/data-platform/create-connection-reference) and [environment variables](/powerapps/maker/data-platform/environmentvariables) to define information about a connector or to store parameter keys and values. This streamlines the process of migrating the solutions between environments.

You should have a good understanding of the solution concepts in the Power Platform—the solution is the baseline for the components across their lifecycle. Learn more at [solution concepts](/power-platform/alm/solution-concepts-alm).

### Environment strategy

The number of solutions used to deliver an application will naturally have an impact on the number of Dynamics 365 instances necessary to build and maintain them. Remember that once an application is live, you'll need to support implementation of the next significant application release version in parallel to maintaining the current live version. This may lead to a requirement for more Dynamics 365 instances. The article [Environment strategy](environment-strategy-overview.md) covers more details about environments recommended in Dynamics 365 apps. Consider the scenario where an application comprises a single solution. Version one implementation takes place and is released to production.

:::image type="content" source="media/application-lifecycle-management-ce-solution-release1.png" alt-text="Release of solution first version":::

The development instance is preserved to support any necessary patching of the live application. In parallel, another development instance is required to enable Version two implementation work to proceed. Patches to Version one are incorporated with enhancements for Version two by propagating as unmanaged changes between development instances.

:::image type="content" source="media/application-lifecycle-management-ce-solution-release2.png" alt-text="Release of solution second version":::

When Version two implementation is complete and releases to production, the development instances are rotated. Dev\_2 is preserved to support any necessary patching of the live application and Dev\_1 is recycled to commence Version three implementation work in parallel.

Let's expand the scenario to consider an application comprising two solutions, one dependent on the other. Here's you can extrapolate that four development instances are required. Consider the example of a core solution, with a regional variant solution dependent on the core solution. The single solution example above demonstrated that two development instances are required to maintain Version one of the core solution in production, while Version two is being implementated in parallel. Given the regionally tailored solution has a dependency on the core solution, a third instance is required to support the dependency on the core solution by importing the managed version of the core solution.

:::image type="content" source="media/application-lifecycle-management-ce-solution-release3.png" alt-text="Release of solution with dependencies":::

Finally, there is potential for regional variations to be implemented on an independent timeline to that of the core solution. This introduces a need for a fourth instance to support Version two of the regional solution to be implemented while Version one is maintained in live use.

<!-- This is F&O content, not CE. Needs to be corrected in the guide as well
For more information about deployment, refer to our guides on how to [create deployable packages in Azure Pipelines](/dynamics365/fin-ops-core/dev-itpro/dev-tools/pipeline-create-deployable-package), [apply updates to cloud environments](/dynamics365/fin-ops-core/dev-itpro/deployment/apply-deployable-package-system), [troubleshoot package application issues](/dynamics365/fin-ops-core/dev-itpro/deployment/deployable-package-troubleshooting), and [uninstall a package](/dynamics365/fin-ops-core/dev-itpro/deployment/uninstall-deployable-package).
-->

### Tools

Several tools are available to help automate the process of managing and shipping solutions. Tools can help increase efficiency, reduce manual labor, and reduce human error when working with solutions throughout their lifecycle.

Consider deploying the ALM Accelerator for [Advanced Makers](https://github.com/microsoft/coe-starter-kit/tree/main/ALMAcceleratorForAdvancedMakers) in order to expedite your ALM setup time. These accelerators are pre-built applications that will provide a starting point for automating your solution version control and migrations between environments.

Tools such as Azure DevOps and GitHub provide developer services that support the activities required to plan, store, collaborate, build, and deploy. This includes synchronization of solution metadata between development environments and your version control system, generating build artifacts, deploying to downstream environments, provisioning or de-provisioning environments, and performing static analysis checks against your solution by using the Power Apps checker service. Consider using the [Power Apps Build tools](/power-platform/alm/devops-build-tools) or [GitHub actions](/power-platform/alm/devops-github-actions) as building blocks in creating your pipelines.

Consider using the following tools:

- Version control system  

  This category of software tools helps record changes to files by keeping track of changes committed to software code. A version control system is a database of changes, which contains all the edits and historical versions of a software project. Version control systems allow you to maintain a single source of truth and recall specific versions when needed. Git and GitHub are a popular example of version control applications.

- The Configuration Migration tool  

  This tool enables you to [move configuration and reference data across environments](/power-platform/admin/manage-configuration-data). Configuration and reference data is data that is stored as records in Dataverse but that supports various aspects of the application such as USD, portal configuration, and lookup values.

- Package deployer  

  The package deployer lets administrators or developers [deploy comprehensive packages](/powerapps/developer/common-data-service/package-deployer/create-packages-package-deployer) of relevant assets to Dataverse environments. Packages can consist of not only solution files, but also flat files, custom code, and HTML files. You have the ability to automate the execution of the package deployer with [DevOps build tools task Deploy package](/power-platform/alm/devops-build-tool-tasks#solution-tasks).

- Solution packager  

  This tool can [unpack or pack a compressed solution file](/power-platform/alm/solution-packager-tool) into multiple XML files and other files or vice versa, so they can be easily managed by a source control system or be deployed to an environment from source control. The execution of this can be automated with [DevOps build tools tasks](/power-platform/alm/devops-build-tool-tasks#solution-tasks).

- The Power Apps CLI  

  The [Power Apps CLI](/powerapps/developer/common-data-service/powerapps-cli) is a simple, single-stop developer command-line interface that empowers developers and app makers to create code components. You can also use this interface to automate the deployment of portal configurations.

- PowerShell cmdlets  

  The [PowerShell cmdlets](/powershell/powerapps/overview) for administrators, app makers, and developers allow automation of monitoring, management, and quality assurance tasks that are possible through the Power Apps admin center user interface.

- Test Studio  

  Use [Test Studio](/powerapps/maker/canvas-apps/test-studio) to ensure the quality of your canvas apps.

- Easy Repro  

  Use [Easy Repro](https://community.dynamics.com/blogs/post/?postid=95889af6-b561-42f5-b2bd-ade35180e545) or Playwright to generate test scripts that can be used to regression test changes to your model driven apps.

- Performance Insights  

  Use [performance insights](/power-platform/admin/analyze-improve-data-query-performance) to analyze runtime user data and provide recommendations.

> [!NOTE]
> Check out our additional resources for [Microsoft Power Platform Build Tools for Azure DevOps](/powerapps/developer/common-data-service/build-tools-overview), [Power Apps build tools for Azure DevOps](https://devblogs.microsoft.com/premier-developer/power-apps-build-tools-for-azure-devops/), and [key concepts for new Azure Pipelines users](/azure/devops/pipelines/get-started/key-pipelines-concepts).
