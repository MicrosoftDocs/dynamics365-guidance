---
title: Fields for Work Item Types
description: Find descriptions of the fields that Microsoft recommends for Azure DevOps work items that you use for deliverables in an implementation project with Dynamics 365 apps.
#customer intent: As a functional consultant, I want to learn how to configure out-of-the-box deliverables in Azure DevOps so that I can tailor Dynamics 365 to meet specific business needs.
author: edupont04
ms.author: edupont
ms.date: 01/13/2026
ms.topic: concept-article
---

# Fields for Azure DevOps work items from the business process catalog template

This article describes the fields that Microsoft includes in the Azure DevOps template that uses the business process catalog to help you run an implementation project with Dynamics 365 apps. The Azure DevOps template for the business process catalog includes these fields by default.

> [!TIP]
> Find descriptions of the different work item types at [Deliverables in the business process catalog as Azure DevOps work items](about-devops-work-items-deliverables.md).

## Fields starting with A

| Field name | Description | Work item type |
| -- | -- | -- |
| Acceptance Criteria | Specifies the conditions that must be met for the work item to be accepted as done. | Requirement, Workflow, Report, Integration, Configuration, Enhancement, Documentation, Job, Migration, Personalization, Security |
| Agenda | Specifies the agenda of the expected content to be covered in the workshop that the work item represents. | Workshop |
| Application family | Specifies a group of Dynamics 365, such as Business Central, or finance and operations apps, that are relevant for this work item. This selection helps categorize the process. | Workflow, Report, Integration, Configuration, Enhancement, Documentation, Job, Migration, Personalization, Security |
| Approval levels | Specifies the number of approval levels required for the work item. | Workflow |
| Approval types | Specifies the types of approval required, such as *Compliance* or *Technical*. Select from the pick list to clarify approval requirements. | Workflow |
| Article status | Specifies the current status of the article, such as *Not started*, *Drafted*, and *Published*. This status indicates the progress of a Microsoft Learn article that documents the process. | Workflow, Report, Integration, Configuration, Enhancement, Job, Migration, Personalization, Security, Workshop, Deliverable, Testing |
| Assigned to | Specifies the owner of the work item. | Requirement, Workflow, Report, Integration, Configuration, Enhancement, Documentation, Job, Migration, Personalization, Security, Workshop, Deliverable, Testing |
| At least one | Specifies if at least one configuration or recommendation is required. Set to **Yes** if mandatory. | Workflow, Report, Configuration, Job |
| Author | Specifies the primary person responsible for creating or contributing the original content for this field. | Requirement, Workflow, Report, Integration, Configuration, Enhancement, Documentation, Job, Migration, Personalization, Security, Workshop, Deliverable, Testing |
| Authorized for deployment | Specifies the environment or branch that is authorized next for the code or data attached to this deliverable. | Report, Integration, Configuration, Enhancement, Job, Migration, Personalization, Security |
| Average daily volume | Specifies the expected average daily transaction volume. Use this value for capacity and performance planning. | Integration |
| Average hourly transactions | Specifies the expected average number of transactions per hour. This value helps with system sizing and monitoring as well as selecting the correct technology for the integration or data migration. | Integration |

## Fields starting with B

| Field name | Description | Work item type |
| -- | -- | -- |
| Baseline complexity | Specifies the baseline complexity, such as *Simple*, *Medium*, and *Complex* for this work item. This value indicates the baseline suggested complexity for estimating the project effort related to the work product. | Requirement, Workflow, Report, Integration, Configuration, Enhancement, Documentation, Job, Migration, Personalization, Security |

## Fields starting with C

