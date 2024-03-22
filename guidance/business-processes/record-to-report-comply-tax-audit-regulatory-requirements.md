---
title: Ensure and optimize tax, audit, and regulatory requirements
description: Learn how you can use Dynamics 365 products to support the organization's business processes to comply with tax, audit, and regulatory requirements.
ms.date: 01/23/2024
ms.topic: conceptual
author: rachelprofitt
ms.author: raprofit
---

# Ensure, optimize, and comply with tax, audit, and regulatory requirements

***Applies to: Dynamics 365 Business Central, Dynamics 365 Customer Service, Dynamics 365 Finance, Dynamics 365 Field Service, Dynamics 365 Fraud Protection, Dynamics 365 Human Resources, Dynamics 365 Project Operations, Dynamics 365 Sales***

This article describes how you can use Dynamics 365 not only to ensure adherence to tax, audit, and regulatory mandates, but also to streamline and optimize these essential business processes.

In the quickly evolving landscape of modern organizations, it's increasingly complex to meet tax, audit, and regulatory requirements. To navigate the intricate web of compliance, organizations are turning to technology solutions such as Dynamics 365 to help support these processes.

Tax compliance, audit compliance, and regulatory compliance are foundational pillars of a well-governed and sustainable business environment. Adherence to these standards is not only a legal necessity but also a strategic imperative. Failure to comply with tax laws, auditing standards, or regulatory requirements can lead to costly penalties, reputational damage, and operational disruptions. As businesses expand across borders and regulations continually evolve, the ability to proactively manage and adapt to these compliance demands is critical for long-term success.

Dynamics 365 Finance offers a robust platform that includes features such as the Globalization Studio, Electronic invoicing, the audit workbench, audit logs, and a comprehensive tax engine to help calculate tax. These features help empower organizations to stay ahead in the compliance landscape. When you use Dynamics 365 Sales, Customer Service, or Field Service, or apps that are built on Dataverse in Power Apps, you can enable audit logging on a table-by-table basis. The [Dataverse auditing](/power-platform/admin/manage-dataverse-auditing) feature is designed to meet the external and internal auditing, compliance, security, and governance policies that are common to many enterprises. [Database logging](/dynamics365/fin-ops-core/dev-itpro/sysadmin/configure-manage-database-log) is a similar feature that is available in Dynamics 365 Finance, Commerce, Supply Chain Management, Human Resources, and Project Operations. Dynamics 365 Fraud Protection includes adaptive AI that can help protect organizations against payment fraud, bots, account takeover, and returns and discount fraud.

In any enterprise resource planning (ERP) implementation, the timely and precise definition, scoping, and implementation of tax, audit, and regulatory compliance processes are paramount. These considerations should be an integral part of the ERP project from the beginning. We recommend that an analysis of these requirements occurs early in the implementation process. Although many features for compliance, localization, and so on, can be added later, project costs and the project timeline can increase significantly if this analysis isn't done early.

If you wait until the later stages of the implementation process or do a multiphase rollout, especially one that involves multiple countries or regions, costly retrofits might be required, or delays and disruptions might occur. Therefore, we recommend a proactive approach instead, where these business process areas are identified, analyzed, and mapped early in the planning phase. It's important to consider the overall architecture of the solution, including datacenter, language, and localization requirements for all countries/regions and phases. It's also important to identify any third-party independent software vendor (ISV) solutions that are needed to meet the requirements for effective planning of the overall project. In this way, you ensure that the Dynamics 365 solution is tailored to the specific compliance needs of the organization. You also ensure that processes and technologies are aligned for maximum efficiency and effectiveness. By defining and scoping these requirements up front, businesses can seamlessly integrate tax, audit, and regulatory compliance into their Dynamics 365 implementation. In this way, they promote a smoother transition and reduce the risks that are associated with noncompliance.

## Stakeholders

Many people across the organization should contribute to the decision-making process and design of the *comply with tax and regulatory requirements* area. The following list provides examples of such stakeholders:

