---
title: Configure Dynamics 365 Identifier Writeback for FHIR
description: Learn how to write back Dynamics 365 GUIDs to an external FHIR server using Microsoft for Healthcare, Dataverse, and Azure Logic Apps.
author: edupont04
ms.author: edupont
ms.reviewer: edupont
ms.date: 10/07/2025
ms.topic: reference-architecture
---
# Configure Dynamics 365 identifier write-back for Fast Healthcare Interoperability Resources (FHIR)

***Applies to***: ***Dynamics 365, Dataverse, Azure Logic Apps***

This article shows how to use Microsoft for Healthcare, Dataverse, and Azure Logic Apps to write back Dynamics 365 globally unique identifiers (GUIDs) to an external FHIR server. This article is for healthcare organizations that use the Fast Healthcare Interoperability Resources (FHIR) standard.

## Introduction

Microsoft for Healthcare includes the Dataverse healthcare APIs and FHIR data maps for each FHIR resource. These components let data flow between Dynamics 365 and an external FHIR server, but they don't let you write back Dynamics 365 identifiers for all FHIR resources out of the box.

Healthcare organizations might need each FHIR resource record to include its Dynamics 365 identifier in write-back. To do this, set up a repeatable solution for each enabled FHIR resource: a custom "identifier" Dataverse table, an expansion map configuration, and a synchronous plugin step.

Use cases include scenarios where:

- Sync patient FHIR resources with Dataverse as needed.
- Filter messages from the FHIR server to include only records and related records' Dynamics 365 identifiers.
- Let external systems reference Dynamics 365 identifiers for reporting.

Because this change affects integration design, data integrity, and implementation effort, decide if it fits during discovery and design, well before you start building. Engage your customer's data stewards and stakeholders from both the business and technical teams who use or work with FHIR server data, specifically the data synced with Dataverse.

## Architecture

This diagram shows the solution architecture.

:::image type="content" source="media/healthcare-writeback-dynamics-365-identifiers-fhir-server-architecture.svg" alt-text="Diagram that shows the architecture for writing Dynamics 365 identifiers back to a FHIR server." lightbox="media/healthcare-writeback-dynamics-365-identifiers-fhir-server-architecture.svg":::

