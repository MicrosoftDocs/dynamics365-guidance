---
title: Application lifecycle management
description: Get guidance for application lifecycle management (ALM) strategy and how end-to-end lifecycle management can provide improved visibility, automation, delivery, and future planning for your solution. We detail the steps to a successful ALM and what that looks like with Dynamics 365. We also provide information on the ALM workshop strategy.
author: abunduc-ms
ms.author: abunduc
ms.date: 03/31/2023
ms.topic: conceptual

---

# Application lifecycle management

Generally, everything has a life and its own lifecycle. Your solution goes through the same process, starting with conception, moving through implementation, then continuous operation, and finally to transition. Application lifecycle management (ALM)  gives you defined processes and practices, a structured team, and tools at your disposal. ALM is the management of your lifecycle (from conception to operation) of your solution.  

ALM includes disciplines across the lifecycle of a solution including the following items:  

- Governance (decision-making)  
- Project management  
- Requirement management  
- Architecture  
- Development  
- Test management  
- Maintenance  
- Support  
- Change management  
- Release management  

A solid application lifecycle management (ALM) strategy brings a successful solution to customers with complete visibility, less manual interaction with automation, improved delivery, and future planning.

We'll talk about ALM in the context of the overall solution lifecycle. Your solution may use one or more of the Dynamics 365 applications such as Finance, Supply Chain Management, Sales, Field Service, or Commerce.

Your entire solution lifecycle may go through several iterations. Your application lifecycle may also be part of a larger solution lifecycle. ALM provides defined guidance for people, processes, and tools. It sets the stage for a successful solution outcome. Additionally, innovation and automation are essential for improving the lifecycle of your solution.

## Objectives

- Explore what ALM looks like.

- Learn the importance of an ALM strategy.

- Understand the steps to successful ALM.

- Discover the recommended Dynamics 365 tools for your ALM strategy.

- Plan your ALM workshop strategy.

## What is ALM?

ALM is about how you manage the end-to-end lifecycle of your solution. It starts when you procure the Dynamics 365 license, and continues through multiple phases. After you deploy the solution to business, you maintain it through the lifetime of your solution.

:::image type="content" source="media/application-lifecycle-management-overview.png" alt-text="Wheel of ALM processes from planning to mapping your business requirements, designing the solution, configuring based on custom requirements, developing, testing, deploying, and maintaining the solution.":::

The high-level lifecycle of your solution could be one or many implementations of your solution.

ALM focuses on a few key concepts:

- Defining best practices, processes, and templates for implementation

- Collaboration between customer, partner, and Microsoft team members

- Multiple phase rollouts of your entire solution

- Innovation and automation using tools

Having well-documented processes connected with teams using various tools will result in team confidence, a complete picture of the implementation, and ultimately the success of your solution.

> [!IMPORTANT]
> Make sure that the implementation team has the appropriate ALM tooling. You need tools such as Azure DevOps to manage all aspects of the solution, including application governance, requirement management, configuration, application development, testing, deployment, and support.  

The tools should connect all team members and all processes. For example, when a developer checks in the code, they mark the changes with a particular work item. This way, the development work item is connected to the work items for business requirement definition and requirement validation.

## Application vs. development lifecycle management

Some people may define ALM as improving development processes such as version control, build automation, release deployments. Although it's part of ALM, we refer to this part of the lifecycle as the software development lifecycle (SDLC), or Dev ALM.

ALM isn't just about the development lifecycle that covers development activities including design, develop, test, and deploy. ALM covers the entire lifecycle of your implementation, including the application development lifecycle and test management.

## Why have an ALM strategy?

When you conceptualize the Dynamics 365 solution, you start the application lifecycle: from the project's *Initiate* phase to the *Implement* phase, *Prepare* phase, and finally the *Operate* phase.

<!--Ideally convert into translatable table-->
:::image type="content" source="media/application-lifecycle-management-project-phases.png" alt-text="ALM in project phases.":::

Throughout the project lifecycle, you identify partner teams, require project management, gather and map business processes, develop new processes, perform testing, deploy code, and finally maintain the solution in production.