- **Finance stakeholders**: Finance professionals are at the forefront of tax compliance and financial reporting. They play a crucial role in defining the specific tax and regulatory requirements that the ERP system must meet. They can provide insights into financial processes, reporting needs, and compliance obligations.
- **Legal and compliance stakeholders**: Legal experts and compliance officers are responsible for staying up to date with the latest regulations and ensuring that the organization adheres to them. Their input is invaluable in identifying the legal and regulatory requirements that the ERP system must address.
- **Tax experts**: If your organization deals with complex tax regulations, the involvement of tax experts or consultants is crucial. They can provide specialized knowledge about tax codes, exemptions, credits, and deductions. This information is vital for accurate configuration of the system.
- **Audit and risk management stakeholders**: Audit and risk management professionals can provide insights into the things that auditors typically look for, and the data and processes that must be in place to ensure a successful audit. Their involvement is essential for ensuring that audit trails and compliance controls are properly integrated into the Dynamics 365 solution.
- **External auditors**: If your organization undergoes external audits, the involvement of auditors in the testing phase can help identify potential issues or gaps in compliance that must be addressed before an actual audit occurs.

## Comply with tax audit and regulatory requirements process flow 

The following diagram illustrates the *comply with tax, audit, and regulatory requirements* business process area. [!INCLUDE [daf-business-process-flow-def](~/../shared-content/shared/guidance-includes/daf-business-process-flow-def.md)]

:::image type="content" source="media/record-to-report-comply-tax-audit-reg-reqs-flow.svg" alt-text="Flow diagram for the business process area, which is explained in the paragraphs after the image." lightbox="media/record-to-report-comply-tax-audit-reg-reqs-flow.svg":::

1. Start
2. *Record to report* end-to-end process
3. *Configure ledger and organizational accounting policies*
4. *Comply with tax audit and regulatory requirements*
5. *Configure taxes*

    1. Record financial transactions (an upstream business process area in the *Record to report* end-to-end process)
    2. Analyze and settle taxes
    3. Report tax and financial data to authorities
    4. Pay tax authorities

6. *Manage security*
7. *Comply with data retention policies*

    1. *Manage data archival*

8. *Audit financial transactions*

    > [!IMPORTANT]
    > The diagram shows an upstream process from *Close financial periods*. The frequency at which you close financial periods is based on your organization and regulatory requirements. Although audits don't typically occur until after the period is closed, you can perform some audit tasks before the financial period is closed.

9. End

> [!NOTE]
> *Pay tax authorities* and *Manage security* have unshown connections to 9. End.

## Benefits of the comply with tax, audit, and regulatory requirements area

There are many key benefits that can be used to monitor and measure the success of implementing technology to support the *comply with tax, audit, and regulatory requirements*. The following sections outline the key benefits that an organization might monitor and measure for complying with tax, audit, and regulatory requirements.

### Automate tax, audit, and regulatory compliance processes

Dynamics 365 automates many of the manual and time-consuming tasks that are associated with tax, audit, and regulatory compliance. This automation helps reduce the risk of errors and frees up employees to focus on more strategic activities. By using built-in workflows that are included with the Audit workbench in Dynamics 35 Finance, you can create criteria for vendor invoices and expense reports (for example, to automatically create audit cases).

By automating processes and reducing the likelihood of compliance errors, organizations can save money on fines, penalties, and audit-related expenses. These capabilities also help optimize resource allocation by eliminating redundant tasks.

### Improved accuracy and data integrity

Dynamics 365 Finance helps maintain accurate and up-to-date financial and compliance data through a double-entry general ledger. Transactions that are posted in subledgers from Dynamics 365 Commerce, Supply Chain Management, and Project Operations are automatically transferred to the general ledger. Controls are in place to ensure that accounts that control the subledger can't have manual entries. This functionality helps ensure that reports and submissions are error-free and comply with regulations. Therefore, it helps reduce the risk of fines or penalties. Additionally, all financial transactions are automatically recorded in the audit trail in the *General ledger* module.

Dynamics 365 provides real-time access to financial and compliance data. Therefore, organizations can generate reports on demand by using Financial Reporter. They can also use Business Performance Analytics near-real-time analytics. This capability is especially beneficial because it helps organizations make informed decisions and promptly respond to regulatory inquiries.

### Increased visibility and audit assurance

Dynamics 365 stores data indefinitely. Therefore, you can easily access past records and reports for reference, audit, or compliance history analysis. By using the data archival features that are available in Finance, you can easily keep the size of your database under control but still look up records and restore data as required.

Dynamics 365 Finance maintains a detailed audit trail of all financial transactions and changes that are made in the system. This transparency is valuable during audits and investigations, because auditors can trace the history of transactions and compliance activities. When you use applications such as Dynamics 365 Sales, Customer Service, or Field Service, you can enable *audit logging* to track full details of changes that are made to any record. Use *database logging* in applications such as Dynamics 365 Finance, Supply Chain Management, Commerce, Human Resources, and Project Operations to enable critical tracking in any table or field.

### Global scalability and compliance

