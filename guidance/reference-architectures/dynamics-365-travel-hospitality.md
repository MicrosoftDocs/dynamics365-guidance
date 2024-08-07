---
title: Dynamics 365 for travel and hospitality
description: Learn about building a business platform for travel and hospitality companies, including outlines on architecture, dataflow, components, and scenario details.
author: dereklh77
ms.author: edupont
ms.topic: article
ms.date: 05/22/2024
---

# Dynamics 365 for travel and hospitality

***Applies to: Dynamics 365 Customer Insights, Dynamics 365 Customer Service, Dynamics 365 Customer Voice, Dynamics 365 Sales, Power Automate, Power Apps, Power Pages, Dataverse, Azure Logic Apps, Azure Functions, Azure Data Lake, Azure Synapse, Azure Key Vault, Azure SQL Database, Azure Active Directory***

This solution combines Dynamics 365 Sales, Dynamics 365 Customer Service, and Dynamics 365 Customer Insights to build a business platform for travel and hospitality companies to allow them to connect with non-Microsoft platforms and resell trip packages.

## Introduction

The solution is based on Dynamics 365 Sales, Customer Service, and Customer Insights connected to one or more Travel and Hospitality platforms. The product catalog (stays, trains, flights) is retrieved from the non-Microsoft Travel and Hospitality platform.

This reference architecture can be used in the travel and hospitality industries especially for resellers of stays offerings.

This architecture should be defined at the beginning of the implementation of the project.

The key stakeholders required in this solution architecture are representatives of sales, customer service, marketing, and IT.

## Architecture

The following diagram illustrates the functional architecture of the solution:

:::image type="content" source="../media/dynamics-365-travel-hospitality-1.svg" alt-text="PowerPoint screenshot outlining main features for sales, customer service, and marketing." lightbox="../media/dynamics-365-travel-hospitality-1.svg":::

The following diagram illustrates the application architecture for the solution:

:::image type="content" source="../media/dynamics-365-travel-hospitality-2.svg" alt-text="Diagram showing the connection between Power Pages, Dynamics 365, Power BI, and content management and delivery." lightbox="../media/dynamics-365-travel-hospitality-2.svg":::

