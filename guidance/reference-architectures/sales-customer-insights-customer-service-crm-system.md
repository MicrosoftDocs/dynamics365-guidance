---
title: Build a Unified CRM System with Dynamics 365
description: Learn how Dynamics 365 Sales, Customer Insights, and Power Platform create a unified CRM solution for lead generation, marketing automation, and customer service.
author: edupont04
ms.author: edupont
ms.reviewer: edupont
ms.date: 10/13/2025
ms.topic: reference-architecture
---
# Unified customer engagement solution with Dynamics 365, Power Apps, Power Pages, and Power Automate

***Applies to***: ***Dynamics 365 Customer Insights—Data, Dynamics 365 Customer Insights—Journeys, Dynamics 365 Customer Service, Dynamics 365 Customer Voice, Dynamics 365 Sales, Power Automate, Power Apps, Power Pages***

This solution combines Dynamics 365 Customer Insights—Data, Dynamics 365 Customer Insights—Journeys, Dynamics 365 Customer Service, Dynamics 365 Customer Voice, Dynamics 365 Sales, Power Automate, Power Apps, Power Pages, and Dataverse. These products build a customer relationship management solution (CRM) that enhances lead and sales management with Dynamics 365 Sales and Customer Insights.

This system lets team members capture incoming leads (loan requests), assign them to the right sales representatives (lenders), and track their progress through the sales journey, from loan qualification to disbursement. For sales managers, it improves visibility into leads and their progress toward opportunity closure.

The solution provides a seamless, end-to-end service experience with Dynamics 365 Customer Service - a single, connected, omnichannel solution that boosts agent productivity, optimizes operations, and customizes customer experiences. With Dynamics 365 Customer Insights, marketers can run campaigns and create relevant marketing materials, like emails and forms.

The solution also uses Power Platform capabilities, such as role-based Power Apps for client teams and Power Automate for workflows and automation. A dedicated portal is part of the solution for members to upload application-related documentation. It applies to any industry that does marketing, sales, and post-sales service.

Define the architecture during the *initiate* phase of the implementation project. This way, you capture all system requirements, understand stakeholders' needs, and align the technology stack with business objectives. Early definition helps outline the project scope, set expectations, and identify potential risks or challenges.

## Architecture

The following diagram shows the solution architecture for the implementation project that inspired this article.

:::image type="content" source="media/sales-customer-insights-customer-service-crm-system.png" alt-text="Diagram that shows the customer engagement system architecture." lightbox="media/sales-customer-insights-customer-service-crm-system.png":::
<!-- 
Download the PowerPoint file for this architecture.   -->

## Dataflow

1. Flow between Customer Insights and Sales:

    1. Lead generation from the marketing team → sales qualification → opportunity creation and assignment.

        1. Users submit loan applications through the website from multiple marketing campaigns and channels.

        1. The system records the loan applications in Dynamics 365 as *leads* or *loan requirements*.

        1. The system sorts applications into queues by city and postal code.

        1. The system sets routing rules to allocate applications to specific agents.

        1. Agents evaluate assigned applications, check eligibility against set criteria, and convert eligible applications into opportunities.

    1. Feedback loop from the sales team → marketing on lead quality and opportunity conversion.

        1. After the system converts applications into opportunities, agents move them through stages. When opportunities reach the proposed stage (indicating prequalification is won), the system automatically transfers them as cases to an external service through backend integration.

        1. Agents manage these cases, and updates flow in both directions, completing the application cycle.

## Components

This reference architecture uses the following components.

- [Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) analyzes customer data related to loan requests, understands customer preferences, and predicts future needs and behaviors. It helps personalize services and improve customer engagement.

