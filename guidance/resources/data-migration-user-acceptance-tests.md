---
title: Guide for User Acceptance Test after Data Migration
description: Discover how to validate data integrity and user experience with targeted UAT in Dynamics 365. Follow proven strategies for successful testing.
#customer intent: As a tester, I want to create realistic test scenarios that mimic real-world use cases so that I can identify potential issues before go-live.
author: edupont04
ms.author: edupont
ms.reviewer: edupont
ms.date: 09/30/2025
ms.topic: concept-article
---
# Guidance for user acceptance test after data migration in solutions with Dynamics 365

User acceptance testing (UAT) and data-focused regression testing are part of a critical phase in the implementation lifecycle, especially after the migration of data. UAT is done by business users in a dedicated and integrated test environment. Data-focused regression testing requires customer data, including migrated data, and the latest solution version and updates. It's the closest test to running live operations. This article provides guidance on targeted UAT and regression testing solutions with Dynamics 365. The guidance stems from projects with Dynamics 365 Customer Service with best practices, potential challenges, and other insights from successful implementations using Dynamics 365 FastTrack guidance.

## Best practices

Our best practices fall into these four categories:

### Thorough planning and preparation

Effective targeted UAT or regression testing starts with meticulous planning. Define clear objectives, scope, and success criteria. Engage stakeholders early to ensure that all business requirements are considered. Create detailed test plans and scripts that cover all functional and nonfunctional aspects of the application.

### Collaboration between teams

Collaboration between IT, business users, and data migration specialists is paramount. Regular communication and feedback loops can help identify and resolve issues promptly. Establishing a cross-functional team ensures that diverse perspectives are considered, leading to a more comprehensive testing process.

### Realistic test scenarios

Develop test scenarios that mimic real-world use cases. You can then identify issues that might not be obvious under ideal testing conditions. To ensure the robustness of the system, include edge cases and scenarios that involve complex data interactions.

### Comprehensive documentation

Document every aspect of the targeted UAT or regression testing, which is a data-focused process, from test plans to issue logs. This documentation serves as a reference for future projects and helps in maintaining compliance with regulatory standards.

