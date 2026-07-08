---
title: Kiwa transforms global service operations with Dynamics 365 and the Business Process Catalog in Mavim
description: Learn how Kiwa uses Dynamics 365, the Business Process Catalog, and Mavim to harmonize global service operations and prepare for AI.
#customer intent: As a business leader, I want to learn how Kiwa modernized global service operations so that I can apply similar ideas in my organization.
author: manditoves
ms.author: manditoves
ms.topic: concept-article
ms.date: 07/06/2026
---

# Kiwa transforms global service operations with Dynamics 365 and the Business Process Catalog in Mavim

**Founded:** 1948  
**Industry:** Testing, inspection, and certification  
**Organization size:** More than 200 legal entities across more than 40 countries and 12,500 employees  
**Region:** Global

[Kiwa](https://www.kiwa.com/) is a global leader in testing, inspection, and certification services. As the company continued to grow through acquisitions, it needed a more connected way to manage customer engagement, service delivery, project execution, and finance across a highly decentralized organization.

By adopting [Dynamics 365](/dynamics365/) and using the [Business Process Catalog](../business-processes/about.md) in [Mavim](https://www.mavim.com/) as the process transformation and governance layer, Kiwa is building a consistent global operating model that improves visibility, supports growth, and prepares the business for greater automation and AI-enabled ways of working.

In this case study, you learn how Kiwa is using Dynamics 365, the Business Process Catalog, and Mavim to modernize global service operations, harmonize business processes, and create a scalable foundation for future AI-driven transformation.

## Business challenge

Kiwa's growth strategy strongly focuses on mergers and acquisitions. Over time, this strategy created a complex landscape of more than 200 legal entities operating across more than 40 countries, with many local systems, process variations, and legacy ways of working.

Each acquired business brought its own enterprise resource planning (ERP) platforms, customer relationship management (CRM) tools, reporting structures, and operational patterns. As a result, Kiwa faced several barriers to scaling and efficiency, including fragmented systems, inconsistent processes, limited transparency, and disconnected data across commercial, operational, and financial domains.

These issues were especially visible in processes such as invoicing, time registration, and financial control. In some cases, processes were manual and error prone. In other cases, the challenge wasn't only technology, but also inconsistent governance, unclear ownership, and the absence of a shared process model across business units and countries.

At the same time, Kiwa needed to integrate acquired businesses faster and more consistently, without adding more complexity to the organization. To support continued growth, the company needed a cloud-based platform and a process-led transformation approach that could align people, data, and operations globally and consistently.

> "We weren't just dealing with system complexity, but with structural fragmentation in how we operate. To scale globally, we needed one process model, not hundreds of local variations."  
> — Program Director, Flow! Program, Kiwa

Before the transformation, key business processes often followed localized patterns. Commercial teams, service delivery teams, finance teams, and local support functions used different tools and different handoff points. This situation made it harder to maintain process consistency, improve reporting quality, and create reliable visibility across the full organization.

The following image shows how Kiwa previously represented the Lead to Cash process in an online portal. The view was static and didn't reflect the underlying complexity or provide clear and consistent information to the business.

:::image type="content" source="media/kiwa-lead-to-cash-before.svg" alt-text="Diagram of Kiwa previous Lead to Cash process representation in an online portal." lightbox="media/kiwa-lead-to-cash-before.svg":::

## Architecture

The core solution architecture includes Dynamics 365, Power Platform, Azure, the Business Process Catalog, and Mavim.

Dynamics 365 supports customer engagement, service delivery, and financial control across the customer lifecycle. Kiwa uses Dynamics 365 Customer Insights - Journeys, Dynamics 365 Sales, and Dynamics 365 Customer Service for marketing, pipeline management, and case handling. Dynamics 365 Project Operations and Dynamics 365 Field Service support service delivery, including planning, scheduling, and execution. Dynamics 365 finance and operations apps support financial control, invoicing, and record-to-report processes.

Power Platform supports automation, low-code extensions, and reporting through Power Automate, Power Apps, Power BI, and Microsoft Copilot Studio. Azure provides integration, security, and data services, with additional integrations to selected local systems and legacy applications.

To support its process transformation, Kiwa uses the Business Process Catalog for blueprinting, solution design, and alignment on core processes such as Lead to Cash, Contract to Cash, Source to Pay, and Record to Report. Kiwa uses Mavim as the process transformation layer for process modeling, navigation, and governance.

## Solution

To support process transformation at scale, Kiwa implemented the Business Process Catalog in Mavim to map, harmonize, and govern key business processes. This approach gives the organization a structured way to compare current-state and future-state processes, align stakeholders around a common operating model, and guide implementation decisions across rollouts.

The transformation focuses on harmonizing end-to-end processes such as Lead to Cash, Contract to Cash, Source to Pay, and Record to Report. This approach helps Kiwa create a repeatable global template while still allowing controlled local adaptation where required.

The following image shows Kiwa's redesigned business process flow in Mavim.

:::image type="content" source="media/kiwa-business-process-flow-mavim.svg" alt-text="Diagram of Kiwa redesigned business process flow in Mavim connecting customer, operational, and financial processes." lightbox="media/kiwa-business-process-flow-mavim.svg":::

In the redesigned model, customer, operational, and financial processes connect through one integrated platform. Customer and commercial activities flow into project and service execution, which then connect directly to billing, financial control, and reporting. This structure creates stronger alignment between business operations and finance, while also improving process visibility and governance.

The following image shows the Source to Pay business process. It enables global Source to Pay visibility, management, and optimization to support local business.

:::image type="content" source="media/kiwa-source-to-pay-process.svg" alt-text="Diagram of Kiwa Source to Pay process for procurement, supplier management, invoicing, and payment." lightbox="media/kiwa-source-to-pay-process.svg":::

The following image shows the manage active suppliers flow within the Source to Pay process.

:::image type="content" source="media/kiwa-manage-active-suppliers.svg" alt-text="Diagram of the manage active suppliers flow within Kiwa Source to Pay process." lightbox="media/kiwa-manage-active-suppliers.svg":::

## Microsoft Business Process Catalog's role

The Business Process Catalog helps Kiwa create a structured starting point for transformation. It provides industry-aligned baseline processes that accelerate blueprinting and solution design. It also helps business and information technology stakeholders align on a single operational model, making it easier to identify where Kiwa can harmonize globally and where the business requires explicit design choices or approved deviations. In a complex multientity environment, this process-led approach reduces implementation risk and supports a more repeatable design approach across countries and business units.

## Mavim's role

Kiwa uses Mavim to model and harmonize business processes, compare current-state and future-state workflows, and govern process changes through versioning and controlled ownership. Mavim also helps connect the Business Process Catalog to real Dynamics 365 process design and rollout decisions.

After go-live, Mavim supports process documentation, adoption, and continuous improvement. This support is especially important in a global template-based program, where process consistency and reuse are essential for scaling successfully.

## Key benefits and impact

Kiwa is creating a more connected and scalable foundation for global operations.

Operationally, the transformation supports greater harmonization across entities, stronger control over key processes, and reduced dependence on fragmented local solutions. It also improves the connection between customer-facing, operational, and financial processes, which helps the business increase visibility and strengthen governance.

From a strategic perspective, the program supports faster integration of acquired businesses, improves the ability to scale globally, and creates a stronger base for data-driven decision-making. It also positions Kiwa to expand AI and automation more effectively over time.

Current adoption is strongest among process owners, business analysts, transformation teams, and selected business specialists involved in automation and redesign. 

These teams benefit from faster process analysis, more structured workflow design, and better identification of repetitive tasks that can be automated. As Kiwa continues to mature its AI capabilities, adoption is expected to expand further into operational and finance teams.

## Implementation approach

To modernize and redesign its operational model, Kiwa launched a global transformation program built around Dynamics 365 and a process-driven template approach. The program is a key strategic pillar that supports Kiwa's growth, scalability, and professionalization.

Kiwa deployed Dynamics 365 as the digital and operational backbone across both customer engagement and ERP domains. On the front-office side, the company uses Dynamics 365 Customer Insights - Journeys, Dynamics 365 Sales, and Dynamics 365 Customer Service to support the customer lifecycle. At the core of service delivery, Kiwa uses Dynamics 365 Project Operations and Dynamics 365 Field Service. For its financial and transactional backbone, Kiwa uses Dynamics 365 finance and operations apps.

Kiwa also uses Microsoft Power Platform to extend workflows, automate tasks, and improve reporting. Together, these capabilities support a more integrated way of working across customer engagement, service operations, project execution, procurement, and finance.

## The Flow! Program

Kiwa adopted a template-driven transformation approach through its global Flow! Program.

The Flow! Program is Kiwa's global transformation program to create one unified IT platform and operating model across all entities. It harmonizes processes and integrates companies into a shared CRM and ERP landscape based on Dynamics 365, complemented by industry-specific applications.

Flow! isn't a single system or project. It drives a structured combination of solutions, standards, and implementation methods. It improves efficiency, enables faster integration of acquisitions, and supports global collaboration and customer insight.

:::image type="content" source="media/kiwa-flow-program.svg" alt-text="Diagram of Kiwa Flow Program and its unified IT platform and operating model." lightbox="media/kiwa-flow-program.svg":::

The company began by defining business goals, scope, and expected outcomes at the start of each initiative. Global and local stakeholders were involved throughout the redesign process, including business leads, finance teams, operational teams, key users, and project leadership. This involvement helped ensure that process decisions were grounded in both global consistency and local business reality.

Blueprinting was structured around the Business Process Catalog and Mavim. Kiwa then used a hybrid Agile delivery model, supported by Azure DevOps, to move from process design into implementation. To improve transparency and control during delivery, the program also introduced structured governance, regular decision forums, and business impact tracking.

Testing focused on process validation, fit-gap discussions, and iterative business user review. Change management was a critical part of the approach, with strong emphasis on local ownership, stakeholder communication, and clear definition of roles and responsibilities.

## Introducing agentic scenarios

Kiwa is starting its agentic transformation. So far, the main outcomes are improved structure in process design, better visibility into where automation can add value, and a stronger foundation for embedding AI into operational and financial workflows. The company is moving from isolated automation opportunities toward a more process-centric AI strategy, where platform, process, and user-level capabilities work together.

One initiative is the Contract to Cash prototype. It focuses on the next generation of the Dynamics 365 template, using a modern AI-oriented architecture across the full scope of Customer Engagement and Finance for its European and North American business. This approach includes the use of agentic patterns to support process execution, orchestration, and decision support across key end-to-end scenarios.

The following image shows the Contract to Cash prototype scope.

:::image type="content" source="media/kiwa-contract-to-cash-scope.svg" alt-text="Diagram of Kiwa Contract to Cash prototype scope for Customer Engagement and Finance." lightbox="media/kiwa-contract-to-cash-scope.svg":::

The following image shows the Contract to Cash use case.

:::image type="content" source="media/kiwa-contract-to-cash-use-case.svg" alt-text="Diagram of Kiwa Contract to Cash use case showing agentic process orchestration and decision support." lightbox="media/kiwa-contract-to-cash-use-case.svg":::

A second initiative focuses on implementing a Model Context Protocol (MCP) server layer for finance and operations apps, aimed at enabling structured and controlled AI interaction with enterprise processes and data. One important initial use case is month-end closing support, where AI can help reduce manual effort and improve consistency in Record to Report activities.

:::image type="content" source="media/kiwa-month-end-closing-support.svg" alt-text="Screenshot of Kiwa month-end closing support scenario for Finance and Operations using AI-assisted process interaction." lightbox="media/kiwa-month-end-closing-support.svg":::

:::image type="content" source="media/kiwa-finance-operations-agentic-scenario.svg" alt-text="Screenshot of a Kiwa Finance and Operations agentic scenario that supports enterprise process and data interaction." lightbox="media/kiwa-finance-operations-agentic-scenario.svg":::

Kiwa is also developing Business Performance Analytics (BPA) and robotic process automation (RPA) use cases for administratively intensive business processes, supported by dedicated business consultants, Copilot Studio, and accelerated development practices. These scenarios include areas such as invoice validation, time registration, approvals, and reconciliation tasks.

In parallel, the organization is exploring Copilot and agents in the Microsoft 365 context, including Outlook, Teams, Excel, and Word, to support reporting, communication, knowledge access, and day-to-day productivity.

## Looking ahead

With its modernized digital core, Kiwa plans to continue extending process harmonization across business units and regions, further mature its global template, and expand AI and agentic automation use cases.

Mavim continues to play a role in helping the company govern process change and drive continuous improvement. At the same time, Kiwa continues exploring new Dynamics 365, Power Platform, and AI capabilities that can help improve productivity, decision-making, and operational consistency across the enterprise.

> "The real value is not just in implementing a system, but in creating one scalable operating model across Kiwa. With Microsoft and Mavim, we now have the foundation to grow, integrate, and continuously improve."  
> — Program Director, Flow! Program, Kiwa

## Related information

- [Overview of business processes in Dynamics 365](../business-processes/overview.md)
- [About the business process catalog](../business-processes/about.md)
- [Navigate the business process catalog in Mavim](../business-processes/about-catalog-mavim-navigate-business-process-catalog.md)
- [Use Model Context Protocol for finance and operations apps](/dynamics365/fin-ops-core/dev-itpro/copilot/copilot-mcp)
