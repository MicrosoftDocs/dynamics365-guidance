---
title:  Define the organizational structure
description: Learn how the organizational structure determines how you can configure and deploy Dynamics 365 for business processes.
ms.date: 10/05/2023
ms.topic: conceptual
author: rachel-profitt
ms.author: raprofit
ms.reviewer: edupont 
---

# Define the organizational structure in Dynamics 365

***Applies to: Dynamics 365***

The organizational structure in Dynamics 365 defines the data structure for all downstream business processes and creates the framework for your application security.

The design for the organizational structure in Dynamics 365 can reflect the structure of legal entities, business unities, teams, and operating units. In the organizational design, you can consider other components such as sites, warehouses, financial dimensions, and chart of accounts.<!--; however, these other components aren't defined in this business process.-->

Define the organizational structure in the project as early as possible, because the organization design affects all other business process designs from data, usability, and security. Making a fundamental change to the design and approach later in the project can cause significant rework.

## Stakeholders

Many people in an organization must contribute to the decision-making process and design of the organizational structure in your Dynamics 365 project. The stakeholders include the following list:

* Finance stakeholders – Examples: CFO, Controller, Accounting manager

* Sales stakeholders – Examples: VP of sales, Sales Directors, General Managers

* Operations stakeholders – Examples: COO, Warehouse managers, Production managers

## Solutions with finance and operations apps

