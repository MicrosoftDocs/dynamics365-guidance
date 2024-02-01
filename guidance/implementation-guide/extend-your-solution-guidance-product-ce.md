---
title: Extend customer engagement apps
description: Learn how to use Power Apps, tools, and best practices to make customer engagement apps in Dynamics 365 work better for your needs.
author: abunduc-ms
ms.author: abunduc
ms.date: 01/24/2024
ms.topic: conceptual
ms.custom:
  - ai-seo-date: 01/24/2024
  - ai-gen-docs-bap
  - ai-gen-title
  - ai-gen-desc
content_well_notification: AI-contribution
---

# Extend customer engagement apps

When you implement a solution that includes Dynamics 365, you might need to go beyond the default capabilities. For solutions with customer engagement apps, you can customize them with Power Apps. This article explains some of these features.

## Power Apps

Until recently, creating custom apps would require professional developers. With Power Apps, "citizen developers" can customize and improve apps with configurations and low-code/no-code options, but pro developers can still use code to extend them. You can even mix the two approaches to provide applications that fit your specific needs.

Power Apps makes building custom business apps easy for nonprofessional developers. You can build feature-rich apps without writing code. But Power Apps also lets professional developers use code to work with data and metadata, apply business logic, create custom connectors, and integrate with external data.

When you offer this feature to users, have a central governance team to set guidelines for some aspects of the solution, such as the security and data models. This way, you can avoid redundancy, gaps in the security model, and bad practices or bad architecture that affect how you maintain, secure, scale, and ship your apps.

The Microsoft Power Platform Center of Excellence (CoE) starter kit gives you a set of components and tools that help you develop a strategy for using and supporting Power Platform. The starter kit helps you set up a CoE to drive innovation and improvement while also providing standards, consistency, and governance.

### Components of Power Apps

Power Apps has four main components:

- **Canvas apps** are apps you build by dragging and dropping elements onto a canvas, without needing professional developers to write code. You can also use connectors to work with data from and to different sources.

- **Model-driven apps** are a component-focused way to build apps without needing code. These apps can be simple or complex. With model-driven apps, most of the layout depends on the components that you add to the app. Model-driven apps can be completely custom or based on Microsoft apps like Dynamics 365 Sales.
  
  Both types of apps are responsive, so they adjust automatically to different devices.

- Power Apps makers can also create **portals** for external users to create and view data in Dataverse.

- **Microsoft Dataverse** securely stores and manages data that canvas and model-driven apps use.

Because Dataverse data follows [Common Data Model](/common-data-model/), a shared data language for business and analytical applications, you can easily extend the data model of Microsoft customer engagement apps like Sales, Customer Service, and Field Service. Using Common Data Model lets you start app development faster with business logic, security, and integration already built in.

Cross-app integration lets you extend solutions on Dataverse with data from Dynamics 365 finance and operations apps. With virtual tables, you can work with data in finance and operations apps and customer engagement apps without needing a lot of integration work. Dual-write is available for scenarios where the business process needs the data to be copied between finance and operations apps and Dataverse. And data and business events let you extend your apps by seamlessly integrating Dataverse, platform, and apps.

## Built-in designers make customization easier

Customer engagement apps and Power Apps give you four types of powerful customization and app-making features to build the look and function of an app:

- **Data**: The entity designer and option set designer determine the data the app is based on. Using these designers, you can change the data model by adding more tables, fields, relationships, and components that use fixed options for users to choose from.

- **User interface (UI)**: Features that can customize the UI include the app designer, site map designer, form designer, and view designer. These designers determine how users interact with the app and let you change the components that appear in the UI.

- **Logic**: The business process flow designer, workflow designer, process designer, and business rule designer determine the app's business processes, rules, and automation.

## Solution analyzers

You also have tools to help you analyze your solutions and find issues before you deploy them:

- **Solution checker**: The solution checker can do a rich static analysis of your solutions against a set of best practice rules to quickly find patterns that might cause problems. The result is a detailed report that includes the issues found, the components and code affected, and links to documentation that explains how to fix each issue. Use the solution checker as part of the solution release cycle.

- **Portal checker**: The portal checker is a self-service diagnostic tool that looks for common issues with portal configuration and offers suggestions on how to fix them.

- **Power Apps checker web API**: The Power Apps checker web API lets you run static analysis checks against customizations and extensions to the Dataverse platform. You can use the API to build your own tools to analyze your solutions.

## Next steps

- Read the [case study](extend-your-solution-case-study.md) of how a company extended its Dynamics 365 app to improve its customer service
- Use the Success by Design [checklist](extend-your-solution-checklist.md) to plan and implement your extensions effectively