| Field name | Description | Work item type |
| -- | -- | -- |
| Can add later | Specifies if this configuration or field can be added later. Set to **Yes** if it's not required at initial setup. | Workflow, Report, Configuration, Job |
| Can change later | Specifies if this configuration or field can be changed after initial setup. Set to **Yes** if changes are allowed. | Workflow, Report, Configuration, Job |
| Catalog status | Specifies the current status of the catalog item, such as New, In progress, Published). Use this field to determine which rows are new, updated, or deprecated from Microsoft. | Workflow, Report, Integration, Configuration, Enhancement, Documentation, Job, Migration, Personalization, Security, Workshop, Deliverable, Testing |
| Compliance requirement | Specifies if there are compliance requirements for this work item. Set to **Yes** if regulatory or policy compliance is needed. | Report, Configuration |
| Configuration keys | Specifies any configuration keys relevant to the application or module. Use this information to manage feature access and settings. | Workflow, Report, Configuration, Job |
| Continuous | Specifies if this process or job is continuous. Set to **Yes** for ongoing or recurring activities. | Workflow, Report, Configuration, Job |
| Contributor | Specifies the contributors for this work item. Use the pick list to assign roles or individuals. | Workflow, Report, Integration, Configuration, Enhancement, Documentation, Migration, Personalization, Security, Workshop, Deliverable, Testing |
| Country region codes | Specifies the applicable country or region codes. Use this information to specify localization or compliance requirements. | Workflow, Report, Configuration, Job |
| Current highest deployment | Specifies the current highest environment or branch for the code or data attached to this deliverable. | Report, Integration, Configuration, Enhancement, Job, Migration, Personalization, Security |
| Cutover method | Specifies how the data is populated for this configuration. | Migration |

## Fields starting with D

| Field name | Description | Work item type |
| -- | -- | -- |
| Data cleansing strategy | Specifies a summary for how you intend to cleanse data for the project before you migrate or integrate the data. | Integration, Migration |
| Data package | Specifies the name of the related data package that uses this configuration to load data into the relevant environments. | Migration |
| Data migration volume | Specifies the estimated volume of data to be migrated. Helps with planning and resource allocation. | Migration |
| Data scrubbing technology | Specifies the technology used for data scrubbing, such as Azure Data Factory, Custom ETL tool. | Migration |
| Data type | Specifies the type of data involved, such as master data or transactional data. | Job |
| Development technology | Specifies the technologies that you use to address the needs of the enhancement. | Enhancement |
| Description | Specifies a detailed explanation of the business need. | Requirement, Workflow, Integration, Configuration, Enhancement, Documentation, Job, Migration, Personalization, Security, Workshop, Deliverable, Testing |
| Duration | Specifies the number of weeks that the phase takes. | Workshop |

## Fields starting with E

| Field name | Description | Work item type |
| -- | -- | -- |
| Early | Specifies if this process or configuration should be completed early in the project lifecycle. Set to **Yes** if applicable. | Workflow, Report, Configuration, Job |
| Estimated complexity | Specifies the estimated complexity, such as Small, Medium, or Large, for this work item. Use the pick list to indicate project impact. | Workflow, Report, Integration, Enhancement, Documentation, Job, Migration, Personalization, Security, Workshop, Deliverable, Testing |
| Estimated project impact | Specifies the estimated impact, such as Low, Medium, or High, that this work item has on the project. Use the pick list to indicate significance. | Workflow, Report, Integration, Enhancement, Documentation, Job, Migration, Personalization, Security, Workshop, Deliverable, Testing |
| Execution frequency | Specifies how often this job or report runs, such as Daily, Weekly, or Monthly. | Job |
| Execution sequence | Specifies the execution sequence number in the specified data package for this process or job. Use the number to define the order of operations. | Migration |

## Fields starting with F

| Field name | Description | Work item type |
| -- | -- | -- |
| Feature management keys | Specifies any feature management keys relevant to the application. Use this information to control feature availability. | Workflow, Report, Configuration, Job |
| Fit Gap Status | Specifies if the requirement matches standard functionality or requires customization. | Requirement |
| Functional design | Specifies the functional design details (content or hyperlink) for how the solution meets the business needs. | Workflow, Report, Integration, Configuration, Enhancement, Job, Migration, Personalization, Security |

## Fields starting with G

| Field name | Description | Work item type |
| -- | -- | -- |
| Gap Solution Approach | Specifies the approach for addressing gaps, if applicable. | Requirement, Configuration |
| Gold environment | Specifies if this process or configuration is considered "gold" indicating the configuration should be completed in the Gold environment. | Workflow, Report, Configuration, Job |

## Fields starting with I

| Field name | Description | Work item type |
| -- | -- | -- |
| Industries | Specifies the industry or industries relevant to this work item, such as Manufacturing, Retail. Use the pick list for options. | Workflow, Report, Integration, Configuration, Enhancement, Documentation, Job, Migration, Personalization, Security |
| Initial data sync mechanism | Specifies the mechanism used for initial data synchronization, such as a batch job or real-time sync. | Integration |
| Internal references | Specifies links to various client specific reference materials. | Workflow, Report, Integration, Configuration, Enhancement, Documentation, Job, Migration, Personalization, Security, Workshop, Deliverable, Testing |
| Iteration | Specifies the sprint or iteration the work item falls under. | Requirement, Workflow, Report, Integration, Enhancement, Job, Migration, Personalization, Security, Workshop, Deliverable, Testing |
| Interface mode | Specifies the mode of interface, such as a batch job or real-time sync. Use the pick list for options. | Integration, Migration |
| Interface model | Specifies the model used for the interface, such as API, File-based. | Integration, Migration |
| Interface technology | Specifies the technology used for the interface, such as Power Automate or Azure Logic App. | Integration |

