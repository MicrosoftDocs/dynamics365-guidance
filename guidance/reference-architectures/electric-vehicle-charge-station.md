---
title: Electric vehicle charging station placement and lifecycle management
description: Learn how to streamline placement, installation, and lifecycle management for electric vehicle charging stations using Dynamics 365 and Power Platform.
author: edupont
ms.author: edupont
ms.topic: reference-architecture
ms.date: 08/01/2025
---

# Electric vehicle charging station placement and lifecycle management

***Applies to: Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Sales, Power Automate, Power Pages, Dataverse, Azure Functions, Azure Key Vault, Microsoft Entra ID***

This solution uses Dynamics 365 Sales, Dynamics 365 Field Service, Power Pages portals, and a Dynamics 365 model driven app to create an ecosystem for electric vehicle (EV) charging station placement and lifecycle management.

## Introduction

This reference architecture applies to companies that are placing and managing EV charging stations. The architecture covers business cases for handling placement requests from public domain (government), asset lifecycle management, customer support, IoT events, and maintenance work orders.

Use this reference architecture before your company installs charging stations to ensure quality placement and maintenance.

Key stakeholders for this architecture are charge point operators, public municipalities (government), grid operators, asset management, customer support, installation partners, and service providers.

## Architecture

The following diagram illustrates the architecture for the solution.

:::image type="content" source="./media/dynamics-365-high-level-architecture.svg" alt-text="Diagram showing the connection between external parties, Microsoft Azure, and Microsoft Dynamics 365." lightbox="./media/dynamics-365-high-level-architecture.svg":::

## Entity relationship diagram

:::image type="content" source="./media/asset-placement-request-model-driven-app.svg" alt-text="Dynamics 365 asset placement entity relationship diagram." lightbox="./media/asset-placement-request-model-driven-app.svg":::

## Use case

:::image type="content" source="./media/field-service-mobile-public-asset-installers.svg" alt-text="Diagram showing Dynamics 365 Field Service mobile app for public asset installers." lightbox="./media/field-service-mobile-public-asset-installers.svg":::

In The Netherlands, external installers place public assets. These installers use a Power Platform portal to look at work orders assigned to them. They plan the work orders in their own system. When the work order is performed, the installers mechanic uses the Field Service mobile app to add the work order and asset details.

## Dataflow

### Charging station placement request to installation

1. An external party sends placement requests through an inbound Azure API to Dynamics 365.

1. Integration creates a Placement Request and a Placement Request Location in Dynamics 365 Dataverse.

1. An asset management operational employee reviews and approves the placement request using the Dynamics 365 Station Management model driven app.

1. When the placement request is approved, the system sends an outbound API call to request installation from the grid operator.

   If the placement request is rejected, the system sends a rejection notification to the external party.

1. The grid operator can approve the installation request and schedule onsite preparation and grid connection in their own system.

   If the grid operator rejects the request, the API receives a rejection message and updates the status of the Public Request in Dynamics 365. The operational team can propose an alternative location and resend it to the grid operator, or reject the placement request and notify the third party.

1. When the grid connection is scheduled, the system receives an inbound API call and updates the placement request status to pending grid installation.

1. When the grid operator schedules the installation, the system creates a work order of type "Installation."

1. Each placement request links to a Tender record in Dynamics 365 Dataverse. The tender includes the charging station products to install and the service provider responsible for maintaining the station. The Dynamics 365 Station Management model driven app includes tender configuration.

   The system uses this information when creating the Customer Asset (station) in Dynamics 365 Field Services to specify the primary service partner for the charging station.

1. When the work order is created, the system copies the installation provider from the tender configuration record to the installation work order. The service provider is set as the owning team of the installation work order.

1. After the work order is created, the operational team adds the work order product line items to define the product and product type of the station to install. These items also serve as placeholder records for the customer asset.

1. External installers use the Power Pages partner portal to monitor new work orders, plan work orders, and update the schedule date.

   > [!NOTE]
   > In this use case, external subcontractors plan work orders outside Dynamics 365 Field Service. They use their own planning software and flexible workforce.

   If the Charge Point Operator (CPO) plans and performs the installation work order, they use Dynamics 365 Field Service for work order planning.

1. When the work order is planned, a subcontractor installs the station. The CPO's warehouse manages hardware distribution. The installer picks up the required stations from the warehouse. At this point, the station isn't registered at a specific location. For asset management, the installer notifies the CPO which station is placed at which location.

1. When the installer arrives onsite to perform the installation, they find the work order in Dynamics 365 Field Service mobile app. They take a station from their vehicle and install it at the requested location. Using the Field Service mobile app, they go to the work order product line and update it with the "hardware id" from the station box. This links the exact station (with preloaded firmware to connect over SIM) to that specific location.

1. After the installer links the station name to the work order product line, they use a custom Power Apps component framework (PCF) control in the mobile app to start the connection test.

1. The connection test triggers a plugin from the work order product line item to create the Customer Asset. The Customer Asset has all the station details like name, brand, product type, and location.

1. When Dynamics 365 creates the Customer Asset, a plugin calls an Azure Function. This Azure Function registers the charging station with the Charging Platform (IOT hub responsible for station management, which is out of scope for this architecture).

1. After the platform registers the station, it accepts the incoming connection request over WebSocket and posts a message on a streaming provider to inform subscribers about the connection status.

1. The PCF control in the Dynamics 365 Field Service mobile app picks up the message and shows the connection status to the installer.

