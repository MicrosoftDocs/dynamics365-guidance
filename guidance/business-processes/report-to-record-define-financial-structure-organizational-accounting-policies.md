---
title: Overview of the define financial structure business process
description: Learn how you can use Dynamics 365 products to support the organization's business processes to define the financial structure policies.
ms.date: 02/07/2025
ms.topic: concept-article
author: rachelprofitt
ms.author: raprofit
---

# Overview of the define financial structure and organizational accounting policies business process

***Applies to: Dynamics 365 Finance***

This article describes how to define the ledger, chart of accounts, currency, banking, asset, and related policies in Dynamics 365 Finance. The content will help you establish policies that are aligned with and support the business now and in the future.

In a Dynamics 365 implementation, definition of the financial structure and definition of organizational policies are crucial steps that significantly affect the success of the implementation and the overall efficiency of the business processes. In Dynamics 365 Finance, the chart of accounts, financial dimensions, and many General ledger parameters and configurations are used in downstream processes. Because Dynamics 365 Finance is a double-entry system that integrates directly with Dynamics 365 Commerce, Project Operations, and Supply Chain Management, all entries that are posted to a subledger are also posted to the general ledger.

By defining the financial structure early and clearly in your implementation, you help ensure accurate financial reporting, compliance, data consistency, and cost allocations. The financial structure in a Dynamics 365 Finance implementation includes the chart of accounts, cost centers, profit centers, financial reporting structures, tax codes, and more.

Organizational accounting policies include things such as the legal entity or company structure, elimination and consolidation rules, and intercompany accounting configuration, including centralized payments. They also define how you handle currency conversion and revaluation of your financial data throughout the system. In addition, if you use the *Fixed assets* or *Asset leasing* module, it covers the asset-related company policies. If you use the *Cash and bank management* module, it covers the banking policies and configurations. It's important to design your processes so that they are streamlined and efficient, to help reduce manual intervention and minimize errors. When you define your organizational accounting policies, you should consider standardizing them across companies and departments. By implementing consistent business processes across the organization, you help ensure uniformity and reduce confusion among employees. This standardization is especially important when different geographies, departments, or companies are involved. Although Dynamics 365 Finance supports flexible configuration across legal entities, the more processes you can standardize, the smoother your implementation is.

Many other areas rely on or are affected by the decisions that are made in the*define financial structure and organizational accounting policies* area. Therefore, the business processes in this area should be defined as early as possible in the overall implementation project.

## Stakeholders

Many people across the organization should contribute to the decision-making process and the design of the *define financial structure and organizational accounting policies* area. The following list provides examples of such stakeholders:

- **Executive Leadership**: Roles such as Chief Executive Officer (CEO), Chief Financial Officer (CFO), Chief Operating Officer (COO), and Chief Information Officer (CIO) should provide strategic direction, allocate resources, and make decisions that affect the overall implementation. Their involvement ensures alignment with organizational goals and vision.
- **Finance Department**: The CFO and finance managers are directly involved in designing the financial structure, chart of accounts, tax codes, and financial reporting requirements. A single stakeholder should be identified as the owner of the chart of accounts and organizational policies that are defined in the system. This approach ensures compliance with accounting standards and regulations.
- **Operations Managers**: The heads of various operational departments, who understand the day-to-day processes and requirements of their departments, should contribute to the process design. This approach ensures that the system design and organizational structure meet operational needs.
- **Legal and Compliance**: Legal counsel and compliance officers should ensure that the implementation adheres to legal and regulatory requirements, data privacy standards, and industry standards.
- **Auditors**: Implementation consultants, industry experts, internal auditors, and external auditors provide specialized knowledge, best practices, and insights to guide the design of processes and policies.
- **Treasury**: The Treasurer and other stakeholders who are responsible for cash flow, banking, and so on, should be involved in the processes for banking.

> [!NOTE]
> Whenever you plan to make changes to your organizational structure, chart of accounts, or the way that your organization reports your financials, we strongly recommend that you consult your auditors or other professionals to ensure compliance with any regulatory requirements.

## Define financial structure and organizational accounting policies process flows

The following diagram illustrates the business process flows for the *define financial structure and organizational accounting policies* area. [!INCLUDE [daf-business-process-flow-def](~/../shared-content/shared/guidance-includes/daf-business-process-flow-def.md)]

:::image type="content" source="media/record-to-report-define-financial-structure-org-acc-policies.svg" alt-text="Flow diagram for the business process area, which is explained in the paragraphs after the image." lightbox="media/record-to-report-define-financial-structure-org-acc-policies.svg":::

