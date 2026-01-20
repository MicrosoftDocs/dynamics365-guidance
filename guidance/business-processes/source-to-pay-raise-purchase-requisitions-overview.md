---
title: Raise purchase requisitions overview
description: Learn about the Raise purchase requisitions business process area, including learning about various stakeholder types.
author: Pjagotra
ms.author: raprofit
ms.topic: concept-article
ms.date: 04/21/2025
---

# Raise purchase requisitions overview

***Applies to: Dynamics 365 Commerce, Dynamics 365 Field Service, Dynamics 365 Finance, Dynamics 365 Project Operations, Dynamics 365 Supply Chain Management***

This article describes the importance of *purchase requisitions* as a crucial internal document in supporting your organization's purchasing needs, and explains how Dynamics 365 products can streamline their creation.

Many organizations use purchase requisitions as a formal request made by an employee or department to acquire goods or services. It serves as the initial step in the procurement process, outlining the need for certain items or services. The benefits of using purchase requisitions are:

- **Control and oversight**: Purchase requisitions help in controlling and monitoring the procurement process by ensuring that all purchases are authorized and align with the organization's budget and objectives.
- **Budget management**: They assist in managing budgets more effectively by providing visibility into planned purchases before they're made.
- **Streamlining procurement**: Purchase requisitions streamline the procurement process by centralizing requests and standardizing documentation, leading to greater efficiency and consistency in the procurement creation process.
- **Compliance and audit**: They contribute to ensuring compliance with internal policies and external regulations by documenting the approval process and providing a paper trail for audits.

Purchase requisitions aren't mandatory for every organization, but they can be useful when you need more control and visibility over the purchasing process. If you want to include purchase requisitions in your scope, plan to address them before purchase orders, as they affect the downstream processes of creating and approving orders. You can also add purchase requisitions later in your project, but this may require some adjustments in your existing purchasing workflows and policies.

A poorly-defined business process for purchase requisitions can lead to inefficiencies, errors, and delays in the purchasing cycle, as well as increased risk of fraud and non-compliance. While a well-defined process can streamline the approval workflow, improve the accuracy and transparency of the purchasing data, and enhance the collaboration and communication between the purchasing and requesting departments.

## Stakeholders

Many people across the organization should contribute to the *raise purchase requisitions* business process. The following list provides examples of such stakeholders:

- **Procurement stakeholders**: Roles such as Buyer, Director of Procurement, Purchasing agent, Purchasing manager and various line managers are integral part of providing insight on purchase process within the organization. Frontline supervisors are critical in the review and approval of purchase requisition.
- **Management**: Roles such as finance managers, CEOs, COOs, and various line managers are for approvals of large purchase requisitions and make decisions on spending and approval authority of organizational personnel.
- **Project managers**: In the context of Dynamics 365 Project Operations and service-based organizations, project managers play key roles by overseeing the purchase requisition process related to their specific project. They can be crucial in the review and approval of purchase requisitions.
- **Compliance officers and internal auditors**: Compliance officers are responsible for ensuring that the organization adheres to relevant regulations and standards. They use the system to monitor and report on compliance, track regulatory changes, and make necessary adjustments to policies and procedures to maintain legal and ethical compliance.
- **Employees**: Employees request for item or services for your business and are responsible for ensuring the accuracy of their records.

## Process flow

The following diagram illustrates the *Raise purchase requisitions* business process area.

:::image type="content" source="media\source-to-pay-raise-purchase-requisitions-process-flow.svg" alt-text="Diagram of the 'create purchase requisitions' business process." lightbox="media\source-to-pay-raise-purchase-requisitions-process-flow.svg":::

The flow diagram covers the following steps:

1. Start
1. Identify Requisition Needs
1. Draft Requisition
1. Review Requistion
1. Approve Requisition?
   - No: Revise Requistion
   - Yes: Submit Requisition
1. End

## Purchase policy overview

A purchasing policy is a set of rules that govern the requisition process, helping procurement administrators align with the organization's strategic purchasing goals. To create a purchasing policy, you must define and configure policy rules along with start date and end date.

A policy must be linked to an organization before it can take effect. Purchasing policies are tied to the procurement internal control hierarchy purpose, thus they only apply to organizations within hierarchies with this designation. Additionally, you can choose organizations from legal entities list known as Companies in the policy framework.

Purchase requisition lines let users choose items from an assigned catalog. If an item or service isn't in the catalog, users can still select the category and manually enter the product name and details.

The purchase policy can be adjusted to match the organization's purchasing process. These rules govern procurement and requisition processes, including catalog and category access, vendor selection, and re-approval for purchase orders. They also define criteria for informal or formal RFQs and offer optional controls for requisition purposes and replenishment. Additionally, they outline policies for consolidating and generating purchase orders from approved requisitions.

