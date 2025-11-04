---
title: Dataverse as a master data system
description: Review a reference architecture for using Dataverse with or without Dynamics 365 apps as a central store for master data that the system then shares with other systems through Azure Integration.
author: edupont04
ms.author: edupont
ms.reviewer: edupont
ms.date: 11/04/2025
ms.topic: concept-article
---

# Dataverse as a master data system

***Applies to***: ***Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Project Operations, Dynamics 365 Sales, Power Apps, Dataverse, Azure Logic Apps, Azure Functions***

This solution combines Dataverse and Azure Integration to use Dataverse as a master data system and publish relevant information in a canonical model (for example a .JSON file) on a service bus so other applications and systems can get this information. Not all implementations with Dynamics 365 apps include Dataverse, so review the list in the ***Applies to*** section.

## Introduction

Use this solution when Dataverse either directly or through a Dynamics 365 app is the master data source for some of the data (such as products, accounts, contacts, and addresses). This solution informs other applications about this data when you create or update it.

This solution is part of the overall integration strategy and landscape of an implementation.

The key stakeholders in this solution are the business users because they're responsible for the master data system and the requirements to have this information available in other systems.

## Architecture

The following diagram illustrates the architecture for the solution.

:::image type="content" source="media/dataverse-master-data-system.png" alt-text="Architecture diagram showing Dataverse integration with Azure Service Bus, Logic Apps, and Azure Functions for master data distribution." lightbox="media/dataverse-master-data-system.png":::
<!-- Download a PowerPoint file with this architecture.   -->

## Dataflow

1. Dataverse maintains the data.
1. A trigger publishes on a service bus whenever a create or update takes place.
1. A Logic App (Standard) listens to these changes. The Logic App calls a Function app to retrieve the relevant data by using FetchXML. The Storage Account stores the FetchXML definition.
1. The Logic App takes the output of the function and transforms it into the Canonical Model by using the Logic App Data Mapper functionality.
1. The result publishes to a Service Bus Topic.
1. Multiple listeners can retrieve the updates from the Service Bus Topic.

## Components

This reference architecture uses the following components.

- Dataverse stores the master data in its tables.
- A service bus endpoint publishes updates to an Azure Service Bus queue.
- A Logic App (standard) triggers to
  - Read the message from the queue.
  - Call the Azure Function to retrieve the data from Dataverse.
  - Call the Logic App Data Mapper to transform the data into a Canonical Model.
  - Send the message in Canonical Model to a Service bus Topic.
- An Azure Function retrieves the data from Dataverse/Dynamics.
  - Gets called from Logic App.
  - Reads relevant FetchXML definition from Storage Account.
  - Executes FetchXML against Dataverse.
  - Returns output.
- An Azure Service Bus topic stores the data in Canonical Model format.
- A storage account stores FetchXML files.

## Scenario details

Use this reference architecture when you define Dynamics 365 apps as the master data source for entities such as products, accounts, contacts, and addresses. In this scenario, you need to make this data available in other systems. This architecture supports fast data distribution.

### Potential use cases

This solution was created for a professional services organization. You can also apply it to other industries where you manage central master data in Dynamics 365 with Dataverse.

- Account management  

  When you create or update a customer account in Dynamics 365, you can automatically share this information with other systems such as ERP, marketing automation, and customer support platforms. This approach ensures that all customer-facing teams have access to the most up-to-date customer information, which improves customer service and sales efficiency.

- Address management  

  Accurate address information is crucial for logistics and delivery services. By using Dynamics 365 as the master data source for addresses, you can automatically reflect any changes or updates to customer addresses in the logistics and delivery systems. This approach reduces the risk of delivery errors and improves customer satisfaction.

## Considerations

These considerations help you implement a solution that includes Dynamics 365. Learn more at [Dynamics 365 guidance documentation](/dynamics365/guidance/).

Consider the following points when implementing this solution:

- Define your canonical model carefully. When the first listener is 'live', it's hard to change the model (you can add but can't delete or restructure).
- The retrieving systems are responsible for retrieval and removal from the bus. They can do this work directly or through Azure services like a Logic App or Azure Function.
- Make the function as flexible as possible so you don't need to write code when adding extra data to messages.

### Cost optimization

Cost optimization is about finding ways to reduce unnecessary expenses and improve operational efficiencies. For more information, see [Overview of the cost optimization pillar](/azure/architecture/framework/cost/overview).

The licenses cover the Dataverse and Dynamics costs.
For Azure, the following costs apply:

- Application Insights
- Azure Key Vault
- Storage Account
- Azure Service Bus
- Azure Function
- Logic App (standard)

If you implement other integrations, you can use the same Azure Service Bus. The same principle applies to Function and Logic App where app plans can be used by other Functions or Logic Apps. Choose the app plans carefully based on the expected load.

## Implementing Dataverse as master data system

### Procedure: Azure Service Bus

1. Create Azure Service Bus.
1. Define queue for retrieving messages from Dataverse.
1. Define topic for publishing data in the canonical model.

### Procedure: Storage Account

1. Create Storage Account.
1. Store FetchXML files in a structured way (for example, folders per entity).

### Procedure: Azure Function

Implement an Azure Function.

1. Define HTTP trigger
1. Implement reading FetchXML from Storage Account
1. Execute FetchXML against Dataverse
1. Return the result

### Procedure: Logic App

Implement a Logic App.

1. Listen to service bus queue
1. Read message
1. Call Azure Function
1. Get result from Azure Function
1. Transform result with Logic App Mapper to Canonical Model
1. Write output to Service Bus Topic
1. Implement error handling

## Related patterns

The following patterns can help guide your implementation of this master data approach.

- [Publisher-Subscriber pattern](/azure/architecture/patterns/publisher-subscriber)  

## Related resources

Use the following resources to learn more about the integration of Dynamics 365 with Azure:

- [Azure integration](/power-apps/developer/data-platform/azure-integration)
- [Query data using FetchXML](/power-apps/developer/data-platform/fetchxml/overview)
- [Logic App Data Mapper](/azure/logic-apps/create-maps-data-transformation-visual-studio-code)
<!-- 
## Tags

*Industries:* Agriculture (01-09), Mining (10-14), Construction (15-17), Manufacturing (20-39), Transportation and Public Utilities (40-49), Wholesale Trade (50-51), Retail Trade (52-59), Finance, Insurance, Real Estate (60-67), Services (70-89), Public Administration (91-99)

*Stakeholders:* Accounts payable, Accounts receivable, Customer services, Engineering, Finance, Operations, Project Management, Purchasing, Sales, Service operations

*Products:* Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Project Operations, Dynamics 365 Sales, Dataverse, Azure Logic Apps, Azure Functions -->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [Jeroen Leeflang](https://www.linkedin.com/in/jeroenleeflang/) | Technical Architect
