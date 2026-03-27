---
title: Azure DevOps Backlog Configuration for the Business Process Catalog
description: "Azure DevOps backlog setup for the Business Process Catalog: streamline team structure, area mapping, and delivery plans for successful project management."
author: rachel-profitt
ms.author: raprofit
ms.reviewer: edupont
ms.date: 03/27/2026
ms.topic: concept-article
---

# Azure DevOps backlog configuration for the Microsoft Business Process Catalog

The backlog configuration for the Microsoft Business Process Catalog Azure DevOps template works with the predefined team structure and functional areas. The recommended team structure works for large organizations and is based on feedback from many partners and customers. However, each organization is unique. Review the team structure and area path mapping with each customer before configuring your teams and uploading them into Azure DevOps. For optimal configuration and adoption of your Azure DevOps project, align the teams to the way your organization and project team are organized. You can optionally rename, merge, or split teams according to the way you're organized. Use the following tips to help you update the teams.

- Avoid renaming the area paths.  

  - If you rename area paths in the ADO Excel template file, make sure you update the values in Business Process Catalog, Deliverables, Delivery Plan, and Objectives files before you upload the work items into Azure DevOps.
  - If you rename area paths, be mindful of this change when taking updates of the official version of the Microsoft Business Process Catalog.
- Rename teams.

  - If your organization calls a team or group of people in your organization something different, rename the team in the Teams tab of the ADO Project Template Excel file. For example, instead of "Accounting", your organization refers to the group or team "Global Finance".
  - Update the mapped team names in the Area paths tab of the ADO Project Template Excel file.

- Merge Teams.

  - In smaller organizations there may be too many teams. You can use the parent level teams easily and ignore the lower level teams easily by selecting the Include sub area option on the Areas tab of the Team configuration page.  
  - You can optionally delete the lower level teams from the Teams tab of the ADO Project Template Excel file. Make sure to update the Area Paths tab with the parent Team name for any rows you delete.

- Split Teams.

  - In larger organizations or complex projects you may need to split a single team into two or more teams. 
  - Insert new rows into the Teams tab of the ADO Project Template Excel file.
  - On the Area Paths tab of the ADO project Template Excel file, manually map the area paths desired to the new Teams you created. 

> [!IMPORTANT]
> You must create iterations in Your Azure DevOps project before you can configure the backlog. The Azure DevOps Project Template Excel file includes a tab named Iteration Paths, but no values are provided. Also, the current version of the Python scripts do not create iterations paths (even if you add them into the spreadsheet.)

## Delivery plan guidance

A delivery plan is the connective tissue between strategy and execution in a project methodology. It describes how work unfolds over time - sequencing major outcomes, aligning teams, and providing a shared view of progress without prescribing every task or step. Rather than being a detailed schedule, a delivery plan focuses on direction, dependencies, and intent, helping stakeholders understand *what* is being delivered and *when* at a meaningful level. In Azure DevOps, a Delivery Plan brings this concept to life by visually aligning work across teams, backlogs, and time horizons, offering a rolling, outcome-oriented view that supports coordination, transparency, and adaptation as the project evolves.

Create a delivery plan that aligns with your methodology and relate your delivery plan tasks to the Deliverables and Business Processes in the Azure DevOps template. Make sure your Delivery plan includes all the Success by Design tasks recommended in the Success by Design Delivery plan. The delivery plan is your methodology for implementing technology solutions and is one key way you can differentiate yourself from other partners. Success by Design isn't a methodology rather a framework for successful implementation and the provided delivery plan includes many critical tasks that are included in our Implementation Guide. 

## Configure team visibility in Azure DevOps

In Azure DevOps, teams provide a way to organize work views, backlogs, boards, and iterations without changing the underlying project structure or security model. By default, teams inherit access from the project they belong to - meaning security is managed at the project level, not individually per team. Teams primarily influence *how* work is seen and managed (such as which area paths, iterations, and backlogs are visible), rather than *who* is allowed to access it. This separation allows organizations to create multiple teams aligned to functional areas, workstreams, or roles, while maintaining consistent security, simplifying governance, and ensuring that visibility and collaboration scale cleanly as the project grows.

While teams don't change a user's underlying security permissions, they *do* provide an effective way to control visibility of work by shaping what each user sees in their day-to-day experience. By associating teams to specific area paths and iterations, organizations can limit which work items appear on a team's backlogs, boards, and delivery views, even when users technically have access to the broader project. This limitation allows teams to focus on the work relevant to their role or functional area without exposing all work items to all users, reducing noise and complexity while preserving a single, governed project structure. In this way, teams act as a practical visibility and scoping mechanism layered on top of project-level security, enabling clarity without fragmentation.

The Microsoft Business Process Catalog Azure DevOps template maps teams to area paths by default, but doesn't map iteration paths by default. The following sections explain how to configure the backlog and views for optimal usage of the Microsoft Business Process Catalog Azure DevOps template.

## Procedure: Configure organizational settings for backlogs

To configure the organizational settings in Azure DevOps for backlogs with the recommended settings, follow these steps.

