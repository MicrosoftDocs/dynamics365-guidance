---
title: Glossary of Dynamics 365 business processes terms
description: A glossary of terms that are good to know if you work with Dynamics 365 and you're reading the business process guidance.
author: rachel-profitt
ms.author: raprofit
ms.topic: glossary
ms.date: 01/15/2024
---

# Glossary of Dynamics 365 business processes terms

This article defines some of the common terms and terms that are specific to Dynamics 365 that are used in the business process guidance on Microsoft Learn. It includes guidelines such as capitalization.

In any given industry, there are terms that are industry-specific and very familiar to people in that industry or line of business. But in many languages, there are more than one term for the same task or object. For example, are the people you do business with your *clients* or your *customers*? Learn more in the following sections.

> [!TIP]
> Use CTRL+F to search for a specific term on this page.

Find generic and specific terms across Microsoft products and languages at [Microsoft Terminology Search](https://msit.powerbi.com/view?r=eyJrIjoiODJmYjU4Y2YtM2M0ZC00YzYxLWE1YTktNzFjYmYxNTAxNjQ0IiwidCI6IjcyZjk4OGJmLTg2ZjEtNDFhZi05MWFiLTJkN2NkMDExZGI0NyIsImMiOjV9).

## A

### Account structure

The term *account structure* in Dynamics 365 Finance refers to an organized list of main accounts and financial dimensions. An account structure defines the financial dimensions that are applicable to each main account. It also defines the rules that determine which combinations of main accounts and dimension values are allowed, which financial dimensions are mandatory, which are allowed to be blank, and so on. Conversely, the combinations that aren't defined in the account structure aren't allowed. Each ledger must have one or more account structures to define its valid main accounts and financial dimensions.

### Accounting Standards Codification (ASC)

The Accounting Standards Codification categorizes accounting standards into a comprehensive, consistent, and accessible framework. It's designed to make it easier for financial professionals, including accountants and auditors, to locate and apply relevant accounting rules and guidance. The ASC covers a wide range of accounting topics, including revenue recognition, financial statement presentation, leases, income taxes, and many others.

The ASC is divided into various sections, each addressing specific areas of accounting. For example, ASC 606 deals with revenue recognition, ASC 842 addresses lease accounting, and ASC 740 covers income taxes. Each section includes detailed guidance, rules, and examples related to the respective accounting topic.

Overall, the Accounting Standards Codification plays a crucial role in maintaining consistency and transparency in financial reporting and accounting practices in the United States. It serves as a comprehensive reference for professionals who need to interpret and apply accounting standards in their work.

### Accruals

[Accruals](/dynamics365/finance/general-ledger/accruals-overview) are used in accounting to track revenue that's recognized in the period that it's earned in, not when payment is received, and to track expenses (costs) that are recognized when they occur, not when payment is made.

### Acquisition cost

It encompasses all the expenses associated with acquiring the asset and making it ready for use in business operations. The asset acquisition cost includes both direct and indirect costs related to the purchase, delivery, and commissioning of the asset.

### Administer system features

System features are the backbone of Dynamics 365 functionality. Administering these features involves fine-tuning configurations, ensuring optimal alignment with evolving business processes in addition to staying up to date with Microsoft release notes and configuring new features from feature management workspace will help ensuring Dynamics 365 is optimized for your business needs. with Power Apps and customizations of Dynamics 365, administrators can tailor the system to the organization's specific requirements. This way, Dynamics 365 remains a tailored and dynamic solution that adapts seamlessly to evolving business processes.

### Adoption

The process of integrating a technology solution Dynamics 365 into the daily operations of an organization, ensuring widespread and effective use by users to achieve business objectives.

### Advanced rule

An advanced rule in Dynamics 365 Finance is a configuration that allows you to define account structure exceptions for financial dimensions that are specific to one or a few main accounts. It allows for more sophisticated workflows and decision-making based on specific conditions for the combinations of main account and financial dimensions. Advanced rules allow you to add additional financial dimensions that aren't included in the account structure to be dynamically presented to the user and control what values or attributes are collected on certain transactions.

### Aging periods

When your collection teams analyze customer balances, they typically need to group customer balances into time periods to determine how far overdue the customer is. These periods might be referred to as aging buckets or aging periods.

Before you can analyze your customer balances in Dynamics 365 Finance, you must [define aging periods](/dynamics365/finance/accounts-receivable/set-up-collections#set-up-aging-period-definitions). If your organization or users want to analyze customer balances in multiple ways, you can define multiple aging periods. The most common way to analyze customer balances is in periods of 30 days, 60 days, 90 days, and more than 180 days. However, you can define aging periods by weeks, months, or quarters as well. Most organizations use aging reports to analyze their customer balances.

> [!IMPORTANT]
> After you define aging periods, Dynamics 365 Finance requires you to run a periodic process to place customer balances into the correct periods for analyzing. Run the [Aging snapshot process](/dynamics365/finance/accounts-receivable/set-up-collections#create-an-aging-snapshot). In most organizations, this process is run once per day as part of a batch operation.

### Allocations

Allocations involve the systematic distribution of costs across different segments or departments within an organization. This process ensures that expenses are appropriately distributed, providing a more granular view of how costs impact various areas of the business.

Dynamics 365 Finance supports several types of allocations including but not limited to the following:

-   Ledger allocations – allocations that are defined directly on a main account and distributes amounts across financial dimensions.

-   Allocation rules – rules that are defined for both a source account with financial dimensions and target accounts with financial dimensions. The rules are run as a periodic process, typically once per ledger period.

-   Budget allocations – allocations that can be defined to spread a budget amount over a period of time or across main accounts and financial dimensions.

### Amortization

Unlike fixed assets, which are typically *depreciated*, intangible assets are *amortized*. Examples of intangible assets are patents, intellectual property, branding, and so on. Amortization is generally spread across the useful life of an asset in a straight line. Assets that are amortized may not have a resale value.

### Appointment scheduling

Appointment scheduling is the process of blocking time for drivers to drop off and pick up loads at the warehouse.

### Appraisers

Asset appraisers are individuals who leverage their expertise to evaluate the condition, usability, and market demand for these assets in their current state. They are usually involved in assessing the potential financial return or salvage value of assets that an organization is planning to retire, sell, scrap, or otherwise remove from its inventory.

### Appropriations

In the public sector, budget appropriation refers to the legal process by which a legislative body, such as a city council or Congress, allocates funds for specific purposes.

### Asset

An asset is something of value that an organization owns. Related definitions are [fixed asset](#fixed-asset) and [asset classification](#asset-classification).

In [service to cash documentation](service-to-cash-overview.md), the term covers a physical object that service can be performed on, regardless of the organization that owns it.

### Asset acquisition strategy

Asset acquisition strategy is the planned approach or actions that an organization implements to acquire assets to support its business objectives and improve its operations. The asset acquisition strategy includes a systematic process for identifying the types of assets needed by the organization. This can involve analyzing existing assets, conducting market research, and considering factors such as technological advancements, industry trends, and local regulatory requirements.

### Asset books

Organizations use books to track an independent financial lifecycle of an asset. Books can be configured to post associated transactions to the general ledger. They are also used for tax reporting purposes. Learn more at [Set up fixed assets (Finance)](/dynamics365/finance/fixed-assets/set-up-fixed-assets#books).

### Asset classification

Generally, you classify assets in the following buckets:

- Current or fixed
- Tangible or intangible
- Operational or nonoperational

The longevity of the asset determines whether it's a current asset or a fixed asset. The form of the asset helps differentiate tangible and intangible assets. Usage often helps tag an asset as an operational asset or a nonoperational asset.

Here are some examples of tangible assets and intangible assets:

- Physical property is typically identified as a tangible asset. Examples of tangible assets include buildings, machinery, and land. They're generally considered long-term assets in financial statements.

- Intangible assets include items that can't be touched but that have value, such as a patent, software, and goodwill.

### Asset decommissioning

Asset decommissioning refers to the process of formally retiring and stopping the use of an asset. Organizations typically initiate the decommissioning process when an asset reaches the end of its useful life or when it's no longer needed. To avoid any regulatory or compliance issues the assets should be clearly disposed of by the organization.

### Asset disposal

Asset disposal refers to the process of removing assets from an organization. This includes selling, recycling, or scrapping assets that have reached the end of life and no longer align with business goals or have become out-of-date due to technological advancements.

### Asset insurance

Fixed asset insurance is a type of insurance that covers the physical assets of a business, such as buildings, machinery, equipment, inventory, and furniture. Fixed asset insurance protects the business from losses due to fire, theft, vandalism, natural disasters, and other perils. Fixed asset insurance can help the business recover from the damage or loss of its assets and resume its normal operations. Fixed asset insurance can also cover the costs of repairing or replacing the assets, as well as the loss of income or profits due to the interruption of business activities.

### Asset lifecycle stages

Fixed Asset lifecycle stages are the phases that an asset typically goes through from the time it's acquired by a business until it's disposed of or retired. These stages include planning, acquisition, operation and maintenance, and disposal. Each stage has its own accounting, financial, and operational implications for the business. Understanding and managing the fixed asset lifecycle can help businesses optimize their asset performance, reduce costs, and comply with regulations.

- Planning: This stage involves identifying the need for a new asset, evaluating the current assets, and determining the budget and specifications for the asset. Planning also includes forecasting the expected benefits, risks, and costs of the asset over its useful life.

- Acquisition: This stage involves purchasing or leasing the asset from a supplier, installing and testing the asset, and recording its initial value and depreciation method in the accounting system.

- Operation and Maintenance: This stage involves using the asset for its intended purpose, monitoring its performance and condition, and performing regular repairs and upgrades to keep it functional. Operation and maintenance also involve tracking the asset's location, ownership, usage, and depreciation in the accounting system.

- Disposal: This stage involves retiring or selling the asset when it's no longer needed or useful for the business. Disposal also involves removing the asset from the accounting system, calculating its gain or loss on disposal, and complying with any environmental or legal requirements for disposing of the asset.

Also, in the asset management process, there are asset lifecycle states that can be set and tracked by users. These are used to define whether an asset is active or inactive.

In Dynamics 365 we have states like created, active and terminated. Learn more at [Asset lifecycle states (Supply Chain Management)](/dynamics365/supply-chain/asset-management/setup-for-objects/object-stages).

### Asset replacement 

Asset replacement refers to the process of exchanging an old asset for a new one, with the value of the old asset offsetting the cost of the new acquisition.

### Asset scrapping

Asset scrapping refers to the process of recycling salvageable components of an obsolete or non-functional asset that can no longer be used effectively. This contributes to sustainable practices by recycling materials rather than discarding them.

### Asset selling

Selling of assets that have outgrown their usefulness to the organization, to third parties who may find value in using that asset after its retirement from the organization.

### Asset tracking

Fixed asset tracking is the process of recording and monitoring the information of the assets owned by an organization. Some of the benefits of fixed asset tracking are:

- Increased efficiency and productivity: By knowing where the assets are and how they are performing, organizations can allocate them to the right tasks and projects, avoid duplication and wastage, and plan for future needs.

- Reduced expenses and losses: By tracking the depreciation and maintenance of the assets, organizations can avoid overpaying taxes and insurance, reduce repair and replacement costs, and prevent theft and damage.

- Enhanced compliance and accountability: By maintaining accurate records of the assets, organizations can comply with legal and financial requirements, audit standards, and industry best practices. They can also assign responsibility and ownership to the employees who use the assets and monitor their usage.

### Asset transfer

A fixed asset transfer is the process of moving an asset from one location, department, or owner to another within an organization. Fixed asset transfers may occur for various reasons, such as relocation, reorganization, sale, donation, or disposal. Fixed asset transfers require proper accounting and documentation to ensure that the asset's value, depreciation, and tax implications are accurately recorded and reported.

### Attribute

An attribute is a characteristic or feature (in this case, of a product) that helps define its quality, functionality, and overall value. Product attributes can include both physical and intangible characteristics, such as size, color, shape, texture, material, durability, performance, reliability, and brand reputation. Consumers often use these attributes to evaluate and compare products and make purchasing decisions. Companies also use attributes to differentiate their products from those of competitors and to communicate their unique selling proposition to customers.

Dynamics 365 Commerce and Supply Chain Management include robust product attribute capabilities. You can [define attributes](/dynamics365/commerce/attribute-attributegroups-lifecycle) for specific products, groups of products, or variants of products.

### Audit management

Audit management involves the planning, execution, and tracking of audit activities within an organization, including internal and external audits. Business applications often have modules for audit management to streamline the audit process.

### Audit trail

An audit trail is a chronological record of all transactions and activities in a business solution. It provides a complete history of changes and actions, which provides transparency and accountability to all entries that are recorded in the general ledger.

## B

### Baseline

A baseline is a fixed reference point that is used to compare project performance over time. Project managers use project baselines to understand how project scope, schedule, and cost are progressing through the completion of a project.

### Batch order

A batch order is a type of production order in Dynamics 365 that is designed for process manufacturing. It's used in conjunction with formulas to manage the creation of specific quantities of products, often in discrete batches. Batch orders streamline the production process in industries where precise control over ingredient proportions and production conditions is critical.

### Bill of materials

A bill of materials (BOM) is a comprehensive list that outlines the components, raw materials, and subassemblies that are required to manufacture a finished product. When you manage product lifecycles in Dynamics 365, the BOM serves as a foundational document that facilitates accurate planning, cost estimation, and production execution. The term *BOM* is generally used in the discrete manufacturing industry.

In Dynamics 365 Supply Chain Management, the term *BOM* is used for the list of items that are required to produce a semi-finished or finished product. Although this term is sometimes used interchangeably with the term *formula*, the two terms have two separate meanings and separate functionality.

In Dynamics 365 Business Central, the term *assembly BOM* covers scenarios where you structure parent items that must be assembled from components with little to no resource use. The term *production BOM* covers items that consist of different components and subassemblies and are produced at a work or machine center. Learn more at [Work with Bills of Material](/dynamics365/business-central/inventory-how-work-boms).

### Billable hours

Of the hours that are worked on tasks, those hours that can be charged to clients or customers are known as billable hours. Billable hours are often used for invoicing purposes and are directly related to revenue generation. Learn more at [Deliver project work](project-to-profit-deliver-project-work.md) and [Non-billable hours](#non-billable-hours).

### Billing rules

Billing rules were used in [Dynamics AX](/dynamicsax-2012/appuser-itpro/create-billing-rules). In Dynamics 365, they're replaced by [billing schedules](#billing-schedules).

### Billing schedules

[Billing schedules](/dynamics365/finance/accounts-receivable/sb-billing-schedules) are rules that define how and when customers can be invoiced for work on a project. They're based on the terms that are specified in the project contract.

### Budget control

In Dynamics 365 Finance, budget control is a set of configurations that allow organizations to closely monitor and control spend by providing warnings or errors when specific criteria is met. This functionality allows organizations to more closely plan, measure, manage and forecast its financial resources throughout the year. Learn more at [Budget control overview](/dynamics365/finance/budgeting/budget-control-overview-configuration).

### Budget cycle

A budget cycle is a configurable time period in which you can control and monitor the budget amounts. Budget cycles are used in both Budget control and Budget planning in Dynamics 365 Finance.

### Budget forecast

A budget forecast is the expected expenditure or revenue per budget line during the period that is defined on the budget line. The forecast equals the budgeted value when the budget is approved. If actual costs are more than the forecasted cost for a budget line, the forecast cost is made equal to the actual cost.

### Budget plan

In Dynamics 365 Finance, a budget plan is the outcome of the process of determining what the budget should be for a period of time. The budget plan only becomes final once it is approved and converted from a plan into an actual budget. Learn more at [Budget planning overview](/dynamics365/finance/budgeting/budget-planning-overview-configuration).

### Budget plan scenario

Budget plan scenarios, sometimes referred to as scenario planning, in Dynamics 365 Finance enables organizations to create multiple budgets based on different assumptions and variables. This feature supports better decision-making by evaluating the potential impact of various scenarios on financial outcomes.

### Budget register entry

In Dynamics 365 Finance, the budget register entry is the equivalent to a journal entry for budget amounts. Budget registers have headers and lines much like a general journal or other types of journals in the system; however, budget register entries do not post to the general ledger. Budget register entries also have different fields, rules, and logic to help with the management of budgeting tasks.

### Budget variance

Budget variance refers to the difference between the budgeted amount and the actual amount spent. In Dynamics 365, monitoring budget variances helps organizations identify discrepancies and adjust future budget plans accordingly.

### Business Continuity Plan

A comprehensive document outlining strategies and procedures for maintaining essential business functions during and after disruptions.

### Business Impact Analysis (BIA)

A systematic process for assessing the potential impact of disruptions on critical business functions, helping prioritize recovery efforts.

## C

### Campaign analytics

Campaign analytics is the process of evaluating data and metrics for a marketing campaign to derive performance insights and optimization opportunities.

### Campaign budget

A campaign budget is the defined marketing expenditure that is allocated to a specific marketing campaign.

### Capital asset budget

The capital asset budget helps an organization plan the purchase of assets that it needs for its business. Big investments in building large-scale property or deployment of assets are covered under this budget.

### Capital assets

Typically, you define [fixed assets](#fixed-asset) as capital assets when you hold them for a year or longer and assign them a [depreciation](#depreciation) profile over their lifespan. Capital assets are often [tangible assets](#asset-classification).

### Cashflow statement

It's one of the three key financial statements used by organizations to report cash and spending information. The cash flow statement, also called the statement of cash flows, is a financial statement that shows how cash flows in and out of a company over a specific period. A general cash flow statement may have two columns. Column one will list the name of the category of receipts and payments and column two will list the total amount in each period.

### Catalog

Businesses can maintain different types of product catalogs, depending on their needs and the types of products they offer. In Dynamics 365 Commerce, you can [define products](/dynamics365/commerce/set-up-retail-products) to include in catalogs, [track source codes](/dynamics365/commerce/call-center-catalogs) to understand the effectiveness of your catalogs, and [define special pricing](/dynamics365/commerce/define-channel-specific-discounts) based on a catalog or source code. Here are some common types of product catalogs:

- A **printed catalog** is a physical booklet or brochure that contains product information, descriptions, and images. It's a traditional form of product catalog that companies use to showcase their products and promote sales.

- A **digital catalog** is an electronic version of a printed catalog that can be accessed online or on a mobile device. Businesses can use a digital catalog to provide customers with an interactive and engaging shopping experience by including features such as product videos, reviews, and recommendations. In Dynamics 365 Commerce, you can design catalogs for specific channels such as businesses or consumers. You can [design the navigation](/dynamics365/commerce/customize-site-navigation) and look and feel of the site using tools in the Commerce Site Builder to create rich content for customers to find and purchase your products.

- A **dynamic catalog** is a product catalog that's generated automatically based on real-time data, such as inventory levels and pricing. Businesses can use a dynamic catalog to provide customers with up-to-date and accurate product information and pricing, which can help increase sales and improve customer satisfaction. In Dynamics 365 Commerce, you can build dynamic catalogs based on product categories and attributes to automatically [create assortments](/dynamics365/commerce/assortments) for different markets.

- A **custom catalog** is a product catalog that's tailored to meet the specific needs of a particular customer or a group of customers. It may include only the products that are relevant to the customer's industry or interests, or it may be customized with the customer's branding and messaging. With the [Business to Business (B2B) Portal](/dynamics365/commerce/catalogs-b2b-sites) capabilities of Dynamics 365 Commerce, you can design customer-specific catalogs for one or more customers.

- An **internal catalog** is a product catalog that's used by a company's internal stakeholders, such as sales teams, procurement teams, or product managers. It may include information that isn't included in customer-facing catalogs, such as product specifications and pricing. Dynamics 365 Commerce and Supply Chain Management support internal catalogs that you can use for reporting and analytical purposes. You can also create an internal procurement catalog by [importing vendor catalogs](/dynamics365/supply-chain/procurement/vendor-catalogs-import).

- A [**punchout catalog**](/dynamics365/supply-chain/procurement/use-external-catalogs-for-punchout) is a type of e-procurement solution that allows buyers or employees to access a supplier's website from Dynamics 365. In this system, users sign in to Dynamics 365 Supply Chain Management and select a supplier's punchout catalog. The punchout catalog authenticates the users and transfers them to the supplier's website. Users can browse the supplier's website, purchase items by adding them to their card, and proceed to checkout. The checkout process redirects the items and amounts back into Dynamics 365 for processing of the receipt and financials.

### Category hierarchy

A category hierarchy refers to a way of organizing and structuring products or items into a hierarchical structure, based on their characteristics, attributes, or relationships. This structure allows for efficient management, classification, and navigation of products in Dynamics 365. Typically, the category hierarchy is set up and maintained in Dynamics 365 Supply Chain Management. With [dual-write](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-home-page), you can then share the setup with other applications, such as Dynamics 365 Sales, Customer Insights, Customer Service, or Field Service.

### Centralized payments

A feature that allows organizations with multiple companies to create and manage payments by using a single company that handles all payments. This feature can help streamline the payment process by eliminating the need to enter the same payments in multiple places.

### Centralized resource allocation

For organizations that centralize the allocation of resources to projects, [project managers](#project-manager) define [resource requirements](#resource-requirement) at the project level, whereas fulfillment of those resource requirements is delegated to a [resource manager](#resource-manager). Project managers can accept or reject resources that the resource manager proposes.

### Change agent

Individuals or teams responsible for driving and facilitating change within the organization. Change agents play a key role in promoting adoption and managing change effectively.

### Change impact assessment

A systematic evaluation of how changes, such as the introduction of Dynamics 365, will impact processes, roles, and the overall structure of the organization.

### Change management

A structured approach to transitioning individuals, teams, and organizations from their current state to a desired future state, mitigating resistance to change during Dynamics 365 implementation.

### Change readiness

The state of organizational preparedness for change, assessing factors such as employee mindset, skills, and resources to gauge the likelihood of successful Dynamics 365 adoption.

### Change resistance

Opposition or reluctance to the changes introduced by Dynamics 365. Understanding and addressing resistance is crucial for successful adoption.

### Chart of accounts

A chart of accounts defines a structured list of all the main accounts used in a ledger. Each main account has a unique code and a description, and they are organized hierarchically to reflect the company's financial structure. In Dynamics 365 Finance and in Dynamics 365 Business Central, a chart of accounts can be assigned to one or more ledgers. To use a shared chart of accounts, you can create one chart of accounts and link it to multiple ledgers.

### Churn

Churn occurs when a customer ends a relationship or stops engaging with a company. Customer relationship management (CRM) helps prevent churn.

### Close the deal

Closing the deal refers to the process of finalizing the agreement with a client or decision makers after an opportunity is won. It involves confirming acceptance, negotiating terms if necessary, preparing and signing the contract, and setting up the required arrangements for the project or business.

### Closing entries

Closing entries in Dynamics 365 Finance are the automated journal entries made at the end of a financial period to transfer the balances of temporary accounts (such as revenue and expense accounts) to permanent accounts (such as retained earnings). This process resets the accounts for the next reporting cycle.

### Closing sheet

The closing sheet in Dynamics 365 is a summarized document that includes the final balances of various accounts and financial indicators after the financial period closure. It provides a snapshot of the financial status at the end of the reporting cycle. Users with proper security can make adjustments to how the balances will be transferred to the opening balances for the next period prior to posting.

### Collaborative budgeting

Collaborative budgeting in Dynamics 365 involves the collective contribution of stakeholders to the budgeting process. This fosters collaboration among budget owners, finance leaders, and departmental managers, ensuring a more comprehensive and accurate budget.

### Collection letters or dunning notes

A collection letter, or dunning note, is a document that communicates to a customer that one or more [invoices](#invoice) are past due. The document informs the customer of options to make a payment and settle the account. Some countries/regions may require collection letters to be sent prior to legal action being taken for overdue invoices.

[Dynamics 365 Finance Insights](/dynamics365/finance/finance-insights/finance-insights-home-page) helps automate the process of sending collection letters to customers. Dynamics 365 Finance can [generate and track](/dynamics365/finance/accounts-receivable/tasks/process-collection-letters) the collection letters you send.

### Collection stakeholders

Depending on its size, the complexity of your collections process, and the frequency of overdue accounts, your organization may use internal collectors, external collectors, or a combination. Together, the people in your collections team are your organization's collection stakeholders. You may want to separate their work, either internally or externally.

Dynamics 365 Finance offers a couple of ways to allocate collections tasks:

- A **collection pool** is a type of **customer pool**(/dynamics365/finance/accounts-receivable/set-up-collections#optional-set-up-customer-pools) that groups customers for collections. You can create as many collection pools as you need. A collection pool can be assigned to a specific [collection agent](/dynamics365/finance/accounts-receivable/set-up-collections#optional-set-up-collections-agents). A collection agent can also be linked directly to specific customers. A collection agent is an individual, either internal or external, who performs collection activities in your organization.
- A [**collection team**](/dynamics365/finance/accounts-receivable/set-up-collections#optional-create-a-collections-team) is a group of collection agents.

### Collections cases

During collection-related activities with your customers, you may want to track the details of the work and conversations you have with your customers. In Dynamics 365, you manage the collections process with cases.

For simple processes, you can use case management in Dynamics 365 Finance. In Finance, you must plan how you want to [classify the collections work](/dynamics365/finance/accounts-receivable/set-up-collections#set-up-a-collections-case-category). You can specify different approval processes for different types of cases.

For more complex processes, you might want to use [case management](/dynamics365/customer-service/overview-cases) in Dynamics 365 Customer Service.

You may also use a combination of both products with [dual-write](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-overview) to keep case data synchronized between Finance and Customer Service.

### Company

A company in Dynamics 365 Finance or Dynamics 365 Business Central represents an individual legal entity or business unit within an organization. Each company can have its own financial data, settings, and operations. The terms "company" and "legal entity" are used interchangeably in Dynamics 365 Finance. A company is a major data boundary in Dynamics 365 Finance where users can be assigned access to each company independently.

### Competency

Competencies in Dynamics 365 refer to the combination of skills, knowledge, and attributes that employees need to perform their roles effectively. The system enables organizations to define and assess competencies for various job positions. Competency management ensures that employees possess the necessary qualities to meet job requirements and align with organizational goals.

### Competency analysis

Competency analysis refers to the process of evaluating and assessing the skills, knowledge, and abilities that employees possess in relation to their job roles. In the context of Dynamics 365 for managing employee performance and growth, competency analysis involves identifying the specific competencies required for various positions within the organization. This analysis aids in defining clear job expectations, aligning employee skills with organizational goals, and facilitating targeted learning and development initiatives.

### Compliance controls

Compliance controls are policies, procedures, and security measures put in place to ensure that an organization's activities and processes adhere to regulatory requirements and standards.

### Compliance reporting

Compliance reporting involves the generation and submission of reports to regulatory authorities to demonstrate an organization's adherence to relevant regulations and standards. ERP systems can generate compliance reports based on stored data.

### Consume materials

Material consumption refers to the use of items in a project. You can register the consumption of items in several ways. You can sell or purchase items from a project, or reserve items for a project. You can order items from the company's inventory for consumption on a project or purchase items from an external vendor. Item consumption is recorded as a posting that registers that the item was used in the project.

### Contractor

Contractors are third-party, or external, service resources that may be used in the service delivery process but are not directly employed by the servicing organization.

### Co-products and by-products

In process manufacturing, co-products and by-products are additional terms that are associated with formulas and batch orders. Co-products are multiple products that are produced simultaneously in a single production process. By-products are secondary products that are obtained incidentally during the production of the primary item. Dynamics 365 Supply Chain Management accommodates these complexities in process manufacturing.

### Correcting entry

A correcting entry fixes a mistake that was posted in the accounting books. You must make correct journal entries as soon as you find an error. Correcting entries ensure that your financial records are accurate.

### Cost

In business and accounting, cost refers to the monetary value of resources that are consumed or sacrificed to achieve a particular objective or goal. It's the amount of money that a business spends on producing a product or providing a service. Defining the cost of products and services is essential for any organization that wants to understand and manage its finances effectively.

In Dynamics 365, costs are tracked on many types of transactions, such as work orders, production orders, sales orders, and purchase orders. The cost typically comes from the product or service definition.

Costs can be direct or indirect, fixed or variable.

- **Direct costs** are expenses that can be directly traced to a product or service, such as the cost of raw materials or labor used to produce or provide it. Direct costs are typically defined as part of the product definition.
- **Indirect costs**, also known as [**overhead costs**](#overhead-costs), are expenses that can't be directly linked to a specific product or service, such as rent, utilities, and advertising. These types of costs are defined in the costing sheet in Dynamics 365 Supply Chain Management.
- **Fixed costs** are expenses that don't vary with changes in the volume of production or sales, such as rent or salaries.
- **Variable costs** are expenses that change with changes in the volume of production or sales, such as the cost of raw materials or labor.

> [!NOTE]
> Cost can be referred to as *cost price*. If you see the term *price* by itself, it typically refers to a sales price or purchase price. In Dynamics 365 Supply Chain Management, the term *item price* is used interchangeably with *cost*.

### Cost accounting

Cost accounting is a branch of accounting that deals with the process of identifying, measuring, analyzing, and reporting costs associated with a business operation. It's a methodical approach to accounting that provides detailed information about the costs of producing goods and services.

Dynamics 365 Finance, Supply Chain Management, and Business Central all include a cost accounting module. In them, you create a secondary set of accounting books that are used to determine and report the cost of goods or services by allocating costs of specific products or services based on the resources consumed in their production or procurement. The goal is to provide accurate information that managers can use to make informed decisions about pricing, resource allocation, and process improvements.

- [Cost accounting in Finance](/dynamics365/finance/cost-accounting/cost-accounting-home-page)
- [Cost accounting in Supply Chain Management](/dynamics365/finance/cost-accounting/cost-accounting-home-page)
- [Cost accounting in Business Central](/dynamics365/business-central/finance-manage-cost-accounting)

### Cost budget

A cost budget represents a point-in-time snapshot of the estimated cost for the project. All actual costs that are incurred on the project, among time, materials, and expenses, are compared against the cost budget to track the costs on the project.

### Costing methodology

A costing methodology is a systematic approach to determining the cost of goods or services. Different methodologies can be used depending on the industry, product, or service that's being produced. Dynamics 365 Supply Chain Management supports four costing methodologies, with variations: FIFO, LIFO, weighted average, and standard.

- [**FIFO** (First In, First Out)](/dynamics365/supply-chain/cost-management/fifo-physical-value-marking): The first units produced or purchased are the first ones to be sold. Therefore, the cost of goods sold is based on the oldest inventory in stock.

- [**LIFO** (Last In, First Out)](/dynamics365/supply-chain/cost-management/lifo-physical-value-marking): The last units produced or purchased are the first ones to be sold. Therefore, the cost of goods sold is based on the newest inventory in stock.

- [**LIFO Date**](/dynamics365/supply-chain/cost-management/lifo-date-physical-value-marking): A variation of the LIFO method. Inventory is valued based on the cost of the goods that are purchased closest to the sale date.

- **Weighted Average**: This method calculates the average cost of all units produced or purchased during a specific period. It's defined slightly differently in [Supply Chain Management](/dynamics365/supply-chain/cost-management/weighted-average-physical-value-marking) and [Business Central](/dynamics365/business-central/design-details-average-cost).

- [**Weighted Average Date**](/dynamics365/supply-chain/cost-management/weighted-average-date): A variation of the weighted average method. The average cost is calculated based on inventory at a specified date.

- [**Moving Average**](/dynamics365/supply-chain/cost-management/moving-average): This method calculates the average cost of units produced or purchased during a specific period, adjusting the cost as new units are produced or purchased.

- [**Running Average**](/dynamics365/supply-chain/cost-management/running-average-cost-price): This method resembles the moving average method, but it calculates the average cost based on all costs incurred since the start of production or procurement. In Dynamics 365 Supply Chain Management, you can't select this costing method. Instead, it's applied in real time when you run the inventory closing process with the FIFO, LIFO, or Weighted Average costing methods.

- **Standard Cost**: This method sets predetermined costs for each component of a product or service, based on estimates of labor, materials, and overhead costs. The actual costs are then compared to the standard costs to identify any variations and adjust as necessary.

Dynamics 365 Business Central also supports [costing methods](/dynamics365/business-central/design-details-costing-methods).

The following diagram illustrates the effect of the FIFO, LIFO, weighted average, and standard costing methods.

:::image type="content" source="media/CostingMethodsDiagram.svg" alt-text="Diagram with boxes that illustrate how inventory is evaluated based on procurement and sales across the four costing methods." lightbox="media/CostingMethodsDiagram.svg":::

### Costing sheet

A [costing sheet](/dynamics365/supply-chain/cost-management/costing-sheets) is a document or tool that is used in [cost accounting](#cost-accounting) to calculate the total cost of a product or service. It's a comprehensive document that lists all the cost components that are involved in producing or providing the product or service. It typically includes all direct costs, such as labor and material, and indirect costs, such as overhead expenses.

### Costing version

In Dynamics 365, a [costing version](/dynamics365/supply-chain/cost-management/costing-versions) is a specific set of cost calculations that are used for tracking and analyzing the costs associated with a specific item or a group of items. A costing version represents a snapshot of the costs of materials, labor, overhead, and other expenses that are associated with producing or purchasing an item at a particular point in time.

### Credit hold

A credit hold is a process or flag that prevents a customer from placing an order on credit to reduce the risk to your business of needing to write off bad debt. Dynamics 365 offers several ways to put customer orders and [invoices](#invoice) on hold based on business rules, like [sales order holds](/dynamics365/supply-chain/sales-marketing/tasks/manage-order-holds) in Supply Chain Management, [free text invoices](/dynamics365/finance/accounts-receivable/cm-sales-order-credit-holds) in Finance, [project invoices](/dynamics365/project-operations/invoicing/post-project-invoices) in Project Operations, and [call center orders](/dynamics365/commerce/tasks/create-call-center-orders) in Commerce.

### Credit limit

A credit limit is the maximum amount of money that a customer can owe you at a given time. The balance on the customer's account determines the credit limit, but the calculation might also include the expected balance of orders that aren't yet invoiced or posted. Organizations use many techniques to determine what a credit limit should be for a customer. Dynamics 365 Finance supports this process of defining, maintaining, and evaluating a customer's balance against their [credit limit](/dynamics365/supply-chain/sales-marketing/credit-limits-customers). You can also [manage credit limits](/dynamics365/business-central/sales-how-register-new-customers#managing-credit-limits) in Business Central.

### Credit note

A credit note is a document that reduces the amount that a customer owes to a seller. It can be created and posted against an invoice for various reasons, such as returns, discounts, or corrections.

### Currency

A currency represents the type of money used for financial transactions. It can be a specific country's currency (e.g., US Dollar, Euro) and is used to denote the value of financial items. Dynamics 365 Finance ships with a predefined list of all ISO currencies. Each transaction is then recorded with three different values for the currencies.

- Transactions currency 

    The transaction currency is the currency that a specific financial transaction is recorded in. It's the currency denomination of a particular transaction.

- Accounting currency 

    The accounting currency is the primary currency in which financial statements are presented. Every transaction is translated from the transaction currency to the accounting currency for recording in the general ledger. The accounting currency is assigned in the ledger, and you can view the accounting currency amounts for all transactions in the general ledger.

- Reporting currency 

    The reporting currency is an additional currency in which financial statements can be presented. Every transaction is translated from the transaction currency to the reporting currency for recording in the general ledger. Organizations with international operations often use the reporting currency to provide financial information in a local currency. The reporting currency is assigned in the ledger, and you can view the reporting currency amounts on all transactions in the general ledger.

### Currency conversion

Currency conversion involves translating financial transactions from one currency to another based on exchange rates. When a transaction is posted in Dynamics 365 Finance, Supply Chain Management, Commerce, or Project Operations for example, the system automatically converts amounts using the specified exchange rates to ensure accurate multi-currency reporting. The system performs the conversion in real-time from the transaction currency to the accounting and reporting currencies.

### Currency policies

Currency policies refer to the rules and guidelines that govern how different currencies are managed within the organization. This includes decisions related to currency conversion rates, default currencies, currency revaluation, and currency-specific pricing strategies.

### Currency revaluation

Currency revaluation is the process of adjusting the value of assets and liabilities denominated in foreign currencies to reflect current exchange rates, which helps maintain accurate financial statements. Dynamics 365 Finance supports four types of currency revaluations:

- Accounts payable – for revaluating vendor open transactions
- Accounts receivable – for revaluating customer open transactions
- Cash and bank management – for revaluating bank balances
- General ledger – for revaluating general ledger account balances

### Customer credit group

A [customer credit group](/dynamics365/finance/accounts-receivable/cm-customer-credit-groups) is a group of customers that have a shared credit limit. The individual credit limit on a customer invoice account is also considered. You can select members of a customer credit group from different legal entities. When you decide how to structure your customer accounts, consider how credit limits are managed. For example, a customer account can have only one credit limit. If a customer account has many delivery addresses that each require a different credit limit, consider whether they should be separate customer accounts. Then you can use a customer credit group to create an overall credit limit across the customer's accounts.

### Customer journey

Customer journey refers to the end-to-end experiences and touchpoints that a customer has with a brand. Customer relationship management (CRM) optimizes journeys.

### Customer lifetime value (CLV)

Customer lifetime value (CLV) is the total revenue that is generated from a customer over the entire relationship timeline. Maximizing CLV is key.

### Customer relationship management (CRM)

Customer relationship management (CRM) involves strategies and processes for managing customer interactions and data across the customer lifecycle to maximize loyalty and growth.

### Customer satisfaction (CSAT)

Customer satisfaction (CSAT) refers to metrics that measure a customer's happiness with a company's products, services, and interactions.

## D

### Date effectivity

For some records, you can specify changes that take effect after a specific date. Job classification, compensation, position, and worker assignments are examples of date-effective records.

### Date intervals

Date intervals define specific time spans used in financial reporting and analysis. Examples include fiscal years, quarters, months, and custom date ranges that help organize and analyze financial data. In Dynamics 365 applications you can use date intervals to run a report with a dynamic date range.

### Deferrals

Deferrals are used in accounting to track revenue that's received but not yet earned, also known as unearned revenue. Organizations use deferrals to recognize revenue before expenses (costs) occur. You can [recognize deferred revenue in Dynamics 365 Finance](/dynamics365/finance/accounts-receivable/revenue-recognition-recognize-deferred-revenue) and [defer revenues and expenses in Dynamics 365 Business Central](/dynamics365/business-central/finance-how-defer-revenue-expenses).

### Define business continuity plan

Crafting a robust business continuity plan ensures that organizations can weather disruptions effectively, safeguarding critical operations and data integrity in the face of unforeseen events. The process of defining a Business Continuity Plan (BCP) under *administer to operate* involves establishing a comprehensive strategy to ensure the organization's resilience in the face of disruptions. Dynamics 365 facilitates this process by providing tools for data backup, disaster recovery, and failover mechanisms. Through features like Azure Site Recovery and Azure Backup, organizations can define and implement robust BCPs, ensuring the continuity of critical operations during unforeseen events.

### Deliverables

Deliverables are all outputs of a project, as defined by the [scope](#scope). Deliverables can be a product, a service, or a capability.

### Departments

Departments are operating units that represent a functional area of a business or an organization, such as sales, accounting, or human resources. A department is used to report on functional areas. It might have profit and loss responsibility, and it might include a group of cost centers. Positions can be assigned to departments. Departments are often defined as part of an organizational hierarchy.

### Departments, jobs, and positions

[Departments, jobs, and positions](/dynamics365/human-resources/hr-personnel-departments-jobs-positions) are organizational elements that are foundational to the [*hire to retire* business process](/dynamics365/guidance/business-processes/hire-to-retire-overview).

- **Departments** are operating units that represent a functional area of a business or an organization, such as sales, accounting, or human resources. A department is used to report on functional areas. It might have profit and loss responsibility, and it might include a group of cost centers. Positions can be assigned to departments. Departments are often defined as part of an organizational hierarchy.

- **Jobs** are collections of tasks and responsibilities that are required of a person who performs a job. Areas of responsibility, tasks, functions, skills, education information, and certificates that are required for a job are also required for positions that are associated with a job. Before you can create jobs, you should set up some reference information, such as job titles, functions, and types. Having these default values available saves you time when you add positions to the job. You can also set up eligibility and use it to filter compensation plans to a specific job.

- **Positions** are individual instances of a job. Positions are an important element of the lower level of an organization hierarchy. For example, the "Sales manager (East)" position is just one of the positions that's associated with the "Sales manager" job. Positions exist in a department and are assigned to workers. Every position has a length of time that it's effective for.

### Depreciation

Depreciation is a key accounting concept that allocates the cost of an asset over its estimated lifespan. Depreciation periodically reduces the value of an asset in a financial statement to reflect the gradual wear and tear, undesirability, or loss of value that occurs over time. Commonly used depreciation methods include straight-line service life, reducing (or declining) balance, and manual.

- **Straight-line service life**: A fixed asset is depreciated by the same amount each year.

- **Reducing balance** or **declining balance**: An asset is depreciated by the same percentage in each depreciation period.

- **Manual**: You enter the percentage depreciation for each interval in the calendar year.

Fixed asset depreciation methods and conventions are handled slightly differently in Dynamics 365 Finance and Dynamics 365 Business Central. Learn more at [Fixed asset depreciation conventions (Finance)](/dynamics365/finance/fixed-assets/fixed-asset-depreciation-conventions) and [Depreciation methods for fixed assets (Business Central)](/dynamics365/business-central/fa-depreciation-methods).

### Disaster Recovery Plan (DRP)

A detailed plan focused on recovering critical systems and data in the aftermath of a disaster.

### Direct expenses 

Direct expenses are those that are directly tied to the project itself such as specialized software, travel and meal expenses, mileage, and per-diem.

### Discounts

A discount is a term used to encompass the concept of reduction in the standard price offered to customers or received from vendors under specific conditions. Various types of discounts, such as percentage discounts, fixed amount discounts, or tiered discounts, can be configured when you use Dynamics 365 applications. Dynamics 365 provides a flexible framework for managing discounts, allowing organizations to tailor their pricing strategies to meet diverse customer needs and market conditions.

### Discount concurrency

Discount concurrency in Dynamics 365 Commerce refers to the capability to apply multiple discounts simultaneously to a transaction. This concept allows organizations to implement complex pricing strategies by combining various discounts, such as volume discounts and promotional discounts, ensuring flexibility and granularity in discount application.

### Discount eligibility

Discount eligibility refers to the criteria and conditions that determine whether a customer qualifies for a discount on services. In Dynamics 365 for managing pricing, discount eligibility is often configured based on factors such as customer loyalty, volume of products or services, or specific promotional campaigns. Establishing clear rules for discount eligibility ensures consistency and transparency in applying discounts to different customer segments.

### Dock management

Dock management is the process of assigning loads to dock doors in a warehouse. In Dynamics 365 Supply Chain Management, you manage docks by using the [driver check-in/check-out](/dynamics365/supply-chain/transportation/tasks/register-driver-check-check-out-appointment) functions.

### Dual currency

Dual currency refers to the ability of Dynamics 365 Finance to manage and report financial data in two currencies simultaneously. It allows organizations to maintain records in both their accounting or base currency and a reporting or secondary currency.

### DUNS numbers

The Data Universal Number System (DUNS) identifies companies in dozens of countries/regions with a unique nine-digit number. The number is issued by Dun & Bradstreet, a provider of commercial data, analytics, and insights for businesses.

You can specify the DUNS number on a customer record in Dynamics 365 Finance. You can use APIs provided with Finance to build integrations with Dun & Bradstreet for your specific business requirements. If you use Dynamics 365 Customer Insights, you can [enrich company profiles with Dun & Bradstreet data](/dynamics365/customer-insights/enrichment-dnb) using a native integration.

### Dynamics 365 Implementation Guide

A comprehensive resource providing guidance on planning, configuring, and deploying Dynamics 365, including insights into best practices for training, adoption, and change management. Learn more at [Dynamics 365 implementation guide](../implementation-guide/overview.md)

## E

### Eligibility criteria

Eligibility criteria refer to the specific conditions or requirements that must be met for a transaction or activity to qualify for a vendor rebate. In Dynamics 365, configuring eligibility criteria is essential to precisely define the circumstances under which incentives will be applied, ensuring accuracy and alignment with business objectives.

### Employee succession planning

Employee succession planning is a strategic process that involves identifying and developing potential candidates to fill key roles within the organization in the future. This proactive approach ensures a smooth transition in leadership positions and critical roles, minimizing disruptions to business operations. In the context of Dynamics 365, succession planning involves creating talent pools, assessing employee readiness, and implementing development plans to groom individuals for future responsibilities.

### Encumbrance accounting

Encumbrance accounting, also referred to as commitment accounting, is a type of accounting that involves setting aside funds for future expenses.

### End-user training

Training programs designed for individuals who will use Dynamics 365 in their daily tasks, ensuring they acquire the necessary skills to navigate the system and perform their roles effectively.

### Engineering change management (ECM)

Engineering change management (ECM) is the process of making sure that changes to a product's design or engineering specifications are properly reviewed, approved, and implemented in a controlled and consistent manner. ECM helps maintain product quality, reduce the risk of errors, and minimize the impact of changes on production schedules and costs.

Dynamics 365 Supply Chain Management includes an [engineering change management](/dynamics365/supply-chain/engineering-change-management/product-engineering-overview) module.

### Estimation to complete

Estimation to complete is an estimation of the funds that are required to complete the remaining work of a project. The project manager tracks this measure along a project to determine the expected remaining cost of completing that project.

### Exchange rate

An exchange rate is the value of one currency in terms of another currency. It represents the rate at which one currency can be converted into another currency and is used to perform currency conversions in financial transactions. Dynamics 365 Finance supports the ability to define an unlimited number of exchange rates which convert from one currency to another on a specific day. You can also use fixed exchange rates on a variety of transactions such as purchase orders, sales orders, and journals to force the entry to use an exchange rate you supply rather than looking it up.

### Exchange rate types

Exchange rate types define a group of exchange rates that are obtained for currency conversion. Common rate types include spot rates, average rates, and historical rates. Default exchange rate types can be configured on the Ledger in each legal entity in Dynamics 365 Finance. Some processes allow you to select the exchange rate type that should be used for the process instead of using the default value for the ledger.

### Executive sponsorship

Leadership support and involvement from top-level executives in driving the Dynamics 365 implementation, emphasizing the importance of training and adoption throughout the organization.

### Expense policies

An expense policy is a formal set of guidelines that clearly outlines what constitutes an approved expense and what doesn't. This helps employees decide what they will be able to expense on the project.

## F

### Financial dimensions

Financial dimensions are attributes or categorizations that you can assign to transactions and main accounts to provide additional information for reporting and analysis. Examples include departments, projects, cost centers, and locations. Dynamics 365 Finance supports up to eleven dimensions in the account structure. Dimensions are assigned to a legal entity by the account structures that are associated with the ledger. Additional financial dimensions can be added through advanced rules, or you can leverage financial tags for additional attributes or categorization. Like the chart of accounts, dimensions are global and can be linked to multiple ledgers.

Financial dimensions are configured and maintained in Dynamics 365 Finance, but they can be specified on transactions in Supply Chain Management, Human Resources, Project Operations, and Commerce.

### Financial periods

Financial periods represent specific time intervals, such as months or quarters, in which financial transactions are recorded. The opening and closing of financial periods are managed to ensure accurate reporting. You can define an unlimited number of fiscal calendars in Dynamics 365 Finance and a fiscal calendar can be used by a single ledger or shared by multiple ledgers.

- Fiscal calendar

    A fiscal calendar is a predefined time structure used for organizing financial activities, reporting periods, and budgeting cycles. In Dynamics 365 Finance, it determines the start and end dates of fiscal years, quarters, and periods for financial reporting purposes. The fiscal calendar helps align financial data with an organization's specific accounting practices and business needs. A fiscal calendar may be based on a calendar year (January through December) or a dynamic range that crosses a calendar year.

- Ledger calendar

    The ledger calendar contains the ledger-specific settings for the periods within the fiscal year for each ledger assigned to the fiscal calendar. Within Dynamics 365 Finance, the same period can be open for one ledger and on hold for another ledger. These controls allow you to manage the entire period, specific modules, or the users that can post to the period and module.

### Financial reporting

Financial reporting involves the preparation and presentation of an organization's financial information, including income statements, balance sheets, and cash flow statements, typically following accounting standards and regulatory requirements.

### Financial statements

Financial statements include the balance sheet, income statement, and cash flow statement, summarizing an organization's financial performance. Dynamics 365 Finance and Business Central help organizations make sure that these statements are accurate and reflective of the closed financial period.

### Financial tags

Financial tags are values assigned to transactions and the corresponding accounting entries to categorize them for reporting and analysis purposes. They serve as an alternative to financial dimensions by providing additional insights into the nature of financial activities, without the structure of financial dimensions. Dynamics 365 Finance supports up to twenty user-defined tags to be used on any transactions. The values that are entered on the transactions are carried to the general ledger when each voucher is posted.

### Finished good

Finished goods are products that are in their final state and ready to be sold. Their final state is often the result of completing a production process. In some cases, companies may buy finished goods to resell.

A finished good is often referred to as a product. In Dynamics 365 Supply Chain Management, a [product](/dynamics365/supply-chain/pim/product-information) can also encompass raw materials and subassemblies.

### Fixed asset

In accounting, a fixed asset is any long-term asset whose cost expiration is recognized over more than one year. Related definitions are [Asset](#asset) and [Asset classification](#asset-classification).

### Fixed-price projects

Projects can be invoiced on either a fixed-price basis or a [time-and-material](#time-and-material-projects) basis. For a fixed-price project, the customer invoice amount is based on [billing schedules](#billing-schedules). Fixed-price projects can be invoiced per project or per project contract. Revenue for a fixed-price project can be calculated and posted throughout the project by using the completed percentage method. Alternatively, revenue can be calculated and posted when the project is completed, by using the completed contract method. Companies can often benefit from using the value of the work in process (WIP) to calculate the degree of completion of a project or a group of projects.

Learn more at [Manage project financials overview](project-to-profit-manage-project-financials-overview.md).

### Flex groups

Flexible working hours let companies minimize payments for overtime by offering workers extra time off during periods when the workload is low. This feature is relevant, for example, in segments that experience seasonal changes in workload. In Dynamics 365 Supply Chain Management flexible working hours are supported with a concept called Flex groups. One or more Flex groups can be created and assigned to different workers to allow for flexible time calculations. Learn more at [Flex groups](/dynamics365/supply-chain/production-control/time-attendance-flex-groups).

### Forecast

A forecast is a prediction about the future. Forecasts are expected to be incorrect to a certain degree. However, to be useful, they should be as accurate as possible. Sometimes forecasts are created based on statistical calculations. In other cases, they're manually created based on shared information; for example, information that's incorporated from a customer forecast. Companies often create different kinds of forecasts as part of their long-term planning cycles.

- **Supply forecasts** predict the supply or inventory that an organization expects to need during some future period. Typically, they're based on the demand forecast, current demand, or vendor contracts. Supply forecasts can be used for budgeting purposes and to compile information about expected purchases to share with suppliers. Organizations can set up [master plans with supply forecasts](/dynamics365/supply-chain/master-planning/planning-optimization/supply-forecast).

- [**Demand forecasts**](/dynamics365/supply-chain/master-planning/introduction-demand-forecasting) predict future needs to drive inventory replenishment activities and inform decisions in the strategic and operational planning process. Typically, they're based on historical transaction data.

- **Revenue forecasts** predict the revenue that a company will make by some future date. Typically, they're based on historical information and parameters that are specific to the industry and the domain in which the organization operates. They support organizations in making budget decisions, understanding the impact of new products and services on revenue, and setting departmental targets.

- **Budget forecasts** predict future business expenditures and revenue. Typically, they're based on the organization's current financial performance and where the industry is trending in the business domain.

- **Position forecasts** predict expenses related to workers. They help organizations to plan for those expenses and to include them in the planning of budgets. [Position forecasting](/dynamics365/finance/budgeting/position-forecasting) uses three main components to provide accurate budget amounts for position expenses:

    - Forecast position; for example, all costs that are related to a single position

    - Budget cost element; for example, base pay, employer-paid health insurance, and cell phone allowances

    - Composition group; for example, a compensation grid of pay rates

- **Expense forecasts** help organizations to plan for business expenses and to determine key costs to be considered by finance stakeholders. Typically, they're based on revenue, headcount, and similar factors.

- **Sales forecasts** predict future sales and revenue expected over a period of time. Typically, they're based on domain trends and historical data. [Sales forecasts](/dynamics365/sales/configure-forecast) are often more subjective than demand forecasts and are often used to drive sales targets.

- **Customer forecasts** represent demand information that customers provide. Often customers choose to share their expected consumption with organizations to support better planning operations or a shorter lead time. Organizations can use customer forecasts to allocate inventory or to hold customers to an agreed number of purchases over a period of time.

- **Labor or resource forecasts** predict an organization's labor needs. Typically, they're based on historical data and domain and industry trends.

### Forecast accuracy: Mean Absolute Percentage Error (MAPE)

The mean absolute percentage error (MAPE) is an industry standard indicator that's used to evaluate the expected accuracy of an Azure Machine Learning forecasting model. The MAPE calculation compares the actual value versus the forecasted value for each data point to find the average difference between the two data series as an absolute value.

In the following diagram, the chart on the left shows the data that was used to determine the forecast model. In the chart on the right, the purple line at the top, labeled "Actual (At)," shows the actual data from the test data set. The light blue line below it, labeled "Forecast (Ft)," shows the model's prediction. The red arrows between the two lines indicate the MAPE value, a measure of how close the forecast is to the actual data&mdash;that is, how accurate the forecast model is.

The equation for calculating MAPE is included at the bottom of the graphic. *A<sub>t</sub>* is the actual value and *F<sub>t</sub>* is the forecast value. The absolute value in this ratio is summed for every forecasted point in the dataset and divided by the number of fitted points *n*.

MAPE is expressed as a percentage, as indicated in the equation in the diagram. The lower the MAPE value is, the more accurate the forecast is likely to be. In general, a MAPE of 20 percent or less is considered acceptable, but 10 percent would be even better. The best MAPE value that an organization can achieve is going to be dependent on the amount of historical data and how volatile the values are.

:::image type="content" source="media/forecast-accuracy-MAPE-calculation.png" alt-text="Charts that illustrate how MAPE is calculated." lightbox="media/forecast-accuracy-MAPE-calculation.png":::

### Forecast dimensions

The attributes that are included when Azure Machine Learning generates a forecast are called dimensions. **Company**, **Site**, and **Allocation key** are mandatory dimensions. If a more detailed forecast is required, the model can include the dimensions **Country/region**, **State**, **Customer group**, **Customer account**, **Warehouse**, **Inventory status**, and **Item number and dimensions**.

### Formula

In the context of process manufacturing in Dynamics 365, a formula is an industry-specific equivalent to a bill of materials (BOM). It defines the precise combination and proportions of ingredients or components that are required to produce a batch of a specific product. Formulas are used with batch orders. They provide detailed instructions for producing items in industries such as chemicals, pharmaceuticals, and food processing.

### Free text invoice

A [free text invoice](/dynamics365/finance/accounts-receivable/create-free-text-invoice-new) is an [invoice](#invoice) that isn't based on a sales order. Instead, you create a free text invoice manually. You can't enter an item number on this kind of invoice, but it can include free-text descriptions, sales amounts, and sales tax if appropriate. Assign a main account for each invoice line. To distribute the amounts to multiple ledger accounts, select the **Distribute amounts** action on the invoice. The customer balance is posted to the summary account from the posting profile that's used for the invoice.

### Freight reconciliation

Freight reconciliation is the process of comparing and reconciling freight bills (estimated charges) with carrier invoices (actual charges). You can [manually manage the process](/dynamics365/supply-chain/transportation/tasks/set-up-automatic-freight-reconciliation) in the **Transportation management** module in Dynamics 365 Supply Chain Management. Alternatively, you can set up integration with a service to automatically manage freight reconciliation.

### Frontline worker

The term *frontline worker* refers to employees who directly interact with customers, clients, or business users in various industries or sectors. Frontline workers are often at the forefront of delivering products, services, or support to customers, and they play a vital role in representing the organization and maintaining customer satisfaction.

### Funding source

A funding source is the entity that [funds work on a project contract](/dynamics365/project-operations/prod-pma/project-contracts#funding-for-project-contracts). This entity can be an internal organization or an external invoice account (customer or grant).

### Funds

A self-balancing set of financial books that is used to control and monitor the planned use of resources, often in compliance with legal and administrative requirements.

## G

### General ledger

A general ledger (GL) is a central repository in an accounting system that contains all the financial transactions and balances of an organization. It's a fundamental part of the double-entry accounting system and serves as a record of the company's financial activities over time. The general ledger is organized into various accounts, each representing a different aspect of the organization's financial operations. In Dynamics 365 Finance, the general ledger is a module that contains all the setup, configuration, data, period closing tasks, reports, and so on that are related to the general ledger.

### Goal

In the context of Dynamics 365, a goal represents a specific, measurable, and time-bound objective set for an individual or team within the organization. Goals align with broader organizational objectives and contribute to the overall success of the business. Dynamics 365 allows for the creation, tracking, and monitoring of goals, providing a structured approach to goal management and fostering a results-oriented culture.

### Goal alignment

Goal alignment in the context of employee performance management refers to the process of ensuring that individual and team goals are directly connected to the broader organizational objectives. This concept involves cascading organizational goals down to individual employees, creating a cohesive framework where every employee's efforts contribute to the achievement of overarching business goals. Goal alignment enhances organizational focus, efficiency, and the overall impact of employee contributions.

### Granularity attribute

A granularity attribute is the unique combination of [dimension values](#forecast-dimensions) that represents the level of detail at which a [forecast](#forecast) is generated.

## H

### High Availability (HA)

A measure of a system's ability to remain operational and accessible with minimal downtime, often achieved through redundancy and failover mechanisms.

### HIPAA (Health Insurance Portability and Accountability Act)

HIPAA is a U.S. federal law that establishes data privacy and security requirements for protected health information (PHI) and governs healthcare providers' and organizations' compliance.

## I

### Incentive programs

In the context of vendor rebates and incentives, incentive programs are structured schemes or agreements established between the organization and vendors. These programs outline the terms, conditions, and criteria for providing incentives, such as volume-based discounts or promotional offerings. Dynamics 365 allows users to define and manage these programs to optimize collaboration with vendors.

### Incident response

Coordinated actions taken to manage and mitigate the impact of incidents, often guided by the Business Continuity Plan.

### Income statement

The income statement, also known as the profit and loss statement, details an organization's revenues, expenses, and profits or losses over a specific period. It plays a crucial role in financial reporting and decision-making.

### Index revaluation

Organizations use indexation to adjust multiple fixed asset values. Revaluation of fixed assets can consist of appreciations, write-downs, or adjustments in value of assets. Some companies may revalue assets more often than others. The purpose of revaluation is to accurately reflect the fair market price of the asset.

### Indirect costs

Indirect costs are expenses that aren't related to production or manufacturing, such as the salaries of administrative employees and the cost of advertising. Contrast with [overhead costs](#overhead-costs).

### Indirect expenses

Indirect expenses are those that aren't directly tied to the project but may be distributed across multiple projects. Examples include administrative costs, support staff, rental fees, and utility costs.

### Intercompany expenses

A worker who is employed by one legal entity in an organization might perform work for another legal entity in the same organization. You can use intercompany expenses to assign the worker's expenses to the legal entity for which the work was performed. The legal entity that employs the worker is called the loaning legal entity. The legal entity for which the worker incurs expenses is called the borrowing legal entity.

### Interest notes

Many organizations charge a fee to customers for late payment of [invoices](#invoice). An interest note is a statement of such a fee. Charging interest helps businesses offset the cost of collecting overdue invoices while encouraging customers to pay their invoices in a timely manner. Depending on the country/region and the industry, customers who don't pay for products or services they received can face legal consequences.

Dynamics 365 Finance automates the [process of calculating and collecting interest](/dynamics365/finance/accounts-receivable/tasks/process-interest) on overdue payments. Organizations can use case management in Dynamics 365 Finance and Customer Service to help manage the legal escalation of overdue invoices.

### Internal controls

Internal controls are processes and mechanisms implemented within an organization to safeguard assets, ensure accurate financial reporting, and ensure compliance with policies and regulations.

### International Accounting Standards Board (IASB) 

The International Accounting Standards Board (IASB) is an independent, private-sector body based in London, United Kingdom. Its primary responsibility is to develop and promulgate International Financial Reporting Standards (IFRS), a set of accounting standards used by companies and organizations worldwide for the preparation and presentation of financial statements.

### International Financial Reporting Standards (IFRS)

IFRS is a set of accounting standards developed by the International Accounting Standards Board (IASB). These standards are widely used in Europe and many other parts of the world for the preparation and presentation of financial statements.

IFRS aims to harmonize accounting practices and provide a common financial reporting framework for businesses operating in different countries. While individual European countries may have their own national accounting standards, many European Union member states have adopted IFRS for the consolidated financial statements of publicly traded companies, particularly for companies listed on European stock exchanges. This adoption of IFRS helps facilitate cross-border comparisons and international investment.

> [!NOTE]
> While IFRS is commonly used in Europe, there may still be some variations or country-specific requirements in accounting and reporting practices in individual European countries. However, for consolidated financial statements of publicly traded companies, IFRS is often the standard used for reporting.

### Internet of Things sensors

The Internet of Things (IoT) is a system of devices that connect and exchange data through a communication network. Sensors on or in the connected devices relay data&mdash;like an internal temperature or the number of items that pass by a point on a production line&mdash;to a monitoring system. Dynamics 365 Supply Chain Management supports connection with IoT sensors through the [**Sensor Data Intelligence Add-In**](/dynamics365/supply-chain/sensor-data-intelligence/sdi-home-page).

### Inventory dimensions

The attributes that Dynamics 365 Supply Chain Management uses to categorize, track, and manage the movement of items in inventory are called inventory dimensions. Organizations can use them to track inventory levels more accurately and efficiently, helping reduce waste and spoilage and optimize inventory levels to meet customer demand.

The following inventory dimensions are most often used in Dynamics 365:

- **Site**: The physical location where the item is stored or will be received

- **Warehouse**: The location in the site where the item is stored

- **Location**: The location in the warehouse where the item is stored, such as a bin or pallet

- **Batch number**: A unique number that identifies a group of items produced together in the same batch

- **Serial number**: A unique number that identifies individual items in a batch or shipment

- [**Product dimension**](/dynamics365/supply-chain/pim/product-dimensions): A customizable attribute for categorizing inventory items by size, color, style, and so on

### Inventory turnover

Inventory turnover is a key performance indicator (KPI) that measures the number of times that inventory is sold or used during a specific period. In the context of product lifecycle management in Dynamics 365, an understanding of inventory turnover helps optimize stock levels, reduce holding costs, and ensure efficient supply chain operations.

### Invoice

An invoice is a document that details one or more transactions between a seller and a buyer. Invoices typically include a line item for each transaction that shows the date, amount, description, and payment terms of the transaction. [An invoice is issued](/dynamics365/finance/accounts-receivable/configure-customer-invoices) to collect payments from customers.

Dynamics 365 Business Central has parallel processes for [sales invoices](/dynamics365/business-central/sales-how-invoice-sales) and [purchase invoices](/dynamics365/business-central/purchasing-how-record-purchases).

### Invoice payment terms

Invoice payment terms are the conditions that specify when and how a customer should pay an invoice. They can include incentives for early payment or penalties for late payment. Common payment terms include the following examples:

- **Net 30**: The full amount is due within 30 days of the invoice date.

- **2/10 Net 30**: The seller offers a 2 percent discount if the buyer pays in full within 10 days of the invoice date. Otherwise, the full amount is due within 30 days of the invoice date.

- **Cash on delivery**: The full amount is due, in cash, when the buyer receives the product or service.

- **End of month**: The full amount is due by the end of the invoice month.

### Item

In the context of inventory management, an item is a specific tangible product or component that a business tracks as part of its inventory. An item can be a physical product that's sold to customers, such as a piece of clothing or a computer, or it can be a raw material or component that's used to manufacture products.

An item is typically assigned a unique identifier, such as a SKU (stockkeeping unit) or part number, which is used to track inventory levels and sales activity. Organizations also store [information about items](/dynamics365/supply-chain/pim/product-information) like description, cost, price, and supplier.

Organizations that use Dynamics 365 Business Central can [register new items](/dynamics365/business-central/inventory-how-register-new-items).

## J

### Jobs

A job is a collection of tasks and responsibilities. In Dynamics 365, areas of responsibility, tasks, functions, skills, and educational or certification requirements for a job are also required for [positions](#positions) that are associated with that job. Before you create jobs, you should set up some reference information, such as job titles, functions, and types. Having this information available saves you time when you add positions to the job. You can also set up eligibility to filter compensation plans for a specific job.

### Journal

The term *journal* is used throughout Dynamics 365 for many types of transactions. Journals can be used to post transactions into ledgers and subledgers. In Dynamics 365 Finance, Supply Chain Management, Project Operations, Commerce, and Business Central, journals always have a header and line. The header defines the type of transaction, such as counting journal to count inventory items, or a general journal batch to record financial transactions in the general ledger. The lines of the journal define the details of the transactions, including the amounts, and so on. For example, a counting journal includes lines for each item that is being counted in the inventory, and it has fields to indicate which location is being counted. The quantity fields indicate how many items are counted, and the system automatically records the cost adjustment of the counted inventory up or down based on the number of items counted. Similarly, a general journal has lines for each account and financial dimension combination being posted to which columns for the debit and credit amounts.

Learn more at [Work with general journals - Business Central](/dynamics365/business-central/ui-work-general-journals) and [General journal postings - Finance](/dynamics365/finance/general-ledger/general-journal-processing), respectively.

### Journal entries

Journal entries are the primary means of recording financial transactions in Dynamics 365. These entries capture the movement of money, assets, or liabilities and serve as the foundation for maintaining accurate and up-to-date financial records.

## K

### Key entities

In Dynamics 365 Customer Insights and Sales, key entities are the most important types of information to [track and manage](#lead-and-opportunity-management) throughout the [sales process](#sales-process-and-stages).

- [**Leads**](#lead) are potential customers, people who have shown interest in your products or services but haven't been [qualified](#lead-and-opportunity-management) as a viable prospect.

- An [**opportunity**](#opportunity) is a qualified lead, a potential customer who has a higher likelihood of making a purchase, and who requires further engagement and nurturing by the sales team.

- **Accounts** are the organizations that you do business with or plan to do business with. They typically represent a customer or potential customer.

- **Contacts** are the individual people who are associated with an account, such as decision-makers, influencers, or users of your products or services.

## L

### Lead

A lead is a potential customer, a person who has shown interest in a product or service but hasn't purchased yet. A *marketing-qualified lead* (MQL) is a lead that Marketing has deemed viable, based on activity, demographics, and so on. It was determined to match the target customer profile and to be sales-ready, based on campaign interactions. A *sales-qualified lead* is a lead that Sales has vetted and found to fit the ideal customer profile and to be ready for contact. Learn more at [Identify and qualify leads overview](prospect-to-quote-identify-qualify-leads.md).

### Lead and opportunity management

Tracking and managing potential customers and sales opportunities throughout the [sales process](#sales-process-and-stages), from initial contact to closing the deal, is called [lead and opportunity](#key-entities) management. It involves three processes:

- **Lead scoring** is a system for ranking leads based on their likelihood of making a purchase. It uses criteria such as engagement, demographics, and behavior. Lead scores help sales teams prioritize their efforts on the most promising prospects.

- **Lead qualification** is the process of determining whether a lead has the potential to become a customer. It's based on such factors as level of interest, budget, and purchasing authority.

- **Opportunity management** is the practice of guiding and nurturing qualified leads through the sales process, with the goal of converting them to customers by addressing their needs, concerns, and objections.

### Lead conversion

Lead conversion is the act of transitioning a qualified lead into a sales pipeline opportunity.

### Lead enrichment

Lead enrichment is the process of augmenting lead records with additional data from various sources.

### Lead nurturing

Lead nurturing refers to ongoing communication with leads to develop awareness and interest over time.

### Lead score

The lead score is a numeric rating that is assigned to a lead to indicate sales readiness. It's based on engagement, profile fit, and so on.

### Learning path

A learning path in outlines a structured and personalized journey for an employee's skill development and career growth. It involves a sequence of courses, training modules, and experiences designed to enhance specific competencies and align with career goals. Learning paths support employees in acquiring new skills, staying current with industry trends, and progressing along defined career trajectories. The system facilitates the tracking of individual learning paths, providing insights for both employees and managers to monitor progress and make informed decisions.

### Lease contracts

A lease contract is a legal document that describes the terms under which the owner of an asset (the lessor) agrees to let a user (the lessee) use the asset. The lessee, in turn, agrees to uphold the terms. 

Dynamics 365 Finance offers [asset leasing](/dynamics365/finance/asset-leasing/asset-leasing-homepage) capabilities that comply with international accounting standards (IFRS 16) and US GAAP standards (ASC 842).

### Lease payment schedule

A lease payment schedule is the predetermined timeline and structure for making lease payments under a lease agreement. It summarizes the specific amounts and timing of the payments that the lessee is obligated to pay to the lessor throughout the lease term.

### Leased assets

Leased assets are [assets](#asset) that a [lessor](#lessor) allows a lessee to use according to terms that both parties agree to. They differ from owned assets in that the user doesn't purchase the asset outright but is merely "renting" it. A leased asset can be a house, an apartment, or a piece of equipment.

### Leave and absence plan

When you use Dynamics 365 Human Resources you must create a leave and absence plan for each type of leave you offer. Leave and absence plans can accrue at different frequencies, such as annually, monthly, or semimonthly. You can also define a plan as a grant, where a single accrual occurs on a specific date. Learn more at [Create a leave and absence plan](/dynamics365/human-resources/hr-leave-and-absence-plans).

### Leave and absence types

Leave types in Dynamics 365 Human Resources define the types of absences that employees can report. You can tailor leave types according to the needs of your organization. Learn more at [Configure leave and absence types](/dynamics365/human-resources/hr-leave-and-absence-types).

### Ledger

A ledger is a financial record-keeping system that contains the chart of accounts, account structures, calendars, and currencies used to classify and summarize financial transactions. In Dynamics 365 Finance, you create a ledger for each legal entity.

### Ledger postings

Ledger postings involve the process of updating the general ledger with transactional data. In Dynamics 365 Finance, this ensures that all financial activities are accurately reflected in the central accounting system, providing a consolidated view of an organization's financial health.

### Legal entity

A legal entity is a separate entity recognized by the law, capable of entering contracts and engaging in business activities. It typically consists of owners/shareholders, management, assets, liabilities, and a distinct legal structure. 

In Dynamics 365 Finance, each legal entity is associated with a separate set of financial records and settings. The term legal entity and company are used interchangeably in Finance, Supply Chain Management, Commerce, Human Resources, and Project Operations.

### Lessee

A lessee is an individual or entity that has a lease agreement with a lessor to obtain the right to use or lease an asset. The lessee has the temporary right to use the assets in exchange for periodic payments.

### Lessor

A lessor is an individual or entity that owns an asset and grants the right to use or lease that asset to another party in exchange for rental payments. In leasing agreements, the lessor is the party that maintains ownership of the asset while allowing the lessee to use it for an agreed duration.

### Load

A load is a physical shipping container, such as a truck or a trailer, that can contain one or more shipments.

## M

### Maintenance

Maintenance involves procedural activities that help to extend the life of an asset or location and avoid impairment. After assets are identified and their location and state are known, the asset maintenance team can develop a basic maintenance plan. Based on an asset's state and risk of failure, different maintenance schedules and methodologies may be deployed. The three types of maintenance are *reactive*, *preventive*, and *predictive*. Learn more at [Maintain and repair internal assets](acquire-to-dispose-maintain-repair-internal-asset.md).

### Maintenance budget

The cost of maintaining assets is planned and managed by using a maintenance budget. Maintenance budgets typically consider factors such as the [maintenance plan](#maintenance-plan) for the asset, the location of the asset, historical data, and the cost of resources.

### Maintenance checklist

A maintenance checklist is associated with a job or work order where the team defines activities with potential outcomes for each checklist item. The maintenance team can define checklist items by maintenance job type, and they can extend the list later. The following list shows examples of checklist items in Dynamics 365:

- Text
- Header
- Template
- Variable
- Measurement

### Maintenance plan

A maintenance plan is a scheduled set of related inspections, calibrations, and [maintenance](#maintenance) activities. Maintenance plans apply to individual assets and locations. A maintenance plan that applies to a group of assets or locations is referred to as a maintenance round. In Dynamics 365, maintenance plans and rounds are used to create [work order](#work-order) proposals.

### Maintenance request

Without creating a work order, teams often want to notify a manager or planner that an asset might require maintenance or repair. This is where the maintenance request comes in as a note or declaration.

The following list shows examples of maintenance requests in Dynamics 365:

- Maintenance requests
- Notes
- Corrections or enhancements
- Investments
- Depot repair (for assets received from another location)

### Maintenance schedule

A maintenance schedule consists of all the maintenance plans, rounds, and requests that an organization expects to be covered. It details which people do which maintenance tasks and in what time frame. The schedule can require maintenance tasks to occur at repeating intervals, or that they must come from a work order. An organization can calculate budget costs on maintenance schedule line items.

### Manage background jobs

Efficient management of background jobs contributes to streamlined operations. This business process area involves overseeing and optimizing background processes to maintain system efficiency. Dynamics 365's Power Automate and Dynamics 365 finance and operations apps batch jobs features enable administrators to automate and manage these background tasks. This process contributes to streamlined operations and improved system efficiency.

### Manage data synchronization
Effective data synchronization is vital for maintaining consistency across the Dynamics 365 ecosystem. Manage data synchronization involves managing data synchronization processes to uphold data integrity. Dynamics 365's data integration features include features like Dual Write and Virtual Entities, and developers can leverage the Power Platform's data connectors and Azure services to synchronize data seamlessly between different systems and applications. This process ensures that data across the organization remains accurate, up-to-date, and aligned with business processes.

### Manage licensing and entitlements

The meticulous management of licensing and entitlements is central to optimizing resource allocation, ensuring that the organization's Dynamics 365 investment aligns seamlessly with user needs and business requirements. Efficiently managing licensing and entitlements is crucial for optimizing resource allocation and ensuring compliance.

Dynamics 365 offers License Management tools that allow organizations to oversee user licenses, track entitlements, and align them with business needs. This process ensures that the organization's investment in Dynamics 365 aligns with user requirements while maintaining compliance with licensing agreements.

### Manage notifications and alerts

Timely awareness of system events is crucial. This business process area includes the management of notifications and alerts to keep stakeholders informed and responsive to critical updates. Dynamics 365 provides features like Power Automate and Power Apps to configure and manage notifications based on predefined triggers. Dynamics 365 finance and operations apps also include an in app alert feature that can be easily integrated with Power Automate. These processes ensure that administrators are promptly alerted to potential issues, enabling proactive responses and issue resolution.

### Manage system access and security

Central to the *administer to operate* framework is the careful management of system access and security. This encompasses the establishment and enforcement of robust user roles, permissions, and security protocols. The process of managing system access and security is critical for safeguarding sensitive data within Dynamics 365. Role-based access control (RBAC), Azure Active Directory integration, and Multi-Factor Authentication (MFA) are integral features that Dynamics 365 provides for securing Dynamics 365 solutions. 

Including a regular user security review including Lifecycle Service and Power Platform Admin Center will ensure that the proper access is maintained. This process ensures that only authorized individuals have access to specific functionalities, maintaining the confidentiality and integrity of organizational data.

### Manage system compliance

Ensuring compliance with regulatory standards and internal policies is paramount in any technology implementation. Managing system compliance includes processes to manage system compliance, safeguarding organizations against risks. The platform provides features like Compliance Manager and Azure Policy integration to assist organizations in monitoring and enforcing compliance. 

Additionally, Dynamics 365 finance and operations apps includes the Audit workbench module and built in audit logs for Dynamics 365 Finance. These process when carefully implemented help to safeguard against risks and ensures that the organization operates within legal and regulatory frameworks.

### Mandatory credit limit

The **Mandatory credit limit** flag on a customer account forces the use of the account's [**Credit limit**](#credit-limit), whether or not the customer is in a [credit limit group](#customer-credit-group). If the value of **Credit limit** is set to 0.00 and the **Mandatory credit limit** flag is set to Yes, the customer effectively has a credit limit of 0.00, and all orders are placed on [credit hold](#credit-hold).

### Manufacturing execution system

A manufacturing execution system (MES) is software that supports the management and execution of a production process in real time.

In Dynamics 365 Supply Chain Management, it's the [**Production floor execution**](/dynamics365/supply-chain/production-control/production-floor-execution-use) module, which has a touch-friendly interface you can use to start production, record progress, consume materials, request maintenance, and perform other production tasks. Dynamics 365 also has a framework for [integrating a third-party MES](/dynamics365/supply-chain/production-control/mes-integration) with the **Production** module.

### Margins

Margins represent the difference between the cost of providing a service and its selling price. Dynamics 365 provides tools for managing pricing, and Dynamics 365 Supply Chain Management includes tools specifically for monitoring margins known as margin alerts. This is crucial process for many organizations seeking to assess the profitability of products or services. The platform provides tools to analyze and optimize margins, ensuring that pricing strategies align with financial objectives while maintaining competitive market positions.

### Marketing campaign

A marketing campaign is a strategic marketing effort across one or more channels over a period of time to promote a product, service, or brand. A *multi-channel campaign* uses multiple channels, such as email, social media, and events, to reach prospects. 

### Merchandising

In Dynamics 365, merchandising is the strategic planning, management, and execution of various activities that are related to product offerings, pricing, promotions, and inventory management. The goal of merchandising in Dynamics 365 is to optimize the presentation and availability of products to drive sales, enhance the customer experience, and improve overall business performance.

### Methods of payment

The ways that vendors can receive payment for their goods or services. Some of the most common vendor payment methods include checks, Electronic Funds Transfers (EFT), wire transfers, credit card and more.

### Microsoft Learn

An online learning platform provided by Microsoft, offering a variety of modules, tutorials, and hands-on labs specifically tailored to Dynamics 365 for user education.

### Modes of manufacturing

Dynamics 365 Supply Chain Management supports four high-level categories of production: discrete, process, lean, and project-based.

- [**Discrete manufacturing**](https://community.dynamics.com/blogs/post/?postid=13f0b0ac-6755-482e-ab73-9fcc1b55380a) refers to production that results in distinct items; for example, products that are tracked in eaches, boxes, rolls, and so on. Industries that commonly use discrete manufacturing include apparel, furniture, and electronics.

- **Process manufacturing**, also known as continuous or batch production, refers to processes that result in items that are tracked by volume or weight, or processes that may have multiple outputs, also known as co-products and by-products. Industries that commonly use process manufacturing include chemical and plastics, food and beverage, and pharmaceuticals and life sciences.

- [**Lean manufacturing**](/dynamics365/supply-chain/production-control/lean-manufacturing-overview) is less about the kind of item that's produced and more about how. Lean is an industry-standard set of practices that's designed to maximize productivity and minimize waste in the production process. It's often used in repetitive production processes and focuses on identifying value. It originated in the automotive industry and is also common in the printing and HVAC industries. Dynamics 365 Supply Chain Management supports lean concepts like value streams, production flows, and kanbans.

- [**Project-based manufacturing**](/dynamics365/project-operations/), also known as job shop manufacturing, refers to items that are custom-made, take a long time to make, or involve a large number of steps to produce. It allows for a more granular billing schedule than other types of production, using either predefined milestones or the passage of time. Industries that commonly use project-based manufacturing include equipment and machinery production, pharmaceuticals, and construction. Projects are also often used to track trial runs of new products and the associated research and development costs.

- **Mixed-mode manufacturing** reflects that businesses aren't restricted to a single type of manufacturing. For example, the pharmaceutical industry commonly uses both process and project-based production. When a business uses multiple modes, it's referred to as a mixed-mode manufacturer.

### Monitor systems, environments, and capacity

Continuous monitoring of system performance, environments, and capacity is imperative. *Administer to operate* focuses on proactive measures to identify and address potential bottlenecks, ensuring optimal system performance. This business process area is essential for proactive issue identification and optimal performance.

Dynamics 365 provides monitoring and diagnostic tools such as Azure Monitor and Application Insights. This process ensures that administrators can track system performance, identify potential bottlenecks, and optimize capacity to deliver a seamless user experience.

### Multicurrency

Multicurrency refers to the ability of the system to handle transactions and financial records in multiple currencies different than the accounting or reporting currency assigned to the ledger. Dynamics 365 Finance and Dynamics 365 Business Central enables organizations to conduct business in various currencies and manage currency-related processes.

## N

### Non-billable hours

Of the hours that are worked on tasks, those hours that aren't directly chargeable to clients are known as non-billable hours. Non-billable hours are essential for project management, internal meetings, training, and other activities that aren't client-facing. Learn more at [Deliver project work](project-to-profit-deliver-project-work.md) and [Billable hours](#billable-hours).

## O

### Opening balances

Opening balances refer to the initial account balances at the start of a new financial period. Dynamics 365 assists in carrying forward the relevant data and balances from the closed period to set the foundation for the upcoming reporting cycle.

### Opportunity

An opportunity is a [lead](#lead) that has been [qualified](#lead-and-opportunity-management) or determined to have the potential to generate revenue. In Dynamics 365, an opportunity typically includes a description of the customer's requirements, the products or services that the customer is interested in, the potential revenue, and the estimated closing date. Opportunities can be *scored* based on their potential, and they can be *nurtured* through ongoing communication that is aimed at developing them.

### Outsourcing

The use of an outside vendor to assist with the production of a semi-finished or finished good. This may be used to support internal capacity issues or used to help with the overall cost reduction of the requested item.

### Overhead costs

While all overhead costs are [indirect costs](#indirect-costs), not all indirect costs are overhead costs. Overhead costs specifically refer to indirect costs that are related to production or manufacturing activities, such as rent for the production facility, maintenance and repairs of production equipment, and the salaries of production supervisors.

## P

### Payment proposal

A proposal that is created to schedule and create Accounts Payable payments to suppliers.

### Per-diem

Per-diem refers to the daily allowance paid to employees for expenses incurred while traveling for work. Depending upon company policy, these expenses can include lodging, meals, and other incidental expenses.

### Performance appraisal

Performance appraisal in Dynamics 365 involves the systematic evaluation of an employee's job performance against predefined criteria and objectives. This process typically includes setting performance goals, conducting regular assessments, providing feedback, and documenting achievements. Dynamics 365 streamlines the performance appraisal process, making it more transparent, data-driven, and conducive to fostering continuous improvement and employee development.

### Performance plan

A performance plan in Dynamics 365 outlines specific objectives, goals, and expectations for an employee's job performance. This plan serves as a roadmap for individuals, providing clear guidance on what is expected in terms of tasks, projects, and skill development. It facilitates goal setting, aligns individual efforts with organizational objectives, and serves as a basis for performance appraisals.

### Performance review

A performance review within Dynamics 365 is a systematic assessment of an employee's job performance over a specific period. It involves evaluating accomplishments, areas for improvement, and alignment with performance goals. Dynamics 365 facilitates a streamlined and transparent performance review process, enhancing communication between managers and employees and providing valuable insights for continuous development.

### Planning

Planning is the process of identifying goals and determining the actions to attain them. Common types of planning include:

- **Strategic and operational planning** refers to separate processes that together encompass a company's long-term strategy and how it expects to execute it. A strategic plan typically details the goals the organization wants to achieve through its business processes and the actions and current and future resources it believes will accomplish them. An operational plan helps organizations evaluate and plan for the day-to-day needs of the business, such as operating expenses and workforce requirements.

- **Demand planning** is the process of using historical data and forecasts to balance inventory on hand with customer demand to maintain an optimal level.

- **Supply planning** helps an organization ensure it has sufficient supplies to meet forecasted demand.

- **Capacity planning** helps an organization schedule its production processes realistically.

### Positions

A position is an individual instance of a [job](#jobs). Positions are an important element of the lower level of an organization hierarchy. For example, the "Sales manager (East)" position is just one of the positions that's associated with the "Sales manager" job. Positions exist in a department and are assigned to workers. Every position has a length of time that it's effective for.

### Posting definition

Posting definitions are used to classify main accounts and financial dimensions on accounting entries. They can be used instead of posting profiles for supported posting types and documents.

### Pre-encumbrance accounting

Pre-encumbrance accounting refers to the process of earmarking funds for future anticipated expenses that might not otherwise be encumbered.

### Prepayment

A payment made by a buyer to a vendor or supplier in advance of receiving goods or services to secure their future delivery.

### Price adjustments

Price adjustments in Dynamics 365 involve modifying service prices based on various factors such as market conditions, customer relationships, or changes in costs. These adjustments provide organizations with the flexibility to adapt pricing strategies dynamically. Dynamics 365 Commerce allows for the automated application of price adjustments and approval processes for price adjustment, streamlining the process and ensuring accuracy.

### Price attributes

Price attributes refer to specific characteristics or parameters that influence the determination of service prices in Dynamics 365 Supply Chain Management and Commerce. These attributes may include features, customization options, or delivery specifications, for example. Leveraging price attributes allows organizations to create nuanced and customer-centric pricing structures, tailoring products and services to meet diverse client needs.

### Price components

Price components in Dynamics 365 Supply Chain Management and Commerce represent the individual elements that contribute to the overall product or service price. These components can include direct costs, overhead, and profit margins, for example. By breaking down prices into components, organizations gain visibility into the factors influencing pricing decisions, facilitating precise control and analysis of pricing structures.

### Pricing agreement

A pricing agreement in Dynamics 365 represents a formal arrangement between a service provider and a customer regarding the pricing of services. This agreement outlines the terms, conditions, and agreed-upon pricing structures for a specified period. The flexibility of pricing agreements allows organizations to tailor their offerings to meet the unique needs of individual clients, fostering long-term relationships and ensuring clarity in service pricing.

### Pricing management

Pricing management involves the comprehensive control and oversight of an organization's pricing strategies. In Dynamics 365, pricing management includes tasks such as setting service fees, product prices, defining discount structures, and optimizing overall pricing strategies. Effectively managing pricing is crucial for achieving profitability, competitiveness, and alignment with organizational goals.

### Pro forma invoice

A pro forma [invoice](#invoice) provides a customer with an estimate of the cost and terms of goods or services before they place an order or make a payment. A pro forma invoice can help the customer set the right expectations and budget accordingly.

In Dynamics 365 Finance, you can create a pro forma invoice either for a [customer invoice](/dynamics365/finance/accounts-receivable/configure-customer-invoices) for a sales order or for a [free text invoice](#free-text-invoice).

### Product

In Dynamics 365, a product is an item or service that a business offers for sale. It can be a finished good that's sold to customers or a raw material that's used to produce finished goods. In [Dynamics 365 Supply Chain Management](/dynamics365/supply-chain/pim/product-information), the following terms are used to describe products:

- A **product master** is a record that contains all the relevant information about a product, such as its description, dimensions, weight, pricing, and supplier. The product master organizes and manages product information in a centralized or global location. Modules in Dynamics 365 Supply Chain Management, such as sales and procurement, use product masters to manage inventory levels, pricing, and sales orders.

- A **product variant** is a variation of a product in terms of specific attributes, such as size, color, style, or configuration. For example, a clothing manufacturer might offer a t-shirt in different sizes and colors, which would be considered product variants. In Dynamics 365 Supply Chain Management, product configuration models define the attributes of and rules for product variants.

- A **released product** is a product that's released for sale or production in a specific legal entity. It's created by copying the product master record and making any necessary modifications, such as changing the pricing or other attributes. Released products are used to manage product versions and track changes over time, and are linked to specific sales orders, purchase orders, and production runs.

You can add products to a [product catalog](/dynamics365/sales/set-up-product-catalog-walkthrough) in Dynamics 365 Sales and [register products as inventory items](/dynamics365/business-central/inventory-how-register-new-items) in Dynamics 365 Business Central.

### Product and price lists

Product and price lists are catalogs of available products/services that include assigned prices. They are used to add items to quotes.

### Product category

A product category is a logical grouping of the products that a business sells, based on common characteristics, attributes, features, or usage. Product categories help both businesses and customers quickly identify and find specific types of products within a larger inventory.

Product categories can be broad or specific, depending on the size and complexity of a business's product offering. Some businesses might have only a few product categories, whereas others might have dozens or even hundreds. In addition to using product categories to organize products for customers, you can use them to manage inventory, track sales, and analyze business performance. Ultimately, product categories enhance organization, navigation, and the customer experience by providing a structured way to manage and present products.

For example, a clothing retailer might have product categories such as the following list:

- Men's Clothing
- Women's Clothing
- Kids' Clothing
- Shoes
- Accessories

An online electronics store might have product categories such as the following list:

- Electronics

    - Smartphones
    - Laptops
    - Tablets
    - Wearable Devices

- Accessories

    - Phone Cases
    - Laptop Bags
    - Screen Protectors

In this scenario, *Electronics* and *Accessories* are main categories, and the subcategories provide further granularity. This hierarchy helps customers quickly find the type of product that they are interested in. It also helps the store's internal operations for inventory management and pricing.

The specific attributes and characteristics that are used to define a product category can vary based on the business's offerings and the goals of categorization. 

In Dynamics 365 Commerce and Supply Chain Management, product categories are also known as [product hierarchies](#product-hierarchy). With the hierarchal structure of product categories, you can define a systematic and organized presentation of products. In this way, you make it easier for users to work with products in various processes, such as sales, marketing, inventory management, and reporting. Learn more at [Create a hierarchy of product classification in Supply Chain Management](/dynamics365/supply-chain/pim/tasks/create-hierarchy-product-classification) and [Manage product categories and products in Commerce](/dynamics365/commerce/category-management-product-creation). In Dynamics 365 Sales, you use [product families](#product-family) for the same purpose.

### Product family

In Dynamics 365 Sales, Customer Service, Field Service, and Customer Insights, a [product family](/dynamics365/sales/create-product-family) is a group of similar products. By creating a hierarchy of product families, you make it easier to manage products. You can use [product categories](#product-category) for the same purpose in Dynamics 365 Supply Chain Management.

### Product hierarchy

A product hierarchy, also known as a product classification or product taxonomy, is a structured system for organizing and categorizing products in a business or organization. It involves creating a hierarchical structure that groups products based on common attributes, characteristics, features, or relationships. This structure helps businesses manage and present their products in a more organized and understandable manner. Learn more at [Create a hierarchy of product classification in Supply Chain Management](/dynamics365/supply-chain/pim/tasks/create-hierarchy-product-classification) and [Manage product categories and products in Commerce](/dynamics365/commerce/category-management-product-creation).

### Product information management (PIM)

Product information management (PIM) is a discipline that involves centralizing and managing all product-related information across an organization. It encompasses the creation, enrichment, and distribution of consistent and accurate product data. In Dynamics 365, the PIM module facilitates this process and ensures uniform and efficient management of product information.

### Product lifecycle management (PLM)

[Product lifecycle management](/dynamics365/supply-chain/pim/product-lifecycle) (PLM) is the process that an organization uses to manage a product from its initial design and development through its retirement and disposal. The goal of PLM is to increase the efficiency of the product development process, reduce time to market, and improve product quality and profitability by managing and organizing all product-related information in a central location. Product-related information includes specifications, engineering designs, bills of materials or formulas, production schedules, and supply chains.

PLM typically involves the following stages in the life of a product:

1. **Concept**: An initial concept or idea for a product is explored and developed.

1. **Design**: The concept is turned into a design that considers factors such as functionality, manufacturability, and cost.

1. **Development**: The product is developed in accordance with the design, tested, and any necessary modifications or adjustments are made.

1. **Launch**: The product is introduced on the market.

1. **Growth**: The product gains acceptance in the market and sales and revenue increase.

1. **Maturity**: The product reaches its peak sales and revenue and may face increased competition or market saturation.

1. **Retirement**: Sales and revenue decline, and the product is retired or replaced by a newer model.

PLM can refer to a system or the use of specific software tools such as Dynamics 365 Supply Chain Management.

### Production journals

Production journals are the journals that are posted against a production or batch order. They include the following types:

- **Pick lists** record the materials that are consumed in a production or batch order. Information that's recorded in a pick list includes part numbers, the quantity of materials consumed, whether the inventory is tracked by lot or serial number, and the lot number and serial numbers of the materials that are consumed. Pick lists can also be used to record raw materials scrap.

- **Route cards** record the production resources&mdash;the labor, machines, and tools&mdash;that are used to make items for a specific production or batch order. Information that's recorded in a route card includes the list of resources, the amount of time that a resource was used, and the amount or quantity of finished product that a resource produced. Route cards can also be used to record raw materials scrap.

- **Job cards** record the start and stop times of operations in a production or batch order to calculate the actual cost of labor and machines. They can be automatically created and posted by user interactions with the production floor execution interface.

- **Report as finished** records the items that are produced in a production or batch order. Information that's recorded for production orders includes the finished good or subassembly item, the quantity of finished good produced, the scrap quantity produced, and whether the production order is complete. Batch orders track the same information. They also support reporting multiple items as outputs of the production process, either co-products or by-products.

### Production schedule

A production schedule, or production plan, is a detailed plan of the production operations that run during a certain time period. It's used to coordinate material procurement efforts, maintenance activities, and customer communications.

### Production source documents

In Dynamics 365 Supply Chain Management, production source documents track the progress of production operations. Each [mode of manufacturing](#modes-of-manufacturing) has its own source document.

- In discrete manufacturing, **production orders** document what product is being made, the list of materials and operations that are expected to be used, when production is scheduled to occur, and the status of production. Updates in the production process, such as material consumption, resource consumption, and recognition of produced inventory, are posted against the production order.

- In process manufacturing, **batch orders** document what product is being made, the list of materials and operations that are expected to be used, when production is scheduled to occur, and the status of production. They also contain data that's unique to process manufacturing, such as the expected yield percentage and whether the production operations are for rework. Updates in the production process, such as material consumption, resource consumption, and recognition of produced inventory, are posted against the batch order.

- In lean manufacturing processes, **kanbans** track information related to picking and production activities and the status of the kanban. Updates are posted against the kanban throughout the production process.

### Production strategies

A production strategy, a subset of operational strategies, refers to the approach that a manufacturer takes to determine when to run a production process. Production strategies help manufacturers balance the cost of carrying finished goods inventory against order fulfillment lead time. Common production strategies include the following examples:

- In a **make to stock** strategy, a forecast or another inventory positioning policy drives the production of finished goods instead of waiting for customers to place orders. It's a common strategy in industries that have a low mix of items with high demand volumes or short customer lead time tolerances. It's also often employed by businesses that want to maximize production efficiency by planning further in advance. One example is the retail industry, where companies with brick-and-mortar stores must have inventory on hand when a customer visits a store.

- In an **assemble to order** strategy, manufacturers stock production components that can be assembled at the time a customer places an order. This approach is more effective than make to stock for companies that have a higher mix of items that share components. It gives them more flexibility than storing fully assembled items and still allows them to fulfill orders on shorter lead times.

- In a **configure to order** strategy, the product offering has a standard scope with specified customizations that can be determined at the time the customer places an order. A good example is a laptop. It isn't cost-effective to keep all possible configurations of a laptop on hand. Instead, you pick the color, memory, storage, and processor chip when you order it. The manufacturer stocks the various components and subassemblies and configures them based on your customizations. The main difference between assemble to order and configure to order is the degree of customization of the finished good that the customer requests. If the customer chooses among options, then it's more likely a configure to order scenario.

- In a **make to order** strategy, the production of an item doesn't start until a customer orders it. This approach allows the business to minimize inventory on hand, but it's only possible when customers tolerate a longer lead time. It's more common in industries that have a high mix of products with low demand or components that have a limited shelf life.

- In an **engineer to order** strategy, the general scope of the product is defined, but the design is only finalized at the time the customer places an order. This approach is common in industries that require very custom solutions, such as construction and bespoke machinery.

### Project budget

A project budget is the total projected costs that are needed to complete a project over a defined period of time. It's used to estimate the project costs for every phase of the project. Creation of a project budget is a critical part of the project planning process. The project budget includes such things as labor costs, material procurement costs, and operating costs. It isn't a static document but can be reviewed and revised throughout the project.

### Project contract

The [project contract](/dynamics365/project-operations/prod-pma/project-contracts) is a formal written agreement between an organization (the contractor) and a client (the buyer) that defines the terms and conditions of a project or business transaction. It includes details such as the scope of work, deliverables, timelines, payment terms, and responsibilities of both parties.

In Dynamics 365, a project that will be invoiced must be associated with a project contract. Settings for a project contract apply to all projects and subprojects that are associated with it. A project contract can specify one or more sources of funding. You can invoice one or more projects at the same time and make sure that a uniform invoicing procedure is applied for each subproject in a project structure.

### Project controller

The project controller works directly with the project manager to help define the project's goals and objectives. They create and maintain a project budget and schedule, analyze progress reported against the work schedules, and recommend actions to improve progress.

### Project delivery

Project delivery is the phase of project management where the planned project outcomes, products, or services are provided to stakeholders or clients according to the project's objectives and scope.

### Project estimate

A project estimate is a projection of the cost and schedule of work on a project. Project estimates can be binding or not. Learn more at [Manage project financials overview](project-to-profit-manage-project-financials-overview.md).

### Project manager

A [project manager](#centralized-resource-allocation) is the individual who is responsible for planning, organizing, executing, and controlling all aspects of a project, from initiation to completion. Project managers are accountable for achieving a project's objectives within the constraints of scope, time, cost, quality, resources, and risk as defined in the [project contract](#project-contract).

### Project phases

The Project Management Institute (PMI) created a five-phase model that groups different activities throughout the project management lifecycle. The five phases are project initiation, project planning, project execution, project monitoring & control, and project closure.

### Project resource

Project resources are the assets, materials, tools, or personnel that are required to run and complete a project.

### Project task

A project task is a specific unit of work in a project that contributes to the overall completion of the project's objectives. Tasks are individual activities or assignments that must be completed to move the project forward. Each task is defined by its scope, its duration, the resources that it requires, and any dependencies that it has on other tasks.

### Project type

In Dynamics 365, projects can be categorized as one of six types depending on the purpose of the project. Each project type is set up differently for costs and revenue recognition. The following [project types](/dynamics365/project-operations/prod-pma/overview-project-management-accounting#create-projects) are available in Dynamics 365 solutions:

- Time and material
- Fixed-price
- Investment
- Cost
- Internal
- Time

### Promissory note

A promissory note is a written agreement in which the maker of the note promises to pay a certain amount at a certain time.

### Promotional pricing

Promotional pricing involves the strategic use of temporary discounts or special offers to stimulate sales and attract customers. In Dynamics 365 Supply Chain Management and Commerce, organizations can set up promotional pricing for specific products or services or during designated time periods. This concept is crucial for marketing initiatives, allowing businesses to create targeted promotions that align with their overall pricing strategy and boost customer engagement.

### Proposal

The document that outlines the scope of work, deliverables, timeline, and estimated cost of a project is called a proposal. A proposal is presented to the customer for review and consideration. It might be subject to negotiation before a final agreement is reached.

### PROSCI

PROSCI stands for "Professional Counselling Services Institute," and it is also the name of a company that specializes in change management. However, when people refer to "PROSCI" in the context of change management methodologies, they are often referring to the Prosci ADKAR® Model, which is a popular and widely used framework for managing the people side of change within organizations.

The ADKAR® Model focuses on the five key elements of successful change: Awareness, Desire, Knowledge, Ability, and Reinforcement. This model helps organizations understand and address the individual and organizational factors that influence successful change initiatives, including those related to technology implementations like Dynamics 365.

### Provider

A provider is a connection point in a supply chain. In the context of Intelligent Order Management in Supply Chain Center, a provider enables integration with other systems by presenting calls between systems as actions that can trigger events that drive orchestration.

### Purchase agreement

A purchase agreement serves as a contractual document between a buyer and a seller. It outlines the terms and conditions for the purchase of goods or services. In Dynamics 365, a purchase agreement provides a comprehensive framework for managing procurement activities. It establishes clear terms for pricing, quantity, delivery schedules, and other relevant terms. This agreement helps make sure that the entire procurement process is efficient, transparent, and compliant with organizational policies and industry regulations.
In Dynamics 365 Supply Chain Management and Dynamics 365 Business Central, purchase agreements are referred to as *blanket orders*.

### Purchase order

A purchase order (PO) serves as a formal document that a buyer issues to a seller to outline the details of a purchase transaction. The purpose of a purchase order is to provide a structured and standardized means of communicating specific information that's related to the procurement of goods or services. It helps ensure accuracy, transparency, and efficiency in the purchasing activities of an organization.

### Purchase requisition

A purchase requisition (PR) serves as a formal request for the procurement of goods or services within an organization. It's an internal document that initiates the procurement process. A purchase requisition is typically generated by a department or individual within the organization when there is a need for new supplies, equipment, or services. Purchase requisitions play a crucial role in the procurement process by facilitating a standardized, controlled, and transparent workflow from the request stage to purchase order creation. They contribute to better financial management, accountability, and efficiency in an organization's procurement activities.

## Q

### Questionnaire

In Dynamics 365, a questionnaire is a tool used to gather feedback and insights from employees, managers, or other stakeholders. Questionnaires can be employed for various purposes, including performance reviews, employee engagement surveys, and competency assessments. Dynamics 365 integrates with tools like Customer Voice to facilitate the creation and distribution of questionnaires, streamlining the feedback collection process.

### Quote

A quote is a document that presents a customer's potential order for products/services together with proposed prices. Quotes enable sales teams to provide estimates to prospects during the sales process. Quotes must be *approved* to ensure that they are aligned with business policies. Organizations typically have a process for approving a finalized quote before it's sent to the customer or prospect.

Quotes can be *revised*. In other words, adjustments can be made to a quote before it's finalized, based on the prospect's feedback. Revisions can optimize pricing.

## R

### Rating

Rating is the process of retrieving a freight charge from a carrier contract.

In Dynamics 365 Supply Chain Management, the [Transportation management module](/dynamics365/supply-chain/transportation/transportation-management-overview) supports freight carriers. If you use parcel carriers, you often need an integration project.

### Raw material

Raw materials are the inputs to a production process, which are used to create subassemblies and finished goods. Raw materials are commonly referred to as components, ingredients, or bulk materials.

### Rebate

A rebate is a trade discount or allowance that a supplier uses as incentives to encourage an increase in sales. They are sometimes referred to as supplier incentives, vendor incentives, channel incentives, special pricing agreements, bonuses, and retroactive discounts.

### Rebate accruals

A rebate accrual In Dynamics 365 is the process of calculating the amount that will be earned on each product by the completion of the trading period and recording the estimated amount in the general ledger on the balance sheet. This accrual is automatically reversed once the actual rebate is earned and moved and posted into the appropriate account in the general ledger.

### Rebate agreement

In Dynamics 365 Supply Chain Management, a vendor rebate agreement is a record of a contract with a vendor that specifies the negotiated terms and conditions under which the company qualifies for a monetary reward in return for achieving preset purchase targets.

### Rebate claim

When purchase orders are placed with a vendor that the company has a rebate agreement with, Dynamics 365 Supply Chain Management automatically identifies any future vendor credit payments. If the purchase orders qualify for a rebate, a rebate claim is generated for every order line as soon as a purchase invoice has been posted. This record that is generated is referred to as a rebate claim.

### Rebate generation

Rebate generation in Dynamics 365 involves the automated calculation and creation of rebate transactions based on predefined criteria. The system streamlines this process, reducing manual effort and minimizing errors. Rebate generation is a critical step for accurately tracking and accounting for incentive-related transactions.

### Rebate processing

Rebate processing encompasses the execution of approved incentive transactions in Dynamics 365. This involves validating and applying rebates to relevant financial records, ensuring that calculated incentives are accurately reflected in the organization's financial data. Efficient rebate processing contributes to financial accuracy and transparency.

### Recipe management

Recipe management is a term that is used in process manufacturing that focuses on creating and maintaining detailed recipes. In Dynamics 365 Supply Chain Management, these recipes are referred to as *formulas*. Recipe management involves specifying the exact quantities, units of measure, and processing instructions for each ingredient. It helps ensure consistent product quality and compliance with industry regulations.

### Reconcile invoices

Invoice reconciliation is the process of comparing and matching supplier invoices with purchase orders and receipts to ensure accurate payment and track manufacturing costs.

### Reconciliation

In finance, reconciliation refers to the process of comparing two sets of financial records to ensure that they're accurate and in agreement. It's a crucial step in accounting that helps to identify discrepancies between two sets of records and correct them. Reconciliation can be used for various purposes, such as vendor payment reconciliation, which involves reconciling vendor payments with vendor invoices to ensure that they match. Dynamics 365 Finance provides features such as vendor payment overview, file formats for methods of payment, and configuring vendor payment formats to help with this process.

### Recovery Point Objective (RPO)

The maximum tolerable amount of data loss measured in time, indicating the point in time to which systems and data must be recovered after an incident.

### Recovery Time Objective (RTO)

The targeted duration within which systems, applications, and services must be restored after a disruption to meet business continuity goals.

### Registrations

The term registration is used in Dynamics 365 applications in several different contexts. One example is inventory registration and another is a time registration. In the example of inventory registration, the termed registered is used to indicate that product has been received physically in the warehouse, but it is not yet put away. Learn more at, [Register items enabled for warehouse management processes using an item arrival journal](/dynamics365/supply-chain/warehousing/tasks/register-items-advanced-warehousing).

In the context of time registration, it refers to an entry that can be performed in one of several modules to report how much time has been consumed performing a specific task. Learn more at [Time and attendance registration overview](/dynamics365/supply-chain/production-control/time-attendance-registrations#registrations).

When you use Dynamics 365 Supply Chain Management for production on the shop flow you can leverage manufacturing execution functionality to register time against production. [Registration for manufacturing execution](/dynamics365/supply-chain/production-control/registration-manufacturing-execution).

### Regulatory compliance

Regulatory compliance encompasses adhering to laws, rules, and regulations imposed by government authorities or industry bodies that govern specific aspects of an organization's operations, such as data protection, environmental standards, or financial reporting.

### Repair

Repair involves restoring a broken asset to bring it to a steady operational state. In repair of intangible assets, especially impaired software, the organization might need more resources to fix the issue, such as consultants. They might also need licenses to get access to capabilities in software. Learn more at [Maintain and repair internal assets ](acquire-to-dispose-maintain-repair-internal-asset.md).

### Replenishment

[Replenishment](/dynamics365/supply-chain/master-planning/planning-optimization/replenishment-methods-quantity-modification) refers to sourcing inventory to a location, either by moving it from one location in the company to another or by purchasing or producing it. [Supply planning](#planning) centers on making decisions about [how inventory will be replenished](inventory-to-deliver-overview.md) to meet expected or actual demand.

### Reporting relationships

Reporting relationships define hierarchies of positions and are reflected in organizational charts. A reporting relationship can be used to route documents through a workflow.

If your organization uses a matrix hierarchy or another custom hierarchy, you can set up hierarchy types in Dynamics 365 and add reporting relationships to positions for each type. For example, an employee might be a part of a project team that has an informal reporting relationship to a project supervisor.

### Request for quotation

A request for quotation (RFQ) serves as a formal document that a buyer issues to potential suppliers to invite them to submit quotations or bids for the supply of specific goods or services. The primary purpose of an RFQ is to facilitate the procurement process by obtaining competitive pricing and terms from multiple suppliers. RFQs help organizations obtain competitive pricing, negotiate favorable terms, and make well-informed decisions when they select suppliers for the provision of goods or services.

### Requirement

A requirement is a capability that must be present in a product, service, or result to satisfy a business need.

### Resource

In the context of employee management and growth processes in Dynamics 365, a resource refers to an individual or asset within the organization. Resources can be employees, equipment, or any entity contributing to the achievement of organizational goals. Dynamics 365 integrates with other Microsoft solutions like Field Service, Project Operations, and Supply Chain Management to optimize resource allocation and enhance overall operational efficiency.

### Resource booking

Bookings are the hard or soft allocation of resources to a project. Hard bookings consume a resource's capacity. Bookings represent organizational concepts for teams, so that they can understand how resources will be engaged across various projects. Dynamics 365 Project Operations considers bookings a project-level concept.

### Resource capacity

Resource capacity refers to the amount of time that a resource has available to perform service work. Generally, it is the resource work hours less the time that they are already booked to perform service work.

### Resource characteristics

Resource characteristics refer to the qualities, attributes, or traits that are associated with the resources that a project uses. They help [project managers](#project-manager) assess the suitability of resources for various project tasks and activities. An understanding of resource characteristics is essential for effective resource selection, allocation, and use.

### Resource costs

The cost of a resource typically refers to the amount a resource is being paid for their time while performing service work.

### Resource manager

A [resource manager](#centralized-resource-allocation), also known as a resource coordinator or resource planner, is the individual who is responsible for managing the allocation and use of resources in an organization. Resource managers oversee the availability, deployment, and scheduling of resources to support various projects, departments, or operational activities.

### Resource requirement

Resource requirements refer to the types and quantities of resources that are needed to run and complete a project within defined scope, timeline, and quality standards.

### Resource schedule optimization

Resource schedule optimization refers to the process of maximizing the efficiency and effectiveness of resource allocation and scheduling. It involves using advanced algorithms and techniques to analyze various factors and constraints, such as resource availability, skills, location, and task requirements, to generate optimal schedules.

### Resource work hours

Works hours define the days, and times, that a service resource is available to be scheduled to perform service work.

### Revenue budget

A revenue budget represents a point-in-time snapshot of estimated revenue for the project. All unbilled and billed sales on the project are compared against the revenue budget to track the revenue on the project.

### Risk management

The systematic identification, assessment, and mitigation of potential risks that could disrupt business operations.

### Risk scores

A risk score is a measure of a customer's credit worthiness. It's used to define a customer's credit management blocking and exclusion rules. The risk score and rules that you define can be used to automatically calculate a customer's credit limit. You can also define risk assessments that can be assigned to customers based on their risk score.

### Roll forward

Rolling forward in Dynamics 365 involves carrying forward specific data, such as account balances or budget figures, from the closed financial period to the beginning of the next period. This ensures a smooth transition and continuity in financial reporting.

### Routing

Routing is the process of assigning a route to a [load](#load). Routes are typically configured when multiple modes of transportation are required or preferred to move goods through the supply chain (for example, by truck, rail, or ocean).

## S

### Sales agreement

A sales agreement outlines the terms and conditions of a sale between a seller and a buyer. In Dynamics 365 Supply Chain Management, sales agreements play a crucial role in defining pricing structures, delivery schedules, and payment terms. These agreements provide a legal framework for the sales process, ensuring clarity and compliance with established terms. Sometimes these are referred to as blanket orders.

### Sales channels

Sales channels are the methods that are used to sell products and services to customers. Examples are direct sales, partners, resellers, retail, and e-commerce.

### Sales compensation

Sales compensation includes commissions, bonuses, and incentives that are offered to motivate specific seller behaviors and achievements.

### Sales documentation and materials

Sales documentation and materials are resources that sales teams use during the [sales process](#sales-process-and-stages). They can include the following types of documentation:

- A **quote** outlines the price and terms for products or services that a customer is interested in purchasing.

- A [**sales order**](#sales-order) details the products or services that a customer has agreed to purchase. It includes pricing, quantities, and delivery details.

- **Activities** are the tasks, appointments, phone calls, emails, and other forms of communication and interaction that are part of the sales process. They're typically used to track and manage engagement with [leads](#lead), [opportunities](#opportunity), and customers.

- **Sales literature** encompasses marketing materials like brochures, whitepapers, presentations, and case studies that salespeople can use to support their sales pitches and educate prospects about a company's products or services.

### Sales enablement

Sales enablement refers to training, content, tools, and coaching that are provided to sales teams to improve performance.

### Sales order

A sales order is a document created by the seller. A sales order helps the seller keep track of the orders they fulfill and manage their resources accordingly. Typically, it's generated because of winning a sales quotation or as a response to receiving a purchase order from a buyer specifying the details about the product or service along with price, quantity, delivery date, buyer details like the shipping address, mode of payment, and terms and conditions. The sales order confirmation generated from the sales order represents the commercial commitment towards a buyer. It's sent in response to the buyer's purchase order when one exists. On the buyer's side, the sales order confirmation is typically referred to as a purchase order confirmation. Learn more at [Create sales orders](/dynamics365/supply-chain/sales-marketing/tasks/create-sales-orders) in the docs for Dynamics 365 Supply Chain Management.

The sales order confirmation that's generated from the sales order represents the seller's commitment to a buyer. It's sent in response to the buyer's purchase order when one exists. On the buyer's side, the sales order confirmation is typically referred to as a purchase order confirmation.

### Sales planning and strategy

Sales planning and strategy describes the process of developing an approach and plan for achieving sales goals and objectives. It includes identifying target markets, setting sales targets, and determining sales tactics and resources.

- **Sales forecasting** is the process of predicting future sales revenue based on historical data, market trends, and other factors, to help sales teams set targets and plan their activities accordingly.

- **Cross-selling** and **upselling** are sales strategies that are designed to increase revenue and customer lifetime value (CLV). Cross-selling involves offering more products or services to existing customers, whereas [upselling](#upsell) involves encouraging customers to upgrade to a higher-priced product or service.

### Sales process and stages

The sales process is a series of steps that a sales team follows to identify, engage, and close deals with potential customers. It includes prospecting, qualification, needs analysis, presentation, handling objections, closing, and follow-up.

- A **sales process** is a series of steps that a salesperson follows to guide a lead or prospect through the stages of becoming a customer, from initial contact to closing the sale.

- A **sales funnel** or **sales pipeline** is a visual representation of the way that leads and opportunities move through each stage in the sales process.

- The **sales cycle** is the time that it takes for a lead to move through the sales process, from initial contact to a closed sale. It can vary depending on factors such as the complexity of the product or service and the customer's decision-making process.

### Sales targets

Sales targets are specific measurable goals that are set for revenue and sales volume over a period of time. Targets are set at the company, business unit, team, and individual levels.

### Sales territories

Sales territories are geographic areas or accounts that are assigned to salespeople. Territories optimize market coverage and account focus.

### Sales tools and technologies

Sales tools and technologies are software and hardware solutions that help sales teams manage and automate aspects of the sales process, such as managing customer relationships, generating leads, and creating sales analytics.

- **Sales automation** refers to the use of software tools and technologies to automate repetitive tasks and activities in the sales process, so that sales teams can focus on more strategic activities, such as building relationships and closing deals.

- A **dashboard** is a visual interface that displays key performance indicators (KPIs) and other data that's related to the sales process, so that sellers and managers can monitor and analyze sales activities.

- **Customer relationship management** (CRM) is a system and process for managing interactions with leads, prospects, and customers throughout the sales process, with the goal of building long-term relationships to improve customer satisfaction and increase sales.

### Sarbanes-Oxley Act (SOX)

The Sarbanes-Oxley Act of 2002 is a U.S. federal law that sets requirements for public company boards, management, and public accounting firms regarding financial reporting and internal control practices.

### Schedule

The purpose of a schedule is to ensure the timely completion of a project. It defines the tasks that must be completed, the priority, the deadlines, and the sequence.

### Scheduling parameters

The term *scheduling parameters* refers to any information in a work order that helps the dispatchers schedule the service work. Examples include the estimated duration, preferred times, required service resources, priority, and territory.

### Scope

A project's scope defines the boundaries of the project. It's a list of specific project goals, deliverables, tasks, costs, and deadlines.

### Scrap

Scrap refers to any excess or unusable material that's identified during the production process. Scrap can be raw materials, subassemblies, or even finished products that don't meet specifications. Typically, it's disposed of. However, in some cases, it can be reworked or reused in the production process. For example, metal shavings from the fabrication process may be melted and worked into a new product.

Scrap can also describe labor or other production resources that result in unusable products or otherwise don't contribute to the subassembly or finished good production. For example, if a subassembly is scrapped, the labor associated with producing that subassembly would also be considered scrapped.

### Segmentation

Segmentation in Dynamics 365 is the practice of dividing a target audience or market into distinct homogeneous groups, based on shared characteristics, behaviors, preferences, or needs. The goals of segmentation are to gain a deeper understanding of the diverse customer base, and to tailor marketing, sales, and business strategies to effectively reach and serve each segment.

Segmentation helps businesses recognize that not all customers are the same, and that different groups have unique preferences and requirements. By identifying and understanding these segments, companies can deliver more personalized and relevant experiences, products, and messages to different customer groups. Dynamics 365 Customer Insights - Journeys supports the creation of segments to help manage customer journeys. Learn more at [Create segments and lists to establish target markets](/dynamics365/marketing/segmentation-lists-subscriptions).

### Service

A [service](/dynamics365/supply-chain/service-management/service-management-home-page) is an intangible offering that a business provides to its customers. Unlike physical [products](#product), services can't be held or touched. Instead, they're typically based on the application of knowledge, expertise, or skill to meet a specific need or solve a particular problem.

Services can take many forms, including professional services such as consulting, legal, or accounting services, personal services such as haircuts or massages, and digital services such as software as a service (SaaS) or cloud computing. Services can be provided in person, over the phone, or online, and may be one-time or recurring. They're often associated with [work orders](/dynamics365/field-service/create-product-or-service).

The delivery of a service often involves a direct interaction between the service provider and the customer. Service providers must often manage the customer experience, including communication, expectations, and quality control, to ensure that the service meets or exceeds the customer's needs and expectations.

In business, services can play a critical role in building customer relationships and generating revenue. By providing high-quality services and building strong customer relationships, businesses can increase customer loyalty, generate repeat business, and differentiate themselves from competitors.

### Service customer

The entity that a service is performed for is the *service customer* or *service account*. It's typically the company that is financially responsible. In Dynamics 365 Field Service, you specify the service customer in the **Billing Account** field.

### Service fees

Service fees encompass the charges associated with specific services offered by an organization. In Dynamics 365 this process involves defining and maintaining service fees involve setting the cost structures for different types of services. This includes considerations such as material costs, labor, and overhead. Clear and accurate service fee management is essential for establishing competitive yet profitable pricing.

### Service Level Agreement (SLA)

A contractual agreement specifying the level of service, performance, and availability guaranteed by a service provider, such as Microsoft for Dynamics 365.

### Service location

In field service scenarios where frontline workers travel to perform service work, the service location defines the location where the work is performed. A service customer can have many service locations. In Dynamics 365 Field Service, you specify the service location in the **Service Location** field.

### Service pricing optimization

Service pricing optimization is the ongoing process of refining and improving pricing strategies to align with organizational goals and market dynamics. In Dynamics 365, this involves leveraging analytics, market insights, and customer feedback to make informed adjustments to service pricing. Continuous optimization ensures that service pricing remains competitive, maximizes profitability, and adapts to changing business environments.

### Service resource

In Dynamics 365 Field Service, a service resource is a person who can be scheduled to perform the service delivery process, or equipment that can be used in that process.

In Dynamics 365 Business Central, the term *service resource* covers the people who provide the service, whereas the term *service item* covers the items that can be serviced. In Dynamics 365 Supply Chain Management, the term *service object* covers the items that can be serviced.

### Service territory

A specific geographic area or region where a company or organization provides its products, services, or support to customers. It represents the designated area in which the company operates and delivers its offerings.

### Settlement

The process of settling transactions between different document types, such as invoices, payments, credit memos, and fees.

### Shipment

A shipment is a delivery to a customer. If you use the packing functionality in Dynamics 365 Supply Chain Management, a shipment can cover one or more order lines or containers.

### Simulation testing

The process of conducting realistic scenarios to simulate disruptions and test the effectiveness of the Business Continuity Plan.

### Skill gap analysis

Skill gap analysis within Dynamics 365 is the process of identifying the disparity between the skills employees currently possess and the skills required for their roles or future responsibilities. By conducting a skill gap analysis, organizations can pinpoint areas where additional training or development is needed, enabling targeted interventions to bridge these gaps. This approach ensures that employees are equipped with the right skills to meet evolving job demands and contribute effectively to organizational success.

### Skills

Skills in Dynamics 365 represent the specific abilities, knowledge, and proficiencies that employees possess. The system allows organizations to define and track individual skills, ensuring a comprehensive understanding of the workforce's capabilities. This information is crucial for competency analysis, skill gap identification, and targeted learning and development initiatives.

### Source document

An original record that evidences the occurrence of one or more economic, resource flow, and accounting events. A source document is entered into a system that records, classifies, tracks, and reports on the economic resources exchanged or committed at the time of the event. Examples of source documents in Dynamics 365 Finance include purchase requisitions, purchase orders, and sales orders.

### Strategic planning

The process of defining organizational goals and priorities, influencing the establishment of Business Continuity Objectives.

### Subassembly

Subassemblies are items that have undergone some of the production steps but aren't at the finished goods stage yet. They're also sometimes referred to as semi-finished goods. Some organizations have breaks throughout the production process and subassemblies may be reported and stored in inventory during these breaks.

### Subcontracting

Subcontracting, also known as tolling or outsourcing, is the process of using a vendor to run some of or all the steps of producing an item. The typical subcontracting process includes sending materials out to the vendor to have them provide a service or other added value and receiving back the updated product to be worked on further or sold.

### Subcontractor

A subcontractor is a hired external worker who performs specialized tasks or produces specific components as part of a larger manufacturing process for a company.

### Subject

In Dynamics 365 Sales, Customer Service, Field Service, and Customer Insights, the term *subject* refers to a categorization or classification for labeling and organizing various records, such as cases, activities, knowledge base articles, sales literature, and products. Subjects help you better organize and manage data in the system. Subjects can be organized into a subject hierarchy. This concept resembles the concept of product categories and a product category hierarchy. However, one key difference is that subjects support the organization of not only products but also other types of data. Learn more at [Define subjects to categorize cases, products, and articles](/power-platform/admin/define-subjects-categorize-cases-products-articles).

### Subledger

In Dynamics 365 Finance, a subledger (also known as a subaccount or subledger account) is a component of the financial accounting system that captures transactions specific to something other than a main account before they are summarized into the general ledger. It's a way to maintain different information about financial transactions and helps provide a clear audit trail and detailed reporting. Many modules in Dynamics 365 include subledgers that integrate directly with the general ledger in Dynamics 365 Finance to include, but not limited to the following:

- **Customer** – This includes any transactions that are posted to a customer account such as sales order invoices, free text invoices, and customer payments. This is primarily related to the Accounts receivable and Sales and marketing modules.

- **Vendor** – This includes any transactions that are posted to a vendor account such as vendor invoices and vendor payments. This is primarily related to the Accounts payable and Procurement and sourcing modules.

- **Inventory** – This includes any receipt or issue from inventory. This only applies to products that are tangible and stocked in your inventory. This can be related to transactions that happen in the Inventory management, Warehouse management, Transportation management, Production control, Sales and marketing, and Procurement and sourcing modules.

- **Project** – This includes any transactions related to a project such as the hours, expenses, fees, and invoices. This is primarily related to the Project management and accounting module.

- **Bank** – This includes any deposits or withdrawals including any fees, interest and so on that are recorded in a bank account. This is related to transactions that occur in the Cash and bank management module; however, it's important to note that most transactions originate in the Accounts payable and Accounts receivable modules.

- **Fixed assets** – This includes the acquisition, depreciation, write up or write, and so on related to any fixed assets. This is primarily related to transactions that are generated in the Fixed asset module; however, there are integrations with Procurement and sourcing, Accounts receivable, and Project management and accounting.

### Success by Design framework

A [framework within the Dynamics 365 Implementation Guide](../implementation-guide/success-by-design.md) that provides guidance on aligning technology solutions with business goals, emphasizing training, and adoption as critical components.

### Supply chain

A network of organizations, resources, activities, and processes that collaboratively design, produce, distribute, and deliver goods or services, ensuring efficient flow from suppliers to customers while minimizing costs and maximizing customer satisfaction.

### Supply chain visibility

Supply chain visibility is the ability to monitor and track the movement of products, components, and information throughout the supply chain. In Dynamics 365, achieving supply chain visibility enhances decision-making by providing real-time insights into inventory levels, order status, and production progress.

### Support systems

*Administer to operate* extends beyond proactive measures to encompass responsive support. This involves addressing user queries, troubleshooting issues, and providing ongoing assistance to maintain a resilient Dynamics 365 environment.

Supporting Systems is an integral aspect of administering to operating any technology solution. The process involves responsive assistance for users and efficient issue resolution. Dynamics 365 offers tools like the Power Platform's Power Virtual Agents for building intelligent chatbots and the Dynamics 365 Support Hub for comprehensive support resources. This process ensures that users receive timely assistance, queries are addressed efficiently, and issues are resolved promptly, contributing to a resilient and smoothly functioning Dynamics 365 environment.

### System uptime

The measure of the time during which a system or service is operational and available for use, often monitored to ensure adherence to SLAs.

## T

### Tax codes and rates

Tax codes represent different types of taxes or tax categories, while tax rates specify the percentages or amounts applied to taxable transactions. Business solutions often store and manage tax codes and rates to automate tax calculations.

### Tax compliance

Tax compliance involves adhering to tax laws and regulations, accurately calculating and reporting taxes owed, and submitting tax returns to the relevant tax authorities on time.

### Tax jurisdiction

A tax jurisdiction is a geographic area, typically defined by a government authority, that has specific tax laws and regulations. Organizations must determine the appropriate tax jurisdictions for their operations to calculate and report taxes correctly.

### Terms of payment

The terms that dictate when a vendor must be paid. These terms vary in policy and are usually included in the invoices generated by companies and sent to customers.

### Time and attendance

Time and attendance is a module available with Dynamics 365 Supply Chain Management that allows organizations to register, calculate, and approve the time worked. It integrates closely with the Production control and Project management and accounting modules.

[Time and attendance registration overview](/dynamics365/supply-chain/production-control/time-attendance-registrations)
### Three-way matching

Three-way matching matches the unit price and the net amount with the purchase order, and the quantity with the product receipt.

### Time and material projects

For time and material projects, the [customer invoice](#invoice) amount is based on transaction lines that are entered on projects. Transactions can be invoiced per project or per [project contract](#project-contract). Learn more at [Manage project financials overview](project-to-profit-manage-project-financials-overview.md).

### Time entry

Time entry is the process of recording and monitoring the time that is spent on various tasks and activities throughout the project's lifecycle. Time tracking provides a record of the work hours that are spent across the various project components. Learn more at [Deliver project work](project-to-profit-deliver-project-work.md).

### Time series forecasting

The main strategy that's used to generate forecasts in Dynamics 365 Supply Chain Management is time series forecasting. It's a model that uses previous demand to predict future demand. The components of a time series forecast model fall into three categories:

- A **trend** is the general direction that demand is moving in, generally either increasing or decreasing.

- **Seasonality** describes the presence of recurring short-term patterns in demand. For example, demand may spike at the end of a quarter due to a push to close sales. Seasonality doesn't have to be related to specific seasons of the year. It can be related to any internal or external event.

- An **error** is an unexplained or random variation in a time series. In real life, it's impossible to create a statistical model that explains the trend and seasonality of demand with complete accuracy. Some degree of error must always be expected.

When the three components are added together, they can be used to predict future demand. The statistical forecasting algorithms used by Dynamics 365 and other forecasting tools calculate and combine these general components in different ways, allowing organizations to compare forecasting models and select the one that seems to predict the demand best. The following graphic illustrates the components and formula that represent time series forecasting.

:::image type="content" source="media/time-series-forecasting.png" alt-text="Graphic illustrating that trend plus seasonality plus error predicts forecasts." lightbox="media/time-series-forecasting.png":::

### Trade agreement

A trade agreement in Dynamics 365 Supply Chain Management refers to a negotiated arrangement between a company and its business partners (customers or vendors), often involving discounts, pricing structures, and terms for the exchange of goods and services. Trade agreements streamline the pricing process, providing a framework for consistent and mutually beneficial transactions between parties.

### Train users and increase adoption

Driving user adoption is a key aspect of ongoing success. *Administer to operate* includes efforts to train users effectively, enhancing their proficiency with Dynamics 365 and promoting widespread adoption. Training users and increasing adoption is a key focus within *administer to operate*, emphasizing the importance of user proficiency and widespread platform adoption.

Dynamics 365 Human Resources includes features to help facilitate user training and onboarding. These processes help ensure that users are equipped with the skills needed to maximize their productivity within Dynamics 365, ultimately driving increased adoption across the organization.

### Travel and expense management (T&E)

T&E is the process of managing expenses related to business travel or otherwise incurred in the process of performing job-related duties. It involves various responsibilities aimed at overseeing and optimizing spending, including tracking and analyzing expenses, creating and enforcing corporate travel and expense policies, establishing the reimbursement process, building approval processes for travel requests, aligning company goals to business travel, and measuring the return on investment for expenses incurred.

### Travel and expense policy

A travel and expense policy is a documented set of processes that govern how organizational money is spent on travel and other relevant expenses. A clear policy is essential for compliance and efficient use.

### Travel requisition

A travel requisition lists the expenses incurred for the purpose of travel. A travel requisition is submitted for review and can be used to authorize expenses. You may be required to submit a travel requisition before you incur any expense that is charged to the organization.

### Trial balance

The trial balance in Dynamics 365 is a summary of all the account balances in the general ledger, serving as a preliminary step in the financial period closure process. It helps identify errors and ensure that debits equal credits before finalizing the closure. The Trial balance in Dynamics 365 Finance can be printed as a report, viewed with a real-time inquiry screen or generated as a financial statement.

### Two-way matching

Two-way matching invoice validation is to match the invoice document unit price with purchase order unit price and net amount with purchase order line net amount.

## U

### Unlimited credit limit

The **Unlimited credit limit** flag on a customer account indicates the account must not be checked against its credit limit. Use it to prevent an important customer from being affected by the credit management capabilities in Dynamics 365 Finance.

Because this option circumvents the standard processes your organization uses, consider its security carefully. You might want to set up database logging to [monitor its use](order-to-cash-monitor-customer-credit-collections-overview.md).

### Upsell

Upselling is the act of selling additional or higher-value products and services to existing customers. It's sometimes confused with *cross-selling*. Learn more at [Sales planning and strategy](#sales-planning-and-strategy).

### Uptake software releases

Staying current with software releases is essential for leveraging new features and improvements. *Administer to operate* facilitates the smooth uptake of software releases, ensuring organizations benefit from the latest advancements.

The *Uptaking software releases* business process area involves seamlessly adopting new features and improvements within Dynamics 365. The platform's continuous updates and releases provide organizations with the latest advancements. Dynamics 365 provides a dedicated Power Platform environment for testing and validating these releases before deployment, ensuring a smooth uptake without disrupting ongoing operations.

### User adoption metrics

User adoption metrics are key performance indicators (KPIs) used to measure the success and effectiveness of user adoption efforts in a technology implementation, such as Dynamics 365. These metrics provide insights into how well users are engaging with the system and whether the organization is achieving its adoption goals. Here are some examples of user adoption metrics:

- Logins and Active Users

    - Metric: Number of logins and active users within a specific time period.

    - Significance: Indicates the frequency of user interactions with Dynamics 365, reflecting the overall engagement level.

- Feature use

    - Metric: Percentage of users actively using specific features or modules within Dynamics 365.

    - Significance: Helps identify which functionalities are most and least used, guiding targeted training efforts.

- Completion of Training Modules

    - Metric: Percentage of users who have completed assigned training modules.

    - Significance: Measures the effectiveness of training programs and identifies areas that may require additional support or resources.

- Survey Feedback

    - Metric: Scores and feedback collected from users through surveys.

    - Significance: Provides qualitative insights into user satisfaction, understanding, and perceived value of Dynamics 365.

- Task Completion Rates

    - Metric: Percentage of successfully completed tasks within Dynamics 365.

    - Significance: Indicates how well users can perform their roles using the system, reflecting overall proficiency.

- Error Rates

    - Metric: Frequency of errors or issues encountered by users during system use.

    - Significance: High error rates may indicate challenges in user adoption and potential areas for improvement or additional training.

- User Support Requests

    - Metric: Number and type of support requests submitted by users.

    - Significance: Identifies common pain points and areas where users may need additional assistance or training.

- Time to Competency

    - Metric: Average time it takes for users to become proficient in using Dynamics 365.

    - Significance: Measures the efficiency of the onboarding and training processes.

- User Engagement with Communication

    - Metric: Interaction rates with communication channels related to Dynamics 365 (e.g., emails, newsletters).

    - Significance:\*Assesses the effectiveness of communication strategies and the level of interest among users.

- Data Accuracy and Completeness

    - Metric: Accuracy and completeness of data entered by users into Dynamics 365.

    - Significance: Reflects the quality of data input and adherence to data management practices.

- Mobile Access and Usage

    - Metric: Percentage of users accessing Dynamics 365 via mobile devices.

    - Significance: Indicates the flexibility of user access and responsiveness to the needs of a mobile workforce.

- Integration with Other Systems

    - Metric: Successful integration and usage of Dynamics 365 with other relevant systems.

    - Significance: Assesses the interoperability of Dynamics 365 within the broader technology landscape.

### User feedback loop

A continuous process of gathering feedback from users regarding their experiences with Dynamics 365, enabling organizations to make timely adjustments and improvements to enhance adoption.

## V

### Variant

See [product](#product).

### Vendor

In Dynamics 365 Supply Chain Management, a vendor is an external entity that supplies goods or services to your organization. When you create a vendor account, you enter information about the vendor. This information is used to automatically enter data in documents and to track activity that involves the vendor.

### Vendor account number

In Dynamics 365 Supply Chain Management, the vendor account number is a unique identifier for a vendor. You can set up account numbers so that they're generated automatically when you create a vendor. Alternatively, configure a number sequence so that account numbers are entered manually.

### Vendor bank accounts

If you must make payments to a vendor bank account, you can enter information about the vendor's bank and bank accounts on the **Vendor bank accounts** page. You can also enter information about validation and payments for the bank account. For example, you can add prenotes to vendor bank accounts. You can then use these prenotes to verify the accuracy of account data, such as routing numbers and account numbers. You must specify a default account for payments to the vendor. However, when you make an actual payment, you can change this account to one of the vendor's other accounts.

### Vendor collaboration portal

With the **Vendor collaboration** module in Dynamics 365 Supply Chain Management, vendors can work with purchase orders, invoices, and also place bids on request for quotations and consignment inventory information. The vendor collaboration module shows a limited set of information about purchase orders, invoices, and consignment stock to external vendor users.

### Viva Learn

A [learning and development platform integrated with Microsoft Viva](/viva), offering personalized and interactive learning experiences for a variety of technology and soft skill development including the use and implementation of Dynamics 365.

## W

### Win/loss analysis

Win/loss analysis is the process of evaluating why deals were won or lost, to improve the marketing process.

### Work breakdown structure (WBS)

A project work breakdown structure (WBS) is a project management tool that adopts a step-by-step approach to complete large projects that have several moving parts. It breaks down the project into smaller components, and integrates scope, cost, and deliverables into a single tool. The Project Management Institute (PMI) defines a WBS as "a deliverable-oriented hierarchical decomposition of the work to be executed by the project team to accomplish the project objectives and create the required deliverables." It organizes and defines the total scope of the project in such a way that each descending level represents an increasingly detailed definition of the project work.

### Work order

A work order helps organizations to understand the maintenance or repair that is needed on an asset or a functional location. The work order assigns the appropriate resources to complete the maintenance request. Jobs associated with work orders help to register consumption details.

For example, you can use a work order to schedule maintenance on a machine. You can also create a work order for inspections, corrective maintenance, and preventive maintenance. In Dynamics 365 Field Service, a work order documents the [maintenance](#maintenance) or [repair](#repair) that an [asset](#asset) or location needs. It assigns the appropriate resources to complete the request, and jobs associated with work orders help register consumption details. Learn more about the work order process in Dynamics 365 Field Service [Work order architecture](/dynamics365/field-service/field-service-architecture).

You can also procure items with work orders. The procurement process typically starts with either a purchase requisition or purchase order request. Often, companies may not have the required items to execute a work order. This is when a purchase request is triggered. You can create a related purchase order or purchase requisition for a work order job in Dynamics 365.

In Dynamics 365 Field Service, the work order is the primary information record that is used to organize information for scheduling and performing service. Work order records hold the critical information that is needed to complete the services. They are used to track the progress of a job or task from start to finish, and can include information such as the job description, the parts and resources that are needed, and the estimated completion time. Dynamics 365 Supply Chain Management and Business Central applications use the term *service order* instead of *work order*.

### Workflow

In the context of Dynamics 365, workflow commonly refers to the system capability of automating business processes, such as the routing of specific business documents (for example, purchase orders, expense approvals, or vendor invoices) to the appropriate person or persons in the organization for approval. You can use the workflow capability in Human Resources to manage employee information and processes, and you can use the configuration of positions and reporting relationships in Human Resources to associate approval workflows with reporting hierarchies in other processes throughout the business.

- Identification numbers
- Courses
- Loaned items
- Human resources actions

When employees are hired, transferred, or terminated, the workflow can include a review process. In this way, a document can be revised, or the terms of an action can be defined as part of the workflow. When the review process is completed, the document or action is completed, and the workflow moves to a final approval step.

### Working time calendar

A working time calendar in Dynamics 365 Human Resources shows the days and hours that employees work in your organization. When an employee submits a time-off request, they don't have to worry about holidays and closures. You can also create working time calendars to assign to resources for production, vendors, customers, and more to help with logistics of your supply chain with Dynamics 365 Supply Chain Management. Learn more at [Create a working time calendar](/dynamics365/human-resources/hr-leave-and-absence-working-time-calendar)

### Write-off

Writing off an asset refers to removing it from the balance sheet when its value has been fully depreciated, or it no longer holds any financial value.

## Y

### Year-end closing

Year-end closing in Dynamics 365 marks the completion of the financial reporting cycle for a fiscal year. This involves finalizing financial statements, making necessary adjustments, and preparing for the start of the next fiscal year.

### Yield

In the context of process manufacturing in Dynamics 365, the term *yield* refers to the quantity of a finished product that is obtained from a specific batch or production run. It's a crucial metric for evaluating production efficiency and determining the actual output in comparison to the expected output that is specified in the formula.

## Z

### Zero-based budgeting

Zero-based budgeting in Dynamics 365 involves building budgets from scratch, requiring justification for each expense. This approach encourages a thorough evaluation of budget needs and aligns expenses with organizational priorities.

## Next steps

Get an overview of all business processes that we have published guidance for at [Dynamics 365 business process documentation](overview.md).

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal authors:

- [Anne Krupke](https://www.linkedin.com/in/annekrupke/) \| FastTrack Solution Architect

- [Rachel Profitt](https://www.linkedin.com/in/rachelprofitt/) \| FastTrack Solution Architect

- [Nikhil Paldhikar](https://www.linkedin.com/in/nikhil-paldhikar-08232211/) \| FastTrack Senior R&D Solution Architect

- Harshad Puthran<!--(https://www.linkedin.com/in/harshadputhran)--> | FastTrack Solution Architect

- [Kody Wildfeuer](https://www.linkedin.com/in/kody-wildfeuer) | FastTrack Solution Architect

Other contributors:

- [Jinal Makwana](https://www.linkedin.com/in/d365lady/) | FastTrack Solution Architect