The following diagram shows a sample [organizational structure](/dynamics365/fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies?context=%2Fdynamics365%2Fcontext%2Fsupply-chain) for an organization implementing finance and operations apps. The diagram shows a solution with a consolidation legal entity, *Corporate*, that consolidates two [legal entities](#legal-entity), one for the USA and one for Europe. The third level shows [operating units](/dynamics365/fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit?context=%2Fdynamics365%2Fcontext). The USA legal entity has units for *Retail* and *Manufacturing*. The EUR legal entity has a unit for *Manufacturing*.

:::image type="content" source="../business-processes/media/organizational-structure-finance-operations.svg" alt-text="Finance and operations apps organization structure." lightbox="../business-processes/media/organizational-structure-finance-operations.svg":::

## Solutions with customer engagement apps

The following diagram shows a sample organizational structure for an organization implementing customer engagement apps with a single instance. The diagram shows a single instance with a parent business unit, *Corporate*, and two subsidiary business units for USA and Europe. The third level shows [teams](#teams). The USA business unit contains teams for sales in East and West regions. The European business unit has a team for sales in Europe.

:::image type="content" source="../business-processes/media/organizational-structure-customer-engagement.svg" alt-text="Customer engagement apps organization structure." lightbox="../business-processes/media/organizational-structure-customer-engagement.svg":::

## Organizational structure relationship between applications

The following diagram shows a sample of how the organizational structure for customer engagement apps relates to the finance and operations apps organizational structure.

:::image type="content" source="../business-processes/media/organizational-structure-compare.svg" alt-text="Organizational structure between applications." lightbox="../business-processes/media/organizational-structure-compare.svg":::

## Organizational structure components

The organization structure components reflect on the Dynamics 365 apps and down-stream business processes you plan to implement. However, at a minimum, you must configure at least one [legal entity](#legal-entity) to use any finance and operations apps, and at least one [business unit](#business-units) to implement any customer engagement apps. The following sections describe each component, the applications they're used with, and the major down-stream business processes they affect.

### Legal entity

A legal entity is an organization that has a registered or legislated legal structure. Legal entities can enter legal contracts and are required to prepare statements that report on their performance. In finance and operations apps, [legal entities](/dynamics365/fin-ops-core/fin-ops/organization-administration/tasks/create-legal-entity?context=%2Fdynamics365%2Fcontext%2Fsupply-chain) are required to perform any configuration and enter any transactions.  

> [!NOTE]
> With each new deployment, you get a default legal entity, *DAT*. However, don't use this legal entity for production use of the system.

In finance and operations apps, two other terms and concepts are tightly related to legal entities: *Company* and *data area ID*.

#### Company and data area ID

A company is a type of legal entity and is currently the only type of legal entity you can create. In other words, the terms *legal entity* and *company* are synonymous. The ID of the legal entity is also the ID of the company. When you perform configurations and process transactions, you must specify the *company* that the transactions and configuration apply to. Most tables that store the data has a **DataAreaID** column. The data area ID is the ID of the company or legal entity. With the values in this table column, you can filter and group data throughout the system by the company or legal entity it belongs to. The exception to this rule is tables that are shared globally throughout the system. Examples of shared tables include workers, products, and chart of accounts, to name a few.

Some types of transactions can cross legal entities, namely *intercompany transactions*. Dynamics 365 supports [intercompany accounting](/dynamics365/finance/general-ledger/intercompany-accounting-setup) with financial journal entries that [cross companies](/dynamics365/finance/general-ledger/example-balanced-journals-interunit-accounting). With Supply Chain Management, you can set up [intercompany trade](/dynamics365/supply-chain/sales-marketing/intercompany-trade-set-up) to handle sales, purchase, or project transactions that cross companies.

### Business units

In customer engagement apps, a business unit is a logical grouping of related business activities.

Set up separate business units to reflect an organization of departments or divisions with separate products, customers, and marketing lists, for example. Business units are mapped to an organization's departments or divisions. Users can securely access data in their own business unit, but they can't access data in other business units.

Business units, security roles, and users are linked together in a way that conforms to the customer engagement apps role-based security model. Use business units together with security roles to control data access so people see just the information they need to do their jobs.  

In finance and operations apps, business units are a type of operating unit. Learn more in the next section.

### Operating units

In finance and operations apps, an [operating unit](/dynamics365/fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit?context=%2Fdynamics365%2Fcontext%2Ffinance) is an organization that is used to divide the control of economic resources and operational processes in a business. People in an operating unit have a duty to maximize the use of scarce resources, improve processes, and account for their performance.

The types of operating units include *cost centers*, *business units*, *value streams*, *departments*, and *commerce channels*. Although operating units are optional in finance and operations apps, they're commonly used as [financial dimensions](/dynamics365/finance/general-ledger/set-up-balance-dimensions).

### Teams

In finance and operations apps, a team is an organizational unit where the members share a common responsibility, interest, or objective. It's important to note that Teams can't be used in organizational hierarchies.  

In customer engagement apps, a team is a group of users who share and collaborate on business records. A user can be associated with multiple teams.

### Sites

In Dynamics 365 Supply Chain Management, a *site* is a grouping of business resources, such as warehouses and production units. These units share interrelated transactions, are located at a specific geographic location, and belong to a single legal entity. A single site can't be shared by multiple legal entities. To use Supply Chain Management, you need at least one site, and you can then add other sites.

In customer engagement apps, a *site* is an office location or other facility where service operations take place.  

### Warehouses

In Dynamics 365 Supply Chain Management, a warehouse is used to track inventory and manage inventory processes such as receipts, issues, transfers, and counting. Although a warehouse isn't required in solutions with Supply Chain Management, a warehouse is required to use the advanced warehouse management functionality. Most organizations that implement Supply Chain Management, create at least one warehouse.

## Organization structure design considerations

Before you define the solution and design in Dynamics 365, for your organizational structure, there are several considerations and design factors that should be considered.

### Countries and regions

For Dynamics 365 solutions with finance and operations apps, each legal entity is tied to one localization. The localization features of Dynamics 365 reflect the country/region that you specify as the primary address of the legal entity. You can't combine multiple countries or regions in a single legal entity in finance and operations apps.

Localizations are controlled by special kernel code that checks the metadata on objects. It's deeply embedded throughout the entire solution. Although finance and operations apps are highly extensible, we recommend that you do *NOT* attempt extending the solution to support multiple localizations within a single legal entity.

### Legally separate entities

Different countries or regions may have different definitions of organizations. Generally speaking, when you have two legally separate entities, the configuration of legal entities in Dynamics 365 matches the legal or regulatory structure of your organization. We do *NOT* recommended that you create separate entities for divisions or business units that are legally the same entity. In other words, don't create a separate legal entity for each site or business unit if the sites or business units are all part of the same legal organization.

### Tax registration IDs

In some countries and regions, a tax registration ID is a separate legal entity. Finance and operations apps support linking tax registration IDs to each legal entity. If your organization has multiple tax registration IDs in the same country/region, consider combining the entities into the same legal entity in Dynamics 365. You are required to use the *Regulatory Configuration Service* (RCS) to support multiple tax IDs in the same legal entity to calculate tax on your transactions throughout finance and operations apps.

### Security

Finance and operations apps have strict security separation between each legal entity by design of the data area ID. For example, your organization has strict security requirements between divisions or departments to separate data, and it restricts users to see data relative to their specific division or department. In such scenarios, use legal entities to represent the divisions or departments.

With finance and operations apps, you can configure record or row level security by using extensible data security (XDS) policies. However, we don't recommended that you use XDS policies as a way to implement widespread row level security.

With customer engagement apps, you can separate security using business units or teams. You should carefully consider your security requirements throughout the system when deciding whether to use business units, teams, or both.

### Data sharing

Finance and operations apps support the sharing of data across legal entities. However, there are some limitations to using data sharing, and some other features that aren't supported when you use data sharing. When you need to separate legal entities, for example, due to localizations, consider if you can share data across legal entities. When you enable data sharing, there are also limitations to the number of legal entities and number of records that can be shared. Make sure you consider the size of your current organization and your growth over the next 5-10 years when considering using data sharing as a part of your organizational approach.  

> [!IMPORTANT]
> Data sharing isn't supported in solutions that combines finance and operations apps and customer engagement apps with Dual Write to synchronize data between the applications.

In other words, don't use data sharing if you have dual write requirements or may have dual write requirements in the future.

When you use separate legal entities, remember that most data is secured and separated for each legal entity. In other words, the data isn't shared by default. As a result, you may have to duplicate or share configuration across legal entities if the data is required in all legal entities. When you need different configurations or parameters between sites, or business units for example, consider if separating the legal entities by sites or business units is the best option. You must weigh the usability of having multiple entities against the configuration or business process differences that would be required when combining legal entities.

### Usability

Usability should be a key consideration when determining how many legal entities you need to create in finance and operations apps. When you use multiple legal entities in your organization, if you transact across the entities, you must use intercompany features. This can be more cumbersome, and it adds complexity to the implementation.

Remember that most pages in finance and operations apps only allow you to see or view data from a single legal entity. This means that a user must change the legal entity to view or enter data related to another legal entity. There are some exceptions to this rule, such as global general journal entries, where you can see or create journal entries from any legal entity on behalf of any legal entity.

### Chart of accounts and the balance sheet

In finance and operations apps, you can share the chart of accounts and financial dimensions across legal entities by linking each ledger to the same chart of accounts. Conversely, you can also have separate charts of accounts and financial dimensions in each legal entity if necessary. When you have multiple legal entities, you can create more consolidation legal entities to combine the financial data into a single legal entity. However, it's important to note that a consolidation or elimination legal entity can't have transactions other than the consolidation performed. For example, you have a parent company that makes purchases and needs to consolidate the financials from three other companies. In this scenario, you create a separate legal entity for the sole purpose of consolidating.

The default behavior of the chart of accounts in finance and operations apps is that it's a double-entry, real-time or near real-time system of accounting. What this means is that for each entry, there's an equal and opposite entry. The trial balance in finance and operations apps always sums to zero. For example, many organizations have a requirement to keep a balance sheet to balance by a division or business unit. You can use one financial dimension in the ledger configuration as a balancing financial dimension. In other words, for each entry to a specific account, the dimension value has an equal and opposite entry. If you have a requirement to maintain multiple balance sheets, we  recommended that you consider using the balancing financial dimension to meet the business requirements instead of creating a separate legal entity.

## Configuring the organization structure

There are various components that are used in the configuration of organization structure in Dynamics 365 applications. The following table shows the configurations available, and the sequence recommended for setting up the configurations. *FO* in the **Product** column indicates finance and operations app, and *CE* indicates customer engagement apps. The **Required** column indicates a *Y* for required and an *N* for not required. Use the links on the configuration component to learn more about how to configure that component.

| Seq | Configuration component | Required | Product | Menu path |
|--|--|--|--|--|
| 1 | [Legal entity](/dynamics365/fin-ops-core/fin-ops/organization-administration/tasks/create-legal-entity) | Y | FO | **Organization administration &gt; Organizations &gt; Legal entities** |
| 2 | [Business units](/power-platform/admin/create-edit-business-units) | Y | CE | **Settings** (in the upper-right corner) **&gt; Advanced Settings &gt; Settings &gt; Security &gt; Business Units** |
| 3 | [Operating units](/dynamics365/fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit) | N | FO | **Organization administration &gt; Organizations &gt; Operating units** |
| 4 | Team types | N | FO | **Organization administration &gt; Organizations &gt; Teams &gt; Team types** (button) |
| 5 | [Teams](/dynamics365/fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies?context=%2Fdynamics365%2Fcontext%2Ffinance#teams) | N | FO | **Organization administration &gt; Organizations &gt; Teams** |
| 6 | [Organization hierarchies](/dynamics365/fin-ops-core/fin-ops/organization-administration/plan-organizational-hierarchy?context=%2Fdynamics365%2Fcontext%2Ffinance) | N | FO | **Organization administration &gt; Organizations &gt; Organization hierarchies** |
| 7 | Organization hierarchy purposes | N | FO | **Organization administration &gt; Organizations &gt; Organization hierarchy purposes** |

## Recommended practices

When implementing your organization structure in Dynamics 365, use the following recommended practices.  

* Consider the usability of the solution  
* Don't combine multiple countries or regions in a single legal entity  
* Don't separate business units or divisions into separate legal entities if they aren't legally separate  

<!--## Tags

Industries: All

Stakeholder: Finance Stakeholders, Operations Stakeholders

Products: Dynamics 365

Configuration stage: Foundational-->