[Download a PowerPoint file with this architecture.](https://github.com/microsoft/dynamics365patternspractices/tree/main/architectures)

## Dataflow

1. An event creates a resource in the FHIR server and generates a FHIR bundle that includes one or more external system identifiers in an identifiers array.
1. The FHIR bundle triggers the Logic App inbound workflow to process it. The exact trigger for the Logic App depends on the specific aspects of the implementation project that are outside the scope of this reference architecture. Examples include an HTTP trigger or an Azure Blob Storage trigger.
1. The Dataverse Healthcare API processes the Upsert request by using the configured Entity and Identifier Expand Map.
1. The system creates the Dataverse record in the mapped table based on the Entity Map. Or, a user can create a record in this table to trigger step 6 onward.
1. The system creates external system identifiers as rows in the 1:N related identifier table based on the Identifier Expand Map.
1. The synchronous FHIR Identifier plugin creates another row in the related identifier table, sets the system column to the Dynamics 365 system Uniform Resource Name (URN), and sets the value column to the created record's identifier. This step triggers the write-back.
1. The Dataverse Healthcare API processes the Writeback request by using the configured Entity and Expand Maps. The FHIR bundle now includes the Dynamics 365 identifier in the identifiers array.
1. The FHIR bundle triggers the Logic App inbound workflow to process it.
1. The originating resource in the FHIR server is updated to include the Dynamics 365 identifier.

## Components

This article describes the components in this reference architecture.

- FHIR server (for example, [Azure Health Data Services](https://azure.microsoft.com/products/health-data-services)) exchanges health data using the Fast Healthcare Interoperability Resources (FHIR) standard. Microsoft for Healthcare integrates with Azure Health Data Services out of the box, and supports connectivity with other providers.

- [Azure Logic Apps](https://azure.microsoft.com/products/logic-apps) relays data between the FHIR server and Dataverse Healthcare APIs.

- [Microsoft for Healthcare](https://www.microsoft.com/industry/health/microsoft-cloud-for-healthcare):

  - Dataverse Healthcare APIs let Dataverse use the FHIR standard and sync with external FHIR services, like Azure Health Data Services.

  - An *entity map* associates FHIR resources with Dataverse entities. The map includes child attribute maps for table columns. For example, the FHIR resource **Patient** corresponds to the Dataverse table **Contact**. Set up the map to enable messages for create, update, and write-back.

  - *Identifier expansion maps* provide the rules for transforming JSON document-based hierarchical data into the Dataverse relational data model. Set up an expansion map for each FHIR resource.

- [Dataverse](https://www.microsoft.com/power-platform/dataverse):

  - FHIR resource table (`msemr prefix`) — each FHIR resource maps to a Dataverse table. For example, Care Plan maps to `msemr_careplan`.

  - Create a custom identifier table for each enabled FHIR resource to store system identifiers as individual rows. For example, the `prefix_careplanidentifier` table is created for the `msemr_careplan` table.

  - The FHIR Identifier plugin adds the Dynamics 365 identifier as a row in the appropriate identifier table and triggers write-back to the FHIR server.

## Scenario details

When FHIR resources exist in multiple systems at the same time, each record's unique identifier from each system is stored in the FHIR resource's `identifier` array, nested under the `id` field. Include each Dynamics 365 record's identifier in the `identifier` array when you write back to the FHIR server to keep data integrity and sync. Here's an example:

```json
{
  "id": "a1c2d3e4-5678-90ab-cdef-1234567890ff",
  "identifier": 
  [
    {
      "system": "urn:oid:org.d365.mc4h.patient.id",
      "value": "123e4567-e89b-12d3-a456-426614174000"
    },
    {
      "system": "urn:oid:org.infra.azure.b2c.id",
      "value": "987f6543-b21d-43c1-9bcd-567890abcdef"
    },
    {
      "system": "urn:oid:org.app.bu1.user.id",
      "value": "d3e91a45-55a4-4d2f-ae5b-764abc3f698d"
    },
    {
      "system": "urn:oid:org.app.bu2.user.id",
      "value": "e6f8219b-92b7-438c-91f2-073a8b1b4c5f"
    },
    {
      "system": "urn:oid:org.app.bu3.user.id",
      "value": "a8c72fd3-67da-4c0a-86cb-5efc0c2e934b"
    }
  ]
}
```

### Potential use cases

This solution supports payor-provider organizations in healthcare and insurance. It also applies to public sector or government healthcare organizations. Any organization that uses Microsoft for Healthcare with the Fast Healthcare Interoperability Resources (FHIR) standards framework can use this architecture if they also have a FHIR server, like Azure Health Data Services or Google Cloud Healthcare Data Engine.

Use this solution to write back Dynamics 365 identifiers to an external FHIR server. Write-back is relevant when not all patient FHIR resources sync with Dynamics 365, and when contact records are created in Dataverse the first time they're needed for a business process, like a clinical case or a live conversation. In these cases, a Dynamics 365 identifier in a FHIR resource's `identifier` array confirms the record syncs with Dataverse and is ready to get updates. The Dynamics 365 identifier filters which records and related records get updates from the FHIR server. External systems can also reference Dynamics 365 identifiers for reporting, for example, to relate FHIR and non-FHIR hierarchical data.

## Considerations

These considerations help you implement a solution that includes Dynamics 365. Learn more in the [Dynamics 365 guidance documentation](../index.yml). The solution design uses a balanced approach to configuration and low-code implementation, and ensures optimal performance.

Low-code configuration in Dataverse and Microsoft for Healthcare lets you define identifier tables and data transformation rules for each enabled FHIR resource. You don't need to adjust the Dataverse healthcare APIs.

The FHIR Identifiers plugin creates Dynamics 365 identifier records as a synchronous plugin that needs a pro-dev skill set. It ensures near real-time availability of Dynamics 365 identifiers in the FHIR server, but you can replace this component with a configurable Power Automate flow if minor latency is acceptable.

### Cost optimization

Cost optimization means finding ways to reduce unnecessary expenses and improve operational efficiency. Learn more in the [overview of the cost optimization pillar](/azure/architecture/framework/cost/overview).

This solution lets you sync FHIR resources with Dataverse as needed, so you don't need upfront data migration or synchronization. It reduces implementation effort and prevents using Dataverse storage for records you don't need right now. For example, an organization can have 1 million patients and related data in the FHIR server but only need a fraction of these records in Dynamics 365. If there are fewer patients, full synchronization can be more suitable, and Dynamics 365 identifier write-back might not be needed.

But creating a Dynamics 365 identifier triggers an extra write-back, so each record created in Dataverse needs two write-back calls instead of one. The first call creates the record, and the second adds the Dynamics 365 identifier to the identifiers array.

The cost for each extra call varies based on business requirements for Azure Logic Apps (standard vs. consumption), and the number of new patients and related records you expect to sync each month. Use the [Write-back Dynamics 365 Identifiers to FHIR Server pricing calculator](https://azure.com/e/bdc1041d4d2b4b8dadb9e7a2fd0f926e).

## Deploying Microsoft for Healthcare powered by Dynamics 365

Before you set up write-back to a FHIR server, finish the deployment steps at [Deploy Microsoft Cloud for Healthcare solutions powered by Dynamics 365](/dynamics365/industry/healthcare/deploy). Install these healthcare solutions in your environment:

1. Care management
1. Data integration toolkit
1. Provider data model
1. Payor data model

## Implementation of the architecture Write back Dynamics 365 Identifiers to FHIR Server

This architecture lets you write back Dynamics 365 identifiers to a FHIR server. The first row in the following table shows steps for a generic Azure Logic Apps configuration. How the Logic App is triggered depends on your implementation and isn't covered in this reference architecture. For example, you can use an HTTP or Azure Blob Storage trigger. The detailed steps focus on writing back Dynamics 365 identifiers and don't repeat instructions already covered in product documentation.

| **No.** | **Step name** |
|----|----|
| 1 | [Configure Dataverse healthcare APIs](/dynamics365/industry/healthcare/dataverse-healthcare-apis-configure) |
| 2 | [Configure entity maps](/dynamics365/industry/healthcare/data-integration-toolkit-entity-maps) |
| 3 | Configure identifier table |
| 4 | [Configure identifier expansion map](/dynamics365/industry/healthcare/data-integration-toolkit-expansion-maps) |
| 5 | Configure entity map identifier attribute |
| 6 | Configure FHIR identifier plugin |

> [!NOTE]
> Step-by-step instructions are provided below for steps without a product documentation link. Repeat steps 3–6 in the preceding table for each FHIR resource you use in your implementation.

### Configure the identifier table

Follow these steps to create identifier tables for each table that needs FHIR integration and Dynamics 365 identifier write-back.

1. Sign in to [Power Apps](https://www.make.powerapps.com). If you don't have a Power Apps account, select the **Get started free** link.
1. In your development environment, open the relevant solution, and create a new `{FHIRResource} Identifier` table. For example, create one with the logical name `prefix_patientidentifier`.
1. Create the primary attribute field **System** (`prefix_system`) as a single line of text.
1. Create the value field **Value** (`prefix_value`) as a single line of text.
1. Create a lookup to the `{FHIRResource}`, such as a patient resource that links to a contact table.
1. Update the new table's main form (**Information**) to show all fields from these steps.

### Configure the identifier expansion map

Follow the steps in [Configure identifier expansion map](/dynamics365/industry/healthcare/data-integration-toolkit-expansion-maps) to create identifier expansion maps for each table that needs FHIR integration and Dynamics 365 identifier write-back.

For each map, fill in the fields as shown in the following table.

|Field|Value or action|
|-|-|
|**Disable**| No|
|**Enable Writeback to FHIR** |Yes|
|**EntityName** |The identifier table you created in the preceding procedure.|
|**Azure FHIR Resource** | Specify the `{FHIRResource}`, such as `Patient resource`.|
|**Supported Messages** |Select **Create**, and then **Update**.|
|**Expand** | **Yes**.|
|**Parent Link Attribute** |Select the lookup created in the preceding procedure.|

After you save your changes, create a new *service attribute map*. Fill in the fields as shown in the following table.

|Field|Value|
|-|-|
|**Attribute Name**|**System** `(prefix_system)`|
|**Action Type** | **Copy Data**|
| **FHIR Element Map** | `{"s":"\$.system"}`|
| **Used in Record Matching** | **Yes**|

Save your changes. After you save your changes, create a second *service attribute map*. Fill in the fields as shown in the following table.

|Field|Value|
|-|-|
|**Attribute Name**|**Value** `(prefix_value)`|
|**Action Type** | **Copy Data**|
| **FHIR Element Map** | `{"s":"\$.value"}`|
| **Used in Record Matching** | **Yes**|

Save your changes.

### Configure entity map identifier attribute

Follow these steps to create *entity map identifier attributes* for each table that needs FHIR integration and Dynamics 365 identifier write-back.

1. Open the Data Integration Toolkit. For more information, see [Overview of data integration toolkit](/dynamics365/industry/healthcare/data-integration-toolkit-overview).
1. Navigate to **Entity Maps**.
1. Open the appropriate Entity Map (for example,` contact \<-\> Patient`)
1. Fill in the fields as outlined in the following table.

    |Field or section|Value or action|
    |-|-|
    |**Service Attribute Maps** |Make sure that the *msemr_identifier* attribute isn't selected.|
    |**Service Attribute Maps** |Select **New**|
    |**Attribute Name** |**Not Applicable**|
    |**Action Type** | **Expand**|
    |**Expansion Entity Map**| Specify the identifier expand map that you created in the previous section.|
    |**FHIR Element Map** |Specify the identifier|

1. Select the **Save** button.
1. From **FHIR Attribute Metadata**, select **New FHIR Attribute Metadata**, and fill in the fields as shown in the following table.

    |Field or section|Value or action|
    |-|-|
    |**Name** |`{FHIRResource} Identifier – Identifier`.|
    |**Azure FHIR Resource** | Specify the `{FHIRResource}`, such as *Patient resource*.|
    |**Return Element** |Specify the identifier|

1. Save and close the panes.
1. For **FHIR Attribute Metadata**, select the FHIR Attribute Metadata you created in the previous step.

### Configure FHIR identifier plugin

Follow these steps to configure the FHIR identifier plugin for each table that needs FHIR integration and Dynamics 365 identifier write-back. You can derive the logic needed in the plugin from these steps. For general instructions to develop plugins, see [Tutorial: Write and register a plug-in](/power-apps/developer/data-platform/tutorial-write-plug-in).

1. Open the **Plugin Registration** tool.
1. For the FHIR identifier plugin, register a plugin step for the appropriate entity (for example, the account entity for the Organization FHIR resource).

    1. Fill in the fields as outlined in the following table.

      |Field or section|Value or action|
      |-|-|
      |**Eventing Pipeline Stage of Execution** |**Post-operation**|
      |**Execution Mode** | **Synchronous**|

    1. For the **Unsecure Configuration** field, enter the following parameters in JSON format:

        1. entityLogicalName (for example, `msemr_careplan`)
        1. identifierEntityLogicalName (for example, `prefix_careplanidentifier`)
        1. lookupColumnName (for example, `prefix_careplan`)
        1. valueColumnName (for example, `prefix_value`)
        1. systemColumnName (for example, `prefix_system`)
        1. system (for example, `urn:oid:org.d365.mc4h.careplan.id`)
1. Make sure the FHIR identifier plugin uses the following parameters:

    1. When a new row is created for the entity (for example, `msemr_careplan`).
    1. To create a new row for the identifier entity (for example, `prefix_careplanidentifier`) with the correct values.

## Next step

1. [What is Microsoft for Healthcare?](/industry/healthcare/overview)
1. [Data integration toolkit overview](/dynamics365/industry/healthcare/data-integration-toolkit-overview)

## Related resources

Review the following related architecture guides, solutions, and other guidance content:

- [Overview of Microsoft for Healthcare reference architectures](/industry/healthcare/architecture/overview)
- [Writeback for Dataverse healthcare APIs](/dynamics365/industry/healthcare/dataverse-healthcare-apis-writeback)
- [Dataverse healthcare APIs: Use Healthcare data pipeline template](/dynamics365/industry/healthcare/dataverse-healthcare-apis-logic-app-deploy)
- [FHIR data maps overview](/dynamics365/industry/healthcare/data-integration-toolkit-manage-fhir-data)
- [Configure attribute maps](/dynamics365/industry/healthcare/data-integration-toolkit-attribute-maps)
- [Configure expansion maps](/dynamics365/industry/healthcare/data-integration-toolkit-expansion-maps)
<!-- 
## Tags

*Industries:* Finance, Insurance, Real Estate (60-67), Services (70-89), Public Administration (91-99)

*Stakeholders:* Administrative, Audit, Customer services, Engineering, Finance, IT, Operations, Service operations

*Products:* *Dynamics 365, Dataverse, Azure Logic Apps* -->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [Monem Ansari](https://www.linkedin.com/in/monemansari) \| Principal - Microsoft Business Applications
