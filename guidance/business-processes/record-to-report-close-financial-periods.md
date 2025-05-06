---
title: Overview of the Close financial periods business process area
description: Learn about the processes around closing financial periods, including descriptions of stakeholders and a diagram of the process flow.
author: rachel-profitt
ms.author: raprofit
ms.topic: concept-article
ms.date: 04/08/2024
---

# Overview of the Close financial periods business process area within the Record to report end-to-end scenario

***Applies to: Dynamics 365 Business Central, Dynamics 365 Commerce, Dynamics 365 Finance, Dynamics 365 Project Operations, Dynamics 365 Supply Chain Management***

This article describes the process around closing financial periods in Dynamics 365.

The ability to efficiently and accurately close financial periods is a critical facet of maintaining the fiscal health and compliance of an organization. We'll explore the significance of this business process area, emphasizing its role in ensuring accurate financial reporting and compliance.

In the ever-evolving world of finance, where data accuracy and compliance with regulatory standards are non-negotiable, the process of closing financial periods emerges as a linchpin in an organization's financial management strategy. This pivotal business process area encapsulates a series of essential tasks, from reconciling accounts to finalizing financial statements. A well-executed financial period closure ensures the accuracy of financial reports, safeguards against errors and fraud, and provides stakeholders with a clear snapshot of an organization's fiscal health. Moreover, it enables businesses to meet their legal obligations and fosters trust among investors, auditors, and regulatory bodies.

To harness the full potential of Dynamics 365 and optimize financial operations, the definition, scoping, and implementation of the financial period closure process should be carefully orchestrated within the broader ERP deployment. This meticulous planning isn't a standalone activity but rather an integral part of the ERP implementation journey. By strategically aligning the closure of financial periods with the ERP system, organizations can streamline their financial workflows, enhance data accuracy, and ultimately drive efficiency across the enterprise. Timely consideration and incorporation of this process during the ERP implementation phase can prevent future bottlenecks, ensuring a smoother transition to a more agile and data-driven financial management system.

## Stakeholders

Many people across the organization should contribute to the decision-making process and design of the *close financial periods* area. The following list provides examples of such stakeholders:

- **Finance leadership stakeholders** include CFOs, VPs of finance, or directors of finance. They provide strategic input, setting the tone for the financial period closure process and aligning it with overall financial goals. Their involvement ensures that the financial period closure meets reporting standards and supports accurate financial insights.

- **Financial controllers** contribute insights into compliance requirements and regulatory standards related to financial period closure. Their active participation ensures that the financial period closure aligns with audit and regulatory expectations, supporting a smooth and compliant process.

- **Accounting stakeholders** include accounts payable and accounts receivable. The accounting team provides detailed input into the procedures and reconciliations required during financial period closure. Active involvement ensures the accurate execution of reconciliation processes and the timely closure of financial periods.

- **Audit stakeholders** include internal and external auditors. Internal auditors contribute insights into best practices, risk mitigation, and compliance considerations for the financial period closure process. While external auditors provide insights into external reporting requirements and expectations for financial period closure. The role of the internal auditor is crucial in validating the effectiveness of internal controls and ensuring compliance during the financial period closure. While the external auditor's involvement ensures that the financial period closure aligns with external audit standards, facilitating a smoother audit process.

- **Treasury stakeholders** contribute insights into the financial activities that impact cash flow during the financial period closure. Their involvement ensures that cash flow statements and related financial reports accurately reflect the organization's liquidity position.

- **Compliance stakeholders** include compliance officers, which provide guidance on ensuring that the financial period closure processes adhere to industry regulations and organizational policies. Their active participation ensures that compliance considerations are integrated into the financial period closure, mitigating risks.

## Close financial periods process flow

The following diagram illustrates the *Financial period close* business process area. [!INCLUDE [daf-business-process-flow-def](~/../shared-content/shared/guidance-includes/daf-business-process-flow-def.md)]

:::image type="content" source="media\record-to-report-close-financial-periods-1.svg" alt-text="Diagram of the Financial period close business process area and its connection to other business processes." lightbox="media\record-to-report-close-financial-periods-1.svg":::

1. Start

    Parallel branches from start connect to *Acquire to dispose*, *Inventory to deliver*, *Order to cash*, *Plan to produce*, *Source to pay*, *Project to profit*, and *Service to cash* end-to-end processes shown on the right, which all have a connect to 3. *Close financial periods*.

2. *Record to report*

3. *Close financial periods*

4. *Define period close processes and procedures*

5. *Record actuals*

6. *Finalize and post transactions*

7. *Perform currency revaluations*

8. *Perform currency revaluations*

9. *Reconcile subledgers to ledgers*

10. *Consolidate financials and perform eliminations*

11. *Close periods*

