---
title: FAQ on Migration from Unified Service Desk to Customer Service workspace
description: Frequently asked questions when migrating from Unified Service Desk to Customer Service workspace.
author: rajislearning
ms.author: rajeeku
ms.topic: how-to
ms.date: 04/10/2025
ms.custom:
  - bap-template
  - O25-Service
  - ai-gen-docs-bap
  - ai-gen-description
  - ai-seo-date:04/10/2025
ms.reviewer: edupont
---

# FAQ on migration from Unified Service Desk(USD) to Customer Service Workspace (CSW)

Below are some of the most commonly asked questions from implementation teams and stakeholders during migratioin from USD to CSW:
  
## How to show external web application in CSW?

CSW Tab with External URL can be used to show external web application.</br>
Please refer - https://learn.microsoft.com/en-us/dynamics365/customer-service/administer/application-tab-templates#third-party-website for more details.

## How to open a desktop application from CSW?

Use Power Automate Desktop Flow. On form event (button click) or Dataverse event trigger, launch Cloud Flow. Launch Power Automate Desktop Flow from within cloud flow. </br>
Please refer https://learn.microsoft.com/en-us/power-automate/desktop-flows/trigger-desktop-flows for more details.

## How to show welcome text in CSW Agent Script?

In Agent script step select Action Type as Text instruction. The instruction can be made dynamics with parametrization. </br>
Please refer https://learn.microsoft.com/en-us/dynamics365/customer-service/administer/agent-scripts#create-agent-scripts for more details.

## While triggering an entity form from script step, how can I prepoulate some values?
- **Using Session Variables**:- You can reference values stored in the session context. These are defined at runtime (e.g., when a call starts).</br>
  Example: Prepopulate the customerid field with the session’s customer ID -  **{{Session.CustomerId}}**
- **Using Power Fx Expressions**:- Power Fx enables string manipulation and logic to generate dynamic values on the fly.</br>
  Example: Prepopulate the title field with a label plus the customer’s name - **"Call from " & Session.CustomerName**
- **Using OData Queries**:- Use inline OData queries to fetch data from Dataverse at runtime and assign it to form fields.</br>
  Example: Prepopulate the emailaddress1 field on the Contact form using the customer’s ID - **${$odata.contact.emailaddress1.?$filter=contactid eq '{Session.CustomerId}'}** 

## In USD, a custom scriptlet was calling external API to validate if  the customer is valid, how can that be done in CSW?
- Use Javascript to trigger API call and process the response.
- Trigger the Javascript from the form/field change event.
- Wrap the API call in a Power Automte.
- Trigger the power automate from the form/field change event.

## How is CTI Integrated in CSW?

CTI providers offer a web-based widget (CTI Adapter) that handles agent login, telephony events (incoming/outgoing calls), and provides controls like accept, reject, hold, and transfer.

Key Steps goes as below:
1. CTI provider shares a widget URL.
2. In CSW, configure a CTI Channel with this widget URL.
3. Create Notification Templates to show call alerts and define session behavior.
4. Configure Session Templates to load relevant tabs on call acceptance.
5. Use Trigger Rules or Macros to automate navigation or data population when a call is received.

Use the CIF v2 simulator for dev & testing purposes: - https://learn.microsoft.com/en-us/dynamics365/guidance/resources/cs-set-up-cif2-simulator
