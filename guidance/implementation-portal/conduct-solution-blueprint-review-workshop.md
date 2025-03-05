---
title: Conduct solution blueprint review workshops
description: Learn how to conduct solution blueprint reviews in Dynamics 365 Implementation Portal to ensure project success and mitigate potential issues early.
ms.date: 03/05/2025
ms.topic: conceptual
author: RajuB-FTSA
ms.author: rabirru
ms.reviewer: prabhav
ms.custom:
  - bap-template
  - ai-gen-docs-bap
  - ai-gen-description
  - ai-seo-date:03/05/2025
#customer intent: As a project manager, I want to conduct a solution blueprint review workshop so that I can ensure project success and mitigate potential issues early.
---
# Conduct solution blueprint review workshops

The *Solution Blueprint Review* (SBR) workshop is the starting point of Success by Design and is required to initiate engagement with the FastTrack team at Microsoft. The workshop helps make the the solution scope and design clearly understood. It also helps identify and mitigate potential issues early in the project, and it provides a solid foundation for planning other Success by Design activities.

Conduct this workshop at the beginning of the project, at the end of the Design phase, or during the Initiate phase, just before the main implementation activities begin. It's essential to have clarity around the scope, approach, and conceptual design at this stage.

## Conduct the solution blueprint review workshop in Dynamics 365 Implementation portal

FastTrack recommends conducting the SBR review in Dynamics 365 Implementation Portal and covers the topics that we list in the following sections. Each topic has several review items, and each review item has several questions. The answers to the questions, the findings, can be matched to scenarios and recommendations. Once all topics, review items, and questions are completed and matched to recommendations, a report is generated. The report provides a summary of the review and highlights the risks, issues, and recommendations based on the answers provided in the review.

Following are the topics that are usually listed, though they might differ based on the scope selected during review process.

1. **Program strategy**

    The program strategy defines the vision and business drivers. The Implementation Strategy explains the methodology for executing the solution. The Rollout model outlines the phases and timelines for deployment. The Project Schedule lists key milestones and deadlines. The Project Governance Considerations detail the roles and responsibilities of stakeholders.

2. **Test strategy**

    The test strategy includes various testing considerations, such as the following list.

    1. The *types of testing* to be performed.  
    1. *The planning involved*.  
    1. The use of *automated testing*.  
    1. The *responsibilities* of different team members.  

3. **Business process strategy**

    The business process strategy involves several key elements.  

    1. *Process-focused solution considerations* address how the solution aligns with business processes.  
    1. *Process maturity* evaluates the current state and readiness of processes.  
    1. *People and organizational structure* examines the roles and hierarchy within the organization.  
    1. *Process scope* defines the boundaries and extent of the processes. There might be other Business Strategy topics focusing on specific topics for some products and these would be displayed depending on the scope of products selected in the previous step.  
    1. *Process implementation drivers* identify the factors driving the implementation of the processes.  
    1. The *template strategy* outlines the use of templates to standardize and streamline processes.

4. **Application strategy**

    The application strategy encompasses several important aspects.  

    1. *Application architecture considerations* involve the overall design and structure of the application.  
    1. *Dynamics components* refer to the elements in Dynamics 365 that the solution uses.  
    1. *Azure components* include the cloud services and resources from Azure that the solution will use.  
    1. *Existing non-Microsoft components* are the current external systems and tools that are incorporated.  
    1. *New non-Microsoft components* are other external systems and tools that are introduced.  
    1. *Custom components* involve any bespoke elements that are developed specifically for the solution.  
    1. The *acquisition strategy* outlines the approach for obtaining and integrating these components.

5. **Data strategy**

    The data strategy includes several key components.  

    1. *Data management considerations* involve the overall approach to handling data throughout its lifecycle.  
    1. *Data modeling* focuses on creating a structured representation of data.  
    1. *Data architecture* defines the framework for data flow and storage.  
    1. *Data migration* addresses the process of transferring data from one system to another.  
    1. *Data storage* involves the methods and technologies used to store data securely.  
    1. *Movement and replication* cover the strategies for moving and copying data across different systems.

6. **Integration Strategy**

    The integration strategy includes several key elements.  

    1. *Methodology* refers to the approach and processes used for integrating different systems.  
    1. *Integration scope* defines the extent and boundaries of the integration efforts. 
    1. *Integration architecture (model, tooling)* involves the design and tools used to achieve seamless integration between systems.

7. **Intelligence strategy**

    The Intelligence Strategy includes several key components.  

    1. *Reporting* involves generating detailed reports to provide insights and track performance.  
    1. *Dashboarding* focuses on creating visual dashboards to monitor key metrics and data points.  
    1. *BI (Business Intelligence)* encompasses the tools and processes used to analyze data and support decision-making.  
    1. *Data replication* covers the methods for copying and synchronizing data across different systems to ensure consistency and availability.

8. **Security strategy**

    The security strategy includes several important aspects.  

    1. *Compliance considerations* involve ensuring that all security measures meet regulatory and legal requirements.  
    1. *Residency considerations address where data is stored and processed, ensuring it complies with local laws and regulations.  
    1. *Privacy considerations* focus on protecting personal and sensitive information.  
    1. *Access considerations* involve managing who has access to data and systems, ensuring that only authorized individuals can access sensitive information.

