---
title: Create a reporting and analytics strategy
description: Learn how to define and implement a reporting and analytics strategy that meets your organization's needs and goals for your Dynamics 365 implementation.
author: TimoGossen
ms.author: timogoss
ms.date: 01/23/2024
ms.update-cycle: 1095-days
ms.topic: concept-article
ms.custom:
  - evergreen
  - ai-seo-date: 01/23/2024
  - ai-gen-docs-bap
  - ai-gen-title
  - ai-gen-desc
content_well_notification: AI-contribution
---

# Create a reporting and analytics strategy

To lead the market, you need to constantly improve your products and services based on customer feedback. You get this feedback from data that you collect and analyze through reporting. Reporting can range from simple status updates to complex financial analyses.

## What makes a good reporting solution?

A good reporting solution gives you an edge over your competitors. It delivers the right information to the right people at the right time, so they can make better decisions faster.

## Plan your analytics strategy

Your analytics strategy defines how you'll provide accurate and timely information to your users. It includes:

- The tools and types of reporting you'll use, such as analytics, static reports, and ad-hoc reports
- How you'll secure and share the information with your users
- The standards, processes, and best practices you'll follow

Your analytics strategy can help you turn data from different sources into insights that help you stay ahead of the market.

Your strategy should cater to the different needs of your users. For example:

- Some users might need printed reports to send to customers or vendors.
- Some users might need data for summary, detail, or ad-hoc reports.
- Some managers might need financial or operational reports to monitor the health of the organization and plan its future direction.

You might need different tools to manage data from multiple sources, such as Azure Synapse Analytics for financial or ad-hoc reporting, or Dynamics 365 apps for manufacturing or sales information.

You should also consider who will be responsible for data, reporting solutions, and maintenance. For example, in a centralized approach, the IT department handles everything. In a self-service approach, the IT department sets up a data platform that lets users access and use data without technical skills.

You should understand your organization's goals and vision before you choose a data platform.

Finally, you should have a plan for how to access historical data from legacy systems for reporting, business intelligence, or audit purposes.

> [!TIP]
> Data skills are essential for any organization. Make sure your users know how to use data and insights to optimize their work, drive efficiency, and make informed decisions. Communicate any changes in data processes clearly and effectively. This will help avoid confusion and increase adoption rates.

## Get deeper insights from data

Business intelligence and analytics are crucial for growth and digital transformation. With technologies like Azure Machine Learning and Adaptive Insights, you can get deeper insights from your data. You should also be aware of these technologies when you design your systems for future data needs.

Cloud-based business intelligence solutions are a good option for many organizations. They're on-demand, self-service, and scalable. To choose the best technology for your current and future needs, you should know your organization's current state and vision for business intelligence and analytics.

## Understand your reporting requirements

Knowing your reporting requirements is key to creating successful reports and improving your business. You should consider the purpose of each report. For example:

- Operational reporting supports daily activities, uses real-time data, and enables quick decisions.
- Financial or regulatory reporting complies with laws or standards, uses predefined formats, and might involve third parties.
- Ad-hoc inquiries answer specific questions, uses flexible data sources, and supports exploration.
- Dashboard and analytical reporting provides an overview of performance, uses visuals and infographics, and supports insights.

You should also collect information about how your reports will be used. For example:

- Will they be printed on paper or sent electronically?
- Will they be used to create other reports or charts?
- Will they be submitted to government agencies or banks?
- Will they be shared with customers or vendors?

You should also identify any reports that require data from other sources, such as front-office apps or transportation systems. This will help you develop a data integration strategy. Data volume might affect how you design and share your reports.

If your reports need to be validated, you should decide how you'll generate and share them, and what data they must include.

You should also consider security policies for encryption, access control, and data protection. And you should consider requirements for data retention, data residency, and personal information.

### Print documents and use Word templates

Some documents need to be printed in a specific format to comply with local laws. For example, you might need to submit regulatory documents to government agencies. The data for these documents usually comes from enterprise resource planning (ERP) systems.

