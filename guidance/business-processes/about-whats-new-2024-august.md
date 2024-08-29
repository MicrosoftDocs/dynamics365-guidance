---
title: What's new or changed in the business process catalog August 2024
description: What's new or changed in the August 2024 version of the business process catalog that Microsoft publishes as a downloadable file.
author: rachel-profitt
ms.author: raprofit
ms.topic: whats-new #Required; don't change.
ms.collection: #Required; Leave the value blank.
ms.date: 08/29/2024
ms.custom: bap-template #Required; don't change.
---
# What's new or changed in the business process catalog August 2024

The August 2024 release of the business process catalog includes improvements across many of the end-to-end processes. It also includes improvements suggested by the community through [GitHub Issues](https://github.com/microsoft/dynamics365patternspractices/issues).  

[!INCLUDE [bus-proc-cat-intro](../includes/bus-proc-cat-intro.md)]  

## Get the latest version

Download the latest version of the catalog from [https://aka.ms/businessprocesscatalog](https://aka.ms/businessprocesscatalog).

## Deprecated rows

The August 2024 version of the business process catalog includes rows where the status is **Deprecated**. These rows are no longer active and will be removed in a future release of the catalog. In addition to the new **Deprecated** status, there's a new column, **Alternate Process Sequence ID**. This column is used to indicate that the deprecated row is available in a new location in the catalog.

## Workshops

A new type of work item, **Workshops**, is included in the business process catalog template for Azure DevOps. There are several types of workshops included in the new template as outlined in the following list:

- **Scenario board workshop**  

  This type of workshop is intended to be the first interaction with the customer to discuss the business requirements, scope, and direction for an end-to-end process. The primary output of this workshop is a storyline or series of user stories that represent the core processes for the business. The information gathered in this workshop should allow the implementation team to configure an end-to-end solution for the business process selected. Each end-to-end process is intended to include one scenario board workshop. This release includes the workshop template for the *Acquire to dispose* end-to-end process.
- **Storyline design review workshop**  

  This workshop is intended to demonstrate the key storyline outlined in the scenario board workshop in the software and to review a high-level solution architecture. This workshop can be thought of as a fit-to-standard workshop. The key outputs of this workshop include a refined list of user stories and any gaps, risks, or issues with the standard approach presented. Each end-to-end process is intended to include one scenario board workshop. This release includes the workshop template for the *Acquire to dispose* end-to-end process.
- **Detailed design workshop**  

  This workshop is intended to further refine and detail the design for the end-to-end solution including edge cases, negative requirements, security, and so on. Each business process area is intended to have at least one detailed design workshop. This release includes detailed design workshops for the *Acquire to dispose* end-to-end process.
- **Success by Design implementation workshops**  

  These workshops are part of the Success by Design implementation approach. The workshops are included in the Administer to operate end-to-end process under the Implement solutions business process area. Learn more in [the implementation guide](../implementation-guide/overview.md).

To include these rows in your import into Azure DevOps, you must create a custom work item type called **Workshop** that includes the following fields:

- **Description**
- **Agenda** (custom field – Text (multiple lines))
- **Workshop assumptions** (custom field – Text (multiple lines))
- **Key questions to ask** (custom field – Text (multiple lines))
- **Estimated time**

## Acquire to dispose improvements

- New workshops and tasks added to the [acquire to dispose end-to-end process](acquire-to-dispose-overview.md).
- New business process area for *Define asset strategy and policies*. Deprecated many processes from other business process areas and moved them under the new area. Refer to the **Alternate process sequence ID** field for a mapping of where the deprecated processes moved to.
- New business process area for *Analyze assets* including new business processes and patterns.
- Added the **Asset leasing** module to configuration deliverables related to asset leasing.

## Case to resolution improvements

- New business process and patterns added for *Analyze service performance*.
- New business process and patterns added for *Optimize services*.

## Design to retire improvements

- Improved pattern names for *Define product design policies*.
- Improved pattern names for *Manage product pricing*.
- Improved pattern names for [Define product costing](design-to-retire-define-product-costing-overview.md).

## Hire to retire improvements

- Improved patterns for *Record employee absences*.

## Inventory to deliver improvements

- New business process area for [Define and manage warehouse operations strategy and policies](inventory-to-deliver-define-manage-warehouse-operations-overview.md).
- Removed duplicate patterns in Maintain inventory levels.
- New patterns to support consigned inventory.

## Plan to produce improvements

- Improved pattern names in [Plan production operations](plan-to-produce-plan-production-operations-overview.md).
- Improved pattern names in [Run production operations](plan-to-produce-execute-production-operations-overview.md).
- New pattern for *Scrap defective inventory*.

## Project to profit improvements

- Improved pattern names in [Govern projects](project-to-profit-govern-projects-overview.md).
- Improved patterns in *Create projects*.
- Improved patterns in [Manage project financials](project-to-profit-manage-project-financials-overview.md).

## Prospect to quote improvements

- Consolidated patterns for *85.50.020 Create opportunities* and *85.50.025 Manage project opportunities*.

## Record to report improvements

- New pattern for *Define parameters for revaluing budget amounts*.
- Updated pattern for *Establishing banking relationships*.
- New and updated patterns for *Entering budget amounts*.

## Service to cash improvements

- Updated pattern names for [manage service assets](service-to-cash-manage-service-assets.md).
- Updated pattern names for [manage service resources](service-to-cash-manage-service-resources.md).
- Updated pattern names for [create and process service work](service-to-cash-create-process-service-work.md).

## Administer to operate improvements

- The entry *99.01 Implement solutions* now includes a new business process area with 17 sections aligned with the Success by Design implementation method. Each section links to [the Dynamics 365 implementation guide](../implementation-guide/overview.md) and covers processes and tasks with best practices. There are over 300 new rows in this update.
- Renamed *99.55 Manage data synchronization* to *99.55 Manage data*.
- Updated and new patterns in [Manage system access and security](administer-to-operate-manage-system-access-security.md), [Train users and increase adoption](administer-to-operate-train-users-increase-adoption-overview.md), *Monitor systems, environments, and capacity*, *Manage data*, and [Support systems](administer-to-operate-support-systems-overview.md).

## Related information

- [About the business process catalog for Dynamics 365 apps and services](about.md)  
