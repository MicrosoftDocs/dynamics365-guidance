---
title:  Challenges in integration projects
description: Find guidance on how to proactively identify and mitigate the challenges of your integration strategy in a Dynamics 365 implementation project.
author: abunduc-ms
ms.author: abunduc
ms.date: 05/23/2023
ms.topic: conceptual

---

# Challenges in integration projects

The diverse applications used in organizations make up the IT backbone of those companies. Organizations use applications that might be a combination of on-premises, cloud, and third parties. These applications need to communicate with each other for different business needs. Integration challenges during a project implementation can cause delays or cost increases. A key focus of any IT department is to ensure that these integrations enable business productivity and not become a blocker to business growth.

Integration challenges can be categorized into the following areas.

## Business

Each integration scenario has a direct impact on the application you're integrating with and on its users. Any downstream applications might also be indirectly affected. For integration to be implemented in a successful manner, address the subjects in the following subsections during the *Initiate* stage. Learn more at [Project Governance](project-governance.md).

### Identification of application owners and stakeholders

Application owners need to identify downstream applications that might be impacted in an integration. However, a common scenario is to bring in these owners after the planning is complete. This often results in misaligned timelines and scope and in turn creates project delays and poor quality. Integration design needs to take every impacted application into consideration.

### Alignment between business owners

Business stakeholders have different needs for their organization's various applications. Unless there's a collective understanding of integration scenarios and approaches, requirements might be mismatched among the various owners. Common results include delayed timelines, cost overruns, and a lack of accountability. As a system integrator, consider the following items:

- Identify the key owners and bring them together to walk through the scenarios.

- Differentiate between process, data, and UI integration to simplify and streamline the integration scope.

- Outline the impact on business groups affected by the integration.

- Highlight issues and risks in the absence of following a consistent approach.

A transparent conversation enables business stakeholders to understand the underlying risks and benefits and thus build a common perspective.

### Ambiguous and unrealistic expectations

Integration requirements can sometimes be ambiguous or incorrectly perceived as mandatory. Common examples of the latter are unnecessary synchronous integrations and replicating high transactional data volumes into your business application to make it a reporting application. Such architecture decisions can result in solutions that aren't scalable and also not performant. Encouraging and facilitating conversations to help business stakeholders define their requirements clearly and understand the necessary tradeoffs as part of the architecture decisions is a critical step in ensuring a smooth implementation.

### Lack of business continuity planning

Business continuity is an aspect of implementing any IT project that most often is ignored. All types of integration, including cloud to cloud and on-premises to cloud, must define operating procedures that the business group will apply as a part of any availability and disaster recovery situation. For example, consider a scenario in which the on-premises application of a Dynamics 365 app is temporarily unavailable. In this scenario, the outage affects the integration components, resulting in data or process issues.

### IT-driven requirements and design

Implementation teams sometimes consider integration between systems as a primarily technical exercise and overlook the critical role played by business teams. However, successful integrations between Dynamics 365 apps often depend completely on a well-defined cross-system business process, and if the specific process details and broader requirements aren't properly defined, the integration project might take longer or go through several iterations of trial and error. For more information, see [Process-focused solution](process-focused-solution.md).

## Technology

Most enterprises have legacy applications with traditional, on-premises architecture. The move to cloud applications requires consideration of the patterns they support and the best practices when planning for integration. A low-code/no-code pattern should now be at the forefront of any integration architecture. The implementation project includes conversations about not just the current setup but also about future planning for performance, extensibility, and maintenance plays a key role in choosing the right technology. When choosing the appropriate technology, consider the questions in the following subsections.

### Does one size truly fit all?

Many enterprises have an enterprise architecture approach that might or might not be aligned with the modern approaches for cloud applications. Prior to investing in a specific approach, evaluate whether the existing architecture aligns with cloud patterns. Sometimes, a generic approach is taken; this can result in inefficiencies in integration, unscalable architecture, and poor user experience and adoption. Therefore, it's crucial to consider design paradigms such as the following:

- Definition of the integration approach based on multiple parameters

- Benefit of a proof of concept to determine the pros and cons of one approach over another

- Synchronous versus asynchronous integration

