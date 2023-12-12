---
title: Business processes, steps, and how to find things 
description: Learn how we how to understand where to find the different pages in the Dynamics 365 apps when you go through the business process content.
author: edupont04
ms.author: raprofit
ms.reviewer: edupont
ms.topic: conceptual #Required; don't change.
ms.collection: get-started #Required; don't change.
ms.date: 10/27/2023
ms.custom: bap-template #Required; don't change.
---

# Business processes, steps, and how to find things

This article describes terminology, concepts, and abbreviations that are used throughout the [Dynamics 365 business process guide](overview.md).

Each business process article includes one or more tables with the steps required to configure and operate Dynamics 365. The following table is an excerpt from the table for the [Set customer credit limits](order-to-cash-monitor-customer-credit-collections-set-customer-credit-limits.md#basic-credit-limit-checking) business process.  

[!INCLUDE [daf-busprocess-example](~/../shared-content/shared/guidance-includes/daf-busprocess-example.md)]

The next sections further explain the columns and define the abbreviations that are used throughout the business process guide.

## Process step

Each business process includes several steps. The first column in the table describes the *process step*. The name of the step is often the name of the form or action that needs to be taken. Choose the hyperlink in each row to navigate to the related product documentation. If the row doesn't have a hyperlink, it's probably because the capability isn't documented. If you find documentation for a step or want to contribute documentation to a step, we invite you to contribute. Learn more at [Contribute to Dynamics 365 Documentation](/dynamics365/get-started/contribute).  

## Process stage terminology

For each process step, the table includes a column, **Process stage**. It describes *when* to complete that step in an implementation project with Dynamics 365 apps. The column includes three values that are separated by semicolons as outlined in the following list:  

- [Project phase](#project-phase)
- [Configuration stage name](#configuration-stage-names)  
- [Process type](#process-types)  

The following sections describe the possible values and their definitions further.

### Project phase

The Dynamics 365 implementation guide organizes and discusses the phases of a project in the following basic stages:  

- Strategize

- Initialize

<!--- Design-->

- Develop

- Prepare

- Operate

Your implementation project team can choose to further classify and delineate the stages of your project. But we recommend that you use the basic stages to characterize all technology implementations. Learn more at [Introduction to Success by Design](../implementation-guide/success-by-design.md).

### Configuration stage names

There are three configuration stages:  

- *Base*  
- *Fundamental*  
- *Optional*  

For each phase, attributes describe if the step is mandatory to run the system or feature, or the configuration can change later.

The following table shows each of the configuration stage names with the indicator for each of the attributes for the stage. The **Phase** column indicates which stage or stages to complete the configuration in. The columns are described after the table.

| **Configuration stage name** | **Mandatory to run the system/ feature** | **Can change later** | **Can add later** | **Phase** |
|--|--|--|--|--|
| Base | YES | NO | NO | Initialize-Design |
| Fundamental | NO | YES | YES | Design-Operate |
| Optional | NO | NO | YES | Design-Operate |

- **Mandatory to run the system or feature**

  Some configurations and base data are required to run and operate any Dynamics 365 application. In some cases, you must set up these configurations for an application, feature, or module in a specific way to meet business requirements, or there may be cross-over between applications for a configuration.

  Examples include number sequences, system parameters, business units, legal entities. Here are some more concrete examples to illustrate the type of configuration or base data:  

  - You need *email templates* before you can send emails  

  - You need *customers* before you can use the order to cash processes  

  - You need *customer groups* before you can add a customer  

- **Can change later**

  This term means updating non-identifying fields or data on a record. Examples include choosing a field, selecting a value in a drop-down, or adding and enriching an existing record with more information.  

  The **Can change later** column has the following values:

  - YES  

    Indicates the values and configuration can be changed later without significant impact to the project and use of the system.

  - NO  

    Indicates the values and configuration can't be changed later without significant impact on the project and use of the system.

  In some cases, users might be able to change a value later, but we highly recommend that you don't change the initial configuration. Such configurations are marked with *NO* in the **Can change later** column.

  > [!NOTE]
  > [!INCLUDE [daf-config-change](../includes/daf-config-change.md)]

  > [!IMPORTANT]
  > Carefully consider the downstream impact if you decide to change any key references or identifiers on your data. Most Dynamics 365 apps have a function to rename or bulk update records. Use these functions with extreme caution.
  >
  > Use a test environment so that you can validate all downstream processes and integrations thoroughly before you rename data in the production environment. Tests must  cover the system performance of running the rename or bulk update function.

- **Can add later**

  Many modules, features, applications, and data points can be added later. For example, if you're implementing Dynamics 365 Finance for basic general ledger capabilities, you can skip the setup, configuration, and use of the *Fixed assets* module. Optionally, add this capability later.  

  But a configuration or design decision early in a project may limit, prevent, or substantially change what you can do later. For example, when you create a warehouse in Dynamics 365 Supply Chain Management, you must specify if you want to switch on advanced warehouse management functionality. This option can't be changed later. Although you can create a new warehouse later, the advanced warehouse management configuration can't be changed. So in this example, the *Warehouse configuration* would be marked as YES for **Can add later**, but the *Enable advanced warehouse management* configuration step would be set to NO.

  - YES  

    Indicates the values and configuration can be added, created, or configured later without significant impact to the project and use of the existing system and processes.

  - NO  

    Indicates the values and configuration can't be added, created, or configured later without significant impact on the project and use of the existing system and processes.

  > [!NOTE]
  > [!INCLUDE [daf-config-change](../includes/daf-config-change.md)]

### Process types

The third value in the **Process stage** column is the *process type*. This value describes if the step is configuration or operational.

- **Configuration**  

  Indicates that the configuration or step is related to the setup of Dynamics. For example, it supports the operation of a business process, but isn't done as a part of the daily, weekly, monthly, or annual business process. Examples include parameters, setup, and so on.

- **Operational**  

  Indicates the configuration or step is operational, meaning that it's part of daily, weekly, monthly, or annual business processes. The configuration or step shouldn't be conducted in a Gold environment prior to the go live. Examples include periodic batch processes, recording of transactions, posting transactions, and so on. For more information about planning environments for your implementation, see [Environment planning (finance and operations apps)](/dynamics365/fin-ops-core/fin-ops/imp-lifecycle/environment-planning).

## Process modifiers

Each process step that is described in a business process can have one or more modifiers to further clarify when and how the configuration or operational step should occur. The following modifiers are used throughout the documentation. When more than one modifier applies to a specific step, they're listed with a semicolon between each relevant modifier.

- **Early**  

  Indicates the configuration/step shouldn't be left to later iterations in the phase.

- **Gold**  

  Indicates the configuration or step is recommended to be part of the Gold configuration. The tag *Gold* is often used to describe the environment that will become the production environment at go-live, especially in projects with finance and operations apps. If the configuration or step is part of a subsequent phase, the step is likely part of the cutover strategy for configuration to be moved in during the go live of the subsequent phase.

- **Continuous**  

  Indicates the configuration or step is expected to change and is likely to be maintained or updated regularly post go-live. Any transactional steps, such as creating orders, posting journals, and so on, are considered continuous.

- **At least one**  

  Indicates that at least one is required to operate the system or feature.

- **Multiple are recommended**  

  Indicates that more than one is required or recommended in order to operate the system or feature.

## User navigation

This article describes the abbreviations we use to describe where to do something that is listed in a business process guide. A business process guide will typically mention a task and then specify how to navigate in which app to carry out that task. Tasks include how to set up, configure, and operate Dynamics 365.

### Application interfaces

Currently, business users access Dynamics 365 in the browser in different layouts, depending on the specific app. The customer engagement apps use the Unified Interface, and the finance and operations apps use a native layout. Learn more at [About Unified Interface for model-driven apps in Power Apps](/power-platform/admin/about-unified-interface) and at [Navigation concepts for finance and operations apps](/dynamics365/fin-ops-core/dev-itpro/user-interface/page-navigation). A full learning course is available at [Navigate finance and operations apps](/training/modules/navigate-finance-operations/).

> [!TIP]
> When you use the business process articles, note which app and where in that app to find the different tasks. If you can't see or navigate to a path, make sure you are in the right app, and that you have the relevant permissions. If the problem persists, work with your system admin. They can help you find out if you have the right licenses and permissions.

### Application abbreviations

The following list shows the abbreviations that are used for each Dynamics 365 app or service and their related user interfaces.

- COM = Dynamics 365 Commerce
- CSB = Commerce site builder
- POS = Commerce Point of Sale
- CSH = Customer Service hub
- FSH = Field Service hub
- FIN = Dynamics 365 Finance
- HR = Dynamics 365 Human Resources
- PMA = Dynamics 365 Project Operations
- POH = Project Operations hub
- SAL = Sales hub
- MKT = Dynamics 365 Marketing
- SCM = Dynamics 365 Supply Chain Management
- WMS = Warehouse Management System mobile device

### Administration and developer experiences abbreviations

The following list shows the abbreviations for applications that are used for administrative and developer experiences to support Dynamics 365 applications.

- PPAC = Power Platform Admin Center
- LCS = Lifecycle services
- VS = Visual Studio
- ADO = Azure DevOps
- AP = Azure portal
- MP = Maker portal (Power Apps, Power Automate, Power Virtual Agents, AI Builder)
- PP = Power Pages maker portal

### Entity

After the navigation, we list the entity for importing or exporting data in either [Dataverse](/power-apps/maker/data-platform/data-platform-intro) (DV) or the [data management framework](/dynamics365/fin-ops-core/dev-itpro/data-entities/data-entities-data-packages) (DMF). The type of entity is indicated with the abbreviation, and the name of the entity is indicated after the colon. Learn more in the [Process stage terminology](#process-stage-terminology) section.  

> [!TIP]
> Not all process steps list an entity. If that process step cannot be configured or set up through Dataverse or the data management framework, the **App, navigation, and entity** field will have *N/A* instead of an entity name.

## Example of process steps

Let's take a closer look at the example table from the start of the article.  

[!INCLUDE [daf-busprocess-example](~/../shared-content/shared/guidance-includes/daf-busprocess-example.md)]

This example shows us that the process step for *credit and collections parameters* must be configured during the *Initialize* process stage. It's part of the *base* configuration stage, and it's a *configuration*. That's what we learn from the the values in the [Process stage](#process-stage-terminology) column for that row in the table. Next, we learn that it's recommended to be part of the Gold configuration, and there must be at least one such configuration. Finally, the table teaches us where to set up things, namely in the Finance app, or by using the *CustomerParameters* entity in the data management framework (DMF).

## Next steps

Learn about the business process guide at [About the business process guide](about.md)  
