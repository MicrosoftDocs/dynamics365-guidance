---
title:  Extend customer engagement apps
description: Find guidance on how we can extend functionality to accommodate your organization’s specific processes and requirements, with a focus on customer engagement apps in Dynamics 365 implementation projects.
author: abunduc-ms
ms.author: abunduc
ms.date: 05/11/2023
ms.topic: conceptual

---

# Extend customer engagement apps in Dynamics 365 implementation projects

When you're implementing a solution that includes Dynamics 365, you often have to extend the default capabilities. For solutions with customer engagements apps, you get more capabilities of the Power Platform.

This article looks at some of these specifics.

## Overview

With the Power Platform, you use configurations and low-code/no-code customizations. But developers can still programmatically extend first-party customer engagement apps such as Dynamics 365 Sales. Custom business applications can also be created. You can even mix the two approaches to provide applications adjusted to specific organizational needs.

:::image type="content" source="media/extend_solution_power_platform.png" alt-text="Power Platform" lightbox="media/extend_solution_power_platform.png":::

## Power Platform

Until recently, creating custom apps would require professional developers. But by using Power Apps, organizations can quickly build custom business applications that provide rich business logic and workflow capabilities to transform manual business processes into digital, automated processes.

Power Apps democratizes custom business app building experience by enabling nonprofessional developers to build feature rich, custom business apps without writing code.

> [!NOTE]
> When you offer this capability to users, have a central governance entity to determine guidelines for certain aspects of the solution, such as security and data model. This approach helps prevent redundancy, gaps in the security model, and bad practices/architecture that impact how apps are maintained, secured, scaled, and shipped.

The Microsoft Power Platform Center of Excellence (CoE) starter kit provides a collection of components and tools that are designed to help organizations develop a strategy for adopting and supporting Microsoft Power Platform. The starter kit helps organizations implement a CoE to drive innovations and improvement while also providing standards, consistency, and governance.

Power Apps also lets professional developers programmatically interact with data and metadata, apply business logic, create custom connectors, and integrate with external data.

## Model the user experience

Power Apps is a high-productivity development platform for business apps and has four major components:

- Canvas apps are intended to build a business app from a canvas in Microsoft Power Apps without requiring professional developers to create code. The apps can be built by using drag and drop elements onto a canvas. With canvas apps, you can also use connectors to integrate data from, and to, various sources.

- Model-driven apps are a component-focused approach to app development, which also doesn't require code. These apps can be simple or complex. With model-driven apps, much of the layout is determined and designated by the components that are added to the app. The model-driven apps can be completely custom or from first-party apps such as Dynamics 365 Sales.

  Both types of apps are built to be responsive by adjusting and being accessible from different devices.

- Power Apps makers can also create externally facing portals so that external users can create and view data in Microsoft Dataverse. The Portals experience reuses components in other apps to determine the experience. It's also possible to customize the Portals experience, similar to how other apps are customizable.

- Microsoft Dataverse securely stores and manages data that is used by business applications.

> [!NOTE]
> Cross-app integration opens opportunities to extend solutions on Dataverse with data from Dynamics 365 finance and operations Apps. Virtual entities offer CRUD integration to data in Finance and Operations from Customer engagement apps without the need for extensive integration work. Dual-write is available for scenarios where the business process requires the data to be physically copied between Finance and Operations and Dataverse. Data and Business events offer seamless extension by integrating Dataverse, platform and apps.

## Business logic and validation within the platform

Business logic and validation to ensure data quality and reduce repetitive tasks can be applied within the Power Platform by using the following approaches:

- Business rules validate data insertion and provide validation messages within the user interface. As an example, with business rules it's possible to display a message when a certain field doesn't have data or doesn't have data in the expected format.

- Business process flows guide users to ensure they enter data and use the solution in a consistent way.  

  For example, if you display the information that is required to complete a business process, like lead to invoice, you provide a consistent approach for all users. You also improve the usability of the solution by making the process more efficient and improving data quality.

- Workflow allows business processes to be automated within the process designer to apply a condition or perform a new action. For example, when closing a support case to send a survey to the customer.

- Business logic with code supports advances developer scenarios to extend the application with code, for example using JavaScript code for form events or plug-ins that apply business logic to data transaction.

Customer engagement apps, such as Dynamics 365 Sales or Dynamics 365 Customer Service, use Dataverse to store and secure the data they use. Organizations can build or extend apps by using Power Apps and Dataverse directly against business data.  

Dataverse data is structured according to the [Common Data Model](/common-data-model/), which is a shared data language for business and analytical applications to use. By using Dataverse, makers can extend the data model of Microsoft's apps such as Sales, Customer Service, Field Service or others. They can jump-start app development by using the Common Data Model with business logic, security, and integration already built in.

Customer engagement apps and the Power Platform provide a powerful customization and app-making capabilities to build the appearance and functionality of an app. These components are distributed in four categories.

### Data

The entity designer and option set designer determine what data the app is based on. These designers allow changes to the data model by adding more tables and fields as well as relationships and components that use predetermined options for users to select.

### User interface (UI)

User interface components include the app designer, site map designer, form designer, and view designer. These designers determine how users interact with the app and allow changes to be made to the components that display in the app UI.

### Logic

The business process flow designer, workflow designer, process designer, and business rule designer determine the business processes, rules, and automation of the app.

## Visualizations

These determine what type of data visualization and reporting the app includes, like charts, dashboards, and reports based on SQL Server Reporting Services.

You can create a range of apps with Power Apps to solve business problems and infuse digital transformation into manual and outdated processes.

### Solution analyzers

- **Solution checker**  

  The solution checker can perform a rich static analysis of the solutions against a set of best practice rules to quickly identify patterns that may cause problems. The result is a detailed report with the following information:

  - The issues identified  
  - The components and code affected  
  - Links to documentation that describes how to resolve each issue  

  > [!NOTE]
  > Include solution checker with the solution release cycle, and after releasing an updated version in a lower environment (sandbox), to make sure that any deprecations or issues related to extensions are identified.

- **Portal checker**  

  The portal checker is a self-service diagnostic tool. It can help you identify common issues by looking at various configuration parameters with a portal. It also provides suggestions on how to fix them.

- **Power Apps checker web API**  

  The Power Apps checker web API provides a mechanism to run static analysis checks against customizations and extensions to the Microsoft Dataverse platform. It's available for makers and developers to perform rich static analysis checks on their solutions against a set of best practice rules to quickly identify problematic patterns.

## Reference links

- [Microsoft Power Apps](https://powerapps.microsoft.com/)

- [Build Power Apps](https://powerapps.microsoft.com/build-powerapps/)

- [Microsoft AppSource](https://appsource.microsoft.com/)

## Next steps

- View the case study at [Extend your solution: Case study](extend-your-solution-case-study.md)  
- Return to the overview at [Extend your solution](extend-your-solution.md)  
- Learn more about extending other apps at [Extend finance and operations apps](extend-your-solution-guidance-product-fo.md)  