## Fields starting with J

| Field name | Description | Work item type |
| -- | -- | -- |
| Job purpose | Specifies the purpose of the job, such as Cleanup, Data processing. Use the pick list for options. | Job |
| Job execution type | Specifies the type of job execution, such as a batch job or event-driven. Use the pick list for options. | Report, Job |
| Job type | Specifies the type of job, such as a custom job or an integration. | Job |

## Fields starting with K

| Field name | Description | Work item type |
| -- | -- | -- |
| Key questions | Specifies the listing of the key questions that are expected to be discussed and resolved as an outcome of the workshop. | Workshop |

## Fields starting with M

| Field name | Description | Work item type |
| -- | -- | -- |
| Mavim ID | Specifies the unique identifier for the work item in Mavim. | Enhancement |
| Mavim reference | Specifies the reference link to the related Mavim content. | Enhancement |
| Mandatory | Specifies if this field or process is mandatory. Set to **Yes** if required for completion. | Workflow, Report, Job |
| Menu item name | Specifies the name of the menu item in the application. Use this name to identify navigation points. | Workflow, Report, Integration, Configuration, Enhancement, Documentation, Job, Migration, Personalization, Security |
| Menu path | Specifies the menu path for accessing the relevant feature or process. | Workflow, Report, Integration, Configuration, Enhancement, Documentation, Job, Migration, Personalization, Security |
| Microsoft ID | Specifies the unique Microsoft ID associated with this work item. Use this ID for matching and taking updates to the work items. | Workflow, Report, Integration, Configuration, Enhancement, Documentation, Job, Migration, Personalization, Security, Workshop, Deliverable, Testing |
| Microsoft references | Specifies any relevant Microsoft documentation or reference links that support this work item. | Workflow, Report, Integration, Configuration, Enhancement, Documentation, Job, Migration, Personalization, Security, Workshop, Deliverable, Testing |
| Middleware | Specifies the middleware technology used for integrations, such as Azure Logic App, Dataverse. | Integration |
| Migration method | Specifies the technology or mechanism used to migrate data into the target system. | Migration |
| Module | Specifies the Dynamics 365 module related to this work item, such as Accounts payable, Inventory management. Use the pick list for options. | Workflow, Report, Integration, Configuration, Enhancement, Documentation, Job, Migration, Personalization, Security |
| Multiple are recommended | Specifies if multiple recommendations are suggested for this configuration. Set to **Yes** if more than one approach is recommended. | Workflow, Report, Configuration, Job |

## Fields starting with P

| Field name | Description | Work item type |
| -- | -- | -- |
| Partner ID | Specifies the partner ID if a partner manages this process or item. This field is required for custom processes that involve external partners. | Workflow, Report, Integration, Configuration, Enhancement, Documentation, Job, Migration, Personalization, Security, Workshop, Deliverable, Testing |
| Partner phase | Specifies the phase of the partner engagement. For consistency's sake, map the phase to the Success by Design phases. | Workshop, Deliverable, Testing |
| Partner references | Specifies any links to partner documentation or references that support this work item. | Workflow, Integration, Configuration, Enhancement, Documentation, Job, Migration, Personalization, Security, Workshop, Deliverable, Testing |
| Partner workshop type | Specifies the workshop type based on the partner's methodology. | Workshop |
| Peak hour volume | Specifies the expected transaction volume during peak hours. Use this value for system capacity planning. | Integration |
| Priority | Specifies the importance to the business. | Requirement, Configuration |
| Products | Specifies the relevant products, such as Customer Service or Finance, that are associated with this work item. Use the pick list for options. | Workflow, Report, Integration, Configuration, Enhancement, Documentation, Job, Migration, Personalization, Security |
| Program areas | Specifies the program area, such as Reporting & Business Analytics or Solution Architecture, that best fits this work item. | Workflow, Report, Integration, Configuration, Enhancement, Documentation, Migration, Personalization, Security, Workshop, Deliverable, Testing |

## Fields starting with R

