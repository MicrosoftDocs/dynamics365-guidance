---
title: Conduct Solution Blueprint review workshop
description: Learn how to conduct Solution Blueprint review reviews in Dynamics 365 Implementation Portal
ms.date: 02/27/2025
ms.topic: conceptual
author: rabirru
ms.author: rabirru
ms.reviewer: prabhav
ms.custom: bap-template
---
# Conduct Solution Blueprint review workshop

## Solution Blueprint review workshop overview

The Solution Blueprint Review (SBR) workshop is the starting point of Success by Design and serves as a mandatory workshop to initiate the FastTrack engagement. It ensures that the solution scope and design are clearly understood, helps identify and mitigate potential issues early in the project, and provides a solid foundation for planning other Success by Design activities.

This workshop should be conducted at the beginning of the project, at the end of the Design phase, or during the Initiate phase, just before the main implementation activities begin. It is essential to have clarity around the scope, approach, and conceptual design at this stage.

## Conducting the Solution Blueprint review workshop in the Dynamics 365 Implementation portal:

FastTrack recommends conducting the SBR review in the Dynamics 365 Implementation Portal and covers the topics listed below. Each topic has several Review Items, and each Review Item has several questions. The answers to the questions, the Findings, can be matched to Scenarios and Recommendations. Once all Topics, Review Items and Questions are completed and matched to recommendations, A report would be generated. The report provides a summary of the review and highlights the risks, issues and recommendations based on the answers provided in the review.

Following are the topics that are usually listed (might differ based on the scope selected during review process)

1. **Program Strategy**

The Program Strategy defines the vision and business drivers. The Implementation Strategy explains the methodology for executing the solution. The Rollout model outlines the phases and timelines for deployment. The Project Schedule lists key milestones and deadlines. The Project Governance Considerations detail the roles and responsibilities of stakeholders.

2. **Test Strategy**

The Test Strategy includes various testing considerations, such as the types of testing to be performed, the planning involved, the use of automated testing, and the responsibilities of different team members.

3. **Business Process Strategy**

The Business Process Strategy involves several key elements. Process-Focused Solution Considerations address how the solution aligns with business processes. Process Maturity evaluates the current state and readiness of processes. People and Organizational Structure examines the roles and hierarchy within the organization. Process Scope defines the boundaries and extent of the processes and There might be additional Business Strategy topics focusing on specific topics for some products and these would be displayed depending on the scope of Products selected in the previous step. Process Implementation Drivers identify the factors driving the implementation of the processes. Finally, the Template Strategy outlines the use of templates to standardize and streamline processes.

4. **Application Strategy**

The Application Strategy encompasses several important aspects. Application Architecture Considerations involve the overall design and structure of the application. Dynamics Components refer to the elements within the Dynamics platform that will be utilized. Azure Components include the cloud services and resources from Azure that will be integrated. Existing Third-Party Components are the current external systems and tools that will be incorporated. New Third-Party Components are additional external systems and tools that will be introduced. Custom Components involve any bespoke elements that will be developed specifically for the solution. Lastly, the Acquisition Strategy outlines the approach for obtaining and integrating these components.

5. **Data Strategy**

The Data Strategy includes several key components. Data Management Considerations involve the overall approach to handling data throughout its lifecycle. Data Modelling focuses on creating a structured representation of data. Data Architecture defines the framework for data flow and storage. Data Migration addresses the process of transferring data from one system to another. Data Storage involves the methods and technologies used to store data securely. Lastly, Movement and Replication covers the strategies for moving and copying data across different systems.

6. **Integration Strategy**

The Integration Strategy includes several key elements. Methodology refers to the approach and processes used for integrating different systems. Integration Scope defines the extent and boundaries of the integration efforts. Integration Architecture (Model, Tooling) involves the design and tools used to achieve seamless integration between systems.

7. **Intelligence Strategy**

The Intelligence Strategy includes several key components. Reporting involves generating detailed reports to provide insights and track performance. Dashboarding focuses on creating visual dashboards to monitor key metrics and data points. BI (Business Intelligence) encompasses the tools and processes used to analyze data and support decision-making. Lastly, Data Replication covers the methods for copying and synchronizing data across different systems to ensure consistency and availability.

8. **Security Strategy**

