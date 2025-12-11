---
title: What's New in the Business Process Catalog in December 2025
description: What's new or changed in the December 2025 version of the business process catalog that Microsoft publishes as a downloadable file.
author: edupont04
ms.author: edupont
ms.reviewer: edupont
ms.date: 12/09/2025
ms.topic: concept-article
---

# What's new or changed in the business process catalog in December 2025

The business process catalog is a standard list of business processes across Dynamics 365 apps and services. Microsoft uses it to organize and prioritize work on the business process documentation.

The December 2025 release of the catalog includes improvements across many of the end-to-end processes. It also includes improvements suggested by the user community through the GitHub issue list and Partner Advisory Board Focus Group.  

Download the latest version of the catalog from [https://aka.ms/businessprocesscatalog](https://aka.ms/businessprocesscatalog).

## Deprecated rows

The December 2025 version of the business process catalog includes rows with a Catalog status of **Deprecated**. These rows are no longer active and are removed in a future release of the catalog. Many of these rows are moved to a new location in the catalog. The **Alternate Process Sequence ID** column indicates that the deprecated row is available in a new location in the catalog.

## Deleted rows

The December 2025 version of the business process catalog includes rows with a catalog status of **Deleted**. Any row that is marked as *Deleted* is no longer included in the catalog in future releases. If you're actively using a row tagged as *Deleted*, update your catalog to use the row that is designated in the **Alternative process sequence ID** field.

## Introducing Level 5 system processes and Level 6 test cases

In this version of the business process catalog, we introduce two new levels:

- **Level 5: System processes**

  The introduction of Level 5 System Processes marks a significant advancement in the catalog's structure by bridging the gap between high-level business scenarios and actionable system steps. This layer breaks down processes into granular, repeatable actions that align with actual application screens, ensuring precision and consistency across implementations. By mapping these steps directly to Dynamics 365 functionality, Level 5 ensures precision, consistency, and traceability across implementation projects. It enables delivery teams to streamline planning, improve governance, and accelerate deployment by offering a standardized structure that supports automation readiness and quality assurance. This addition empowers partners and project teams to achieve greater efficiency and confidence in solution reliability.
- **Level 6: Test cases**

  Level 6 Test Cases is a granular layer within the business process catalog that's designed to validate system processes through structured testing. Each Level 6 entry corresponds to a specific test case aligned with Dynamics 365 functionality, ensuring accuracy and compliance for every business scenario. These test cases not only strengthen traceability from business objectives to executable steps but also align closely with training initiatives—providing a foundation for hands-on exercises and reinforcing user adoption through practical, scenario-based learning. By embedding these cases into the catalog framework, delivery teams can accelerate quality assurance, reduce manual effort, and enhance governance, ultimately improving confidence in solution reliability. Examples include *Validate Demand Planning Setup*, *Confirm Financial Forecast Configuration*, and *Verify Vendor Payment Workflow*.

Together, Level 5 and Level 6 make the business process catalog more actionable and auditable. Level 5 standardizes system‑process steps tied to application screens. Level 6 captures discrete test cases that verify those steps—so teams get clear traceability, consistent naming, and repeatable validation across discovery, configuration, and deployment.

Learn more at [Overview of the business process catalog levels](about-catalog-levels.md).

## Improvements to Forecast to plan

We made several key updates to strengthen clarity and usability across *Forecast to plan*. These changes focus on improving process alignment and refining definitions for greater clarity. The following list summarizes the improvements to the *Forecast to plan* end-to-end process:

- **Updated Level 2 Process Structure**  

  We updated the sequence for the *Conduct Financial Planning* process and its subprocesses from **50.55** to **50.20** to improve alignment and provide a smoother, more logical flow within the overall *Forecast to plan* process.

- **Enhanced Level 4 Process Definitions**  

  We improved Level 4 processes to better identify scenarios and patterns. These refinements help articulate unique ways of executing specific business processes, often tailored for particular industries, requirements, or product-specific needs.

## New Azure DevOps template

The updated Azure DevOps template introduces significant enhancements for Dynamics 365 projects. It expands the hierarchy to include deeper levels for system processes and test cases, improving granularity and traceability. Legacy deliverables are deprecated in favor of a clearer configuration structure that organizes items by functional area and deployment phase, ensuring better alignment with Success by Design principles. This structure standardizes naming conventions, groups related artifacts under logical folders, and incorporates metadata for easier filtering and reporting. New custom work item types strengthen linkage between business processes and technical tasks, while cross‑sectional views enable focused planning and governance. It also organizes work into four interconnected trees so teams can plan, govern, and report with clear, cross‑sectional views by functional area.  

The following list outlines what to use each tree for.

- **Business Process Catalog Tree (Why)**  

  Captures the "what" of the implementation—end‑to‑end processes through to scenarios, with Level 5 and Level 6 adding system process steps and test cases for traceability and scope definition.

- **Deliverables Tree (What)**  

  Documents the work to tailor the solution—workflows, configurations, enhancements, integrations, and infrastructure/environment items—using custom work item types to improve metadata, workflow visibility, and conversion from requirements to deliverables.

- **Project Methodology Tree (When/How)**  

  Outlines phases, workshops, and delivery steps; supports planning and tracking (including a delivery plan/Gantt view) and links to the methodology for execution.

- **Objectives Tree (Goals)**  

  Stores executive and project goals, program increments, and sprint objectives to keep work aligned with strategic outcomes and provide a single place to track progress against goals.

Learn more at [Use the business process catalog as a template in Azure DevOps Services](about-import-catalog-devops.md).

## Configuration deliverables

This release deprecates all configuration deliverables and replaces them with a structured hierarchy of specialized deliverable types for better tracking and management as outlined in the following list:

- Workflows
- Reports
- Integrations
- Configurations
- Enhancements
- Documentation
- Jobs
- Migrations
- Personalization
- Security (WRICEDJMPS)

Each deliverable type has tailored fields, required metadata, and lifecycle states. Organize these deliverables by department, responsibility, function, application, type, and task. The following list provides examples of how you might structure area paths. Use standardized naming conventions and default tags to improve traceability and reporting. We added a **Catalog Status** field with the values *Draft*, *Approved*, and *Updated*. Type‑specific form layouts enforce consistency. Plus, cross‑sectional views and dashboards support governance by functional area and phase. A migration path reclassifies existing configuration items into the new types, populates the new fields, and aligns artifacts to the catalog hierarchy from Level 1 through Level 6, so deliverables map directly to system processes and test cases.

We also enhanced the business process catalog with columns that were never populated before. We'll continue to enhance them over the next couple of releases. The following list outlines the new columns.

- Sequence

- Success by design phase

- Mandatory

- Can change later

- Can add later

- Process types

- Early

- Gold

- Continuous

- At least one

- Multiple are recommended

## APQC mapping

[APQC](https://www.apqc.org/) is a globally recognized organization specializing in benchmarking, best practices, process and performance improvement, and knowledge management. In this release, we introduced two new fields, **APQC ID** and **APQC Description**, across the end-to-end scenarios, process areas, and processes to enable direct mapping between the business process catalog and APQC values. This enhancement updates more than 500 rows with corresponding APQC information, significantly improving process alignment and traceability. Special thanks to the team at Alfa Laval Technologies AB for their outstanding community contribution, which was instrumental in making this integration possible.

## Advanced Quality Management System (AQMS)

We're pleased to announce the integration of Advanced Quality Management features within Dynamics 365 Supply Chain Management. These features offer enhanced capabilities across critical process areas such as *Case to resolution*, *Design to retire*, *Inventory to deliver*, *Order to cash*, *Plan to produce*, and *Source to pay*. These updates, reflected in more than 100 new and revised configuration deliverables and scenarios, significantly strengthen quality management processes for our customers and partners. We encourage you to explore and adopt these robust features, supported by comprehensive guidance available in the Microsoft Learn articles. Learn more at [Advanced quality management overview](/dynamics365/supply-chain/inventory/advanced-quality-management-overview). Our sincere thanks go to the Alithya team for their valuable contributions and product expertise in making these advancements possible.

## Introducing jobs

This release adds a dedicated **Jobs** work item type to the Deliverables tree, prepopulated with more than 700 out-of-the-box jobs in the finance and operations apps. These items capture scheduled and background processes, such as batch jobs, job queue entries, and scheduled flows. They include key fields for job type, execution frequency, purpose, and monitoring. These entries confirm scope and link to related deliverables and process artifacts, bringing clearer visibility, governance, and auditability to operational automation.

> [!NOTE]
> These entries represent jobs in finance and operations apps, such as [batch jobs](/dynamics365/fin-ops-core/dev-itpro/sysadmin/batch-processing-overview) or [scheduled tasks](/dynamics365/supply-chain/production-control/job-scheduling). They don't represent jobs in Dynamics 365 Business Central that are now [projects](/dynamics365/business-central/projects-manage-projects).


## Updated Business Central scenarios

We removed erroneous descriptions for 35 Business Central scenarios in *Project to Profit*. We also updated five Business Central-related scenarios that had mismatched values in the **Process Sequence ID** field. Thank you, Marcin, for submitting these issues and collaborating to ensure the catalog is accurate.

## Related information

- [What's new or changed in the business process catalog](about-whats-new.md)  
- [About the business process catalog for Dynamics 365 apps and services](about.md)  
