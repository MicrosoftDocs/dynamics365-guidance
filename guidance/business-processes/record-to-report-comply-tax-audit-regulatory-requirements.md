---
title: Comply with tax, audit, and regulatory requirements overview
description: Learn how you can use Dynamics 365 products to support the organization's business processes to comply with tax, audit, and regulatory requirements.
ms.date: 11/09/2023
ms.topic: conceptual
author: rachelprofitt
ms.author: raprofit
---

# Comply with tax, audit, and regulatory requirements overview

***Applies to: Dynamics 365 Business Central, Dynamics 365 Customer Service, Dynamics 365 Finance, Dynamics 365 Field Service, Dynamics 365 Fraud Protection, Dynamics 365 Human Resources, Dynamics 365 Project Operations, Dynamics 365 Sales***

This article describes how you can use Dynamics 365 to not only ensure adherence to tax, audit, and regulatory mandates but also streamline and optimize these essential business processes.

In the fast-evolving landscape of modern organizations, meeting tax, audit, and regulatory requirements has become increasingly complex. To navigate this intricate web of compliance, organizations are turning to technology solutions like Microsoft Dynamics 365 to help support these processes.

Tax, audit, and regulatory compliance are foundational pillars of a well-governed and sustainable business environment. Adherence to these standards isn't just a legal necessity but also a strategic imperative. Failure to comply with tax laws, auditing standards, or regulatory requirements can result in costly penalties, reputational damage, and operational disruptions. As businesses expand across borders and regulations continually evolve, the ability to proactively manage and adapt to these compliance demands is critical for long-term success.

Microsoft Dynamics 365 Finance offers a robust platform with features like the Globalization Studio, Electronic invoicing, the audit workbench, audit logs, and a comprehensive tax engine to help calculate tax. These features help to empower organizations to stay ahead in this compliance landscape. When you use Dynamics 365 Sales, Customer Service, Field Service, or Power Apps built on the Dataverse, you can enable audit logging on a table-by-table basis. The [Dataverse auditing](/power-platform/admin/manage-dataverse-auditing) feature is designed to meet the external and internal auditing, compliance, security, and governance policies that are common to many enterprises. A similar feature is available in Dynamics 365 Finance, Commerce, Supply Chain Management, Human Resources, and Project Operations called [Database logging](/dynamics365/fin-ops-core/dev-itpro/sysadmin/configure-manage-database-log).

Dynamics 365 Fraud Protection includes adaptive AI that can help protect organizations against payment fraud, bots, account takeover, and returns and discount fraud.

In any ERP implementation, the timely and precise definition, scoping, and implementation of tax, audit, and regulatory compliance processes are paramount. These considerations should be an integral part of the ERP project from the outset. We recommend that an analysis of these requirements happens early in the implementation process. While many features for compliance, localization, and so on, can be added later, project costs and timeline can increase significantly when the analysis isn't performed early.

If you wait until the later stages of implementation, or in a multi-phased rollout, especially with multiple countries or regions, it can lead to costly retrofits, delays, and disruptions. Instead, a proactive approach is recommended, where these business process areas are identified, analyzed, and mapped early in the planning phase. It's also important to consider the overall architecture of the solution including data center, language, and localization requirements for all countries/regions and phases, and identify the need for any third-party ISV solutions to meet the requirements to plan the overall project effectively. This way, you make sure that the Dynamics 365 solution is tailored to the specific compliance needs of the organization, aligning processes and technologies for maximum efficiency and effectiveness. By defining and scoping these requirements upfront, businesses can seamlessly integrate tax, audit, and regulatory compliance into their Dynamics 365 implementation, promoting a smoother transition and reducing the risks associated with noncompliance.

## Stakeholders 

Many people across the organization should contribute to the decision-making process and design of the *comply with tax and regulatory requirements* area. The following list provides examples of such stakeholders:

- **Finance stakeholders**: Finance professionals are at the forefront of tax compliance and financial reporting. They play a crucial role in defining the specific tax and regulatory requirements that the ERP system must meet. They can provide insights into financial processes, reporting needs, and compliance obligations.

- **Legal and compliance stakeholders**: Legal experts and compliance officers are responsible for staying up to date with the latest regulations and ensuring that the organization adheres to them. Their input is invaluable in identifying the legal and regulatory requirements that the ERP system must address.

- **Tax experts**: If your organization deals with complex tax regulations, involving tax experts or consultants is crucial. They can provide specialized knowledge about tax codes, exemptions, credits, and deductions, which is vital for configuring the system accurately.

- **Audit and risk management stakeholders**: Audit and risk management professionals can provide insights into what auditors typically look for and what data and processes need to be in place for a successful audit. Their involvement is essential for ensuring that audit trails and compliance controls are properly integrated into the Dynamics 365 solution.