The Security Strategy includes several important aspects. Compliance Considerations involve ensuring that all security measures meet regulatory and legal requirements. Residency Considerations addresses where data is stored and processed, ensuring it complies with local laws and regulations. Privacy Considerations focus on protecting personal and sensitive information. Lastly, Access Considerations involve managing who has access to data and systems, ensuring that only authorized individuals can access sensitive information.

9. **Application Lifecycle Management (ALM) Strategy**

The ALM (Application Lifecycle Management) Strategy includes several key components. CCM Considerations involves the approach to Change and Configuration Management, ensuring that changes are systematically controlled and documented. The Software Development Strategy outlines the existing methodologies and practices for developing software. Solution / Customer Constraints address any limitations or requirements imposed by the solution or the customer. Lastly, the Config Management / Movement Strategy focuses on how configurations are managed and moved across different environments to maintain consistency and control.

10. **Environment and Capacity Strategy**

The Environment and Capacity Strategy includes several important aspects. Environment Strategy Considerations involve planning and managing different environments to support development, testing, and production. Compliance Considerations ensure that all environments meet regulatory and legal requirements. Geo/Location Considerations address the geographical locations where environments are hosted, ensuring they comply with local laws and regulations. Non-Geo/Locations Considerations focus on environments that are not tied to specific geographical locations. Tenant Strategy involves managing multiple tenants within the environment. Pre-Production Environment(s) are used for testing and validation before deploying to production. Lastly, Environment Lifecycle Considerations cover the management and maintenance of environments throughout their lifecycle.

## Step-by-Step Guide to create and conduct the Solution Blueprint Review in Dynamics 365 Implementation Portal

Follow these steps to create and conduct the Solution Blueprint Review via the Dynamics 365 Implementation Portal.

1.Login to the Dynamics 365 Implementation portal: https://experience.dynamics.com/ftimplementationportal/

2.Navigate to the Projects section and select the project you would like to conduct an SBR for.

3.On Summary tab, choose Reviews and click the + Created New Review option (Note: Please note that this option would be displayed only for projects that are under active FastTrack engagement) sign to create a new review. Provide a name for the Solution Blueprint Review. Confirm that the Project Name auto-populates.

4.In the Review section, select the “Solution Blueprint Review Workshop” from the lookup Field and click Save.

5.Launch the newly created review and follow the instructions displayed in the UI.

6.Click Next to proceed.

7.Select products that are in scope for the project.

## Detailed Steps Within the Review
When you select products, only questions related to those selected products will appear. Similarly, if you exclude products, questions related solely to those excluded products won’t appear. Questions that apply to more than one product will appear as long as one of the applicable products is selected. Make sure the relevant products are included for the review. Once done, click 'Next' to proceed."

## Review Details Tab:
In a solution blueprint review, depending on the selected scope, there might be 10 or more strategic topics, each serving as a fundamental area of focus. Within each strategic topic, there are several review items that break down the topic into more specific areas for evaluation. Each review item is further divided into multiple questions designed to explore critical aspects in greater detail.

The responses to these questions are documented and referred to as findings, which provide insights into the current state, gaps, or opportunities within the solution

These findings are then carefully analyzed and mapped to relevant scenarios, which represent specific use cases, challenges, or contexts that the solution must address. Based on these scenarios, tailored recommendations are developed to address the identified issues, improve the solution, or align it more closely with strategic goals.

Additionally, these recommendations can be further supplemented with detailed guidance, actionable steps, or best practices to provide more comprehensive and practical support for implementation. This layered approach ensures a thorough and structured evaluation, enabling stakeholders to make informed decisions and improvements to the solution.

## Scenario & Recommendation Section:
Select scenario types such as Assertion, Risk, or Issue based on each topic:

**Assertions**: Findings that are either neutral or represent a recommended practice which can be verified over time.

**Risks**: Findings that have the potential to have a negative impact to the implementation if not mitigated.

**Issues**: Findings that are currently impacting the implementation negatively or that will impact the implementation if not resolved.

Recommendations are automatically generated based on the selected scenario and can be refined with additional guidance if needed.

Ensure that all topics, questions, and scenarios align with the Solution Blueprint Review template for consistency and clarity.

## Finalizing the Submission
Once the Review Details Tab is completed, click Generate Document and select Draft for the initial review and verify the draft version.If the draft is satisfactory, the final version can be generated. This will also create and display the risks and issues in the 'Risks and Issues' section. Once generated, an email will be sent to the person who created the SBR for review.