## Implement raise purchase requisitions

Purchase requisition is a global feature that allows users to create a request across all legal entities in the organization. This means that a user can specify that they want a product or service for Company A or Company B, for example. In contrast, purchase orders are always specific to the current company.

In Dynamics 365, you have the option to create a purchase requisition before creating a purchase order to take advantage of the benefits mentioned above. Alternatively, Dynamics 365 also allows you to directly create a purchase order without first creating a purchase requisition.

[!INCLUDE [bus-proc-config-table-explained](../includes/bus-proc-config-table-explained.md)]

For more information about the abbreviations and explanations of the values used in this table, refer to [Business processes, steps and how to find things](about-steps-navigation.md).

| Process step | Process stage | Process modifier | Application: Navigation and Entity |
| ------------ | ------------- | ---------------- | ---------------------------------- |
| [Purchase requisition permission](/dynamics365/supply-chain/procurement/tasks/set-up-permissions-ordering-products) | Initialize; Configuration; Base | Early; Continuous; multiple recommended | **SCM**: Procurement and sourcing > Setup > Policies > Purchase requisition permissions</br>**DMF**: N/A |
| [Set up number sequences for purchasing](/dynamics365/fin-ops-core/fin-ops/organization-administration/number-sequence-overview) | Initialize; Configuration;  Base | Early; Gold; At least one; More than one recommended | **SCM**: Procurement and sourcing > Setup > Procurement and sourcing parameters> number sequences> Purchase requisition voucher</br>**DMF**: N/A |
| [Legal entity](/dynamics365/fin-ops-core/fin-ops/organization-administration/tasks/create-legal-entity) | Initialize; Configuration; Base | Early; Gold; At least one | **FIN**: Organization administration > Organizations > Legal entities</br>**DMF**: Legalentities |
| [Operating unit](/dynamics365/fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit) | Initialize; Configuration; Base | Early; Gold; At least one | **FIN**: Organization administration > Organizations > Operating Units</br>**DMF**: OperatingUnit |
| [Release product](/dynamics365/supply-chain/pim/tasks/create-released-product-single-company) | Initialize; Configuration; Base | Gold; More than one recommended | **SCM**: Product information management > Products > Released products</br>**DMF**: ReleaseProductsV2 |
| [Procurement category](/dynamics365/supply-chain/procurement/tasks/set-up-procurement-category-hierarchy) | Design; Configuration; Optional | Gold; More than one recommended | **SCM**: Product information management > Setup</br>Categories and attributes > Category hierarchies</br>**DMF**: Productcategoryhierarchies |
| [Vendor](/dynamics365/supply-chain/procurement/tasks/create-vendor-account) | Initialize; Configuration; Base | Early; Gold; At least one | **FIN**: Accounts payable > Vendors > All vendors</br>**DMF**: VendorV2 |
| Business Justification | Design; Configuration; Optional | Gold; Continuous | **SCM**: Procurement and sourcing</br>Setup > Policies > Business justifications</br>**DMF**: PurchPurchaseRequisitionBusinessJustification |
| [Unit of measure](/dynamics365/supply-chain/pim/tasks/manage-unit-measure) | Initialize; Configuration; Base | Early; Gold; At least one | **FIN**: Organization administration</br>Setup > Units > Units</br>**DMF**: Units |
| [Currency](/training/modules/configure-currencies-dyn365-finance/) | Initialize; Configuration; Base | Early; Gold; At least one | **FIN**: Cost accounting > Ledger setup > Currencies > Currency exchange rates</br>**DMF**: Exchangerates |
| [Purchasing policy](/dynamics365/supply-chain/procurement/purchase-policies) | Initialize; Configuration; Base | Early; Gold; At least one | **SCM**: Procurement and sourcing</br>Setup > Policies > Purchasing policies</br>**DMF**: N/A |
| [Employee](/dynamics365/human-resources/hr-personnel-enter-worker-information) | Initialize; Configuration; Base | Early; Gold; At least one | **FIN**: Human resources > Workers > Employees</br>**DMF**: EmployeeV2 |
| [User](/dynamics365/fin-ops-core/fin-ops/sysadmin/create-new-users) | Initialize; Configuration; Base | Early; Gold; At least one | **FIN**: System administration > Users > Users</br>**DMF**: N/A |
| [Purchase requisition workflow](/dynamics365/supply-chain/procurement/purchase-requisitions-workflow) | Initialize; Configuration; Base | Early; Gold; At least one | **SCM**: Procurement and sourcing</br>Setup > Procurement and sourcing > workflows</br>**DMF**: N/A |
| [Item sales tax group](/dynamics365/finance/general-ledger/tasks/set-up-sales-tax-groups-item-sales-tax-groups) | Initialize; Fundamental; Configuration | Gold; Continuous | **FIN**: Tax > Indirect taxes > Sales tax > Item sales tax groups</br>**DMF**: Item sales tax group |
| [Sales tax group](/dynamics365/finance/general-ledger/indirect-taxes-overview) | Initialize; Fundamental; Configuration | Gold; Continuous | **FIN**: Tax > Indirect taxes > Sales tax > Sales tax groups</br>**DMF**: Sales tax groups |
| Inventory dimensions | Initialize; Fundamental; Configuration | Early; Gold; At least one | **SCM**: Inventory management</br>Setup > Inventory breakdown</br>**DMF**: Sites V2, Warehouses, Warehouse locations |
| [Financial dimensions](/dynamics365/finance/general-ledger/financial-dimensions) | Initialize; Fundamental; Configuration | Early; Gold; At least one | **FIN**: General ledger > Chart of accounts > Dimensions > Financial dimensions</br>**DMF**: Financial dimensions |