Think about taking a trip. You set dates, book flights and hotels, and plan places to visit. All that planning will likely result in a great vacation.

In the same way, a well-planned ALM will lead to a solution that grows your business. With ALM recommended practices, you're set for success in your solution implementation. You gain visibility into several areas:

- The current work items (requirement, development, testing)

- The work items completed, in progress, or planned

- The teams that worked, are working, or will work on specific tasks

- Issues and risks associated with solution implementation

- Development best practices

- Code history or code version control

- Build and release automation

- A testing plan, test cases, and test results against requirements

Your ALM may not be perfect right from the start. But it's a foundation you can refine your ALM practices over time.

### Implementation without defined ALM

ALM is the lifeline of your implementation. Let's return to the planned trip. You planned your dates and booked your flights, but you didn't book lodging or decide on any sightseeing excursions or activities. Your trip could be a disappointment, and you might end up spending more time planning when you should be out having fun.

Like a poorly planned trip, if you don't have effective ALM, you can expect a negative impact on your implementation, solution quality, and business satisfaction.

Without effective ALM, you may have poor decision-making, recommended practices may not be followed, and teams are disjointed in the implementation, which can cause delays.

### Is ALM only for complex implementations?

You might think that implementing well-defined processes and tracking work items, individuals, and using automation tools is too much work for a small or straightforward implementation.

However, every implementation, no matter its size, should follow application lifecycle components. Have a project plan, define the scope, the business requirements, and the documentation. Your implementation might not require development or integration, but it will still have configurations and application version updates.

With effective ALM and well-defined practices, you can keep your solution healthy and up to date with the latest application releases.

## Steps to successful ALM

You should use ALM from solution conception through operation. In this section, we dive into some of the areas of the ALM process.

### During implementation

While you're implementing the solution, you go through multiple phases: Initiate, Implement, and Prepare. ALM applies to all these aspects in your implementation:

- Project management

- Business process management

- Application configuration

- Development

- Testing

- Bug tracking

- Ideas, issues, risks, and documents

- Release management

### After implementation

When you're live in production, you're in the Operate phase. ALM continues with the following aspects:

- Continuous updates

- Independent software vendor (ISV) updates

- Maintenance and support

- New features

- Next phase

### Project management

Efficient ALM requires having documented processes, templates, and tools for all project management activities. The following list covers examples of such activities:

- Project planning  
- Cost management  
- Team management  
- Ideas for improvements or solutions, issues, and risk management  

A project manager performs their responsibilities efficiently when these areas are defined and documented. For example, you should have a template for the project plan that the project manager can apply in the *Implement* phase.

Learn more at [Project governance](project-governance.md).

### Business process management

ALM processes and tools should include managing business requirements and processes efficiently and effectively. After you define your templates and tools, provide a framework for functional team members to work together to define requirements and business processes efficiently. Teams can track business requirements for business processes and connect further with configuration and development.

For example, a functional team member gathers and defines business requirements in a given template and tracks them in Azure DevOps. They get requirements reviewed by business users through assignment of work items. The business requirement document is stored in a repository.

Learn more at [Process-focused solution](process-focused-solution.md).

### Application configuration

ALM processes and tools should also include managing application configurations. Before configuring an application, the business should define and review business processes and requirements. Functional team members should have defined processes with tools to perform fit gap analysis, and a defined configuration required in the application.

> [!IMPORTANT]
> Track your configuration setup and changes using tools such as Azure DevOps. Configuration is often a one-time activity without documentation and tracking. Such cases lead to confusion, no visibility, and questions about why particular decisions were made. Always maintain your documentation for application configuration during testing, user acceptance testing (UAT), cutover, and even after going live during maintenance and support.

### Development

Having an efficient development lifecycle is one of the mandatory aspects of ALM. In general, the development lifecycle consists of the following phases:  

- Design  
- Develop  
- Build  
- Test  
- Deploy  

Continuous integration and continuous deployment (CI/CD) is one of the best and latest practices to enable delivering code changes more frequently and reliably.

