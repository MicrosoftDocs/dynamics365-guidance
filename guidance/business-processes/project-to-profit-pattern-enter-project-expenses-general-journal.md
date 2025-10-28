---
title: Enter Project Expenses in General Journal
description: Learn how to enter project expenses using the general journal in Dynamics 365 Finance. Simplify financial tracking, ensure accuracy, and optimize expense management.
#customer intent: As a system administrator, I want to configure access controls for General Journal entries so that I can prevent unauthorized changes.
author: edupont04
ms.author: edupont
ms.reviewer: edupont
ms.date: 10/28/2025
ms.topic: concept-article
ms.custom: 
  - ai-gen-docs-bap
ai-usage: ai-assisted
---

# Pattern for entering project expenses in the general journal in Dynamics 365 Finance

***Applies to: Dynamics 365 Finance, Dynamics 365 Project Operations***

This article describes the process of entering project expenses in the general journal in Dynamics 365 Finance. It's a pattern under the *Track project expenses* business process in the [Manage project delivery](project-to-profit-deliver-project-work.md) area of the [Project to profit](project-to-profit-overview.md) end-to-end scenario.

## Context and problem

Entering project expenses by using the general journal in Dynamics 365 Finance through the *General Ledger* module is crucial for maintaining comprehensive financial records and ensuring accurate financial reporting. By recording project expenses in the general journal, you can consolidate all financial transactions in one place, providing a holistic view of the organization's financial health. This method allows for precise tracking of expenses, ensuring that all costs are accurately captured and reflected in the financial statements. It also facilitates better budget management and financial planning, as project expenses are integrated into the overall financial framework of the business.

For most organizations, using the general journal in Dynamics 365 offers several key benefits. It simplifies the process of recording and managing project expenses, ensuring that all financial data is centralized and easily accessible. This centralization supports detailed financial analysis and reporting, enabling businesses to identify cost trends, monitor budget adherence, and make informed financial decisions. Additionally, the general journal provides a robust audit trail, enhancing transparency and compliance with financial regulations. By using the general journal for project expenses, businesses can optimize their financial management processes, improve accuracy in financial reporting, and ensure better control over project finances.

## When to use this pattern

Use this pattern when you need to:

- **Adjust or correct transactions:** If you need to make adjustments or corrections to previously recorded project expenses, use the general journal to directly modify the financial records without affecting the original transaction entries.

- **Account for accruals and prepayments**: When you need to record expenses that you incurred but didn't invoice, or prepayments for future expenses, use the general journal to accurately reflect these expenses in your financial statements.

- **Process intercompany transactions**: For projects that involve multiple legal entities within your organization, use the general journal to facilitate the recording of intercompany expenses, ensuring that each entity's financial records are correctly updated.

- **Enter manual expenses**: In cases where expenses aren't captured through automated processes or integrated systems, such as miscellaneous or one-off expenses, use the general journal to manually enter these costs directly into the project ledger.

- **Reclassify accounts**: If you need to reclassify expenses from one project to another or from one account to another, use the general journal to make these changes efficiently and accurately.

This pattern might not be suitable for:

- **Detailed tracking and reporting**: If you need detailed tracking and reporting of project expenses, the general journal might not be ideal. Expenses entered through the general journal might not appear in specific project reports or dashboards, which can hinder visibility and analysis.

- **Integration with other modules**: When expenses need to be integrated with other modules, such as Accounts Payable or Procurement, use the dedicated expense entry methods like Vendor Bills or Expense Entries. This approach ensures that all related processes and workflows are properly triggered.

- **Automated processes**: For expenses that are part of automated processes, such as recurring expenses or expenses captured through integrated systems, using the general journal can bypass these automations, leading to inconsistencies and extra manual work.

- **Compliance and audit trails**: If maintaining a clear audit trail and compliance with internal controls is crucial, the general journal might not be the best choice. Dedicated expense entry methods often have built-in controls and approval workflows that enhance compliance.

- **Project-specific allocations**: When you need to allocate expenses to specific tasks or phases within a project, using the general journal can be less efficient. Project-specific expense entry methods allow for more precise allocation and tracking.

## Solution: Enter project expenses using general journal

### Procedure: Enter project expenses

Use the following steps to enter project expenses by using the general journal.

1. Go to the **Expense Journal**.

    1. Go to the *General Ledger* module, select **Journals**, then select **Expense Journals**.

1. Create a new journal entry.

    1. Select **New** to create a new journal entry.  
    1. Enter the necessary details such as date, account, and expense amount.
    1. Add descriptions, and attach relevant documents if needed.

1. Post the journal entry.

    1. Review the entry for accuracy.
    1. Select **Post** to update your financial records.

## Issues and considerations

Consider the following points when you're deciding how to implement this pattern:

### Best practices

- Define specific journal names  

  - Create distinct journal names for different purposes (such as adjustments and accruals) to streamline data entry and enhance internal controls.
- Use workflow approvals  

  - Implement workflow approvals to ensure that all journal entries are reviewed and approved based on predefined criteria, enhancing accuracy and compliance.
- Use templates and recurring journals  

  - Use voucher templates and set up recurring journals for repetitive entries to save time and reduce errors.

### Cost considerations