Jira from Atlassian is a tool that you can use for comprehensive documentation and report generation of the testing stages. Jira can also help you with automation of targeted UAT and regression testing. Learn more at [How to Manage UAT, Defects, and Reporting in Jira Without a Plugin: A Step-by-Step Guide](https://community.atlassian.com/t5/Jira-articles/How-to-Manage-UAT-Defects-and-Reporting-in-Jira-Without-a-Plugin/ba-p/2861958) or [Jira - Connectors](/connectors/jira/).

If you use EasyRepro, integrate with Azure DevOps for end-to-end automation of documentation and reporting for the testing process. Learn more at [Test Automation and EasyRepro: 05 - Adding EasyRepro Tests to Azure DevOps](https://techcommunity.microsoft.com/blog/testingspotblog/test-automation-and-easyrepro-05---adding-easyrepro-tests-to-azure-devops/2283048).

## Potential challenges and solutions

Any implementation project can run into challenges. The following subsections provide high-level definitions of common issues and potential solutions.

### Data integrity issues

After migration, data integrity is a common challenge. Ensure that all data is accurately migrated and that there are no discrepancies. Use automated tools or platform built-in features to validate data integrity and consistency. Some built-in features that you can use are duplicate detection, bulk deletion, and data merge.

Learn more in the following articles:

- [Merge data - Power Platform](/power-platform/admin/merge-data)

- [Detect duplicate data with match codes and rules - Power Platform](/power-platform/admin/detect-duplicate-data)

Another aspect of data integrity can be targeted UAT or regression testing from an access and visibility perspective.  

### User resistance

Changes in systems can lead to user resistance. To gain their buy-in and address their concerns, involve users early in the testing process. Provide adequate training and support to help them adapt to the new system.

### Scope creep

Targeted UAT or regression testing can also encounter scope creep if you introduce new requirements midway. Scope creep can adversely affect meeting the essential timelines if you're performing such testing. To address this challenge, we recommend that you establish a change control process and adhere to the initially defined scope. Assess any new requirements for their effect on the project timeline and resources.

### Resource constraints

Limited resources can hinder the targeted UAT or regression testing, which is a data-focused process. Plan resource allocation meticulously and consider using automated testing tools to augment manual efforts. Prioritize critical test cases to ensure that the most important aspects of the system are thoroughly evaluated. A few key examples of constraints are:

- Time constraints  

  Limited time for targeted UAT or regression testing can result in rushed testing, incomplete test coverage, and insufficient time to address issues you discover. Proper time planning is important for successfully targeted data-focused testing.

- Personnel constraints  

  A lack of skilled testers or business users available for testing can hinder the effectiveness of targeted UAT or regression testing. Involving the right people is crucial for identifying real-world issues. You can also mitigate this constraint by automating the targeted UAT or regression testing, provided you do the use cases and scoping of targeted UAT or regression testing with proper care.

- Evaluate environment constraints  

  Creating a testing environment that accurately replicates the production environment can be challenging and resource-intensive, especially where complex integrations are involved.

- Ambiguous requirements  

  Vague or ambiguous requirements can lead to disputes and delays, requiring more time and resources to clarify and document requirements.

- Communication gaps  

  Poor communication between development teams, testers, and business users can lead to misunderstandings and inefficiencies in the testing process.

## Metrics for measuring success

The following subsections provide tips for how to measure the success of the implementation project.

### Defect density

Measure the number of defects identified per unit of code. A lower defect density indicates a higher quality of the migrated data and system.

### User satisfaction

Conduct surveys and gather feedback from business users to gauge their satisfaction with the new system. High user satisfaction is indicative of a successful UAT or regression testing.

### Test coverage

Evaluate the percentage of test cases executed versus planned. High test coverage helps make sure that you evaluate all critical functionality.

### Post-implementation issues

Track the number of issues reported post-implementation. Fewer issues signify a robust targeted UAT or regression testing in a data focused process.

## Practical examples

Let's get practical. Here, we outline concrete steps to take.

### Set the objectives

The purpose of targeted UAT or regression testing is to validate the model driven application navigation options along with data ownership and visibility to correct business users post data migration.

### Set the scope

1. Our targeted UAT focuses only on UI navigation & data validation for specific business scenarios.

1. The targeted UAT must be performed in a dedicated environment with required integrations and required business data along with the latest solution.

1. Proper security roles and access must be documented and allocated to predesignated business users.

1. There should be no data migration or solution imports once the targeted UAT test cases are documented and agreed upon by the development team, testing team, and business leads.

1. You can run the UAT manually with designated business users, or by using a testing automation tool.

1. No new UX shall be introduced once this targeted UAT is initiated.

1. Document 5-8 significant business process steps. They are the test cases that you must run during the targeted UAT. To write comprehensive test scenarios and test cases, go back to the *Initiate* phase and find all the important scenarios. Learn more at [Implement a solution based on your business processes](../implementation-guide/process-focused-solution.md).  

    - Ensure that the business processes are inclusive and accurate.

    - Ensure these steps are listed in the execution order of the targeted UAT.

    - Make sure these processes include navigation action and data validation plus visualization action.

    - Make sure to get an agreement from business leads to these processes as the most important business processes that must be evaluated during this targeted UAT.

    - Make sure that these processes cover all user interfaces across model-driven apps, canvas apps, Power Pages, and so on.

    - Make sure that these processes are evaluated for predetermined security roles or personas. Keep in mind that the same data might be required to be visible to non-owning user as well.

## Schedule for targeted UAT and regression testing

Determine and document the timelines for the targeted UAT or regression testing. Here's an example timeline.

1. Preparation (Week 1)

    1. Define UAT requirements and criteria.

    1. Create test plans and assess cases.

    1. Set up the Azure DevOps environment and configure necessary permissions.

1. Evaluate Environment Setup (Week 2)

    1. Configure the test environment to match production settings.

    1. Install necessary tools and dependencies.

    1. Ensure all test data is available and accurate.

1. Evaluate Execution (Week 3-4)

    1. Assign testers and notify them about the test plan.

    1. Run test cases and log results in Azure DevOps.

    1. Monitor test progress and address any issues that arise.

1. Defect Management (Week 5)

    1. Identify and document defects.

    1. Prioritize and assign defects to developers for resolution.

    1. Retest fixed defects to ensure they're resolved.

1. Final Review (Week 6)

    1. Conduct a final review of test results and defect resolutions.

    1. Validate that all requirements are met, and the product is ready for release.

    1. Prepare UAT sign-off documents.

1. Sign-off and Closure (Week 7)

    1. Obtain formal sign-off from stakeholders.

    1. Close out the UAT process in Azure DevOps.

    1. Archive test artifacts and documentation.

### Resources

1. Dedicated targeted UAT or regression testing Power Platform environment with proper integrations configured is needed.

1. Business user records and business data are imported into the environment.

1. If you test a canvas app, then review this article to understand the testing process with the built-in editor: [Test Studio - Power Apps](/power-apps/maker/canvas-apps/test-studio).

    - Understand that not all test cases can be automated.

    - You might prefer to use a test suite instead of just evaluate cases to accommodate a higher number of test cases that might belong to similar area of UX or steps.

1. For automating targeted UAT or regression testing where the main user experience is a model-driven app, we recommend that you use Easy Repro. The following links provide step-by-step instructions for how to configure and use this tool. There's also a link to the GitHub repository. Keep in mind that Easy Repro is an open-source tool. Like any other SDK library, you can bring this tool into your environment, and then configure it and use it for performing testing.  

    - [Test Automation and EasyRepro: 05 - Adding EasyRepro Tests to Azure DevOps](https://techcommunity.microsoft.com/blog/testingspotblog/test-automation-and-easyrepro-05---adding-easyrepro-tests-to-azure-devops/2283048)

    - [GitHub - microsoft/EasyRepro: Automated UI testing API for Dynamics 365](https://github.com/Microsoft/EasyRepro)

## Conclusion

User acceptance testing after data migration in Dynamics 365 implementation projects is a vital step to ensure the success of the implementation. By adhering to best practices, anticipating potential challenges, and drawing insights from successful case studies, organizations can achieve a smooth transition and high user satisfaction. Metrics play a crucial role in measuring the effectiveness of targeted UAT or regression testing, which is data focused, providing actionable insights for continuous improvement.