1. Start
2. *Record to report* end-to-end process
3. *Define financial structure and organizational accounting policies*

    1. *Update required?*

        1. *No* connects to 4. *Define company structure*.
        2. *Yes* has parallel branches that connect to each of the following processes:

            1. *Update company structure*
            2. *Update financial periods*
            3. *Maintain financial segments*
            4. *Maintain chart of accounts*, which connects to End

4. *Define company structure*
5. *Define financial periods*
6. *Design and configure financial segments*
7. *Design and configure the chart of accounts*

    Parallel branches connect to each of the following downstream business process areas in the *Record to report* end-to-end process:

    1. *Manage cash and bank transactions*
    2. *Manage budgets*
    3. *Record financial transactions*
    4. *Close financial periods*

8. *Define and configure currency policies*

    1. *Define currency revaluation policies*

9. *Define banking policies*

    1. *Establish banking relationships*

10. *Define asset policies*
11. End

The downstream business process areas for 7. *Design and configure the chart of account*, 8.a. *Define currency revaluation policies*, and 9.a. *Establish banking relationships* all have connections to End.

## Define financial structure and organizational accounting policies benefits

There are many benefits that can be realized by implementing technology to support the *define financial structure and organizational accounting policies* area. The following sections outline the benefits that an organization might monitor and measure for the *define financial structure and organizational accounting policies* area.

### Centralized data management of financial configuration

In Dynamics 365 Finance, you can define and manage your company's organizational structure, including subsidiaries, divisions, and business units, from a single platform. This capability ensures consistency and accuracy in financial reporting across the entire organization.

### Automated period management

Dynamics 365 Finance streamlines the process of defining and managing financial periods (months, quarters, and years). It helps automate the opening and closing of periods, and therefore reduces the chance of errors and ensures that transactions are recorded in the correct periods. Because Dynamics 365 integrates seamlessly with Dynamics 365 Supply Chain Management, Commerce, and Project Operations, all your transactions are automatically recorded by using a single set of controls for the periods.

### Flexible chart of accounts

In Dynamics 365 Finance, you can easily define and customize your organization's chart of accounts to align it with your organizational structure and reporting needs. Therefore, you have the flexibility to accurately categorize and track financial transactions. Dynamics 365 Finance supports a global chart of accounts and overrides to support local requirements. This flexibility means that you can design a chart of accounts for a small organization that has one company or a global company that has complex requirements across multiple countries/regions.

### Enhanced reporting

Dynamics 365 Finance supports the use of financial dimensions and financial tags to categorize transactions based on specific attributes, such as departments, projects, and cost centers. This capability allows for more detailed and insightful reporting, and therefore aids in better decision-making. The flexibility of tightly controlled financial dimensions means that you can control financial data to ensure accuracy or use financial tags to enrich your data without the need for complex rules.

### Efficient consolidations

For organizations that have multiple subsidiaries or business units, Dynamics 365 Finance streamlines the process of consolidating financial data across different currencies to ensure accurate consolidation of financial statements. You can easily set up consolidation companies and elimination companies, and create a hierarchy that represents your organization. Another option is to use financial reporting for financial consolidations and currency translation. Dynamics 365 Finance supports intercompany transactions in Dynamics 365 Supply Chain Management, Commerce, and Project Operations that are automated through one-time configuration. The amounts are then automatically posted to each company's ledger. Dynamics 365 Finance also supports functionality to easily eliminate the transactions when you consolidate your financials across companies.

### Minimized financial data entry errors

Dynamics 365 automates and standardizes processes that are related to currency and financial structure. Therefore, it minimizes the risk of manual errors that can arise from complex currency conversions and ledger management. In addition, Dynamics 365 Finance helps maintain compliance with financial regulations by accurately recording currency-related transactions and providing an audit trail. This functionality is crucial for demonstrating adherence to legal requirements. Dynamics 365 Finance also automates currency revaluation based on policies and market fluctuations. This functionality ensures that financial statements reflect the most accurate valuation of assets and liabilities.

## Next steps

If you want to implement Dynamics 365 solutions to assist with your *define financial structure and organizational accounting policies* business process area, use the following resources and steps to learn more. (Links are added when the articles are ready.)