| Field name | Description | Work item type |
| -- | -- | -- |
| Reason | Specifies an auto-populated reason associated with the state change. | Requirement, Workflow, Report, Integration, Configuration, Enhancement, Documentation, Job, Migration, Personalization, Security, Workshop, Deliverable, Testing |
| Report type | Specifies the type of report, such as Analytical, Audit, Financial. Use the pick list for options. | Report |
| Report technology | Specifies the technology used to generate the report, such as Power BI, SSRS. Use the pick list for options. | Report |
| Report audience | Specify the intended audience for the report, such as Internal Executive, External Customer. Use the pick list for options. | Report |
| Requirement Mapping | Specifies details on how other deliverables meet the requirement. | Requirement, Configuration |
| Responsible party | Specifies the party responsible for this work item, such as Business Process Owner, Project Manager. | Workflow, Report, Integration, Configuration, Enhancement, Documentation, Job, Migration, Personalization, Security, Workshop, Deliverable, Testing |
| Responsible role | Specifies the role responsible for this work item, such as Application Administrator or Data Architect. Use the pick list for options. | Workflow, Report, Integration, Configuration, Enhancement, Documentation, Migration, Personalization, Security, Workshop, Deliverable, Testing |
| Role type | Specifies the type of role involved, such as Functional, Technical, Executive. Use the pick list for options. | Workflow, Report, Integration, Configuration, Enhancement, Documentation, Job, Migration, Personalization, Security, Workshop, Deliverable, Testing |

## Fields starting with S

| Field name | Description | Work item type |
| -- | -- | -- |
| Scheduling notes | Specifies information that helps determine when the workshop should be scheduled. | Workshop |
| Scope | Define the scope of the work item, such as In scope, Out of scope. Use the pick list for boundaries and expectations. | Workflow, Report, Integration, Configuration, Enhancement, Documentation, Job, Migration, Personalization, Security, Workshop, Deliverable, Testing |
| Scope approach | Specifies how to do the work from an implementation perspective. | Requirement |
| Start date | Specifies the date to start the work that the work item represents. | Workshop |
| State | Tracks lifecycle status, such as New, Active, Closed. | Requirement, Workflow, Report, Integration, Configuration, Enhancement, Documentation, Job, Migration, Personalization, Security, Workshop, Deliverable, Testing |
| Story points | Specifies the estimate in hours to complete the work for the deliverable. You can use decimals for partial hours. | Workflow, Report, Integration, Configuration, Enhancement, Job, Migration |
| Source data entity | Specifies the name of the source data entity for migration or integration. Track where data originates. | Integration, Migration |
| Source system | Specifies the source system for migration or integration, such as Customer Service or Finance. | Integration, Migration |
| Success by Design phase | Specifies the phase from the Success by Design framework that the work item applies to, such as Strategize or Test. | Workshop, Deliverable, Testing |

## Fields starting with T

| Field name | Description | Work item type |
| -- | -- | -- |
| Target data entity | Specifies the target data entity in Finance and Operations for migration or integration. | Integration, Migration |
| Target system | Specifies the target system for migration or integration, such as Customer Service or Finance. | Integration, Migration, Security |
| Technical design | Specifies the technical design details (content or hyperlink) for how the solution is completed technically. | Report, Integration, Enhancement, Migration |
| Transformation technology | Specifies the technology used for data transformation, such as Azure Data Factory, Custom ETL tool. | Integration, Migration |

## Fields starting with U

| Field name | Description | Work item type |
| -- | -- | -- |
| Update comments | Specifies any comments or notes about updates made to this work item. Provide context for changes or revisions. | Workflow, Report, Integration, Configuration, Enhancement, Documentation, Job, Migration, Personalization, Security, Workshop, Deliverable, Testing |

## Fields starting with V or W

| Field name | Description | Work item type |
| -- | -- | -- |
| Validation method | Specifies the method to use to validate data or processes, such as an audit trail review or checksum validation. Use the pick list for options. | Integration, Migration |
| Workflow type | Specifies the type of workflow associated with this work item, such as a custom workflow extension or a Dataverse business process flow. Use the pick list for options. | Workflow |
| Workshop assumptions | Specifies any assumptions and prerequisites expected before each workshop. | Workshop |

## Related content

- [Deliverables in the business process catalog as Azure DevOps work items](about-devops-work-items-deliverables.md)  
- [Use the business process catalog as a template in Azure DevOps Services](about-import-catalog-devops.md)  
