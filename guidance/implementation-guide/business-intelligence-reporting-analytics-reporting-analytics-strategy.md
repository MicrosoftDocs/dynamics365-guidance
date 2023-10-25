---
title: Reporting and analytics strategy
description: Learn about how to define your reporting strategy.
author: TimoGossen
ms.author: timogoss
ms.date: 10/19/2022
ms.topic: conceptual

---
# Reporting and analytics strategy

To be a market leader, an organization's products and services must evolve continuously and exceed customer expectations. The information used to improve a product or service is based on data that comes to the surface via reporting. Reporting requirements can be as simple as determining the status of an order or as complex as a cash-flow analysis for a global organization.

## What is a reporting solution?

An effective reporting solution is one of the essential elements for business success. A properly implemented reporting solution provides a competitive advantage, as users have access to the exact information they need exactly when they need it, which accelerates and improves the decision-making process.

## Define your analytics strategy

An analytics strategy determines how an organization will provide the ideal level of accurate information to users for timely decision-making.

The strategy includes a list of tools and types of reporting (such as analytics, static reports, and ad-hoc reporting), as well as how the information will be secured and shared with users. Implementation of the strategy forms a foundation for defining standards, processes, and best practices.

Your analytics strategy can help transform data collected from different processes and systems into knowledge to help you stay competitive in the market.

A successful strategy caters to user requirements and how those requirements must be fulfilled. For example, some business users may require printed reports, which can be sent to customers and vendors. Others may need data to be available for summarized, detailed, or ad-hoc reporting. Business management may require financial or operational reports to understand the health of the organization and determine an overall strategy. Serving such varied user needs often requires different tools to manage data coming from multiple sources. For example, financial and ad-hoc reporting requirements may rely on data extracted and stored in a staging location utilizing Microsoft Azure data services such as Azure Synapse Analytics, as well as manufacturing or sales information in Dynamics 365 apps.

With a centralized data and business intelligence strategy, the IT department is usually responsible for data, ETL processes, and reporting solutions. In a self-service approach, the IT team implements a data analytics platform that enables users without statistical, analytical, or data-handling expertise to access and use data. Teams should understand their organization's goals and strategy before implementing an enterprise data platform.

Any reporting solution requires ongoing maintenance and updates as underlying system requirements and business priorities change. The project team should clearly define the delivery, maintenance, and operational responsibilities. There should also be a plan for making historical data from legacy systems available for reporting, business intelligence, or audit purposes.

> [!TIP]
> Every organization needs people who understand how to  analyze and use data. Training and communication are key to ensuring that business users know how to use data and insights to optimize their work, drive efficiency, and make informed decisions. Data and analytics processes change periodically to improve how information is provided. Make sure users are aware of any upcoming change and understand how it will affect them. Constant updates without appropriate change management can confuse users, but effective change management can improve the adoption rate of analytics.

## Gain deeper insights from data

For most organizations, business intelligence and analytics are critical to their growth and digital transformation. With technology such as Azure Machine Learning and Adaptive Insights, organizations can gain deeper insights from their data. Having an early understanding of these technologies also can help organizations design their systems for future-state data consumption.

Public, cloud-based business intelligence solutions are a good fit for many organizations, as they are on-demand, self-service, and scalable solutions. To choose the best technology to meet requirements today and in the future, the implementation team must understand their organization's current state and the future vision for enterprise business intelligence and analytics.

## Understand reporting requirements

Understanding reporting requirements is key to delivering successful reports and helping improve the entire business. Reporting requirements must be examined in the context of the business process for the purpose of the report—such as operational reporting, financial or regulatory reporting, ad-hoc inquiries, and dashboard and analytical reporting—and should not be an afterthought.

As part of the business requirements gathering process, organizations must address reporting requirements, and collect information about how reports will be used, such as:

- Printed on paper and sent with a shipment on a truck

- Used to create a pivot table in Microsoft Excel and build another report

- Submitted to government agencies at the end of the year

- Provided to a bank on a periodic basis for audit purposes

Organizations must also identify any critical reports that require data mash-up with other sources, such as front-office apps or transportation systems, to develop an appropriate data integration and solution strategy. Data volume may help determine how reports will be designed and shared with users.

If reports will be validated by a third party, organizations need to determine how reports will be generated and shared, and what data must be included in the report before it can be approved.

Requirements gathering also includes security policies—encryption, access controls, and row and column level—and requirements related to data retention, data residency, and personally identifiable information (PII).

### Document printing and electronic reporting

[Document printing requirements](/dynamics365/fin-ops-core/dev-itpro/analytics/print-documents?toc=/dynamics365/finance/toc.json) are another factor to consider. To comply with local laws, businesses typically must submit regulatory and compliance documents in a pre-defined printed or electronic format provided by government agencies. The data required for these documents often resides in enterprise resource planning (ERP) systems.

