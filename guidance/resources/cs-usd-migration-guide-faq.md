---
title: Migrate from Unified Service Desk to Customer Service workspace
description: Learn how to replace Unified Service Desk functionalities with Customer Service workspace features for enhanced productivity.
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

# USD to CSW FAQ

This Frequently Asked Questions (FAQ) article is for end users, helping in USD to CSW migration.
  
## How to show external web application in CSW?

CSW Tab with External URL can be used to show external web application. 
Please refer - https://learn.microsoft.com/en-us/dynamics365/customer-service/administer/application-tab-templates#third-party-website

## How to open a desktop application from CSW?

Use Power Automate Desktop Flow. On form event (button click) or Dataverse event trigger, launch Cloud Flow. Launch Power Automate Desktop Flow from within cloud flow. 
Please refer https://learn.microsoft.com/en-us/power-automate/desktop-flows/trigger-desktop-flows for details

## How to show welcome text in CSW Agent Script?

In Agent script step select Action Type as Text instruction. The instruction can be made dynamics with parametrization. 
Please refer https://learn.microsoft.com/en-us/dynamics365/customer-service/administer/agent-scripts#create-agent-scripts

## While triggering an entity form from script step, how can I prepoulate some values?

In Macro navigate action, you can prefill using Session variables, odata queries & Power Fx expressions. 
Examples - 
Using Session variable (set customerid) = {{Session.CustomerId}}
Using Power Fx (set title) = ""Call from "" & Session.CustomerName
Using Odata query (set contacts email) = ${$odata.contact.emailaddress1.?$filter=contactid eq '{Session.CustomerId}'} 
Please refer - https://learn.microsoft.com/en-us/dynamics365/customer-service/administer/macros

## In USD, a custom scriptlet was calling external API to validate if  the customer is valid, how can that be done in CSW?

Use Javascript to trigger API call and process the response. Trigger the Javascript from the form/field change event.
Wrap the API call in a Power Automte. Trigger the power automate from the form/field change event.
