---
title: Azure DevOps Backlog configuration for the Microsoft Business Process Catalog
description: The backlog configuration for the Microsoft Business Process Catalog Azure DevOps template is designed to work with the pre-defined Team structure and Functional Areas. The recommended Team structure is defined to work for large organizations and based on feedback from many parters and customers. However, each organization is unique. We recommend that you review the Team structure and Area path mapping with each customer prior to configuring your teams and uploading them into Azure DevOps. For optimal configuration and adoption of your Azure DevOps project, align the teams to the way your organization and project team are organized. You can optionally rename, merge, or split teams according to the way you are organized. Use the following tips to help you update the Teams.
author: rprofitt
ms.author: rprofitt
ms.date: 03/24/2026
ms.topic: how-to
ms.service: dynamics-365
ms.subservice: guidance
---

# Azure DevOps Backlog configuration for the Microsoft Business Process Catalog

The backlog configuration for the Microsoft Business Process Catalog Azure DevOps template is designed to work with the pre-defined Team structure and Functional Areas. The recommended Team structure is defined to work for large organizations and based on feedback from many parters and customers. However, each organization is unique. We recommend that you review the Team structure and Area path mapping with each customer prior to configuring your teams and uploading them into Azure DevOps. For optimal configuration and adoption of your Azure DevOps project, align the teams to the way your organization and project team are organized. You can optionally rename, merge, or split teams according to the way you are organized. Use the following tips to help you update the Teams.

- Avoid renaming the Area paths. 
   - If you rename area paths in the ADO Excel template file, make sure you update the values in Business Process Catalog, Deliverables, Delivery Plan, and Objectives files before you upload the work items into Azure DevOps.
   - If you rename area paths, be mindful of this when taking updates of the official version of the Microsoft Business Process Catalog.
- Rename Teams.
   - If your organization calls a team or group of people in your organization something different, rename the Team in the Teams tab of the ADO Project Template Excel file. For example, instead of “Accounting”, your organization refers to the group or team “Global Finance”.
   - Update the mapped Team names in the Area paths tab of the ADO Project Template Excel file.
- Merge Teams. 
   - In smaller organizations there may be too many teams. You can use the parent level teams easily and ignore the lower level teams easily by selecting the Include sub area option on the Areas tab of the Team configuration page. 
   - You can optionally delete the lower level teams from the Teams tab of the ADO Project Template Excel file. Make sure to update the Area Paths tab with the parent Team name for any rows you delete.
- Split Teams.
   - In larger organizations or complex projects you may need to split a single team into two or more teams. 
   - Insert new rows into the Teams tab of the ADO Project Template Excel file.
   - On the Area Paths tab of the ADO project Template Excel file, manually map the area paths desired to the new Teams you created. 
> [!IMPORTANT]
> It is important to note that you must create iterations in Your Azure DevOps project before you can configure the backlog. The Azure DevOps Project Template Excel file includes a tab named Iteration Paths, but no values are provided. Additionally, the current version of the Python scripts do not create iterations paths (even if you add them into the spreadsheet.)

## Delivery plan guidance

A delivery plan is the connective tissue between strategy and execution in a project methodology. It describes how work is intended to unfold over time—sequencing major outcomes, aligning teams, and providing a shared view of progress without prescribing every task or step. Rather than being a detailed schedule, a delivery plan focuses on direction, dependencies, and intent, helping stakeholders understand *what* is being delivered and *when* at a meaningful level. In Azure DevOps, a Delivery Plan brings this concept to life by visually aligning work across teams, backlogs, and time horizons, offering a rolling, outcomeoriented view that supports coordination, transparency, and adaptation as the project evolves.

We recommend Partners create a delivery plan that aligns with your methodology and relate your delivery plan tasks to the Deliverables and Business Processes in the Azure DevOps template. Make sure your Delivery plan includes all the Success by Design tasks recommended in the Success by Design Delivery plan. The delivery plan is your methodology for implementing technology solutions and is one keyway you can differentiate yourself from other partners. Success by Design is not a methodology rather a framework for successful implementation and the provided delivery plan includes many critical tasks that are included in our Implementation Guide. 

## Configure Team visibility in Azure DevOps

In Azure DevOps, Teams provide a way to organize work views, backlogs, boards, and iterations without changing the underlying project structure or security model. By default, Teams inherit access from the project they belong to—meaning security is managed at the project level, not individually per Team. Teams primarily influence *how* work is seen and managed (such as which area paths, iterations, and backlogs are visible), rather than *who* is allowed to access it. This separation allows organizations to create multiple Teams aligned to functional areas, workstreams, or roles, while maintaining consistent security, simplifying governance, and ensuring that visibility and collaboration scale cleanly as the project grows.

While Teams do not change a user’s underlying security permissions, they *do* provide an effective way to control visibility of work by shaping what each user sees in their day-to-day experience. By associating Teams to specific area paths and iterations, organizations can limit which work items appear on a Team’s backlogs, boards, and delivery views, even when users technically have access to the broader project. This allows teams to focus on the work relevant to their role or functional area without exposing all work items to all users, reducing noise and complexity while preserving a single, governed project structure. In this way, Teams act as a practical visibility and scoping mechanism layered on top of project-level security, enabling clarity without fragmentation.