The [Electronic reporting](/dynamics365/fin-ops-core/dev-itpro/analytics/general-electronic-reporting?toc=/dynamics365/finance/toc.json) (ER) tool can help organizations adopt new regulatory requirements and generate documents in the required format to electronically exchange information with government bodies, banks, and other parties. Targeted at business users instead of developers, the ER tool lets users configure different document formats instead of writing code, making the processes for creating and adjusting formats for electronic documents faster and easier. It works with the TEXT, XML, Microsoft Word document, and OPENXML worksheet formats, and an extension interface provides support for additional formats.

Users of the customer engagement apps can [use Word templates to create standardized documents](/power-platform/admin/using-word-templates-dynamics-365). With Dynamics 365 Sales, users can [gain insights with dashboard](/dynamics365/sales/dashboards), and they can [print quotes, invoices, or other records](/dynamics365/sales/print-records) and [create PDF files from sales records](/dynamics365/sales/create-quote-pdf).

### Business document management

[Business document management](/dynamics365/fin-ops-core/dev-itpro/analytics/er-business-document-management) is built on top of the ER framework, and enables business users to edit document templates by using Microsoft 365 or a Microsoft Office desktop application. Edits might include changing business document designs and adding placeholders for additional data without source code changes and new deployments. No knowledge of the ER framework is required to update templates of business documents.

### Financial reporting

Finance and business professionals use financial reporting to create, maintain, deploy, and view financial statements. [Financial reporting](/dynamics365/fin-ops-core/dev-itpro/analytics/financial-reporting-intro?toc=/dynamics365/finance/toc.json) capabilities in Dynamics 365 finance and operations apps support currency translation and financial dimensions to efficiently design financial reports.

Financial reporting in Dynamics 365 Finance provides default financial reports that organizations can use as is or as a starting point for their financial reporting needs. In addition to traditional financial reports such as income statement and balance sheet, the app's [default reports](/dynamics365/finance/general-ledger/financial-reporting-getting-started#default-reports) include examples of the many types of financial reports you can create and customize.

### Dashboards, charts, and analytical workspaces

The Dynamics 365 Sales app uses [dashboards](/dynamics365/sales-enterprise/dashboards) to provide an overview of actionable business data across an organization, and give insights on sales data and team performance. Sales representatives and managers can use an out-of-the-box [sales pipeline chart](/dynamics365/sales-enterprise/sales-pipeline-chart) in Dynamics 365 Sales to visualize the revenue for an opportunity based on each pipeline phase.

Dynamics 365 Finance and Supply Chain Management deliver rich and interactive reports that are seamlessly integrated into application workspaces. By using infographics and visuals supported by Microsoft Power BI, [analytical workspaces](/dynamics365/fin-ops-core/dev-itpro/analytics/embed-power-bi-workspaces?toc=/dynamics365/finance/toc.json) let users explore the data by selecting or touching elements on the page. They also can identify cause and effect, perform simple what-if operations, and discover hidden trends—all without leaving the workspace. Power BI workspaces complement operational views with analytical insights based on near-real-time information. Power users can use web-friendly design tools to customize the analytical reports that are embedded in the application. By using the free-form canvas designer, users who are familiar with the relevant business insights that are required can help make the organization successful. Customizations that are made to the embedded analytical reports are automatically deployed by the service and made available to other users of the system. Partners and independent software vendors (ISVs) can develop the Power BI content for their solutions and embed it directly into the application.

## Reporting categories

Reporting needs for an organization can be classified into two categories: operational reporting and business reporting.

### Operational reporting

Examples of operational reporting include orders received in a day, delayed orders, and inventory adjustments in a warehouse. This kind of reporting supports the detailed, day-to-day activities of the organization. It is typically limited to a short duration, uses real-time granular data, and supports quick decision-making to improve efficiency. It also helps organizations identify their issues and achievements, as well as future strategies and actions that may affect the business. Operational reports can empower businesses to determine their next steps for improving organizational performance. Organizations can fulfill operational reporting requirements using elements such as native controls, [SSRS reports](/dynamics365/fin-ops-core/dev-itpro/analytics/ssrs-report?toc=/dynamics365/finance/toc.json), dashboards, and [business documents](/dynamics365/fin-ops-core/dev-itpro/analytics/er-business-document-management?toc=/dynamics365/finance/toc.json).

### Business reporting

Business reporting refers to reports detailing operating expenses and financial key performance indicators (KPIs) to business stakeholders so they can understand the organization's overall health and make more informed decisions. This kind of reporting delivers a view of current performance to enable the stakeholders to identify growth opportunities and areas for improvement, and track business performance against the planned goals for the organization.