12. *Prepare financial statements*

    A parallel branch connects to the *Report and analyze financials and cash flows* business process area shown on the right, which has a connection to 16. End.

13. Is year end?

    1. *Yes* branches to *Perform year end activities*

        Perform year end activities has parallel branches that connect to 14. Is audit required? and 15. Prepare tax, audit, and regulatory documents.

    2. *No* branches to *Is Audit required?*

14. *Is audit required?*

    1. *Yes* branches to *Prepare for financial audits*

    2. *No* branches to *End*.

15. *Prepare tax, audit, and regulatory documents*

16. End

## Close financial periods benefits

There are many benefits that can be used to monitor and measure the success of implementing technology to support the financial period close. The following sections outline the key benefits that an organization might monitor and measure during financial period close.

## Ensured accuracy in financial reporting

Dynamics 365 facilitates accurate financial reporting by providing robust features for reconciliations, adjustments, and closing procedures. The system's automated reconciliation tools help identify and resolve discrepancies, ensuring that financial statements accurately reflect the organization's financial position.

KPIs for this benefit include the reduction in reconciliation errors and improvements in the accuracy of financial statements following the closure of each period.

## Enhanced compliance and audit preparedness

The financial period closure processes in Dynamics 365 are designed to adhere to regulatory standards and industry best practices. The system provides tools for documenting compliance procedures, maintaining an audit trail, and generating compliance reports. This ensures that organizations are well-prepared for external audits and regulatory scrutiny.

KPIs for this benefit include the successful completion of compliance checks and a reduction in audit findings related to financial period closure processes.

## Streamlined transition to the next reporting cycle

Dynamics 365 simplifies the transition to the next reporting cycle by providing features for updating account balances, and initiating new financial periods seamlessly. The system's automation capabilities reduce manual efforts and accelerate the process of starting a new reporting cycle. Additionally, Dynamics 365 Finance and Supply Chain Management include data archival features to help organizations manage their data over time.

KPIs for this benefit include the reduction in the time taken to close a financial period and the efficiency in initiating the next reporting cycle.

## Next steps

If you would like to implement Dynamics 365 solutions to assist with your *closing of financial period* business processes, you can use the following resources and steps to learn more.

1. [Define ledger structure and organizational accounting policies](report-to-record-define-financial-structure-organizational-accounting-policies.md)

2. [Comply with tax, audit, and regulatory requirements](record-to-report-comply-tax-audit-regulatory-requirements.md)

3. [Manage budgets](record-to-report-manage-budgets.md)

4. [Manage fund accounting](record-to-report-manage-fund-accounting.md)

5. [Record financial transactions](record-to-report-record-financial-transactions.md)

6. *Close financial periods* (the article that you're currently reading)

7. *Report and analyze financials and cash flow*

## Related information

You can use the following resources to learn more about the close financial period process in Dynamics 365.

- [Close the general ledger at period end - Finance](/dynamics365/finance/general-ledger/close-general-ledger-at-period-end)

- [Financial period close workspace - Finance](/dynamics365/finance/general-ledger/financial-period-close-workspace)

- [Optimize year-end close series – Dynamics 365 Finance](https://community.dynamics.com/blogs/post/?postid=02e7b3df-15c1-4c61-97bd-eba2fbbb3558)

- [Awareness between ledger settlement and year-end close - Finance](/dynamics365/finance/general-ledger/awareness-between-ledger-settlement-year-end-close)

- [Work with accounting periods and years - Business Central](/dynamics365/business-central/finance-accounting-periods-and-fiscal-years)

- [Close years and periods - Business Central](/dynamics365/business-central/year-close-years-periods)

<!--## Tags

*Industries:* Agriculture (01-09), Mining (10-14), Construction (15-17), Manufacturing (20-39), Transportation and Public Utilities (40-49), Wholesale Trade (50-51), Retail Trade (52-59), Finance, Insurance, Real Estate (60-67), Services (70-89), Public Administration (91-99)

*Stakeholders:* Accounts payable, Accounts receivable, Audit, Finance, Merchandising, Operations, Production, Project Management, Purchasing, Retail store operations, Sales, Service operations, Transportation, Treasury

*Products:* Dynamics 365 Business Central, Dynamics 365 Commerce, Dynamics 365 Finance, Dynamics 365 Project Operations, Dynamics 365 Supply Chain Management -->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- \[Rachel Profitt\](https://www.linkedin.com/in/rachelprofitt/) \| Principal Program Manager

Other contributors:

- \[Eric Pegors\]( https://www.linkedin.com/in/ericpegors/) \| Principal FastTrack Solution Architect

- \[Jodi Christiansen\]( https://www.linkedin.com/in/jodi-christiansen-2537aa9/) \| Senior Program Manager