After the business requirements are defined and identified, the development team should get involved to work on any gaps in the solution. The development team analyzes the requirements, reviews the functional design, prepares the technical design, and gets the technical design reviewed. The development team should use version control, create development tasks, link check-ins with work items, and prepare a unit-testing document.

Finally, use build definitions and pipelines for automation and to identify and fix any build issues. Build automation is vital for continuous integration or gated check-ins. Manual builds are error-prone and time-consuming. The build process, either manual or automated, is mandatory for development.

The following example of a CI/CD approach has a centralized version control in place, a build agent using build definitions, and release pipelines to push code to a sandbox or other environments. In this scenario, Dev A develops Solution A and Dev B develops Solution B. Dev A gets Solution B (Dev B code) using version control and after a successful build automation. When the build is successful, the code is released to the sandbox environment using the release pipelines. After successful testing, the code is released to the production environment.

:::image type="content" source="media/application-lifecycle-management-cicd.png" alt-text="Example of ALM CI/CD.":::

### Testing

Testing is an integral part of ALM. Under ALM, test management processes and tools should be defined with templates to help manage test preparation, implementation, and reporting. It should also include what tools to use for these steps. Article [Testing strategy](testing-strategy.md) provides more information about test management.

### Maintenance and support

In addition to the steps taken for planning, developing, and deploying your solution, as part of effective ALM, you should have a plan to make sure your solution continues to be optimal and healthy.

If you'd like to find more about the support process, check [Service the solution](service-solution.md) and [Transition to support](transition-to-support.md).

## ALM strategy for Dynamics 365

ALM can improve every aspect of Dynamics 365 solution that includes use one or more of the Dynamics 365 applications such as Finance, Supply Chain Management, Sales, Field Service, or Commerce. Learn more at [ALM strategy for Dynamics 365](application-lifecycle-management-product.md).

### ALM workshop

The [ALM workshop](application-lifecycle-management-workshop.md) is part of the [Success by Design](success-by-design.md) framework. It's designed to validate that the development approach is aligned between the customer and the partner and that it follows the best practices of Dynamics 365 ALM.

## Conclusion

ALM is the management of your solution lifecycle from conception to operation. It includes disciplines across the lifecycle of a solution including the following items:  

- Governance (decision-making)  
- Project management  
- Requirement management  
- Architecture  
- Development  
- Test management  
- Maintenance  
- Support  
- Change management  
- Release management  

Your solution lifecycle may go through several evolutions. Each evolution may use the same SDLC methodology. Basically, SDLC is part of ALM, ALM is far bigger than Dev ALM, and Dev ALM is part of SDLC.

## Next steps

- Access the checklist > [Application lifecycle management Success by Design checklist](application-lifecycle-management-checklist.md)

- Access the case study > [Global transport systems company finds ALM strategy to be a cornerstone of implementation](application-lifecycle-management-case-study.md)

- Access the book > [Implementation guide](https://aka.ms/D365ImplementationGuide)

- Access the chapter in the book > [Application lifecycle management](https://aka.ms/d365-chapter-alm)

## Resources

### DevOps and Azure Pipelines

[DevOps solutions on Azure](https://azure.microsoft.com/solutions/devops/)

[Release pipelines](/azure/devops/pipelines/release)

[Sign up for Azure Pipelines](/azure/devops/pipelines/get-started/pipelines-sign-up)

### Finance and operations apps

[Implement application lifecycle management in finance and operations apps](/learn/modules/application-lifecycle-finance-operations/)

[Business process modeler in Lifecycle Services](/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/bpm-overview)

[Dynamics 365 finance and operations tools](https://marketplace.visualstudio.com/items?itemName=Dyn365FinOps.dynamics365-finops-tools&ssr=false)

### Customer engagement apps

[Application lifecycle management (ALM) with Microsoft Power Platform](/power-platform/alm/solution-packager-tool)

[Microsoft Dynamics CRM SDK Templates](https://marketplace.visualstudio.com/items?itemName=DynamicsCRMPG.MicrosoftDynamicsCRMSDKTemplates&referrer)

[Solution Lifecycle Management: Customer engagement apps in Dynamics 365](https://www.microsoft.com/download/details.aspx?id=57777)
