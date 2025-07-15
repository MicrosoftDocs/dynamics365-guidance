---
title: Customized work order summary with fields from custom tables
description: Learn how to configure work order summary in Dynamics 365 Field Service to include data from custom tables.
ms.date: 07/15/2025
ms.topic: best-practice
author: rajislearning
ms.author: rajeeku
ms.custom:
  - O25-FieldService
---

# Customized work order summary with fields from custom tables

This article describes how you can extend work order summaries to include fields from both standard and custom tables so that technicians are fully prepared before site visits.

Learn more about prerequisites on how to configure work order summary at [Work order summary with Copilot in Field Service](/dynamics365/field-service/work-order-recap).

## Business scenario

A facilities management company delivers HVAC maintenance services across multiple client locations. 
Each work order includes specific prerequisites - such as safety briefings, access instructions, and required tools that technicians must have before starting work. 
These prerequisites are stored in a custom table, **Work Order Prerequisites**.

## Solution

When an administrator extends the **Work Order Summary** form to incorporate fields from this custom table, technicians gain immediate access to all essential information. 
This helps reduce errors, enhance compliance, and improve first-time fix rates ultimately boosting operational efficiency and customer satisfaction.

## Configuration

To meet this business need, the organization chooses fields from the following tables:

- Work Order:
  - **City** - to inform technicians of the service location, aiding in scheduling and travel preparation.
- Work Order Prerequisites:
  - **Prerequisite Type** - An Option set field with the option values **Safety** and **Access** to highlight critical preparations.
  - **Prerequisite Ask** - A text field to specify mandatory actions before work begins such as *Complete Safety Induction*.

## Prerequisites

Ensure the **Copilot for Work Order** feature is enabled:

1. Open the Field Service app.
2. Navigate to **Settings**.
3. Go to **Field Service Settings**.
4. On the **Features** tab, toggle the **Copilot for Work Order** field to switch the capability on.

> [!NOTE]
> This capability doesn't require environment-level use of Copilot. The work order summary functionality operates independently from the full Copilot sidecar experience.

## Configuration steps

1. Navigate to **Field Service Settings** > **Copilot Settings**.
2. Open **Summary Configuration**.
3. Select **Work Order** as the record type for customization.
4. Enable **Configure Summary**.
5. Add the following tables:
   - Work Order
   - Work Order Prerequisites
6. Select the fields that provide critical context to technicians, ensuring they have the necessary information to perform their tasks efficiently and compliantly.

## Test the configuration

1. In the **Sample Summary** section, select a Work Order record with related data.
2. Choose the **Test** action to generate and review the summary output.

  :::image type="content" source="media/field-service-work-order-summary-custom-table.png" alt-text="Work order summary preview with custom table data":::

This preview allows validation of field selections and ensures the summary meets business needs before deployment.

## Related content

- [Custom work order summary with related case details](field-service-work-order-summary-related-case-details.md)  
- [Work order summary configuration template](fs-work-order-summary-configuration-template.md)  