- Process, UI, and data integration

- Single record or batch

- Frequency and direction of the integration

- Message reliability and speed

- Data volume

- Time expectations (some scenarios require a batch integration to be completed during a specific time window)

- Error management and retries

### Will sensitive data be exposed?

System integrators must understand IT and customer concerns around security, especially in the context of integrating on-premises applications with Dynamics 365 apps. Categorizing security concerns as follows aids in identifying who and what is required to help address them:

- Access control

- Data protection

- Compliance and regulatory requirements

- Transparency

Learn more at [Security](security.md).

### Storage costs and platform limits

To ensure service quality and availability, Dynamics 365 apps and Power Platform enforces entitlement limits. These limits help protect service quality and performance from interference by noisy behavior that can create disruptions. System integrators must incorporate these limits as part of the overall architecture. If these aren't planned for, the service is throttled, resulting in failure and errors within the integration layer. Storage costs are also often ignored. Although it might not have an impact initially, over time, it can result in increased storage costs and therefore should be planned appropriately.

### Connectivity

Network latency can become a constraint, especially in heavy data-load scenarios. System integrators must ensure that they design payloads accordingly for the efficient use of network resources without compromising performance.

### Anti-patterns

Implementation architects should follow the best practices for Dynamics 365 apps. Sometimes these architects don't take cloud patterns sufficiently into account in integration scenarios with on-premises applications, resulting in poor performance. The behaviors leading to such situations are referred to as anti-patterns. Consider the following common anti-patterns:

- Are there repeated connections between on-premises components and Dynamics 365 apps that influence performance? If so, consider sending data in batches.

- Is there latency between a customer's on-premises applications and a Dynamics 365 datacenter? If so, consider using a cloud service such as Power Automate, Azure Functions, or Azure SQL to reduce the latency impact.

- Is much data being synchronized with Dynamics 365 apps for reporting purposes? Keep in mind that the database under Dynamics 365 apps isn't intended to be a data warehouse for all of the organization's data assets. Consider using a dedicated datastore for reporting purposes.

### Proprietary technology

Customers might be using third-party technology within their IT landscape that doesn't provide interface details or adequate support to enable integration easily. Often such issues are identified either toward the end of design or during the development stage. This causes delays in the project timeline, burdening the customer with time constraints to mitigate such risks. System integrators must highlight such dependencies in the planning stage to ensure adequate support or an alternate approach.

### Readiness

With the increasing pace of transformations in the technology world, architects sometime choose an approach due more to its familiarity than its applicability. Customers and system integrators must evaluate whether to request more resources specialized in the specific technology who will be a better fit for their current and future needs.

## Project governance

The initial stage of a project should include a defined project governance model. Integration between on-premises and Dynamics 365 apps can range from simple to complex. The lack of well-defined project governance areas results in gaps and issues in the smooth implementation of a project.

The following are common project governance concerns specifically for the integration components:

- Has the impact of the integrations been identified for the end user, process, and reporting? This might require planning for change management activities, including communication and training.

- Making a solution performant should be at the forefront of any design decisions made by the implementation team. This applies equally to the integration layer and the application layer. Is performance testing planned and does it cover integration components? Performance testing is another activity that tends to be considered optional. However, architects and project managers must consider embedding this in their Dynamics 365 apps implementations. This helps identify any performance bottlenecks prior to deployment for end users.

- Are development and test environments available for all applications for thorough system integration testing? Is a plan for stub-based testing during the unit testing phase required?

Asking these questions during the initial stages of the project enables both the implementation partner and customer to proactively identify and plan for any dependencies and risks.

Learn more at [Project governance](project-governance.md)  

## Next steps

- [Define business goals](integrate-other-solutions-business-goals.md)  
- [Choose a platform](integrate-other-solutions-choose-platform.md)  
- [Choose a design](integrate-other-solutions-choose-design.md)  
- [Choose a pattern](integrate-other-solutions-choose-pattern.md)  
- [Product-specific guidance for integration scenarios](integrate-other-solutions-guidance-product.md)  
- [Checklist](integrate-other-solutions-checklist.md)  
- [Case study](integrate-other-solutions-case-study.md)  
