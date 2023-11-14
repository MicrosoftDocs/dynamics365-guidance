---
title: Glossary of terms in Dynamics 365 business processes
description: A glossary of terms that are good to know if you work with Dynamics 365 and you're reading the business process guidance.
author: rachel-profitt
ms.author: raprofit
ms.topic: glossary
ms.date: 10/31/2023
---

# Glossary of terms in Dynamics 365 business processes

This article defines some of the common terms and terms that are specific to Dynamics 365 that are used in the business process guidance on Microsoft Learn. It includes guidelines such as capitalization.

In any given industry, there are terms that are industry-specific and very familiar to people in that industry or line of business. But in many languages, there are more than one term for the same task or object. For example, are the people you do business with your *clients* or your *customers*? Learn more in the following sections.

> [!TIP]
> Use CTRL+F to search for a specific term on this page.

Find generic and specific terms across Microsoft products and languages at [Microsoft Terminology Search](https://msit.powerbi.com/view?r=eyJrIjoiODJmYjU4Y2YtM2M0ZC00YzYxLWE1YTktNzFjYmYxNTAxNjQ0IiwidCI6IjcyZjk4OGJmLTg2ZjEtNDFhZi05MWFiLTJkN2NkMDExZGI0NyIsImMiOjV9).

## A

### Accruals

[Accruals](/dynamics365/finance/general-ledger/accruals-overview) are used in accounting to track revenue that's recognized in the period that it's earned in, not when payment is received, and to track expenses (costs) that are recognized when they occur, not when payment is made.

### Acquisition cost

It encompasses all the expenses associated with acquiring the asset and making it ready for use in business operations. The asset acquisition cost includes both direct and indirect costs related to the purchase, delivery, and commissioning of the asset.

### Aging periods

When your collection teams analyze customer balances, they typically need to group customer balances into time periods to determine how far overdue the customer is. These periods might be referred to as aging buckets or aging periods.

Before you can analyze your customer balances in Dynamics 365 Finance, you must [define aging periods](/dynamics365/finance/accounts-receivable/set-up-collections#set-up-aging-period-definitions). If your organization or users want to analyze customer balances in multiple ways, you can define multiple aging periods. The most common way to analyze customer balances is in periods of 30 days, 60 days, 90 days, and more than 180 days. However, you can define aging periods by weeks, months, or quarters as well. Most organizations use aging reports to analyze their customer balances.

> [!IMPORTANT]
> After you define aging periods, Dynamics 365 Finance requires you to run a periodic process to place customer balances into the correct periods for analyzing. Run the [Aging snapshot process](/dynamics365/finance/accounts-receivable/set-up-collections#create-an-aging-snapshot). In most organizations, this process is run once per day as part of a batch operation.

### Amortization

Unlike fixed assets, which are typically *depreciated*, intangible assets are *amortized*. Examples of intangible assets are patents, intellectual property, branding, and so on. Amortization is generally spread across the useful life of an asset in a straight line. Assets that are amortized may not have a resale value.

### Appointment scheduling

Appointment scheduling is the process of blocking time for drivers to drop off and pick up loads at the warehouse.

### Appraisers

Asset appraisers are individuals who leverage their expertise to evaluate the condition, usability, and market demand for these assets in their current state. They are usually involved in assessing the potential financial return or salvage value of assets that an organization is planning to retire, sell, scrap, or otherwise remove from its inventory.

### Asset

An asset is something of value that an organization owns. Related definitions are [fixed asset](#fixed-asset) and [asset classification](#asset-classification).

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

Asset decommissioning refers to the process of formally retiring and stopping the use of an asset. Organizations typically initiate the decommissioning process when an asset reaches the end of its useful life or when it is no longer needed. To avoid any regulatory or compliance issues the assets should be clearly disposed of by the organization.

### Asset disposal

Asset disposal refers to the process of removing assets from an organization. This includes selling, recycling, or scrapping assets that have reached the end of life and no longer align with business goals or have become out-of-date due to technological advancements.

### Asset insurance

Fixed asset insurance is a type of insurance that covers the physical assets of a business, such as buildings, machinery, equipment, inventory, and furniture. Fixed asset insurance protects the business from losses due to fire, theft, vandalism, natural disasters, and other perils. Fixed asset insurance can help the business recover from the damage or loss of its assets and resume its normal operations. Fixed asset insurance can also cover the costs of repairing or replacing the assets, as well as the loss of income or profits due to the interruption of business activities.

### Asset lifecycle stages

Fixed Asset lifecycle stages are the phases that an asset typically goes through from the time it is acquired by a business until it is disposed of or retired. These stages include planning, acquisition, operation and maintenance, and disposal. Each stage has its own accounting, financial, and operational implications for the business. Understanding and managing the fixed asset lifecycle can help businesses optimize their asset performance, reduce costs, and comply with regulations.

- Planning: This stage involves identifying the need for a new asset, evaluating the current assets, and determining the budget and specifications for the asset. Planning also includes forecasting the expected benefits, risks, and costs of the asset over its useful life.

- Acquisition: This stage involves purchasing or leasing the asset from a supplier, installing and testing the asset, and recording its initial value and depreciation method in the accounting system.

- Operation and Maintenance: This stage involves using the asset for its intended purpose, monitoring its performance and condition, and performing regular repairs and upgrades to keep it functional. Operation and maintenance also involve tracking the asset's location, ownership, usage, and depreciation in the accounting system.

- Disposal: This stage involves retiring or selling the asset when it is no longer needed or useful for the business. Disposal also involves removing the asset from the accounting system, calculating its gain or loss on disposal, and complying with any environmental or legal requirements for disposing of the asset.

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

## B

### Baseline

A baseline is a fixed reference point used to compare project performance over time. Project baselines are used by project managers to understand how project scope, schedule, and cost are progressing through the completion of a project.

### Billable hours

The hours worked on tasks that can be charged to clients or customers. Billable hours are often used for invoicing purposes and are directly related to revenue generation. Learn more at [Deliver project work](project-to-profit-deliver-project-work.md) and [Non-billable hours](#non-billable-hours).


### Billing rules

Billing rules were used in [Dynamics AX](/dynamicsax-2012/appuser-itpro/create-billing-rules). In Dynamics 365, they're replaced by [billing schedules](#billing-schedules).

### Billing schedules

[Billing schedules](/dynamics365/finance/accounts-receivable/sb-billing-schedules) are rules that define how and when customers can be invoiced for work on a project. They're based on the terms that are specified in the project contract.

### Budget forecast

A budget forecast is the expected expenditure or revenue per budget line during the period that is defined on the budget line. The forecast equals the budgeted value when the budget is approved. If actual costs are more than the forecasted cost for a budget line, the forecast cost will be made equal to the actual cost.

## C

### Campaign analytics

The process of evaluating data and metrics for a marketing campaign to derive performance insights and optimization opportunities.

### Campaign budget

The defined marketing expenditure allocated to a specific marketing campaign.

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

A category hierarchy refers to a way of organizing and structuring products or items into a hierarchical structure based on their characteristics, attributes, or relationships. This hierarchy allows for efficient management, classification, and navigation of products within Dynamics 365. Typically, the category hierarchy is set up and maintained in Dynamics 365 Supply Chain Management. With [dual-write](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-home-page), you can then share the setup with other applications such as Dynamics 365 Sales, Customer Insights, Customer Service, or Field Service.

### Centralized resource allocation

For organizations that centralize the allocation for resources to projects, [project managers](#project-manager) define [resource requirements](#resource-requirement) at the project level, while the fulfillment of the resource requirements is delegated to a [resource manager](#resource-manager). Project managers can accept or reject resources that the resource manager proposes.

### Churn

When a customer ends a relationship or stops engaging with a company. CRM helps prevent churn.

### Close the deal

Closing the deal refers to the process of finalizing the agreement with a client or decision-makers after an opportunity is won. It involves confirming acceptance, negotiating terms if necessary, preparing and signing the contract, and setting up the required arrangements for the project or business.

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

### Consume materials

Material consumption refers to the use of items in a project. You can register the consumption of items in several ways. You can sell or purchase items from a project, or reserve items for a project. You can order items from the company's inventory for consumption on a project or purchase items from an external vendor. Item consumption is recorded as a posting that registers that the item was used in the project.

### Correcting entry

A correcting entry fixes a mistake that was posted in the accounting books. You must make correct journal entries as soon as you find an error. Correcting entries ensures that your financial records are accurate.

### Cost

In business and accounting, cost refers to the monetary value of resources that are consumed or sacrificed to achieve a particular objective or goal. It's the amount of money that a business spends on producing a product or providing a service. [Defining product and service costs](/dynamics365/guidance/business-processes/product-service-define-cost-overview) is essential for any organization that wants to understand and manage its finances effectively.

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

A cost budget represents a point-in-time snapshot of the estimated cost for the project. All actual costs that are incurred on the project, among time, materials, and expenses are compared against the cost budget to track the costs on the project.

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

### Customer credit group

A [customer credit group](/dynamics365/finance/accounts-receivable/cm-customer-credit-groups) is a group of customers that have a shared credit limit. The individual credit limit on a customer invoice account is also considered. You can select members of a customer credit group from different legal entities. When you decide how to structure your customer accounts, consider how credit limits are managed. For example, a customer account can have only one credit limit. If a customer account has many delivery addresses that each require a different credit limit, consider whether they should be separate customer accounts. Then you can use a customer credit group to create an overall credit limit across the customer's accounts.

### Customer journey

The end-to-end experiences and touchpoints a customer has with a brand. CRM optimizes journeys.

### Customer lifetime value (CLV)

The total revenue generated from a customer over the entire relationship timeline. Maximizing CLV is key.

### Customer Relationship Management (CRM)

Strategies and processes for managing customer interactions and data across the customer lifecycle to maximize loyalty and growth.

### Customer satisfaction (CSAT)

Metrics that measure a customer's happiness with a company's products, services, and interactions.

## D

### Date effectivity

For some records, you can specify changes that take effect after a specific date. Job classification, compensation, position, and worker assignments are examples of date-effective records.

### Deferrals

Deferrals are used in accounting to track revenue that's received but not yet earned, also known as unearned revenue. Organizations use deferrals to recognize revenue before expenses (costs) occur. You can [recognize deferred revenue in Dynamics 365 Finance](/dynamics365/finance/accounts-receivable/revenue-recognition-recognize-deferred-revenue) and [defer revenues and expenses in Dynamics 365 Business Central](/dynamics365/business-central/finance-how-defer-revenue-expenses).

### Deliverables

Deliverables are all outputs of your project as defined by the [scope](#scope). Deliverables can be a product, a service, or a capability.

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

### Direct expenses 

Direct expenses are those that are directly tied to the project itself such as specialized software, travel and meal expenses, mileage, and per-diem.

### Discounts

Percentage or dollar reductions in the quoted price. Discounts can be applied to incentivize customers.

### Dock management

Dock management is the process of assigning loads to dock doors in a warehouse. In Dynamics 365 Supply Chain Management, you manage docks by using the [driver check-in/check-out](/dynamics365/supply-chain/transportation/tasks/register-driver-check-check-out-appointment) functions.

### DUNS numbers

The Data Universal Number System (DUNS) identifies companies in dozens of countries/regions with a unique nine-digit number. The number is issued by Dun & Bradstreet, a provider of commercial data, analytics, and insights for businesses.

You can specify the DUNS number on a customer record in Dynamics 365 Finance. You can use APIs provided with Finance to build integrations with Dun & Bradstreet for your specific business requirements. If you use Dynamics 365 Customer Insights, you can [enrich company profiles with Dun & Bradstreet data](/dynamics365/customer-insights/enrichment-dnb) using a native integration.

## E

### Engineering change management (ECM)

Engineering change management (ECM) is the process of making sure that changes to a product's design or engineering specifications are properly reviewed, approved, and implemented in a controlled and consistent manner. ECM helps maintain product quality, reduce the risk of errors, and minimize the impact of changes on production schedules and costs.

Dynamics 365 Supply Chain Management includes an [engineering change management](/dynamics365/supply-chain/engineering-change-management/product-engineering-overview) module.

### Estimation to complete

Estimation to complete is an estimation of funds required to complete the remaining work of a project. The project manager will track this measure along the project that shows the remaining cost you expect in order to complete a project.

### Expense policies

An expense policy is a formal set of guidelines that clearly outlines what constitutes an approved expense and what is not. This helps employees decide what they will be able to expense on the project.

## F

### Finished good

Finished goods are products that are in their final state and ready to be sold. Their final state is often the result of completing a production process. In some cases, companies may buy finished goods to resell.

A finished good is often referred to as a product. In Dynamics 365 Supply Chain Management, a [product](/dynamics365/supply-chain/pim/product-information) can also encompass raw materials and subassemblies.

### Fixed asset

In accounting, a fixed asset is any long-term asset whose cost expiration is recognized over more than one year. Related definitions are [Asset](#asset) and [Asset classification](#asset-classification).

### Fixed-price projects

Projects can be invoiced on either a fixed-price basis or a [time-and-material](#time-and-material-projects) basis. For a fixed-price project, the customer invoice amount is based on [billing schedules](#billing-schedules). Fixed-price projects can be invoiced per project or per project contract. Revenue for a fixed-price project can be calculated and posted throughout the project by using the completed percentage method. Alternatively, revenue can be calculated and posted when the project is completed, by using the completed contract method. Companies can often benefit from using the value of the work in process (WIP) to calculate the degree of completion of a project or a group of projects.

Learn more at [Manage project financials overview](project-to-profit-manage-project-financials-overview.md). 

### Forecast

A forecast is a prediction about the future. Forecasts are expected to be incorrect to a certain degree, but to be useful they should be as accurate as possible. Sometimes forecasts are created based on statistical calculations. In other cases, they're manually created based on shared information; for example, information that's incorporated from a customer forecast. Companies often create different kinds of forecasts as part of their long-term planning cycles.

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

MAPE is expressed as a percentage, as indicated in the equation in the diagram. The lower the MAPE value is, the more accurate the forecast likely is. In general, a MAPE of 20 percent or less is considered acceptable, but 10 percent would be even better. The best MAPE value that an organization can achieve is going to be dependent on the amount of historical data and how volatile the values are.

:::image type="content" source="media/forecast-accuracy-MAPE-calculation.png" alt-text="Charts that illustrate how MAPE is calculated.":::

### Forecast dimensions

The attributes that are included when Azure Machine Learning generates a forecast are called dimensions. **Company**, **Site**, and **Allocation key** are mandatory dimensions. If a more detailed forecast is required, the model can include the dimensions **Country/region**, **State**, **Customer group**, **Customer account**, **Warehouse**, **Inventory status**, and **Item number and dimensions**.

### Free text invoice

A [free text invoice](/dynamics365/finance/accounts-receivable/create-free-text-invoice-new) is an [invoice](#invoice) that isn't based on a sales order. Instead, you create a free text invoice manually. You can't enter an item number on this kind of invoice, but it can include free-text descriptions, sales amounts, and sales tax if appropriate. Assign a main account for each invoice line. To distribute the amounts to multiple ledger accounts, select the **Distribute amounts** action on the invoice. The customer balance is posted to the summary account from the posting profile that's used for the invoice.

### Freight reconciliation

Freight reconciliation is the process of comparing and reconciling freight bills (estimated charges) with carrier invoices (actual charges). You can [manually manage the process](/dynamics365/supply-chain/transportation/tasks/set-up-automatic-freight-reconciliation) in the **Transportation management** module in Dynamics 365 Supply Chain Management. Alternatively, you can set up integration with a service to automatically manage freight reconciliation.

### Funding source

A funding source is the entity that [funds work on a project contract](/dynamics365/project-operations/prod-pma/project-contracts#funding-for-project-contracts). This entity can be an internal organization or an external invoice account (customer or grant).

## G

### Granularity attribute

A granularity attribute is the unique combination of [dimension values](#forecast-dimensions) that represents the level of detail at which a [forecast](#forecast) is generated.

## I

### Index revaluation
Organizations use indexation to adjust multiple fixed asset values. Revaluation of fixed assets can consist of appreciations, write-downs, or adjustments in value of assets. Some companies may revalue assets more often than others. The purpose of revaluation is to accurately reflect the fair market price of the asset.

### Indirect costs

Indirect costs are expenses that aren't related to production or manufacturing, such as the salaries of administrative employees and the cost of advertising. Contrast with [overhead costs](#overhead-costs).

### Indirect expenses

Indirect expenses are those that are not directly tied to the project but may be distributed across multiple projects. Examples include administrative costs, support staff, rental fees, and utility costs.

### Intercompany expenses

A worker who is employed by one legal entity in an organization might perform work for another legal entity in the same organization. You can use intercompany expenses to assign the worker's expenses to the legal entity for which the work was performed. The legal entity that employs the worker is called the loaning legal entity. The legal entity for which the worker incurs expenses is called the borrowing legal entity.

### Interest notes

Many organizations charge a fee to customers for late payment of [invoices](#invoice). An interest note is a statement of such a fee. Charging interest helps businesses offset the cost of collecting overdue invoices while encouraging customers to pay their invoices in a timely manner. Depending on the country/region and the industry, customers who don't pay for products or services they received can face legal consequences.

Dynamics 365 Finance automates the [process of calculating and collecting interest](/dynamics365/finance/accounts-receivable/tasks/process-interest) on overdue payments. Organizations can use case management in Dynamics 365 Finance and Customer Service to help manage the legal escalation of overdue invoices.

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

## K

### Key entities

In Dynamics 365 Customer Insights and Sales, key entities are the most important types of information to [track and manage](#lead-and-opportunity-management) throughout the [sales process](#sales-process-and-stages).

- [**Leads**](#lead) are potential customers, people who have shown interest in your products or services but haven't been [qualified](#lead-and-opportunity-management) as a viable prospect.

- An [**opportunity**](#opportunity) is a qualified lead, a potential customer who has a higher likelihood of making a purchase, and who requires further engagement and nurturing by the sales team.

- **Accounts** are the organizations that you do business with or plan to do business with. They typically represent a customer or potential customer.

- **Contacts** are the individual people who are associated with an account, such as decision-makers, influencers, or users of your products or services.

## L

### Lead

A lead is a potential customer, a person who has shown interest in a product or service but hasn't purchased yet. A *marketing-qualified lead* is a lead deemed viable by marketing based on activity, demographics, and so on. A *sales-qualified lead* is a lead vetted by sales as fitting ideal customer profile and ready for contact. A *marketing-qualified lead (MQL)* is a lead determined to match target customer profile and be sales-ready based on campaign interactions. Learn more at [Identify and qualify leads overview](prospect-to-quote-identify-qualify-leads.md).

### Lead and opportunity management

Tracking and managing potential customers and sales opportunities throughout the [sales process](#sales-process-and-stages), from initial contact to closing the deal, is called [lead and opportunity](#key-entities) management. It involves three processes:

- **Lead scoring** is a system for ranking leads based on their likelihood of making a purchase. It uses criteria such as engagement, demographics, and behavior. Lead scores help sales teams prioritize their efforts on the most promising prospects.

- **Lead qualification** is the process of determining whether a lead has the potential to become a customer. It's based on such factors as level of interest, budget, and purchasing authority.

- **Opportunity management** is the practice of guiding and nurturing qualified leads through the sales process, with the goal of converting them to customers by addressing their needs, concerns, and objections.

### Lead conversion

The act of transitioning a qualified lead into a sales pipeline opportunity.

### Lead enrichment

The process of augmenting lead records with additional data from various sources.

### Lead nurturing

Ongoing communication with leads to develop awareness and interest over time.

### Lead score

A numeric rating assigned to a lead to indicate sales-readiness based on engagement, profile fit, and so on.

### Lease contracts

A lease contract is a legal document that describes the terms under which the owner of an asset (the lessor) agrees to let a user (the lessee) use the asset. The lessee, in turn, agrees to uphold the terms. 

Dynamics 365 Finance offers [asset leasing](/dynamics365/finance/asset-leasing/asset-leasing-homepage) capabilities that comply with international accounting standards (IFRS 16) and US GAAP standards (ASC 842).

### Lease payment schedule

A lease payment schedule is the predetermined timeline and structure for making lease payments under a lease agreement. It summarizes the specific amounts and timing of the payments that the lessee is obligated to pay to the lessor throughout the lease term.

### Leased assets

Leased assets are [assets](#asset) that a [lessor](#lessor) allows a lessee to use according to terms that both parties agree to. They differ from owned assets in that the user doesn't purchase the asset outright but is merely "renting" it. A leased asset can be a house, an apartment, or a piece of equipment.

### Legal entity

A legal entity is a separate entity recognized by the law, capable of entering contracts and engaging in business activities. It typically consists of owners/shareholders, management, assets, liabilities, and a distinct legal structure.

### Lessee

A lessee is an individual or entity that has a lease agreement with a lessor to obtain the right to use or lease an asset. The lessee has the temporary right to use the assets in exchange for periodic payments.

### Lessor

A lessor is an individual or entity that owns an asset and grants the right to use or lease that asset to another party in exchange for rental payments. In leasing agreements, the lessor is the party that maintains ownership of the asset while allowing the lessee to utilize it for an agreed duration.

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

### Mandatory credit limit

The **Mandatory credit limit** flag on a customer account forces the use of the account's [**Credit limit**](#credit-limit), whether or not the customer is in a [credit limit group](#customer-credit-group). If the value of **Credit limit** is set to 0.00 and the **Mandatory credit limit** flag is set to Yes, the customer effectively has a credit limit of 0.00, and all orders are placed on [credit hold](#credit-hold).

### Manufacturing execution system

A manufacturing execution system (MES) is software that supports the management and execution of a production process in real time.

In Dynamics 365 Supply Chain Management, it's the [**Production floor execution**](/dynamics365/supply-chain/production-control/production-floor-execution-use) module, which has a touch-friendly interface you can use to start production, record progress, consume materials, request maintenance, and perform other production tasks. Dynamics 365 also has a framework for [integrating a third-party MES](/dynamics365/supply-chain/production-control/mes-integration) with the **Production** module.

### Margins

The profit margin or percentage on a quoted deal. Visibility into margins allows profitable quoting.

### Marketing campaign

A strategic marketing effort across one or more channels over a period of time to promote a product, service, or brand. A *multi-channel campaign* leverages multiple channels such as email, social media, and events, to reach prospects. 

### Merchandising

In Dynamics 365, merchandising is the strategic planning, management, and execution of various activities related to product offerings, pricing, promotions, and inventory management. The goal of merchandising in Dynamics 365 is to optimize the presentation and availability of products to drive sales, enhance customer experience, and improve overall business performance.

### Modes of manufacturing

Dynamics 365 Supply Chain Management supports four high-level categories of production: discrete, process, lean, and project-based.

- [**Discrete manufacturing**](https://community.dynamics.com/blogs/post/?postid=13f0b0ac-6755-482e-ab73-9fcc1b55380a) refers to production that results in distinct items; for example, products that are tracked in eaches, boxes, rolls, and so on. Industries that commonly use discrete manufacturing include apparel, furniture, and electronics.

- **Process manufacturing**, also known as continuous or batch production, refers to processes that result in items that are tracked by volume or weight, or processes that may have multiple outputs, also known as co-products and by-products. Industries that commonly use process manufacturing include chemical and plastics, food and beverage, and pharmaceuticals and life sciences.

- [**Lean manufacturing**](/dynamics365/supply-chain/production-control/lean-manufacturing-overview) is less about the kind of item that's produced and more about how. Lean is an industry-standard set of practices that's designed to maximize productivity and minimize waste in the production process. It's often used in repetitive production processes and focuses on identifying value. It originated in the automotive industry and is also common in the printing and HVAC industries. Dynamics 365 Supply Chain Management supports lean concepts like value streams, production flows, and kanbans.

- [**Project-based manufacturing**](/dynamics365/project-operations/), also known as job shop manufacturing, refers to items that are custom-made, take a long time to make, or involve a large number of steps to produce. It allows for a more granular billing schedule than other types of production, using either predefined milestones or the passage of time. Industries that commonly use project-based manufacturing include equipment and machinery production, pharmaceuticals, and construction. Projects are also often used to track trial runs of new products and the associated research and development costs.

- **Mixed-mode manufacturing** reflects that businesses aren't restricted to a single type of manufacturing. For example, the pharmaceutical industry commonly uses both process and project-based production. When a business uses multiple modes, it's referred to as a mixed-mode manufacturer.

## N

### Non-billable hours

The hours worked on tasks that are not directly chargeable to clients. These hours are essential for project management, internal meetings, training, and other non-client-facing activities. Learn more at [Deliver project work](project-to-profit-deliver-project-work.md) and [Billable hours](#billable-hours).

## O

### Opportunity

An opportunity is a [lead](#lead) that's been [qualified](#lead-and-opportunity-management), or determined to have the potential to generate revenue. In Dynamics 365, an opportunity typically includes a description of the customer's requirements, the products or services they're interested in, the potential revenue, and the estimated closing date. Opportunities can be *scored* based on their potential, and they can be *nurtured* with ongoing communication to develop the opportunities.

### Overhead costs

While all overhead costs are [indirect costs](#indirect-costs), not all indirect costs are overhead costs. Overhead costs specifically refer to indirect costs that are related to production or manufacturing activities, such as rent for the production facility, maintenance and repairs of production equipment, and the salaries of production supervisors.

## P

### Per-diem

Per-diem refers to the daily allowance paid to employees for expenses incurred while traveling for work. Depending upon company policy, these expenses can include lodging, meals, and other incidental expenses.

### Planning

Planning is the process of identifying goals and determining the actions to attain them. Common types of planning include:

- **Strategic and operational planning** refers to separate processes that together encompass a company's long-term strategy and how it expects to execute it. A strategic plan typically details the goals the organization wants to achieve through its business processes and the actions and current and future resources it believes will accomplish them. An operational plan helps organizations evaluate and plan for the day-to-day needs of the business, such as operating expenses and workforce requirements.

- **Demand planning** is the process of using historical data and forecasts to balance inventory on hand with customer demand to maintain an optimal level.

- **Supply planning** helps an organization ensure it has sufficient supplies to meet forecasted demand.

- **Capacity planning** helps an organization schedule its production processes realistically.

### Positions

A position is an individual instance of a [job](#jobs). Positions are an important element of the lower level of an organization hierarchy. For example, the "Sales manager (East)" position is just one of the positions that's associated with the "Sales manager" job. Positions exist in a department and are assigned to workers. Every position has a length of time that it's effective for.

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

Catalogs of available products/services with assigned prices. Used to add items to quotes.

### Product category

A product category is a logical grouping of the products that a business sells, based on common characteristics, attributes, features, or usage. Product categories help both businesses and customers quickly identify and locate specific types of products within a larger inventory.

Product categories can be broad or specific, depending on the size and complexity of a business's product offering. Some businesses may have only a few product categories, while others may have dozens or even hundreds. In addition to organizing products for customers, you can use product categories to manage inventory, track sales, and analyze business performance. Ultimately, product categories enhance organization, navigation, and customer experience by providing a structured way to manage and present products.

For example, a clothing retailer might have product categories such as the following list:

- Men's Clothing
- Women's Clothing
- Kids' Clothing
- Shoes
- Accessories

Similarly, an online electronics store might define product categories such as the following list:

- Electronics

    - Smartphones

    - Laptops

    - Tablets

    - Wearable Devices

- Accessories

    - Phone Cases

    - Laptop Bags

    - Screen Protectors

In this scenario, *Electronics* and *Accessories* are main categories, and the subcategories provide further granularity. This hierarchy helps customers quickly locate the type of product they are interested in and aids the store's internal operations for inventory management and pricing.

The specific attributes and characteristics used to define a product category can vary based on the business's offerings and the goals of categorization. 

In Dynamics 365 Commerce and Supply Chain Management, product categories are also known as [product hierarchies](#product-hierarchy). With the hierarchal structure of product categories, you can define a systematic and organized presentation of products, making it easier for users to work with products in various processes such as sales, marketing, inventory management, and reporting. Learn more at [Create a hierarchy of product classification in Supply Chain Management](/dynamics365/supply-chain/pim/tasks/create-hierarchy-product-classification) and [Manage product categories and products in Commerce](/dynamics365/commerce/category-management-product-creation). In Dynamics 365 Sales, you use [product families](#product-family) for the same purpose.

### Product family

In Dynamics 365 Sales, Customer Service, Field Service and Customer Insights, a [product family](/dynamics365/sales/create-product-family) is a group of similar products. You can create a hierarchy of product families to make it easier to manage products. You can use [product categories](#product-category) for the same purpose in Dynamics 365 Supply Chain Management.

### Product hierarchy

A product hierarchy, also known as a product classification or product taxonomy, is a structured system for organizing and categorizing products within a business or organization. It involves creating a hierarchical structure that groups products based on common attributes, characteristics, features, or relationships. This hierarchy helps businesses manage and present their products in a more organized and understandable manner. Learn more at [Create a hierarchy of product classification in Supply Chain Management](/dynamics365/supply-chain/pim/tasks/create-hierarchy-product-classification) and [Manage product categories and products in Commerce](/dynamics365/commerce/category-management-product-creation).

### Product lifecycle management (PLM)

[Product lifecycle management](/dynamics365/supply-chain/pim/product-lifecycle) (PLM) is the process that an organization uses to manage a product from its initial design and development through its retirement and disposal. The goal of PLM is to increase the efficiency of the product development process, reduce time to market, and improve product quality and profitability by managing and organizing all product-related information in a central location. Product-related information includes specifications, engineering designs, bills of materials or formulas, production schedules, and supply chains.

PLM typically involves the following stages in the life of a product:

1. **Concept**: An initial concept or idea for a product is explored and developed.

1. **Design**: The concept is turned into a design that considers factors such as functionality, manufacturability, and cost.

1. **Development**: The product is developed in accordance with the design, tested, and any necessary modifications or adjustments are made.

1. **Launch**: The product is introduced to the market.

1. **Growth**: The product gains acceptance in the market and sales and revenue increase.

1. **Maturity**: The product reaches its peak sales and revenue and may face increased competition or market saturation.

1. **Retirement**: Sales and revenue decline, and the product is retired or replaced by a newer model.

PLM can refer to a system or the use of specific software tools such as Dynamics 365 Supply Chain Management.

### Production journals

Production journals are the journals that are posted against a production or batch order. They include the following types:

- **Pick lists** record the materials that are consumed in a production or batch order. Information that's recorded in a pick list includes part numbers, the quantity of materials consumed, whether the inventory is tracked by lot or serial number, and the lot number and serial numbers of the materials that are consumed. Pick lists can also be used to record raw materials scrap.

- **Route cards** record the production resources&mdash;the labor, machines, and tools&mdash;that are used to make items for a specific production or batch order. Information that's recorded in a route card includes the list of resources, the amount of time that a resource was used, and the amount or quantity of finished product that a resource produced. Route cards can also be used to record raw materials scrap.

- **Job cards** record the start and stop times of operations in a production or batch order to calculate the actual cost of labor and machines. They can be automatically created and posted by user interactions with the production floor execution interface.

- **Report as finished** records the items that are produced in a production or batch order. Information that's recorded for production orders includes the finished good or subassembly item, the quantity of finished good produced, the scrap quantity produced, and whether the production order is complete. Batch orders track the same information, and also support reporting multiple items as outputs of the production process, either co-products or by-products.

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

A project budget is the total projected costs needed to complete a project over a defined period of time. It's used to estimate what the costs of the project will be for every phase of the project. Creating a project budget is a critical part of the project planning process. The project budget will include such things as labor costs, material procurement costs and operating costs. It's not a static document, and it can be reviewed and revived throughout the project.

### Project contract

The [project contract](/dynamics365/project-operations/prod-pma/project-contracts) is a formal written agreement between an organization, the contractor, and a client, the buyer, that defines the terms and conditions of a project or business transaction. It includes details such as scope of work, deliverables, timelines, payment terms, and responsibilities of both parties.

In Dynamics 365, a project that will be invoiced must be associated with a project contract. Settings for a project contract apply to all projects and subprojects that are associated with it. A project contract can specify one or more sources of funding. You can invoice one or more projects at the same time and make sure that a uniform invoicing procedure is applied for each subproject in a project structure.

### Project controller

The project controller works directly with the project manager to help define the project's goals and objectives. They create and maintain a project budget and schedule, analyze progress reported against the work schedules and recommend actions to improve progress.

### Project delivery

The phase in project management where the planned project outcomes, products, or services are provided to stakeholders or clients according to the project's objectives and scope.

### Project estimate

A project estimate is a projection of the cost and schedule of work on a project. Project estimates can be binding or not. Learn more at [Manage project financials overview](project-to-profit-manage-project-financials-overview.md).

### Project manager

A [project manager](#centralized-resource-allocation) is the individual responsible for planning, organizing, executing, and controlling all aspects of a project, from initiation to completion. Project managers are accountable for achieving a project's objectives within the constraints of scope, time, cost, quality, resources, and risk as defined in the [project contract](#project-contract).

### Project phases

The Project Management Institute (PMI) created a 5-phase model that groups different activities throughout the project management lifecycle. The five phases are project initiation, project planning, project execution, project monitoring & control and project closure.

### Project resource

A project resource is an asset, material, tool, or personnel required to run and complete a project.

### Project task

A specific unit of work within a project that contributes to the overall completion of the project's objectives. Tasks are individual activities or assignments that need to be accomplished to move the project forward. Each task is defined by its scope, duration, resources required, and any dependencies it might have on other tasks.

### Project type

In Dynamics 365, projects can be categorized as one of six types depending on the purpose of the project. Each project type is set up differently for costs and revenue recognition. The following [project types](/dynamics365/project-operations/prod-pma/overview-project-management-accounting#create-projects) are available in Dynamics 365 solutions:

- Time and material
- Fixed-price
- Investment
- Cost
- Internal
- Time

### Proposal

The document that outlines the scope of work, deliverables, timeline, and estimated cost of a project is called a proposal. A proposal is presented to the customer for review and consideration. It may be subject to negotiation before a final agreement is reached.

### Provider

A provider is a connection point in a supply chain. In the context of Intelligent Order Management in Supply Chain Center, a provider enables integration with other systems by presenting calls between systems as actions that can trigger events that drive orchestration.

## Q

### Quote

A document presenting a customer's potential order for products/services along with proposed prices. Quotes allow sales teams to provide estimates to prospects during the sales process. Quotes must be *approved* to make sure that they align with the business policies. Organizations typically have a process for approving a finalized quote before it's sent to the customer or prospect.

Quotes can be *revised*, meaning that adjustments are made to a quote before finalizing based on the prospect's feedback. Revisions can optimize pricing.

## R

### Rating

Rating is the process of retrieving a freight charge from a carrier contract.

In Dynamics 365 Supply Chain Management, the [Transportation management module](/dynamics365/supply-chain/transportation/transportation-management-overview) supports freight carriers. If you use parcel carriers, you often need an integration project.

### Raw material

Raw materials are the inputs to a production process, which are used to create subassemblies and finished goods. Raw materials are commonly referred to as components, ingredients, or bulk materials.

### Reconcile invoices

Invoice reconciliation is the process of comparing and matching supplier invoices with purchase orders and receipts to ensure accurate payment and track manufacturing costs.

### Repair

Repair involves restoring a broken asset to bring it to a steady operational state. In repair of intangible assets, especially impaired software, the organization might need more resources to fix the issue, such as consultants. They might also need licenses to get access to capabilities in software. Learn more at [Maintain and repair internal assets ](acquire-to-dispose-maintain-repair-internal-asset.md).

### Replenishment

[Replenishment](/dynamics365/supply-chain/master-planning/planning-optimization/replenishment-methods-quantity-modification) refers to sourcing inventory to a location, either by moving it from one location in the company to another or by purchasing or producing it. [Supply planning](#planning) centers on making decisions about [how inventory will be replenished](inventory-to-deliver-overview.md) to meet expected or actual demand.

### Reporting relationships

Reporting relationships define hierarchies of positions and are reflected in organizational charts. A reporting relationship can be used to route documents through a workflow.

If your organization uses a matrix hierarchy or another custom hierarchy, you can set up hierarchy types in Dynamics 365 and add reporting relationships to positions for each type. For example, an employee might be a part of a project team that has an informal reporting relationship to a project supervisor.

### Requirement

Requirement is a capability that is required to be present in a product, service, or result to satisfy a business need.

### Resource booking

Bookings are the hard or soft allocation of resources to a project. Hard bookings consume a resource's capacity. Bookings represent organizational concepts for teams so that they can understand how resources will be engaged across various projects. Dynamics 365 Project Operations considers bookings a project-level concept.

### Resource characteristics

Resource characteristics refer to the qualities, attributes, or traits that are associated with the resources a project uses. They help [project managers](#project-manager) assess the suitability of resources for various project tasks and activities. Understanding resource characteristics is essential for effective resource selection, allocation, and use.

### Resource manager

A [resource manager](#centralized-resource-allocation), also known as a resource coordinator or resource planner, is the individual responsible for managing the allocation and use of resources in an organization. Resource managers oversee the availability, deployment, and scheduling of resources to support various projects, departments, or operational activities.

### Resource requirement

Resource requirements refer to the types and quantities of resources needed to run and complete a project within defined scope, timeline, and quality standards.

### Revenue budget

A revenue budget represents a point-in-time snapshot of estimated revenue for the project. All unbilled and billed sales on the project are compared against the revenue budget, to track the revenue on the project.

### Risk scores

A risk score is a measure of a customer's credit worthiness. It's used to define a customer's credit management blocking and exclusion rules. The risk score and rules that you define can be used to automatically calculate a customer's credit limit. You can also define risk assessments that can be assigned to customers based on their risk score.

### Routing

Routing is the process of assigning a route to a [load](#load). Routes are typically configured when multiple modes of transportation are required or preferred to move goods through the supply chain (for example, by truck, rail, or ocean).

## S

### Sales channels

Sales channels are the methods used to sell products and services to customers. Examples are direct sales, partners, resellers, retail, e-commerce.

### Sales compensation

Sales compensation includes commissions, bonuses, and incentives offered to motivate certain seller behaviors and achievements.

### Sales documentation and materials

Sales documentation and materials are resources that sales teams use during the [sales process](#sales-process-and-stages). They can include the following types of documentation:

- A **quote** outlines the price and terms for products or services that a customer is interested in purchasing.

- A [**sales order**](#sales-order) details the products or services that a customer has agreed to purchase. It includes pricing, quantities, and delivery details.

- **Activities** are the tasks, appointments, phone calls, emails, and other forms of communication and interaction that are part of the sales process. They're typically used to track and manage engagement with [leads](#lead), [opportunities](#opportunity), and customers.

- **Sales literature** encompasses marketing materials like brochures, whitepapers, presentations, and case studies that salespeople can use to support their sales pitches and educate prospects about a company's products or services.

### Sales enablement

Sales enablement refers to training, content, tools, and coaching provided to sales teams to improve performance.

### Sales order

A sales order is a document created by the seller. A sales order helps the seller keep track of the orders they fulfill and manage their resources accordingly. Typically, it's generated because of winning a sales quotation or as a response to receiving a purchase order from a buyer specifying the details about the product or service along with price, quantity, delivery date, buyer details like the shipping address, mode of payment and terms and conditions. The sales order confirmation generated from the sales order represents the commercial commitment towards a buyer. It's sent in response to the buyer's purchase order when one exists. On the buyer's side, the sales order confirmation is typically referred to as a purchase order confirmation. Learn more at [Create sales orders](/dynamics365/supply-chain/sales-marketing/tasks/create-sales-orders) in the docs for Dynamics 365 Supply Chain Management.

The sales order confirmation that's generated from the sales order represents the seller's commitment to a buyer. It's sent in response to the buyer's purchase order when one exists. On the buyer's side, the sales order confirmation is typically referred to as a purchase order confirmation.

### Sales planning and strategy

Sales planning and strategy describes the process of developing an approach and plan for achieving sales goals and objectives. It includes identifying target markets, setting sales targets, and determining sales tactics and resources.

- **Sales forecasting** is the process of predicting future sales revenue based on historical data, market trends, and other factors, to help sales teams set targets and plan their activities accordingly.

- **Cross-selling** and **upselling** are sales strategies that are designed to increase revenue and customer lifetime value. Cross-selling involves offering more products or services to existing customers, whereas [upselling](#upsell) involves encouraging them to upgrade to a higher-priced product or service.

### Sales process and stages

The sales process is a series of steps that a sales team follows to identify, engage, and close deals with potential customers. It includes prospecting, qualification, needs analysis, presentation, handling objections, closing, and follow-up.

- A	**sales process** is a series of steps that a salesperson follows to guide a lead or prospect through the stages of becoming a customer, from initial contact to closing the sale.

- A **sales funnel** or **sales pipeline** is a visual representation of the way that leads and opportunities move through each stage in the sales process.

- The **sales cycle** is the time that it takes for a lead to move through the sales process, from initial contact to a closed sale. It can vary depending on factors such as the complexity of the product or service and the customer's decision-making process.

### Sales targets

Sales targets are specific measurable goals set for revenue and sales volume over a period of time. Targets are set at the company, business unit, team, and individual levels.

### Sales territories

Sales territories are geographic areas or accounts assigned to salespeople. Territories optimize market coverage and account focus.

### Sales tools and technologies

Sales tools and technologies are software and hardware solutions that help sales teams manage and automate aspects of the sales process, such as managing customer relationships, generating leads, and creating sales analytics.

- **Sales automation** refers to the use of software tools and technologies to automate repetitive tasks and activities in the sales process, so that sales teams can focus on more strategic activities, such as building relationships and closing deals.

- A **dashboard** is a visual interface that displays key performance indicators (KPIs) and other data that's related to the sales process, so that sellers and managers can monitor and analyze sales activities.

- **Customer relationship management** (CRM) is a system and process for managing interactions with leads, prospects, and customers throughout the sales process, with the goal of building long-term relationships to improve customer satisfaction and increase sales.

### Schedule

Schedule aims to ensure the timely completion of a project. It consists of defining the tasks to accomplish, the priority, the deadlines, and the sequence.

### Scope

A project's scope defines the boundaries of the project. The scope is a list of specific project goals, deliverables, tasks, costs, and deadlines.

### Scrap

Scrap refers to any excess or unusable material that's identified during the production process. Scrap can be raw materials, subassemblies, or even finished products that don't meet specifications. Typically, it's disposed of, but in some cases it can be reworked or reused in the production process. For example, metal shavings from the fabrication process may be melted and worked into a new product.

Scrap can also describe labor or other production resources that result in unusable products or otherwise don't contribute to the subassembly or finished good production. For example, if a subassembly is scrapped, the labor associated with producing that subassembly would also be considered scrapped.

### Segmentation

Segmentation in Dynamics 365 is the practice of dividing a target audience or market into distinct and homogeneous groups based on shared characteristics, behaviors, preferences, or needs. The purpose of segmentation is to gain a deeper understanding of the diverse customer base and to tailor marketing, sales, and business strategies to effectively reach and serve each segment.

Segmentation helps businesses recognize that not all customers are the same and that different groups have unique preferences and requirements. By identifying and understanding these segments, companies can deliver more personalized and relevant experiences, products, and messages to different customer groups. Dynamics 365 Customer Insights - Journeys supports the creation of segments to help manage customer journeys. Learn more at [Create segments and lists to establish target markets](/dynamics365/marketing/segmentation-lists-subscriptions).

### Service

A [service](/dynamics365/supply-chain/service-management/service-management-home-page) is an intangible offering that a business provides to its customers. Unlike physical [products](#product), services can't be held or touched. Instead, they're typically based on the application of knowledge, expertise, or skill to meet a specific need or solve a particular problem.

Services can take many forms, including professional services such as consulting, legal, or accounting services, personal services such as haircuts or massages, and digital services such as software as a service (SaaS) or cloud computing. Services can be provided in person, over the phone, or online, and may be one-time or recurring. They're often associated with [work orders](/dynamics365/field-service/create-product-or-service).

The delivery of a service often involves a direct interaction between the service provider and the customer. Service providers must often manage the customer experience, including communication, expectations, and quality control, to ensure that the service meets or exceeds the customer's needs and expectations.

In business, services can play a critical role in building customer relationships and generating revenue. By providing high-quality services and building strong customer relationships, businesses can increase customer loyalty, generate repeat business, and differentiate themselves from competitors.

### Shipment

A shipment is a delivery to a customer. If you use the packing functionality in Dynamics 365 Supply Chain Management, a shipment can cover one or more order lines or containers.

### Subassembly

Subassemblies are items that have undergone some of the production steps but aren't at the finished goods stage yet. They're also sometimes referred to as semi-finished goods. Some organizations have breaks throughout the production process and subassemblies may be reported and stored in inventory during these breaks.

### Subcontracting

Subcontracting, also known as tolling or outsourcing, is the process of using a vendor to run some of or all the steps of producing an item. The typical subcontracting process includes sending materials out to the vendor to have them provide a service or other added value and receiving back the updated product to be worked on further or sold.

### Subcontractor

A subcontractor is a hired external worker who performs specialized tasks or produces specific components as part of a larger manufacturing process for a company.

### Subject

In Dynamics 365 Sales, Customer Service, Field Service, and Customer Insights, the term *subject* refers to a categorization or classification for labeling and organizing various records, such as cases, activities, knowledge base articles, sales literature, and products. It helps in better organizing and managing data within the system. Subjects can be organized into a subject hierarchy. This concept is like the concept of a product category and product category hierarchy. However, one key difference is that subject support not only the organization of products but other types of data. Learn more at [Define subjects to categorize cases, products, and articles](/power-platform/admin/define-subjects-categorize-cases-products-articles).

### Supply chain

A network of organizations, resources, activities, and processes that collaboratively design, produce, distribute, and deliver goods or services, ensuring efficient flow from suppliers to customers while minimizing costs and maximizing customer satisfaction.

## T

### Time and material projects

For time and material projects, the [customer invoice](#invoice) amount is based on transaction lines that are entered on projects. Transactions can be invoiced per project or per [project contract](#project-contract). Learn more at [Manage project financials overview](project-to-profit-manage-project-financials-overview.md).

### Time entry

The practice of recording and monitoring the time spent on various tasks and activities throughout the project's lifecycle. Tracking time provides a record of work hours that are invested across the various project components. Learn more at [Deliver project work](project-to-profit-deliver-project-work.md).

### Time series forecasting

The main strategy that's used to generate forecasts in Dynamics 365 Supply Chain Management is time series forecasting. It's a model that uses previous demand to predict future demand. The components of a time series forecast model fall into three categories:

- A **trend** is the general direction that demand is moving in, generally either increasing or decreasing.

- **Seasonality** describes the presence of recurring short-term patterns in demand. For example, demand may spike at the end of a quarter due to a push to close sales. Seasonality doesn't have to relate to specific seasons of the year, and can be related to any internal or external event.

- An **error** is an unexplained or random variation in a time series. In real life, it's impossible to create a statistical model that explains the trend and seasonality of demand with complete accuracy. Some degree of error must always be expected.

When the three components are added together, they can be used to predict future demand. The statistical forecasting algorithms used by Dynamics 365 and other forecasting tools calculate and combine these general components in different ways, allowing organizations to compare forecasting models and select the one that seems to predict the demand best. The following graphic illustrates the components and formula that represent time series forecasting.

:::image type="content" source="media/time-series-forecasting.png" alt-text="Graphic illustrating that trend plus seasonality plus error predicts forecasts.":::

## U

### Unlimited credit limit

The **Unlimited credit limit** flag on a customer account indicates the account must not be checked against its credit limit. Use it to prevent an important customer from being affected by the credit management capabilities in Dynamics 365 Finance.

Because this option circumvents the standard processes your organization uses, consider its security carefully. You might want to set up database logging to [monitor its use](order-to-cash-monitor-customer-credit-collections-overview.md).

### Upsell

Sometimes confused with *cross-selling*, the term covers the act of selling additional or higher-value products and services to existing customers. Learn more at [Sales planning and strategy](#sales-planning-and-strategy).

## V

### Variant

See [product](#product).

## W

### Win/loss analysis

The job of evaluating why deals were won or lost to improve the marketing process.

### Work Breakdown Structure (WBS)

A Project Work Breakdown Structure (WBS) is a project management tool that adopts a step-by-step approach to complete large projects with several moving parts. It breaks down the project into smaller components, integrating scope, cost, and deliverables into a single tool. The Project Management Institute (PMI) defines WBS as "a deliverable-oriented hierarchical decomposition of the work to be executed by the project team to accomplish the project objectives and create the required deliverables." It organizes and defines the total scope of the project, with each descending level representing an increasingly detailed definition of the project work.

### Work order

A work order helps organizations to understand the maintenance or repair that is needed on an asset or a functional location. The work order assigns the appropriate resources to complete the maintenance request. Jobs associated with work orders help to register consumption details.

For example, you can use a work order to schedule maintenance on a machine. You can also create a work order for inspections, corrective maintenance, and preventive maintenance. In Dynamics 365 Field Service, a work order documents the [maintenance](#maintenance) or [repair](#repair) that an [asset](#asset) or location needs. It assigns the appropriate resources to complete the request, and jobs associated with work orders help register consumption details. Learn more about the work order process in Dynamics 365 Field Service [Work order architecture](/dynamics365/field-service/field-service-architecture).

You can also procure items with work orders. The procurement process typically starts with either a purchase requisition or purchase order request. Often, companies may not have the required items to execute a work order. This is when a purchase request is triggered. You can create a related purchase order or purchase requisition for a work order job in Dynamics 365.

### Workflow

In the context of Dynamics 365, workflow commonly refers to the system capability of automating business processes, such as the routing of specific business documents (for example, purchase orders, expense approvals, or vendor invoices) to the appropriate person or persons in the organization for approval. You can use the workflow capability in Human Resources to manage employee information and processes, and you can use the configuration of positions and reporting relationships in Human Resources to associate approval workflows with reporting hierarchies in other processes throughout the business.

- Identification numbers
- Courses
- Loaned items
- Human resources actions

When employees are hired, transferred, or terminated, the workflow can include a review process. In this way, a document can be revised, or the terms of an action can be defined as part of the workflow. When the review process is completed, the document or action is completed, and the workflow moves to a final approval step.

### Write-off

Writing off an asset refers to removing it from the balance sheet when its value has been fully depreciated, or it no longer holds any financial value.

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