9. **Application Lifecycle Management (ALM) Strategy**

    The ALM (Application Lifecycle Management) strategy includes several key components.  

    1. *CCM considerations involve the approach to change and configuration management, ensuring that changes are systematically controlled and documented.  
    1. The *software development strategy* outlines the existing methodologies and practices for developing software.  
    1. *Solution / customer constraints* address any limitations or requirements imposed by the solution or the customer.  
    1. The *Configuration management / movement strategy* focuses on how configurations are managed and moved across different environments to maintain consistency and control.

10. **Environment and capacity strategy**

    The environment and capacity strategy includes several important aspects.  

    1. *Environment strategy considerations* involve planning and managing different environments to support development, testing, and production.  
    1. *Compliance considerations* ensure that all environments meet regulatory and legal requirements.  
    1. *Geo/location considerations* address the geographical locations where environments are hosted, ensuring they comply with local laws and regulations.  
    1. *Non-geo/locations considerations* focus on environments that aren't tied to specific geographical locations.  
    1. *Tenant strategy* involves managing multiple tenants in the environment.  
    1. *Preproduction environments* are used for testing and validation before deploying to production.  
    1. *Environment lifecycle considerations* cover the management and maintenance of environments throughout their lifecycle.

## Step-by-step guide to create and conduct the solution blueprint review in Dynamics 365 Implementation Portal

Follow these steps to create and conduct the solution blueprint review via the Dynamics 365 Implementation Portal.

1. Sign in to the Dynamics 365 Implementation portal at [https://experience.dynamics.com/ftimplementationportal/](https://experience.dynamics.com/ftimplementationportal/).
1. Navigate to the **Projects** section, and then select the project you want to conduct an SBR for.
1. On the **Summary** tab, select **Reviews**, and then select the **+ Create New Review** option.

    > [!NOTE]
    > This option only shows for projects that are under active FastTrack engagement.
1. Sign in to create a new review. Provide a name for the Solution Blueprint Review. Confirm that the **Project Name** autopopulates.
1. In the **Review** section, select the *Solution Blueprint Review Workshop* from the lookup field, and then select **Save**.
1. Launch the newly created review and follow the instructions displayed in the portal.
1. Select **Next** to proceed.
1. Select the products that are in scope for the project.

## Detailed steps for the review

When you select products, only questions related to those selected products appear. Similarly, if you exclude products, questions related solely to those excluded products don't appear. Questions that apply to more than one product appear as long as one of the applicable products is selected. Make sure the relevant products are included for the review. Once done, select the **Next** action to proceed.

### Review details tab

In a solution blueprint review, depending on the selected scope, there might be 10 or more strategic topics, each serving as a fundamental area of focus. Within each strategic topic, there are several review items that break down the topic into more specific areas for evaluation. Each review item is further divided into multiple questions designed to explore critical aspects in greater detail.

The responses to these questions are documented and referred to as findings, which provide insights into the current state, gaps, or opportunities within the solution.
These findings are then carefully analyzed and mapped to relevant scenarios, which represent specific use cases, challenges, or contexts that the solution must address. Based on these scenarios, tailored recommendations are developed to address the identified issues, improve the solution, or align it more closely with strategic goals.

Additionally, these recommendations can be further supplemented with detailed guidance, actionable steps, or best practices to provide more comprehensive and practical support for implementation. This layered approach ensures a thorough and structured evaluation, enabling stakeholders to make informed decisions and improvements to the solution.

### Scenario and recommendation section

Select scenario types such as *assertion*, *risk*, or *issue* based on each topic:

- **Assertions**: Findings that are either neutral or represent a recommended practice which can be verified over time.

- **Risks**: Findings that have the potential to have a negative impact to the implementation if not mitigated.

- **Issues**: Findings that are currently impacting the implementation negatively or that will impact the implementation if not resolved.

Recommendations are automatically generated based on the selected scenario and can be refined with more guidance if needed.

Ensure that all topics, questions, and scenarios align with the Solution Blueprint Review template for consistency and clarity.

## Finalize the submission

Once you complete the **Review Details** tab, select the **Generate Document** action, select *Draft* for the initial review, and then verify the draft version. If the draft is satisfactory, you can generate the final version. This also creates and displays the risks and issues in the **Risks and Issues** section. Once generated, an email is sent to the person who created the SBR for review.

## Related content

- [Conduct project reviews for your Dynamics 365 implementation projects](conduct-project-reviews.md)  
- [Solution Blueprint Review workshops](../fasttrack/solution-workshops.md)  
- [TechTalk: Solution blueprint review with FastTrack for Dynamics 365](../techtalks/implement-solution-blueprint-review-fasttrack-dynamics-365.md)  
- [What is the Dynamics 365 Implementation Portal?](overview.md)  
- [Introduction to Dynamics 365 implementation tools and samples](../resources/overview.md)  
- [Introduction to the Dynamics 365 implementation guide](../implementation-guide/introduction.md)

