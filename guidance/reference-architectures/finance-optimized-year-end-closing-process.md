---
title: Optimize Year-End Closing with Dynamics 365 Finance
description: Learn how to enhance your year-end closing process with Dynamics 365 Finance. Reduce downtime, improve accuracy, and simplify financial workflows.
#customer intent: As a Dynamics AX 2012 user, I want to compare the year-end closing process in Dynamics 365 Finance so that I can understand the performance improvements.
author: edupont04
ms.author: edupont
ms.reviewer: edupont
ms.date: 10/07/2025
ms.topic: reference-architecture
---
# Optimize year-end closing with Dynamics 365 Finance

***Applies to***: ***Dynamics 365 Finance***

Reduce downtime and improve accuracy during year-end closing with Dynamics 365 Finance.

## Introduction

Year-end closing is a core accounting task across industries. Large volumes of accounting data and how they're recorded affect performance. chief financial officers (CFOs) and accounting leaders need a quick, reliable way to transfer balances between years. This article compares year-end closing in Dynamics AX 2012 and Dynamics 365 Finance to highlight the improved performance.

## Architecture

The diagram shows the solution architecture.

:::image type="content" source="media/finance-optimized-year-end-closing-process-flow.png" alt-text="Screenshot of the architecture diagram showing the components and workflow for the optimized year-end closing process.":::

Components include parameters, processes, and the Dynamics 365 Finance accounting information database. The architecture integrates Dynamics 365 Finance with the **Optimize year-end close** microservice, which runs closing logic outside Dynamics 365 Finance and returns the results to Dynamics 365 Finance.

## Workflow

:::image type="content" source="media/finance-optimized-year-end-closing-process-compare.png" alt-text="Screenshot of the workflow diagram comparing Dynamics AX 2012 inefficient process with Dynamics 365 efficient process.":::

The year-end closing process in Dynamics AX 2012 involved several high-impact steps with low reliability. The diagram illustrates the inefficient process that was previously followed:

1. Restarting the AOS causes system downtime.

1. Consistency checks are time consuming.

1. System unavailability causes customer dissatisfaction.

1. Cleaning database log tables blocks the system.

1. Allocating extra database space causes IT overhead and extra costs.

1. Running the process in large implementations might take between 8 to 12 hours.

1. Validating incidents often ends with errors.

In other words, this process is time consuming and causes frustration for customers and system users.

The proposed architecture in Dynamics 365 Finance optimizes the year-end closing process and focuses on two key areas:

- *Cleaning up financial information*: legal entities and financial dimensions.

- *Year-end close microservice add-in*: using the Optimize year-end close microservice.

This solution involves the following steps, shown on the right side of the image at the start of the section:

- Analyze and remove unused financial dimensions  

  In Dynamics AX 2012, the client created legal entities that are inactive in the Dynamics 365 Finance migration but still consume database space and keep unused financial-dimension configurations. The team identified and excluded the inactive legal entities and unused financial dimensions from the Dynamics 365 Finance migration.

- Configure the microservice  

  The year-end close microservice reduces the execution time of the closing process in Dynamics 365 Finance and improves performance. Configure the microservice first in Lifecycle Services and then in Dynamics 365 Finance.

- Run the year-end closing process  

  Let the microservice run the year-end closing process.

- Review results  

  After the previous steps, validate results. You can achieve up to 50 to 70 percent improvement in the entire year-end process with minimal IT involvement.

## Components

Use these components in the reference architecture:

- *Year-end closing process parameters*: legal entity, fiscal year, and execution parameters.

- *Batch jobs for the closing process*, including batch tasks that communicate with the microservice and run the closing logic.

- *Optimize year-end close* microservice. Learn more at [Optimize year-end close](/dynamics365/finance/general-ledger/optimize-year-end-close).

- *Dynamics 365 Finance AX database* with the accounting data and year-end close results.

- *SQL client database for the microservice process*. The microservice doesn't store data.

## Scenario details

One common issue in Dynamics AX 2012 implementations is long processing time during year-end closing because of physical resource limitations (AOS and database), data volume, number of legal entities, financial dimensions, and process complexity.

The organization's goals are to avoid system downtime during the closing process, reduce IT overhead, run the year-end process multiple times to validate results, and shrink the time involved from seven days to a maximum of three days.

With this new microservice, Dynamics 365 Finance helps the organization achieve the following:

1. Significant reduction of the time spent on the year-end close process.

1. Minimal impact on SQL database during year-end closing because it occurs outside Dynamics 365 Finance and its Azure SQL database.

1. Several executions of the process are done even during office hours, so controllers can immediately react to parameter changes.

1. Eliminate IT overhead related to AOS services and SQL databases.

### Potential use cases

This solution was created for a public financial organization. You can also apply it to industries such as retail, finance, manufacturing, healthcare, government, energy, telecommunications, education, automotive, nonprofit, agriculture, and so on. Effectively, it can be used by any organization that manages their accounting in Dynamics 365 Finance.

## Considerations

These considerations help implement a solution that includes Dynamics 365. Learn more at [Dynamics 365 guidance documentation](/dynamics365/guidance/):

- You can use the **Optimize year-end close** microservice using your current Finance licenses. It's licensed as part of the standard licenses for the system. There are no extra costs associated with using this microservice.

- Closing execution parameters such as *transfer dimension for balance sheet and profit and loss* affects the performance, so validate with the client if dimension usage is necessary for the closing process.

- Keep dimension groups as small as possible, as they affect balance reconstruction by dimension during the closing process.

- Evaluate whether it's necessary to create closing transactions during transfer to avoid unnecessary other processes.

- No data is stored in the **Optimize year-end close** microservice.

### Cost optimization

The cost benefits are reflected in performance improvements and IT resources involvement. The reduction in time from the previous process was around 60% with minimal participation of the IT team.

## Deploying Optimize Year-end close add-in

To download and install the **Optimize year-end close** add-in follow these steps.

1. Go to the [Lifecycle Services](https://lcs.dynamics.com/) portal.

1. Select the project to apply the add-in

1. Select the environment to install the add-in

1. In the section **ENVIROMENT ADD-INS**, select **Install a new Add-In**, and then choose **Optimize year-end close** to install it.

## Implement the Optimize year-end close add-in

1. In Dynamics 365 Finance, go to **Management Features** and activate the feature **Optimize year-end close**.

1. Go to **General ledger \> Period close \> Year-end close**. The process creates closing batch jobs and tasks for the legal entities that are being closed.

> [!NOTE]
> The *Optimize year-end close* add-in creates a year-end close service job for each legal entity that's being closed. Then it runs the year-end close logic. 
>
> Finance listens to the microservice to determine when the process finishes. The year-end close results are then updated on the **Year-end close** page in Finance.

## Related resources

Review the following related architecture guides, solutions, and other guidance content:

- [Optimize year-end close](/dynamics365/finance/general-ledger/optimize-year-end-close)

- [Year-end close](/dynamics365/finance/general-ledger/year-end-close)

<!-- ## Tags

*Industries:* Agriculture (01-09), Mining (10-14), Construction (15-17),
Manufacturing (20-39), Transportation and Public Utilities (40-49),
Wholesale Trade (50-51), Retail Trade (52-59), Finance, Insurance, Real
Estate (60-67), Services (70-89), Public Administration (91-99)

*Stakeholders:* Accounts payable, Accounts receivable, Administrative,
Audit, Finance, Operations

*Products**:* Dynamics 365 Finance, Dynamics 365 Supply Chain Management -->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [Diana Marcela Parroquiano](https://www.linkedin.com/in/diana-marcela-parroquiano-2326a512/) | Functional Solution Architect
