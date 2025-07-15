---
title: Custom work order summary with related case details
description: Learn how to configure work order summaries in Dynamics 365 Field Service by incorporating data from related case details.
ms.date: 07/15/2025
ms.topic: best-practice
author: rajislearning
ms.author: rajeeku
ms.custom:
  - O25-FieldService
---
# Custom work order summary with related case details

This article describes how you can extend work order summaries to include fields from related case entities.

Learn more about prerequisites on how to configure work order summary at [Work order summary with Copilot in Field Service](/dynamics365/field-service/work-order-recap).

## Business scenario

Organizations often begin service requests as support cases, capturing key context like issue descriptions, urgency, and communication history. When these cases are converted into work orders, technicians may lose access to this valuable information.

## Solution

Dynamics 365 Field Service allows administrators to extend the Work Order Summary with fields from related case entities. The following section outlines how to configure the Work Order Summary to include related case details, ensuring technicians receive all relevant information briefly.

## Configuration

To meet this business need, a sample configuration may include columns from respective tables:

- Work Order:
  - **City** - to inform technicians of the service location, aiding in scheduling and travel preparation.
- Case:
  - **Description** – to understand customer sentiment directly from verbatim
  - **Priority** – Customer's sentiment on how critical the issue is

## Prerequisites

Ensure the **Copilot for Work Order** feature is enabled:

1. Open the Field Service app.
2. Navigate to Settings.
3. Go to Field Service Settings.
4. Under the Features tab, toggle the **Copilot for Work Order** to switch on the capability.

> [!NOTE]
> This capability doesn't require environment-level use of Copilot. The work order summary functionality operates independently from the full Copilot sidecar experience.

## Configuration steps

1. Navigate to **Field Service Settings** > **Copilot Settings**.
2. Open **Summary Configuration**.
3. Select **Work Order** as the record type for customization.
4. Enable **Configure Summary**.
5. Add the following tables:
   - Work Order
   - Case
6. Select the fields that provide critical context to technicians, ensuring they have the necessary information to perform their tasks efficiently and compliantly.

## Test the configuration

1. In the **Sample Summary** section, select a Work Order record with related data.
2. Choose the **Test** action to generate and review the summary output.

  :::image type="content" source="media/field-service-work-order-summary-related-case-details.png" alt-text="Work order summary preview with related case details.":::

This preview allows validation of field selections and ensures the summary meets business needs before deployment.

## Related content

- [Custom work order summary with custom fields](field-service-work-order-summary-custom-tables.md)  
- [Work order summary configuration template](fs-work-order-summary-configuration-template.md)  