1. *Define financial structure and organizational accounting policies* (the article that you're currently reading)

2. [Comply with tax audit and regulatory requirements](record-to-report-comply-tax-audit-regulatory-requirements.md)

3. *Manage fund accounting*

4. *Manage budgets*

5. *Record financial transactions*

6. *Close financial periods*

7. *Report and analyze financials and cash flow*

## Related information

You can use the following resources to learn more about the *define financial structure and organizational accounting policies* area in Dynamics 365.

- [TechTalk Series: Planning and Configuring your Chart of Accounts (dynamics.com)](https://community.dynamics.com/blogs/post/?postid=e8a7e07a-8f8d-48a2-849e-ed4fede81761)
- [Fiscal calendars, fiscal years, and periods - Finance](/dynamics365/finance/budgeting/fiscal-calendars-fiscal-years-periods)
- [Configure ledgers - Finance](/dynamics365/finance/general-ledger/configure-ledger)
- [Plan your organizational hierarchy - Finance & Operations](/dynamics365/fin-ops-core/fin-ops/organization-administration/plan-organizational-hierarchy?context=%2Fdynamics365%2Fcontext%2Ffinance)
- [Plan your chart of accounts - Finance](/dynamics365/finance/general-ledger/plan-chart-of-accounts)
- [Financial dimensions - Finance](/dynamics365/finance/general-ledger/financial-dimensions)
- [Configure account structures - Finance](/dynamics365/finance/general-ledger/configure-account-structures)
- [Create and assign advanced rule structures - Finance](/dynamics365/finance/general-ledger/tasks/create-assign-advanced-rule-structures)
- [Configure your organization in finance and operations apps - Training](/training/paths/configure-your-organization-finance-ops/)
- [Plan and implement legal entities in finance and operations apps - Training](/training/modules/plan-implement-legal-entities-finance-operations/)
- [Configure chart of accounts in Dynamics 365 Finance - Training](/training/modules/configure-chart-accounts-dyn365-finance/)
- [Set up financial processes - Business Central](/dynamics365/business-central/finance-setup-finance)
- [Set up or change the chart of accounts - Business Central](/dynamics365/business-central/finance-setup-chart-accounts)
- Find definitions of terminology that is used in content for tax, audit, and regulatory processes in the [Glossary of terms in Dynamics 365 business processes](glossary.md) article. For example, this glossary includes the following terms:

    - [Account structure](glossary.md#account-structure)
    - [Advanced rule](glossary.md#advanced-rule)
    - [Audit trail](glossary.md#audit-trail)
    - [Chart of accounts](glossary.md#chart-of-accounts)
    - [Company](glossary.md#company)
    - [Currency](glossary.md#currency)
    - [Currency conversion](glossary.md#currency-conversion)
    - [Currency policies](glossary.md#currency-policies)
    - [Currency revaluation](glossary.md#currency-revaluation)
    - [Date intervals](glossary.md#date-intervals)
    - [Dual currency](glossary.md#dual-currency)
    - [Exchange rate](glossary.md#exchange-rate)
    - [Exchange rate types](glossary.md#exchange-rate-types)
    - [Financial dimensions](glossary.md#financial-dimensions)
    - [Financial periods](glossary.md#financial-periods)
    - [Financial tags](glossary.md#financial-tags)
    - [General ledger](glossary.md#general-ledger)
    - [Ledger](glossary.md#ledger)
    - [Legal entity](glossary.md#legal-entity)
    - [Ledger](glossary.md#ledger)
    - [Subledger](glossary.md#subledger)

<!-- ## Tags

*Industries:* Agriculture (01-09), Mining (10-14), Construction (15-17), Manufacturing (20-39), Transportation and Public Utilities (40-49), Wholesale Trade (50-51), Retail Trade (52-59), Finance, Insurance, Real Estate (60-67), Services (70-89), Public Administration (91-99)

*Stakeholders:* Audit, Finance, Operations

*Products:* Dynamics 365 Business Central, Dynamics 365 Commerce, Dynamics 365 Finance, Dynamics 365 Project Operations, Dynamics 365 Supply Chain Management -->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal authors:

- [Rachel Profitt](https://www.linkedin.com/in/RachelProfitt/) \| Sr. FastTrack Solution Architect
- [Eric Pegors](https://www.linkedin.com/in/EricPegors/) \| FastTrack Solution Architect

Other contributors:

- [Kristi Slininger](https://www.linkedin.com/in/kristi-slininger-597218133/) \| Principal Product Manager Lead
- [Kevin Giardini](https://www.linkedin.com/in/kevin-g-7ab91238/) \| Senior Program Manager, Advanced Cloud Engineering (ACE)