1. After the installer finishes the installation, they perform a site inspection and fill out an inspection using the Dynamics 365 Field Service mobile app. This inspection is called a Site Acceptance Test (SAT).

1. When the installer finishes the SAT, Power Automate updates the work order and placement request status. This update informs the operational team that they can review the SAT.

1. The operational team reviews the SAT and approves it.

1. After the SAT has been approved, use the SAT questions and answers to generate a PDF document. Upload the document to the placement request in Dynamics 365 Dataverse so the party that requested the installation can check proper delivery of the charging station.

1. The station is installed and operational.

1. Follow-up processes in this reference architecture include invoicing the work order, case management, maintenance, and more, but these processes aren't covered in this document.

## Components

The following components are used in the reference architecture.

- Dynamics 365 Sales Hub handles billing for station placements. This article covers public placements, but the EV company also supports business-to-consumer (B2C) placements sold using a customized lead-to-cash process. Services and repairs are sold using the Sales module. The sales and billing process isn't in scope for this reference architecture. Learn more at [Dynamics 365 Sales](https://www.microsoft.com/en-us/dynamics-365/products/sales).

- Dynamics 365 model-driven app is a business-specific application that handles the placement process. It uses custom tables, Dynamics 365 Field Service tables, and Dynamics 365 Sales tables to finish the installation request process. Learn more at [Overview of building a model-driven app with Power Apps](/power-apps/maker/model-driven-apps/model-driven-app-overview).

- Power Pages provides a partner portal for external parties to interact with Dataverse placement request and work order data. Municipalities track the status of their placement request. External installers view and update assigned work orders. Learn more at [Power Pages - website builder](https://www.microsoft.com/power-platform/products/power-pages).

- A PCF control checks station connectivity and interacts with the IoT hub that manages station connections. The PCF control is embedded in the Dynamics 365 Field Service mobile app work order product line item. Learn more at [Power Apps component framework overview in Microsoft Dataverse](/power-apps/developer/component-framework/overview).

- Dynamics 365 Power Automate acts as a CRUD event handler to update related Dataverse data. Learn more at [Power Automate – Process Automation Platform](https://www.microsoft.com/power-platform/products/power-automate).

- Plugins act as CRUD event handlers to interact with Azure Functions. Learn more at [Use plug-ins to extend business processes (Microsoft Dataverse)](/power-apps/developer/data-platform/plug-ins).

- Azure Functions handle interactions between Dynamics 365 Dataverse and integration layers (APIs). Learn more at [Azure Functions Overview](/azure/azure-functions/functions-overview).

- Dynamics 365 Field Service and mobile app manage the station installation work order process. Learn more at [Field Service Management Software](https://www.microsoft.com/dynamics-365/products/field-service).

## Scenario details

A Charge Point Operator (CPO) builds EV charging sites, installs hardware from different electric vehicle supply equipment (EVSE) vendors, and ensures ongoing EV charging operations. Installation is complex because requests come in through internal and external channels. The CPO approves requests, grid operators set up grid connections, and external parties plan and perform installations, often working with subcontractors.

Use Dynamics 365, Power Platform, Dataverse, Power Pages, and Power Automate with as many out-of-the-box components as possible to meet most requirements in a sustainable, cost effective way through configuration and low-code solutions.

Dynamics 365 integrates with Microsoft 365 and lets the company use AI solutions like Copilot.

### Potential use cases

This solution is for eMobility Charge Point Operator (CPO) organizations. Organizations in energy, home appliance installation, government, and facilities can use it. Any organization that does onsite installation from an installation or placement request can use this solution.

Use this solution to:

- Manage installation and placement requests.
- Create work orders.
- Let frontline workers interact with work orders in the field and perform inspections.
- Give external partners access to Dataverse information.

## Considerations

These considerations help implement a solution that includes Dynamics 365. Learn more at [Dynamics 365 guidance documentation](/dynamics365/guidance/).

### Cost optimization

Cost optimization is about looking at ways to reduce unnecessary expenses and improve operational efficiencies. For more information, see [Overview of the cost optimization pillar](/azure/well-architected/cost-optimization/).

Dynamics 365 users need a Dynamics 365 Field Service license. For pricing details, see [Field Service software pricing](https://www.microsoft.com/dynamics-365/products/field-service/pricing).

Dynamics 365 sales users need a Dynamics 365 Sales Professional or Enterprise license. For pricing details, see [Sales pricing](https://www.microsoft.com/dynamics-365/products/sales/pricing).

Azure functions run back-end processes. The cost is pay as you go and depends on the volume of actions.

Azure API management handles integration with external parties.

The cost of the solution scales according to the number of users and license cost. Throughput volume is another cost dimension. When more chargers are registered and communicated with external parties, API costs increase. Compared to license cost, API cost is relatively low. Storage volume is the third cost dimension. Dynamics 365 tenants include default storage capacity and increased storage for each license purchased. Learn more in the [Dynamics 365 Licensing guide](https://go.microsoft.com/fwlink/?linkid=2320604&clcid=0x809).

<!--

## //Next steps

## //Related patterns

## Tags

*Industries**: *Transportation and Public Utilities (40-49)

*Stakeholders:* Accounts payable, Accounts receivable, Administrative, Audit, Customer services, Engineering, Finance, IT, Marketing, Operations, Project Management, Purchasing, Sales, Service operations, Transportation, Warehouse

*Products:** *Dynamics 365 Field Service, Dynamics 365 Sales
--->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

Merijn van Raaij (https://www.linkedin.com/in/merijn-van-raaij-2b676175/) | Senior Solution Architect Dynamics 365 & Power Platform