The [Electronic reporting](/dynamics365/fin-ops-core/dev-itpro/analytics/general-electronic-reporting?toc=/dynamics365/finance/toc.json) (ER) tool can help you meet your reporting requirements. It lets you configure different document formats without writing code. It works with text, XML, Word document, and OpenXML worksheet formats.

If you use customer engagement apps, you can [use Word templates](/power-platform/admin/using-word-templates-dynamics-365) to create standardized documents. With Dynamics 365 Sales, you can [print quotes](/dynamics365/sales/print-records), [create PDF files](/dynamics365/sales/create-quote-pdf), [use dashboards](/dynamics365/sales-enterprise/dashboards), [and visualize sales pipelines](/dynamics365/sales-enterprise/sales-pipeline-chart).

### Manage business documents

[Business document management](/dynamics365/fin-ops-core/dev-itpro/analytics/er-business-document-management) is built on the ER framework. It lets you edit document templates using Microsoft 365 or an Office desktop app. You can change the design of business documents and add placeholders for more data without changing the source code.

### Create financial reports

Financial reporting helps finance professionals create, maintain, and view financial statements. [Financial reporting](/dynamics365/fin-ops-core/dev-itpro/analytics/financial-reporting-intro?toc=/dynamics365/finance/toc.json) in Dynamics 365 finance and operations apps supports currency translation and financial dimensions to design financial reports.

You can use the [default reports](/dynamics365/finance/general-ledger/financial-reporting-getting-started#default-reports) in Dynamics 365 Finance as they are or customize them to meet your needs. The default reports include income statements, balance sheets, and other types of financial reports.

### Use dashboards, charts, and analytical workspaces

Dynamics 365 Sales uses [dashboards](/dynamics365/sales-enterprise/dashboards) to give you an overview of your sales data and team performance. You can use the [sales pipeline chart](/dynamics365/sales-enterprise/sales-pipeline-chart) to see the revenue for each stage of the sales process.

Dynamics 365 Finance and Supply Chain Management use rich and interactive reports that are integrated into workspaces. You can use infographics and visuals powered by Power BI to explore the data by selecting elements on the page. You can also identify cause and effect, do simple what-if scenarios, and discover hidden trends, all without leaving the workspace.

Power BI workspaces complement operational views with analytical insights based on near-real&ndash;time data. You can customize the embedded reports using web-friendly design tools. Your customizations are automatically deployed by the service and made available to other users. Partners can develop Power BI content for their solutions and embed it directly into the app.

## Reporting categories

You can classify your reporting needs into two categories: operational reporting and business reporting.

### Operational reporting

Operational reporting helps you run your daily operations efficiently. It shows you things like orders received, delayed orders, or inventory adjustments. It uses real-time granular data and supports quick decisions. It also helps you identify problems
and successes, and actions that might affect your business. Operational reports can help you improve your performance and plan your next steps. You can use native controls, [SSRS reports](/dynamics365/fin-ops-core/dev-itpro/analytics/ssrs-report?toc=/dynamics365/finance/toc.json), dashboards, and [business documents](/dynamics365/fin-ops-core/dev-itpro/analytics/er-business-document-management?toc=/dynamics365/finance/toc.json) for operational reporting.

### Business reporting

Business reporting helps you understand your organization's health and make strategic decisions. It shows you things like operating expenses or financial key performance indicators (KPIs). It gives you a view of your current performance and helps you find opportunities for growth or improvement. It also helps you track how well you're meeting your goals.

## Next steps

- Learn about the benefits and challenges of the [data estate and data modernization](business-intelligence-reporting-analytics-data-estate.md), and how they relate to reporting and analytics in Dynamics 365
- Explore the [components of the modern data estate](business-intelligence-reporting-analytics-data-estate-components.md), such as data sources, data integration, data storage, data processing, and data consumption
- Use the Success by Design [checklist](business-intelligence-reporting-analytics-checklist.md) to assess and improve your reporting and analytics strategy