The Microsoft Business Process Catalog Azure DevOps template maps Teams to area paths by default, but does not map iteration paths by default. The following sections explain how to configure the backlog and views for optimal usage of the Microsoft Business Process Catalog Azure DevOps template.

## Procedure: Configure Organizational settings for backlogs

To configure the Organizational settings in Azure DevOps for backlogs with the recommended settings, follow these steps.

   1. Open the Organization in Azure DevOps.
   2. Click **Organization Settings** in the left navigation.
   3. Click Process under the Boards group in the left navigation.
   4. Click your process in the list.
   5. Click the **Backlog levels** tab.
   6. Click the … (Ellipses/More button) on the Epic backlog under the Portfolio area.
   7. Select **Edit/Rename**.
   8. Set the **Name** to Level.
   9. Select the following **Work item types on this backlog level**:
      a. End to end
      b. Process
      c. Process area
   10. Select Process in the **Default work item type** field.
   11. Click **Save**.
   12. Click the … (Ellipses/More button) on the Feature backlog under the Portfolio area.
   13. Select **Edit/Rename**.
   14. Set the **Name** to Lowest.
   15. Select the following **Work item types on this backlog level**:
      a. Folder
      b. Phase
      c. Scenario
      d. System process.
   16. Select Scenario in the **Default work item type** field.
   17. Click **Save**.
   18. Click **New top level portfolio backlog**.
   19. Enter Highest in the **Name** field.
   20. Select a color, for example Pink.
   21. Select the following **Work item types on this backlog level**:
      a. Functional area
      b. Tree
   22. Select Functional area in the **Default work item type** field.
   23. Click **Save**.
   24. Click **New top level portfolio backlog**.
   25. Enter Kanban in the **Name** field.
   26. Select a color, for example Blue.
   27. Select the following **Work item types on this backlog level**:
      a. Test Case
   28. Select Test Case in the **Default work item type** field.
   29. Click **Save**.
   30. Click the **… (Ellipses/More button)** on the Requirements backlog under the **Requirements backlog** area.
   31. Select **Edit/Rename**.
   32. Set the **Name** to Deliverables.
   33. Select the following **Work item types on this backlog level**:
      a. Configuration
      b. Deliverable
      c. Documentation
      d. Enhancement
      e. Environment
      f. Infrastructure
      g. Integration
      h. Job
      i. Migration
      j. Personalization
      k. Report
      l. Requirement
      m. Security
      n. Testing
      o. Workflow
   34. Select Configuration in the **Default work item type** field.
   35. Click **Save**.
   36. Click the **… (Ellipses/More button)** on the Tasks under the **Iteration backlog** area.
   37. Select **Edit/Rename**.
   38. Select the following **Work item types on this backlog level**:
      a. Action item
      b. Business task
      c. Task
   39. Select Task in the **Default work item type** field.
   40. Click **Save**.
   41. Validate the following work items are in the **Other work item types** areas under the **No associated backlog** row
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

   1. Open the Project in Azure DevOps.
   2. Click **Project Settings** in the left navigation.
   3. Select **Team configuration** under **Boards** on the left navigation.
   4. In the top navigation bar, select the Team you want to configure. For example, select Accounting.
   5. Click the **Iterations** tab.
   6. Click **Change** next to **Default iteration**.
   7. Select the iteration you want to be used by default. (You can optionally leave “@CurrentIteration” in this field. Otherwise, we recommend selecting the Parent node of your Iterations and then click **Set**.
   8. Click **Change** next to **Backlog iteration**.
   9. Select the **Parent node** of your **Iterations** and then click **Set**.
   10. Click **Select iteration(s).**
   11. Select each iteration you want to include. We recommend including all iterations.
   12. Click **Save and close**.
   13. Click the **Areas** tab.
   14. Validate the correct areas are selected. For example, the Accounting team should include the Accounting area. 
   15. Click the **… (Ellipses/More button)** on the Area row and select Include sub areas to ensure any child areas are included under the area.
   16. Repeat steps 4-15 for each Team.
## Procedure: Configure the user experience and view settings for each team

Use the follow steps to configure the backlog for your user 

   1. Open the Project in Azure DevOps.
   2. Click **Boards > Backlogs** on the left navigation pane.
   3. Select the **Team** you want to view from the Team drop-down list.
   4. On the **View selector** on the far right, use the drop-down box to select **Lowest**.
   5. Click the **View options** button.
   6. Select **Parents (on).**
   7. Click **Configure team settings** (Gear icon).
   8. Select **Bugs are managed with requirements** radio button under **Working with bugs**.
   9. Click **Save**.
   10. Repeat steps 3-9 for each team you want to configure for your users.
> [!TIP]
> We recommend using the Lowest view with Parents enabled to get an overall picture of all business processes, deliverables, delivery plan, and objectives for the Team you are assigned or working on.

> [!TIP]
> We recommend using the Deliverables view without Parents enabled to see the raw working items that need to be done. This view filers to only show the deliverables (no business processes, delivery plan, or objectives.