1. Open the organization in Azure DevOps.
1. Select **Organization Settings** in the left navigation.
1. Under the **Boards** group in the left navigation, select **Process**.
1. Select your process in the list.
1. Select the **Backlog levels** tab.
1. Select the **...** (Ellipses/More button) on the **Epic** backlog under the **Portfolio** area.
1. Select **Edit/Rename**.
1. Set the **Name** to **Level**.
1. Select the following **Work item types on this backlog level**:
    - End to end
    - Process
    - Process area
1. Select **Process** in the **Default work item type** field.
1. Select **Save**.
1. Select the **...** (Ellipses/More button) on the **Feature** backlog under the **Portfolio** area.
1. Select **Edit/Rename**.
1. Set the **Name** to **Lowest**.
1. Select the following **Work item types on this backlog level**:
     - Folder
     - Phase
     - Scenario
     - System process
1. Select **Scenario** in the **Default work item type** field.
1. Select **Save**.
1. Select **New top level portfolio backlog**.
1. Enter **Highest** in the **Name** field.
1. Select a color, such as **Pink**.
1. Select the following **Work item types on this backlog level**:
      - Functional area
      - Tree
1. Select **Functional area** in the **Default work item type** field.
1. Select **Save**.
1. Select **New top level portfolio backlog**.
1. Enter **Kanban** in the **Name** field.
1. Select a color, such as **Blue**.
1. Select the following **Work item types on this backlog level**:
      - Test Case
1. Select **Test Case** in the **Default work item type** field.
1. Select **Save**.
1. Select the **...** (Ellipses/More button) on the **Requirements** backlog under the **Requirements backlog** area.
1. Select **Edit/Rename**.
1. Set the **Name** to **Deliverables**.
1. Select the following **Work item types on this backlog level**:
      - Configuration
      - Deliverable
      - Documentation
      - Enhancement
      - Environment
      - Infrastructure
      - Integration
      - Job
      - Migration
      - Personalization
      - Report
      - Requirement
      - Security
      n. Testing
      o. Workflow
1. Select Configuration in the **Default work item type** field.
1. Select **Save**.
1. Select the **… (Ellipses/More button)** on the Tasks under the **Iteration backlog** area.
1. Select **Edit/Rename**.
1. Select the following **Work item types on this backlog level**:
      a. Action item
      b. Business task
      c. Task
1. Select Task in the **Default work item type** field.
1. Select **Save**.
1. Validate the following work items are in the **Other work item types** areas under the **No associated backlog** row
    a. Assumption
    b. Change request
    c. Decision
    d. Issue
    e. Objective
    f. Risk
    g. Status report
    h. Test Plan
    i. Test Suite
    j. Ticket
    k. Workshop

## Procedure: Configure Teams backlog

To configure the Teams backlog with the recommended settings, follow these steps.

1. Open the project in Azure DevOps.
1. Select **Project Settings** in the left navigation.
1. Under **Boards** in the left navigation, select **Team configuration**.
1. In the top navigation bar, select the team you want to configure. For example, select Accounting.
1. Select the **Iterations** tab.
1. Select **Change** next to **Default iteration**.
1. Select the iteration you want to use by default. You can optionally leave `@CurrentIteration` in this field. Otherwise, select the parent node of your iterations and then select **Set**.
1. Select **Change** next to **Backlog iteration**.
1. Select the **Parent node** of your **Iterations** and then select **Set**.
1. Select **Select iterations**.
1. Select each iteration you want to include. Include all iterations.
1. Select **Save and close**.
1. Select the **Areas** tab.
1. Validate the correct areas are selected. For example, the Accounting team should include the Accounting area. 
1. Select the **… (Ellipses/More button)** on the Area row and select **Include sub areas** to ensure any child areas are included under the area.
1. Repeat steps 4-15 for each team.

## Procedure: Configure the user experience and view settings for each team

Use the following steps to configure the backlog for your user. 

1. Open the project in Azure DevOps.
1. Select **Boards** > **Backlogs** in the left navigation pane.
1. Select the **Team** you want to view from the Team drop-down list.
1. On the **View selector** on the far right, use the drop-down box to select **Lowest**.
1. Select the **View options** button.
1. Select **Parents (on).**
1. Select **Configure team settings** (Gear icon).
1. Under **Working with bugs**, select **Bugs are managed with requirements**.
1. Select **Save**.
1. Repeat steps 3-9 for each team you want to configure for your users.

> [!TIP]
> Use the **Lowest** view with **Parents** enabled to get an overall picture of all business processes, deliverables, delivery plan, and objectives for the team you are assigned or working on.

> [!TIP]
> Use the **Deliverables** view without **Parents** enabled to see the raw working items that need to be done. This view filters to only show the deliverables and no business processes, delivery plan, or objectives.

## Related content

- [Use the business process catalog as a template in Azure DevOps Services](about-import-catalog-devops.md)  
- [Introduction to the business process catalog for Dynamics 365 apps and services](about.md)  