[Download a PowerPoint file](https://github.com/microsoft/dynamics365patternspractices/blob/ref-arch/architectures/reference-architecture-dynamics-365-travel-hospitality.pptx) with these architectures. To download an architecture, choose the file in the explorer, and then choose the download raw file icon.

## Dataflow

The following table describes the dataflow between Dynamics 365 and the rest of the components in this reference architecture:
    
| # | Name | Source | Target | Objects | Description |
|---|------|--------|--------|---------|-------------|
| 1 | Stays 1 | Travel and Hospitality platform | Dynamics 365 Sales | Stay, Flight,Train,Car | The Travel and Hospitality platform is used as a *Configure, Price Quote* (CPQ) tool. <br></br> The platform is displayed in an iFrame in the Dynamics 365 Opportunity form. <br> </br> A stay configurator is built in the Opportunity form using the Travel and Hospitality platform APIs. |
| 2 | Stays 2 | Travel and Hospitality platform | Power Pages | Stay, Flight,Train,Car | The Travel and Hospitality platform is used as a CPQ tool. <br> </br> The platform is displayed in an iFrame in the Power Pages client portal. <br></br> A stay configurator is built in the Power Pages client portal using the Travel and Hospitality platform APIs. |
| 3 | Data Quality 1 | Data Quality Management (DQM) platform | Dynamics 365 Sales | Contact details | The DQM platform is used to help during data input on the contact creation. Usage of email address existence, phone number existence, duplicate detection, postal address existence. The DQM platform APIs are called from the Contact form in real time. |
| 4 | Data Quality 2 | Data Quality Management (DQM) platform | Power Pages | Contact details | The DQM platform is used to help during data input on the contact creation. Usage of email address existence, phone number existence, duplicate detection, postal address existence. The DQM platform APIs are called from the Contact form in real time. |
| 5 | Internal collaboration | Outlook/Teams | Dynamics 365 | Email, Appointment, Chat, Call, Task | Internal collaboration of the teams |
| 6 | Content Management | Content management system (Can be Power Pages or other) | Dynamics 365 | Landing pages, Event pages</br>Subscription centers</br>Websites | Content management to be used by Dynamics 365 Customer Insights |

## Components

The following list outlines the components of the architecture:

- Dynamics 365 Sales manages sales.

- Dynamics 365 Customer Service manages client questions.
 
- Omnichannel features communicate with the customer on every channel.

- Dynamics 365 Customer Insights manages the communication campaigns and events.

- Power Pages is a customer portal with personal space.

- Microsoft Entra ID manages internal user identities.

- Azure B2C manages customer identities.

- SharePoint Online manages documentation and collaboration.

- Power BI reports data.

- Microsoft Outlook and Teams help businesses communicate.

- The Travel and Hospitality platform is a product repository and CPQ tool to browse for available stays offerings. This platform produces, administers, distributes, and manages offers on every distribution channel.

- The data quality management platform helps agents and customers input correct data. This platform creates partnerships with post offices from the countries where the company operates to get a correct address validation.

- The contact management and delivery platform builds and serves landing pages, event pages, subscription centers, and other websites.

## Scenario details

This reference architecture may apply in a scenario where an existing company with an existing business-to-consumer (B2C) business has a significant number of customers and wishes to complete its offerings with travel and vacations. For example, a car rental company has offices worldwide and has customers created in all these offices. The company can enrich its offerings with vacations and stays offerings. This way the customer calling for a car rental can book a hotel room at the same time. The company doesn't have any hotels of its own but can use existing platforms that already have partnerships with hotel chains and other vacation offering companies and provide these products. This way the car rental company can become a reseller of the stays. The Data Quality Management platform is a must-have for every B2C business nowadays.

### Potential use cases

This solution was created for a B2C organization wanting to become a reseller of stays but isn't the owner of the hotels. It can also be applied to industries like travel or companies from other industries wanting to extend their activities with travel. It can be used by any organization that wants to combine its current activities with travel without acquiring the hotels or the travel companies. They can use specialized platforms to get access to travel offerings including stays and transportation.

You can use this solution to:

- Add traveling in your offering without investing in hotels.

- Use a large number of offerings provided by specialized companies that have partnerships with major hotel chains and so on.

- Provide tools for customer and internal agents to have the same product selection experience.

## Considerations

These considerations help implement a solution that includes Dynamics 365. Learn more at [Dynamics 365 guidance documentation](../../guidance/overview.md).

### Cost optimization

Cost optimization is about looking at ways to reduce unnecessary expenses and improve operational efficiencies. Learn more at [Overview of the cost optimization pillar](/azure/architecture/framework/cost/overview).

The cost is equivalent to a standard Dynamics 365 project including Sales/Customer Service and Marketing plus the cost of the external API calls to the Travel and Hospitality platform and the Data Quality Management platform. These platforms normally offer costs per usage and it depends on the quantity of data transaction you'll have with them.

Many of these platforms have existing AppSource solutions:

[Microsoft AppSource Hospitality Applications](https://appsource.microsoft.com/marketplace/apps?search=hospitality&page=1)

[Microsoft AppSource DQM Applications](https://appsource.microsoft.com/marketplace/apps?search=dqm&page=1)

<!--

## Tags

*Industries:* Transportation and Public Utilities (40-49), Retail Trade (52-59), Services (70-89)

*Stakeholders:* Customer services, IT, Marketing, Operations, Sales,, Transportation

*Products:* Dynamics 365 Customer Insights, Dynamics 365 Customer Service, Dynamics 365 Customer Service Insights, Dynamics 365 Customer Voice, Dynamics 365 Sales -->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [Zoran Ivanov](https://www.linkedin.com/in/zoranivanov/) \| Dynamics 365 Customer Engagement Architect
