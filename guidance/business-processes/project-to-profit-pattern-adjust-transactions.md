---
title: Adjust project transactions pattern
description: Discover the pattern for processing transaction adjustments. Use it to fix discrepancies, recalculate costs, and maintain compliance with financial regulations.
#customer intent: As a system administrator, I want to configure transaction statuses for adjustments so that users can make changes without data integrity issues.
author: edupont04
ms.author: edupont
ms.reviewer: edupont
ms.date: 10/16/2025
ms.topic: design-pattern
ms.custom: 
  - ai-gen-docs-bap
ai-usage: ai-assisted
---
# Pattern for adjust project transactions

***Applies to: Dynamics 365 Finance, Dynamics 365 Project Operations***

This article describes the process of *adjusting transactions* in Dynamics 365. It explains when you can or can't use that process. It's a pattern under the *correct project transactions* business process in the *manage project financials* area in the *project to profit* end-to-end scenario. In the current version of [the business process catalog](about.md), it's listed as *80.50.030.100 Adjust project transactions (in mass) in Dynamics 365 Project Operations for manufacturing*.

## Context and problem

Dynamics 365 Finance and Dynamics 365 Project Operations help you streamline transaction adjustments. These tools let you adjust project transactions individually or in bulk, so your financial data stays accurate and current. This feature helps you keep project accounting accurate because you can fix errors, update billable statuses, and recalculate costs after configuration changes. The system also handles different transaction statuses, like posted or invoiced transactions, so you can make adjustments without disrupting your work.

## When to use this pattern

Use this pattern when:

- You correct errors. If there are mistakes in the original transaction entries (like incorrect amounts, dates, or project codes), use adjustments to fix these errors and keep financial records accurate.
- You update the billable status. When you must change the billable status of a transaction (like from non-billable to billable), make an adjustment.
- You recalculate costs. After configuration changes (like updates to cost rates or allocation methods), use adjustments to recalculate costs so they're correct in project accounting.
- You change funding sources. If the funding source for a project changes, update the transactions with adjustments to show the new funding arrangement.
- You handle invoiced transactions. Use adjustments to fix discrepancies or update financial dimensions in invoiced transactions.
- You make mass updates. For large projects, use adjustments to make bulk updates to multiple transactions at once. This saves time and keeps the project consistent.

This pattern isn't suitable for:

- Finalized transactions. If transactions are finalized and reported in financial statements, making adjustments can cause discrepancies and require restatements. Avoid adjustments in these cases unless they're absolutely necessary and approved by financial auditors.
- Regulatory compliance. When adjustments might break regulatory compliance or accounting standards, check with compliance officers or auditors before you continue. Unauthorized adjustments can cause legal and financial problems.
- System limitations. Certain transaction statuses (like fully invoiced or eliminated transactions) can't be adjusted depending on system settings. Trying to adjust these transactions can cause errors or data integrity issues.
- Audit trails. If keeping a clear audit trail is critical, frequent adjustments can make tracking and auditing harder. In these cases, use other methods like journal entries to fix transaction errors.
- Mass adjustments without review. Don't make mass adjustments without reviewing each transaction. Bulk changes can cause new errors if you don't manage them carefully.

## Solution: Adjust project transactions

Dynamics 365 Project Operations and Dynamics 365 Finance give you more financial transparency and control. The adjustment features help you avoid financial discrepancies and improve project management. When you use these tools, your financial records match your project activities, so you can make better decisions and trust your financial reports. This helps you stay compliant with financial regulations and builds stakeholder confidence in your financial practices.

### Procedure: Decide whether to adjust the transactions

Follow these steps to decide whether to adjust the transactions.

1. Identify the need for adjustments.  

    1. Check for errors in the original transaction entries, like incorrect amounts, dates, or project codes.
    1. Check if the billable status or other attributes of the transaction need to be updated.
    1. Check if a configuration change can require cost recalculation.
    1. Check whether the funding source on the project changed which needs to be reflected in the transaction.
1. Evaluate transaction status.  

    Ensure that the transaction is in the status that allows adjustments (for example, posted, but not fully invoiced or eliminated). Also, check the system configuration to confirm that the transaction status is enabled for adjustments. [Project adjustments](/dynamics365/project-operations/project-accounting/project-adjustments)
1. Consider regulatory and compliance requirements.  

    Review if the adjustments comply with regulatory standards and accounting principles and consult with compliance officers or auditors if necessary to avoid legal and financial repercussions.