- [Sales](https://dynamics.microsoft.com/sales/overview/) captures incoming leads related to loan requests, assigns them to appropriate lenders, and tracks their progress through the sales journey—from qualification to disbursement. It enhances visibility for sales managers, letting them oversee lead progression and opportunity closure.

- [Customer Service](https://dynamics.microsoft.com/customer-service/overview/) provides an omnichannel support system that boosts agent productivity by optimizing service operations and customizing customer experiences. It ensures customers receive consistent and efficient service at every touchpoint.

- [Power Apps](https://powerapps.microsoft.com/)—Role based Power Apps let teams use custom apps that match their workflows, improving operational efficiency and user experience.

- [Power Pages](https://powerpages.microsoft.com/)—A Power Pages portal lets members upload application documentation, ensuring smooth data submission for loan applications and other services.

- [Power Automate](https://powerautomate.microsoft.com/) streamlines workflows and automates repetitive tasks, such as lead assignment, notification triggers, document processing, and backend integration with an external system, reducing manual effort and improving CRM efficiency.

## Stakeholders

Stakeholders in this solution architecture.

- Project sponsor: Provide overall direction and support for the implementation.

- Business analysts: Gather and document business requirements.

- Subject-matter experts (SMEs): Business users who give practical insights into requirements and workflows.

- IT team: Design the technical solution and align it with existing systems.

- CRM admins: Ensure the system's configuration meets business and technical requirements.

- Customer service users: Provide input on customer interactions and service delivery.

- Compliance and legal teams: Ensure the solution meets regulatory requirements, especially in financial services.

- User representatives: Loan officers and marketers who use the system daily.

- Business unit leaders: Manage user adoption and training.

## Scenario details

- Business problem  
  
  The organization faces challenges managing leads and sales, especially for loan applications. The existing systems might lack integration and visibility, making it difficult to track the progress of loan requests and manage customer relationships effectively.

- Solution purpose  
  
  The unified CRM system streamlines these processes using Dynamics 365 Sales and Customer Insights. It provides a centralized platform to capture leads, assign them to lenders, and track their progress through the sales journey, improving operational efficiency and customer satisfaction.
  
- Need for enhanced efficiency  
  
  The organization recognizes the need to improve lead management, sales tracking, and customer service experiences. The lack of integration and visibility in existing systems likely prompts the move toward a unified solution to better manage loan applications and customer interactions.

- Competitive edge  
  
  Improving these processes is crucial for maintaining a competitive edge in the financial services industry, where customer experience and operational efficiency are key differentiators.

### Benefits of the architecture

- Improved efficiency and productivity: Automation of workflows and streamlined processes reduced manual effort and enhanced productivity.

- Enhanced customer experience: A seamless, omnichannel service approach improved customer interactions and satisfaction.

- Better sales management: Sales managers gained visibility into lead progression, improving their ability to close opportunities.

- Effective marketing: Marketers were empowered to design and execute relevant campaigns, enhancing engagement.

- Data-driven insights: Improved data integration provided actionable insights into customer behaviors and preferences, aiding in personalization strategies.

### Potential use cases

This solution was designed for a financial institution. You can apply it to organizations that focus on lead generation, sales tracking, and customer relationship management, including retail, insurance, healthcare, and telecommunications.

Use this solution for these use cases:

- Lead and sales management: Capturing, tracking, and managing sales leads and opportunities.

- Customer relationship management (CRM): Enhancing customer interactions and relationships.

- Marketing automation: Designing and executing targeted marketing campaigns.

- Customer service management: Providing seamless service experiences across channels.

- Workflow automation: Streamlining and automating business processes.

## Considerations

These considerations help you implement a solution that uses Dynamics 365. Learn more in [Dynamics 365 guidance documentation](/dynamics365/guidance/).

### Cost optimization

Reduce unnecessary expenses and improve operational efficiency. Learn more in [Overview of the cost optimization pillar](/azure/architecture/framework/cost/overview).

Licensing costs depend on the number of users and the features you need. Costs increase with more users and more complex features, like advanced analytics or AI capabilities. Estimate costs for your configuration with the pricing calculator at [Dynamics 365 Pricing](https://dynamics.microsoft.com/pricing/).

Things to consider:

- Review the roles and responsibilities of users to assign appropriate licenses without over-provisioning.  
- Design Power Automate flows to minimize unnecessary runs and improve performance.
- Adjust user licenses as your organization scales.

## Related content

- [Dynamics 365 Customer Insights documentation](/dynamics365/customer-insights/)  
- [Dynamics 365 Customer Service documentation](/dynamics365/customer-service/)  
- [Dynamics 365 Sales documentation](/dynamics365/sales/)  
- [Power Apps documentation](/power-apps/)  
- [Power Automate documentation](/power-automate/)  
- [Power Pages documentation](/power-pages/)  
- [Dynamics 365 documentation](/dynamics365/)  

<!-- 
## Tags

*Industries:* Retail Trade (52-59), Finance, Insurance, Services (70-89), Public Administration (91-99)

*Stakeholders: Administrative, Audit, Customer services, Engineering, IT, Marketing, Sales, Service operations, Leadership/Executives*

*Products:* *Dynamics 365 Customer Insights – Data, Dynamics 365 Customer Insights - Journeys, Dynamics 365 Customer Service, Dynamics 365 Customer Voice, Dynamics 365 Sales, Power Automate, Power Apps, Power Pages* -->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [Prakash Omer](https://www.linkedin.com/in/prakashomer/) | Senior Solution Architect