Dynamics 365 applications can grow with your organization. As your business expands or encounters more complex compliance requirements, the system can scale to accommodate those changes without requiring a complete overhaul.

For multinational organizations, Dynamics 365 can handle the complexities of complying with tax and regulatory requirements in multiple countries/regions. Therefore, it helps harmonize compliance efforts across different regions.

## Next steps

If you want to implement Dynamics 365 solutions to assist with your *record to report* business processes, use the following resources and steps to learn more. (Links are added, when the articles are ready.)

1. [Define financial structure and organizational policies](report-to-record-define-financial-structure-organizational-accounting-policies.md)

2. *Comply with tax, audit, and regulatory requirements* (the article that you're currently reading)

3. *Manage fund accounting*

4. *Manage budgets*

5. *Record financial transactions*

6. *Close financial periods*

7. *Report and analyze financials and cash flow*

## Related resources

You can use the following resources to learn more about the tax, audit, and regulatory processes in Dynamics 365.

- [Globalization resources - Finance & Operations](/dynamics365/fin-ops-core/dev-itpro/lcs-solutions/country-region?context=%2Fdynamics365%2Fcontext%2Ffinance)
- [Globalization Studio overview - Finance](/dynamics365/finance/localizations/globalization-studio-overview?context=%2Fdynamics365%2Fcontext%2Ffinance)
- [Product localization and translation availability guide](https://aka.ms/dynamics_365_international_availability_deck)
- [Dynamics 365 Finance, Supply Chain Management, and Commerce operated by 21Vianet in China](/dynamics365/fin-ops-core/dev-itpro/deployment/china-local-deployment)
- [Manage Dataverse auditing - Power Platform](/power-platform/admin/manage-dataverse-auditing)
- [Overview of Dynamics 365 Fraud Protection](/dynamics365/fraud-protection/)
- [Regional availability of Dynamics 365 Fraud Protection services](/dynamics365/fraud-protection/global-availability)
- [Compliance Overview - Business Central](/dynamics365/business-central/compliance/compliance-overview?)
- [Local functionality in Business Central](/dynamics365/business-central/about-localization)
- [General Data Protection Regulation - Microsoft GDPR](/compliance/regulatory/gdpr)
- [Compliance offerings for Microsoft 365, Azure, and other Microsoft services](/compliance/regulatory/offering-home)
- [Dynamics 365 compliance list](https://aka.ms/d365-compliance-list)
- Find definitions of terminology that is used in content for tax, audit, and regulatory processes in the [Glossary of terms in Dynamics 365 business processes](glossary.md) article. For example, this glossary includes the following terms:

    - [Accounting Standards Codification (ASC)](glossary.md#accounting-standards-codification-asc)
    - [Audit trail](glossary.md#audit-trail)
    - [Audit management](glossary.md#audit-management)
    - [Compliance controls](glossary.md#compliance-controls)
    - [Compliance reporting](glossary.md#compliance-reporting)
    - [Financial reporting](glossary.md#financial-reporting)
    - [HIPAA (Health Insurance Portability and Accountability Act)](glossary.md#hipaa-health-insurance-portability-and-accountability-act)
    - [Internal controls](glossary.md#internal-controls)
    - [International Accounting Standards Board (IASB)](glossary.md#international-accounting-standards-board-iasb)
    - [International Financial Reporting Standards (IFRS)](glossary.md#international-financial-reporting-standards-ifrs)
    - [Regulatory compliance](glossary.md#regulatory-compliance)
    - [Sarbanes-Oxley Act (SOX)](glossary.md#sarbanes-oxley-act-sox)
    - [Tax compliance](glossary.md#tax-compliance)
    - [Tax jurisdiction](glossary.md#tax-jurisdiction)
    - [Tax codes and rates](glossary.md#tax-codes-and-rates)

<!-- ## Tags

*Industries:* Agriculture (01-09), Mining (10-14), Construction (15-17), Manufacturing (20-39), Transportation and Public Utilities (40-49), Wholesale Trade (50-51), Retail Trade (52-59), Finance, Insurance, Real Estate (60-67), Services (70-89), Public Administration (91-99)

*Stakeholders:* Accounts payable, Accounts receivable, Audit, Customer services, Finance, Human Resources, IT, Production, Project Management, Purchasing, Treasury

*Products:* Dynamics 365 Business Central, Dynamics 365 Finance, Dynamics 365 Fraud Protection, Dynamics 365 Project Operations -->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [Rachel Profitt](https://www.linkedin.com/in/rachelprofitt/) \| Principal Program Manager, Microsoft