- **External auditors**: If your organization undergoes external audits, involving auditors in the testing phase can help identify potential issues or gaps in compliance that need to be addressed before an actual audit takes place.

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
    > We show an upstream process from *Close financial periods*. The frequency at which you close financial periods is based on your organization and regulatory requirements. Typically audits do not occur until after the period is closed, but you can perform some audit tasks prior to the financial period being closed.

9. End

> [!NOTE]
> *Pay tax authorities* and *Manage security* have unshown connections to 9. End.

## Benefits to the area Comply with tax, audit, and regulatory requirements

There are many key benefits that can be used to monitor and measure the success of implementing technology to support the *comply with tax, audit, and regulatory requirements*. The following sections outline the key benefits that an organization might monitor and measure for complying with tax, audit, and regulatory requirements. 

### Automate tax, audit, and regulatory compliance processes

Dynamics 365 automates many of the manual and time-consuming tasks associated with tax, audit, and regulatory compliance. This reduces the risk of errors and frees up employees to focus on more strategic activities. With built-in workflows that are included with the Audit workbench in Dynamics 35 Finance, you can create criteria for vendor invoices and expense reports, for example to create audit cases automatically.

By automating processes and reducing the likelihood of compliance errors, organizations can save money on fines, penalties, and audit-related expenses. It also optimizes resource allocation by eliminating redundant tasks.

### Improved accuracy and data integrity 

Dynamics 365 Finance helps maintain accurate and up-to-date financial and compliance data through a double-entry general ledger. Transactions posted in subledgers from Dynamics 365 Commerce, Supply Chain Management, and Project Operations are automatically transferred to the general ledger and controls are in place to ensure that accounts controlling the subledger can't have manual entries. This helps ensure that reports and submissions are error-free and compliant with regulations, reducing the risk of fines or penalties. Additionally, all financial transactions are automatically recorded in the Audit trail in the General ledger module.

Dynamics 365 provides real-time access to financial and compliance data, allowing organizations to generate reports using Financial Reporter on-demand, and with Business Performance Analytics near-real-time analytics. This is especially beneficial for making informed decisions and responding to regulatory inquiries promptly.

### Increased visibility and audit assurance

Dynamics 365 stores data indefinitely making it easy to access past records and reports for reference, audit, or compliance history analysis. When you use the data archival features available with Finance, you can easily keep the size of your database in control while still having the ability to look up records and the ability to restore data when required.

Dynamics 365 Finance maintains a detailed audit trail of all financial transactions and changes made within the system. This transparency is valuable during audits and investigations, as auditors can trace the history of transactions and compliance activities. When you use applications like Dynamics 365 Sales, Customer Service, or Field Service, you can enable *Audit logging* to track full details of changes made to any record. Use *Database logging* in applications such as Dynamics 365 Finance, Supply Chain Management, Commerce, Human Resources, and Project Operations, to enable critical tracking in any table or field.

### Global scalability and compliance

Dynamics 365 applications can grow with your organization. As your business expands or encounters more complex compliance requirements, the system can scale to accommodate those changes without requiring a complete overhaul.

For multinational organizations, Dynamics 365 can handle the complexities of complying with tax and regulatory requirements in multiple countries/regions, helping to harmonize compliance efforts across different regions.

## Next steps

If you want to implement Dynamics 365 solutions to assist with your tax, audit, and regulatory compliance business processes, you can use the following resources and steps to learn more. Links are added when articles become available.

1. [Define financial structure and organizational policies](report-to-record-define-financial-structure-organizational-accounting-policies.md)  

2. *Comply with tax, audit, and regulatory requirements* (the article you're currently reading)   

3. Manage fund accounting

4. Manage budgets

5. Record financial transactions

6. Close financial periods

7. Report and analyze financials and cash flow

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
- Find definitions of terminology used in content for tax, audit, and regulatory processes in the [Glossary of terms in Dynamics 365 business processes](glossary.md) article, including the following terms:

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
## Tags

*Industries:* Agriculture (01-09), Mining (10-14), Construction (15-17), Manufacturing (20-39), Transportation and Public Utilities (40-49), Wholesale Trade (50-51), Retail Trade (52-59), Finance, Insurance, Real Estate (60-67), Services (70-89), Public Administration (91-99)

*Stakeholders:* Accounts payable, Accounts receivable, Audit, Customer services, Finance, Human Resources, IT, Production, Project Management, Purchasing, Treasury

*Products:* Dynamics 365 Business Central, Dynamics 365 Finance, Dynamics 365 Fraud Protection, Dynamics 365 Project Operations

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- Rachel Profitt (https://www.linkedin.com/in/rachelprofitt/) \| Principal Program Manager, Microsoft
