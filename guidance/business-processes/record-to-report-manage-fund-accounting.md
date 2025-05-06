---
title: Overview of the Manage fund accounting business process area
description: Learn about the concept of fund accounting and which Dynamics 365 products support this area out of the box.
author: lifiatamara-ms
ms.author: lifiatamara
ms.topic: concept-article
ms.date: 02/10/2025
---

# Overview of the Manage fund accounting business process area within the Record to report end-to-end scenario

***Applies to: Dynamics 365 Finance, Dynamics 365 Project Operations, Dynamics 365 Supply Chain Management***

This article describes the business process area of *fund accounting* and provides an overview of how you can use Dynamics 365 products to manage fund accounting for efficient financial management and accountability.

> [!NOTE]
> This business process area is deprecated in the November 2024 version of the business process catalog. Learn more at [Improvements to Record to report processes](about-whats-new-2024-november.md#improvements-to-record-to-report-processes).

Fund accounting is a crucial business process area, especially for non-profit organizations and government entities. It provides a detailed account of income and expenditure to help the organization provide transparency and accountability in financial operations. With Dynamics 365, organizations can streamline their fund accounting processes and track funds effectively, maintain regulatory compliance, and make informed financial decisions.

Defining, scoping, and implementing fund accounting in an overall business solution implementation should ideally occur during the initial stages of the project. This is because fund accounting forms the backbone of financial management and influences other business processes. Early implementation allows for seamless integration with other modules and ensures that the system accurately reflects the organization's financial structure. Moreover, it provides ample time for testing and adjustments before going live, minimizing potential disruptions to operations.

## Stakeholders

Many people across the organization should contribute to the decision-making process and design of the *Manage fund accounting* area. The following list provides examples of such stakeholders:

- **Finance managers**: As the primary users of fund accounting, they can provide valuable insights into the specific needs and challenges of the organization.

- **External auditors or consultants**: They can provide an outside perspective, ensuring the system meets regulatory requirements and follows best practices.

- **Governments**: Governments can have legal and administrative requirements for fund accounting.

## Manage fund accounting process flow

The following diagram illustrates the *Manage fund accounting* business process area. [!INCLUDE [daf-business-process-flow-def](~/../shared-content/shared/guidance-includes/daf-business-process-flow-def.md)]

:::image type="content" source="media\record-to-report-manage-fund-accounting-1.svg" alt-text="Diagram showing the connection the Manage fund accounting business process area and other business processes." lightbox="media\record-to-report-manage-fund-accounting-1.svg":::

The following steps are illustrated in the *Manage fund accounting* business process flow diagram.

1. Start

2. *Record to report* end-to-end process

3. *Define ledger structure and organizational accounting policies* business process area

4. *Manage budgets* business process area

5. *Manage fund accounting* business process area

    1. *Define restricted and unrestricted funds*  

        The first step where you define the types of funds that the system must manage.

    2. *Define posting policies*  

        After defining the funds, you must establish the rules for how transactions will be posted to these funds.

    3. *Configure budget planning for fund accounting*  

         Once the funds and posting policies are defined, you can set up the budget planning process tailored to fund accounting.

    4. *Create and manage preliminary budgets*  

        After configuring budget planning, you can create preliminary budgets for each fund.

    5. *Process appropriations*  

        Appropriations are processed next, which involves allocating money to the different funds.

    6. *Manage an approved budget*  

        Once appropriations are processed, you can manage the approved budget for each fund.

    7. *Prevent budget overages for a fund*  

        Implement measures to prevent spending more than what's available in a fund's budget.

    8. *Record revenues against funds*  

        As revenues are received, they're recorded against the appropriate funds.

    9. *Process expenditures against funds*  

        Similarly, as expenses are incurred, they're processed against the appropriate funds.

    10. *Review available financial resources*  

        Regularly review the financial resources available in each fund.

    11. *Perform ledger settlements for funds*  

        At the end of a period, perform ledger settlements to ensure all transactions are properly accounted for in each fund.

    12. *Complete closing entries for fund accounting*  

        Finally, complete the closing entries for the accounting period.

6. End.

There's a parallel branch from h, *Record revenues against funds* subprocess to the *Order to cash* and *Service to cash* end-to-end processes and the [Record financial transactions](record-to-report-record-financial-transactions.md) business process area because documents, such as free text invoices, are posted and revenues are recorded to the appropriate funds.

A second parallel branch exists from i, *Process expenditures against funds* subprocess to *Source to pay* end-to-end processes as documents, such as vendor invoices, are posted, and expenditures are recorded to the appropriate funds.

A third parallel branch exists from j, *Review available financial resources* subprocess to *Report and analyze financials and cash flow* business process area.

A fourth parallel branch exists from l, *Complete closing entries for fund accounting* subprocess to *Close financial periods* business process area.

## Manage fund accounting benefits

There are many benefits that can be used to monitor and measure the success of implementing technology to support the *Manage fund accounting* area. The following sections outline the key benefits that an organization might monitor and measure for Manage fund accounting.

### Efficiency

Dynamics 365 automates many of the routine tasks involved in fund accounting, reducing manual effort and increasing efficiency. Here's how Dynamics 365 contributes to efficiency:

- *Automated processes*: Dynamics 365 can automate many routine tasks in fund accounting, such as data entry, calculations, and report generation. This not only saves time but also allows staff to focus on more strategic tasks.

- *Streamlined workflows*: Dynamics 365 supports customizable workflows that can streamline fund accounting processes. For example, it can automatically route transactions for approval based on predefined rules, reducing delays and improving process efficiency.

- *Centralized data*: With Dynamics 365, all fund accounting data is stored in a centralized system. This eliminates the need for multiple spreadsheets or systems, making it easier to manage and access data.

- *Reduced training time*: The user-friendly interface of Dynamics 365 reduces the learning curve for staff members, reducing training time and costs.

By enhancing efficiency, Dynamics 365 helps organizations get more done in less time, which leads to cost savings and an improved financial management.

### Accuracy

Automated calculations and processes reduce the risk of human error, ensuring more accurate financial reporting. Dynamics 365 enhances accuracy in several ways:

- *Automated calculations*: Dynamics 365 automates complex calculations required in fund accounting. This minimizes the risk of human errors that can occur with manual calculations, ensuring more accurate results.

- *Data validation*: The system has built-in data validation rules that check for errors or inconsistencies at the point of data entry. This helps to ensure the accuracy of financial data.

- *Audit trails*: Dynamics 365 maintains a complete audit trail of all transactions. This not only ensures accountability but also allows for accurate tracking and reporting of funds.

- *Consistent data*: Since all fund accounting data is stored in a centralized system, it ensures consistency across all reports and financial statements.

By enhancing accuracy, Dynamics 365 helps organizations maintain financial integrity, comply with regulatory requirements, and make informed decisions based on reliable data.

### Compliance

Dynamics 365 has built-in features to help organizations comply with regulatory requirements related to fund accounting. Dynamics 365 aids in maintaining compliance in several ways:

- *Regulatory compliance*: Dynamics 365 is designed with regulatory compliance in mind. It includes features that help organizations adhere to various fund accounting standards and regulations. For example, it can generate reports that align with specific regulatory formats.

- *Audit trails*: Dynamics 365 maintains detailed audit trails of all transactions. This feature is crucial for compliance, as it allows organizations to demonstrate accountability and transparency in their use of funds.

- *Access controls*: Dynamics 365 allows for robust access controls, ensuring that only authorized individuals can access sensitive financial data. This helps prevent fraud and misuse of funds, thereby aiding in compliance.

- *Data integrity*: By ensuring the accuracy and consistency of financial data, Dynamics 365 indirectly supports compliance. Accurate data is crucial for meeting reporting requirements and demonstrating regulatory compliance.

By enhancing compliance, Dynamics 365 not only helps organizations avoid penalties and damage to their reputation but also fosters trust among donors, board members, and the public.

## Next steps

If you want to implement Dynamics 365 solutions to assist with your *Manage fund accounting* business processes, you can use the following resources and steps to learn more. (Links are added when the articles are ready.)

1. [Define ledger structure and organizational accounting policies](/dynamics365/guidance/business-processes/report-to-record-define-financial-structure-organizational-accounting-policies)
1. [Manage budgets](record-to-report-manage-budgets.md)
[Record financial transactions](record-to-report-record-financial-transactions.md)
1. [Close financial periods](record-to-report-close-financial-periods.md)
1. *Report and analyze financials and cash flow*
1. *Manage fund accounting* (the article you're currently reading)
 
## Related information

You can use the following resources to learn more about the Manage fund accounting process in Dynamics 365.

- [Posting definitions - Finance](/dynamics365/finance/general-ledger/posting-definitions)

- [Funds in the public sector - Finance](/dynamics365/finance/public-sector/funds-public-sector)

- [Configure Dynamics 365 Finance for public sector - Training](/training/modules/configure-public-sector-dyn365-finance)

- [Microsoft Certified: Dynamics 365 Finance Functional Consultant Associate](/certifications/exams/mb-310)

<!-- ## Tags

*Industries:* Services (70-89), Public Administration (91-99)

*Stakeholders:* Accounts payable, Accounts receivable, Audit, Finance, Project Management, Purchasing, Treasury

*Products:* Dynamics 365 Finance, Dynamics 365 Project Operations, Dynamics 365 Supply Chain Management -->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [Lifia Tamara](https://www.linkedin.com/in/lifia/) | Consultant

Other contributors:

- [Rachel Profitt](https://www.linkedin.com/in/RachelProfitt) | Principal Program Manager