1. Review the impact on financial statements.  

    Analyze how the adjustments will affect financial statements and reporting (avoid adjustments that can cause discrepancies in finalized financial statements unless absolutely necessary and approved by auditors.
1. Assess the need for audit trails.  

    Determine if a clear audit trail is critical for that transaction. If yes, you can consider using alternative methods (for example, journal entries) in cases where frequent adjustments may complicate the tracking and auditing processes.
1. Plan for mass adjustments.  

    In order to avoid new errors for large projects, plan and review mass adjustments carefully (ensure project consistency by reviewing each transaction before making a bulk adjustment).
1. Execute adjustments.  

    Use the adjustment functionality in Dynamics 365 Finance or Dynamics 365 Project Operations, and follow the system's process flow. [Project adjustments](/dynamics365/project-operations/project-accounting/project-adjustments)

### Procedure: Execute the transaction adjustment

Use the following steps to execute the transaction adjustment.

1. Access the adjustment functionality.
1. Select transactions for adjustment.
1. Initiate the adjustment.  

    Perform the modifications on the transaction lines.
1. Enter the changes and review the pending adjustment.  

    Manually update the fields with the correct information and review those changes before proceeding.
1. Finalize the adjustment.  

    Review the changes to ensure accuracy and confirm the adjustment to update the transactions in the system.
1. Verify the adjustment.  

    Check the updated financial statements or project reports to ensure that the adjustments are accurately reflected.

## Issues and considerations

Consider the following points when you're deciding how to implement this pattern:

- Best practices
  - Conduct regular reviews of project transactions to identify and correct errors promptly.
  - Maintain clear audit trails for all adjustments to ensure transparency and ease of auditing.
  - Provide comprehensive training for users on how to perform adjustments correctly and efficiently.
  - Implement approval workflows for adjustments to ensure that changes are reviewed and authorized by appropriate personnel.
- Cost considerations
  - Be aware of the licensing costs associated with Dynamics 365, as these can vary based on the number of users and specific functionalities required.
  - Consider the costs of implementing and customizing the system to fit your business needs, including any third-party integrations.
  - Factor in the costs for ongoing maintenance, support, and updates to the system.
- Security considerations
  - Use role-based access control to ensure that only authorized users can make adjustments to project transactions.
  - Implement data security measures to protect sensitive financial information from unauthorized access.
  - Ensure that adjustments comply with regulatory requirements and internal policies to avoid legal and financial repercussions.
- Performance considerations
  - Monitor system performance to ensure that adjustments do not negatively impact the overall performance of the system.
  - Use batch processing for large volumes of adjustments to minimize system load and improve efficiency.
  - Ensure that the system can handle the volume of transactions and adjustments as your business grows.
- Non-functional requirements
  - Ensure high availability of the system to support continuous business operations, with minimal downtime.
  - The system should be scalable to accommodate increasing transaction volumes.
  - Maintain optimal performance with quick response times for transaction adjustments.
  - Adhere to compliance and regulatory requirements relevant to your industry.
  - Implement data retention policies to manage the lifecycle of financial data effectively.

## Next steps

If you want to implement Dynamics 365 solutions to assist with your *adjust project transactions* business processes, you can use the following resources and steps to learn more.

1. [Develop project strategy](project-to-profit-develop-project-strategy-overview.md)  
1. [Manage project contracts](project-to-profit-manage-project-contracts-overview.md)
1. [Plan projects](project-to-profit-manage-project-scope-schedule-overview.md)  
1. [Manage project delivery](project-to-profit-deliver-project-work.md)
1. [Manage project financials](project-to-profit-manage-project-financials-overview.md)  

    1. *Correct project transactions*  

        1. *Adjust project transactions* (the article that you're currently reading)
    1. *Convert projects to fixed assets*
    1. *Invoice project milestones*
    1. *Invoice project transactions*
    1. [Recognize project revenue](project-to-profit-recognize-project-revenue.md)  
1. [Analyze project performance](project-to-profit-monitor-analyze-project-performance-overview.md)

## Related resources

You can use the following resources to learn more about the transaction adjustment in Dynamics 365.

- [Project adjustments](/dynamics365/project-operations/project-accounting/project-adjustments)
- [Microsoft Certified: Dynamics 365 Finance Functional Consultant Associate - Certifications](/credentials/certifications/d365-functional-consultant-financials/?practice-assessment-type=certification)
- [Get started with Dynamics 365 Project Operations - Training](/training/modules/get-started-project-operations/)  
- [What are the end-to-end scenarios and business processes in Dynamics 365?](overview.md)

<!-- 
## Tags

*Industries:* Finance

*Stakeholders:* Finance, Operations, Project Management

*Products:* Dynamics 365 Finance, Dynamics 365 Project Operations -->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [Isidora Kupresak](https://www.linkedin.com/in/isidorakupresak) | Junior Functional Consultant for Dynamics 365 Finance and Supply Chain Management

- [Sa.global (https://www.saglobal.com/)](https://www.saglobal.com/en-us) | Business Applications and Modern Work, Microsoft Inner Circle Partner  

Other contributors:

- [Mila Mojsilovic](https://www.linkedin.com/in/mila-mojsilović-747793225) | Junior Functional Consultant for Dynamics 365 Finance and Supply Chain Management

- [Irena Zivkovic](https://www.linkedin.com/in/irena-živković-46593422a) | Junior Functional Consultant for Dynamics 365 Finance and Supply Chain Management

- [Satya Teki](https://www.linkedin.com/in/satyateki) | Senior Solution Architect