- Licensing and subscription fees  

  - Make sure your Dynamics 365 subscription includes the modules and features you need to use the general journal effectively.
- Training and support  

  - Set aside budget for training staff on best practices for using the General journal and for ongoing support to address any issues that arise.

### Security considerations

- Access controls  

  - Implement strict access controls to limit who can create, edit, and approve journal entries. This approach reduces the risk of unauthorized changes.
- Audit trails  

  - Maintain detailed audit trails for all journal entries to track changes and ensure accountability.
- Data encryption  

  - Ensure that all data entered into the general journal is encrypted to protect sensitive financial information.

### Performance considerations

- High volume processing  

  - Use the General journal entity for high volume import scenarios to ensure efficient processing and avoid performance bottlenecks.
- Set-based processing  

  - Enable set-based processing for large data imports to improve performance and reduce processing time.
- System maintenance  

  - Regularly maintain and optimize your Dynamics 365 environment to ensure smooth performance and quick response times.

### Non-functional requirement considerations

- **Scalability**: Ensure that your Dynamics 365 setup can scale to accommodate increasing volumes of journal entries as your business grows.
- **Reliability**: Implement robust backup and recovery procedures to ensure that journal data isn't lost if there are system failures.
- **Usability**: Design the journal entry process to be user-friendly, with clear instructions, and intuitive interfaces to minimize user errors.

## Next steps

To implement Dynamics 365 solutions that assist with your *enter project expenses with expense management* business processes, use the following resources and steps to learn more.

1. [Develop project strategy](project-to-profit-develop-project-strategy-overview.md)  
1. [Manage project contracts](project-to-profit-manage-project-contracts-overview.md)
1. [Plan projects](project-to-profit-manage-project-scope-schedule-overview.md)  
1. [Manage project delivery](project-to-profit-deliver-project-work.md)

    1. *Govern projects*  
    1. *Control project scope*  
    1. *Track project expenses*  

        1. [Enter project expenses using credit card transaction import in Dynamics 365 Project Operations](project-to-profit-pattern-enter-project-expenses-credit-card-transaction-import.md)  
        1. *Enter project expenses using purchase transactions in Dynamics 365 Business Central*  
        1. [Enter project expenses using an expense journal in Dynamics 365 Project Operations for manufacturing](project-to-profit-pattern-enter-project-expenses-expense-journal.md)  
        1. *Enter project expenses using an entry journal in Dynamics 365 Project Operations Integrated with ERP*  
        1. [Enter project expenses using the Expense management module in Dynamics 365 Project Operations](project-to-profit-pattern-enter-project-expenses-expense-management.md)  
        1. *Use the expense mobile app in Dynamics 365 Project Operations*  
        1. *Use the expense entry agent to automatically create expenses in Dynamics 365 Project Operations*  
        1. *Enter project expenses using general journal in Dynamics 365 Finance* (the article that you're currently reading)  
        1. *Enter project expenses using general journal in Dynamics 365 Business Central*  
        1. *Enter project expenses in Dynamics 365 Project Operations Core*  
    1. *Track project time*  
    1. *Track project fees*  
    1. *Purchase project materials*  
    1. *Use and track project materials*  
    1. *Produce project materials*  
    1. *Subcontract project components*  
    1. *Manage project communications*  
    1. *Manage project knowledge and documentation*  
1. [Manage project financials](project-to-profit-manage-project-financials-overview.md)  
1. [Analyze project performance](project-to-profit-monitor-analyze-project-performance-overview.md)

## Related resources

Use the following resources to learn more about entering project expenses by using the general journal in Dynamics 365.

- [Create and confirm Entry journals](/dynamics365/project-operations/actuals/create-confirm-entry-journals)
- [General journal processing](/dynamics365/finance/general-ledger/general-journal-processing)
- [General journal entity](/dynamics365/fin-ops-core/dev-itpro/data-entities/entity-general-journal)
- [Microsoft Certified: Dynamics 365 Finance Functional Consultant Associate - Certifications](/credentials/certifications/d365-functional-consultant-financials/?practice-assessment-type=certification)
- [Set up ledgers and journals in Dynamics 365 Finance - Training](/training/modules/configure-ledgers-journals-dyn365-finance/)
<!-- 
## Tags

*Industries:* Finance

*Stakeholders:* Finance, Operations, Project Management

*Products:* Dynamics 365 Finance, Dynamics 365 Project Operations -->

## Contributors

Microsoft maintains this article. The following contributors originally wrote it.

Principal author:

- [Mila Mojsilovic](https://www.linkedin.com/in/mila-mojsilović-747793225) | Junior Functional Consultant for Dynamics 365 Finance and Supply Chain Management
- [Sa.global (https://www.saglobal.com/)](https://www.saglobal.com/en-us) | Business Applications and Modern Work, Microsoft Inner Circle Partner  

Other contributors:

- [Irena Zivkovic](https://www.linkedin.com/in/irena-živković-46593422a) | Junior Functional Consultant for Dynamics 365 Finance and Supply Chain Management
- [Isidora Kupresak](https://www.linkedin.com/in/isidorakupresak) | Junior Functional Consultant for Dynamics 365 Finance and Supply Chain Management
- [Satya Teki](https://www.linkedin.com/in/satyateki) | Senior Solution Architect