## Requisition purposes

Requisition purposes make the process of fulfilling requisition demands more flexible. When you create a requisition, you can assign one of two purposes to it:

- Consumption
- Replenishment

In the procurement policies, you can control the requisition purposes that're available when a requisition is created for your organization.

- **Purpose of consumption**: A requisition that has a purpose of consumption represents demand for items or services that are used internally by your organization. The demand is created by a purchase order. If purchasing policy is set up with automatically creation of purchase order, then order is created and is in approved state.
- **Purpose of replenishment**: A requisition that has the purpose of replenishment represents demand to replenish inventory. For example, you create a requisition to replenish items so that they can be sold at a specific location at a specific time. The demand for such requisition can result in purchase order, transfer order, or production order.

## Next steps

If you would like to implement Dynamics 365 solutions to assist with the *Raise purchase requisitions* business process, you can use the following resources and steps to learn more. (Links are added when the articles are ready.)

1. [Define procurement and sourcing strategies](source-to-pay-define-procurement-sourcing-strategy-overview.md)  
1. [Manage supplier relationships](source-to-pay-manage-vendor-relationships-overview.md)  
1. *Source and contract goods and services*
1. [*Procure goods and services*](source-to-pay-procure-materials-services-overview.md)   

    1. *Raise purchase requisitions overview* (the article that you're currently reading)
    2. *Issue purchase order*
    3. *Manage open purchases*
    4. *Issue blanket purchase orders*  
    5. *Return goods to suppliers*  
    6. *Consolidate requisitions*  
    7. *Analyze supply purchase plan*
1. [Manage accounts payable](source-to-pay-manage-accounts-payable-overview.md)  
1. *Analyze procurement and sourcing*  

## Related patterns

The following patterns can help your implementation of the *raise purchase requisitions* business process. (Links are added when the articles are ready.)

- Add a category line to a purchase requisition
- Add an item to purchase requisition
- Add products using punch-out e-procurement
- Import purchase requisitions from a third-party system

## Related information

You can use the following resources to learn more about the *Raise purchase requisitions* business process in Dynamics 365:

- [Purchase requisition overview - Supply Chain Management](/dynamics365/supply-chain/procurement/purchase-requisitions-overview)
- [Create a requisition for consumption - Supply Chain Management](/dynamics365/supply-chain/procurement/tasks/create-requisition-consumption)
- [Purchase requisition workflow - Supply Chain Management](/dynamics365/supply-chain/procurement/purchase-requisitions-workflow)
- [Create a purchase requisition - Training](/training/modules/configure-perform-procure-purchase-dyn365-supply-chain-mgmt/6-requisition)
- [Source to Pay business process overview in Dynamics 365 Finance & Supply Chain Management | TechTalk](https://community.dynamics.com/galleries/gallery-posts/?postid=5583207c-e8ff-ee11-a1fd-6045bdd6d499)

<!-- ## Tags

*Industries:* Manufacturing (20-39), Public Utilities (40-49), Wholesale Trade (50-51), Retail Trade (52-59), Finance, Insurance, Real Estate (60-67), Services (70-89), Public Administration (91-99)

*Stakeholders:* Accounts payable, Administrative, Audit, Finance, Human Resources, IT, Marketing, Merchandising, Operations, Production, Project Management, Purchasing

*Products:* Dynamics 365 Finance, Dynamics 365 Project Operations, Dynamics 365 Supply Chain Management -->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [Amir Hemani](https://www.linkedin.com/in/amirhemani1) \| Consulting Manager / Solution Architect

Other contributor:

- [Adi Vijayashankar](https://www.linkedin.com/in/adithya-adi-vijayashankar-b3490a16) \| Senior Solutions Architect, FastTrack for Dynamics 365
