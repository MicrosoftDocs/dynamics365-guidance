---
title: Overview of the Terminate employee business process
description: Learn how the Terminate employee business process can help you maintain a productive work environment by efficiently offboarding staff members.
ms.date: 11/19/2024
ms.topic: concept-article
author: edupont04
ms.author: edupont
---

# Overview of the Terminate employee business process within the Hire to retire end-to-end scenario

***Applies to: Dynamics 365 Human Resources***

This article describes the background of the *Terminate employee* business process in Dynamics 365 Human Resources. The purpose of terminating an employee is to formally end their employment. When you terminate a worker's employment, you conclude all position assignments and employment affiliations for that worker.

*Worker affiliations* represent the various roles, positions, and responsibilities that a worker can have in an organization.

Here are some key points about worker affiliations:

- **Employment affiliation**: This affiliation is the primary association between a worker and the organization. It defines the worker's employment status (for example, full-time employee, part-time employee, or contractor) and other relevant details.
- **Position affiliation**: A worker can be affiliated with one or more positions. Each position represents a specific job role in the organization. For example, a worker might be affiliated with a *Software Engineer* position.
- **Effective dates**: Affiliations have start and end dates that indicate when a worker holds a particular role. For example, a worker might be affiliated with a position from January 1 through December 31.

This process ensures that the organization accurately reflects the employee's status. It also allows for proper management of workforce-related activities.

When employment is terminated, and an employee leaves the organization, the consequences for employee benefits depend on your organization's policies and local regulations. Here are some scenarios:

- Some organizations continue health coverage for a specific period after termination, whereas other organizations terminate coverage immediately.
- Contributions to retirement plans usually stop after termination. In some cases, there is an option to roll over or withdraw pension funds.
- Some companies pay out accrued vacation days or allow you to use them before termination. In other companies, employees who leave the organization forfeit any unused vacation days.
- Depending on the company and the policies in the specific region, some organizations must provide severance pay to terminated employees.

Termination significantly affects payroll processing. The following list outlines key steps that must be completed:

- Calculate and process the employee's final paycheck, including any accrued vacation days or unused time off. Additionally, deduct any outstanding loans or advances.
- Update tax withholding based on the termination date, and ensure accurate federal, state, and local tax calculations.
- Stop benefit deductions for health insurance, retirement plans, and other benefits.
- As applicable for the employee, process severance pay according to company policy, based on what is agreed between the company and the employee.
- Maintain records based on termination of the employee, for tax reporting, compliance, and loan policies.

## Stakeholders

Definition of the *Terminate employee* business process in Dynamics 365 Human Resources involves several key stakeholders.

- **Human Resources managers** play a crucial role in defining the organizational structure, and in planning and managing the employee lifecycle. They define and manage hiring needs, employee benefits, compensation plans, and other Human Resources processes.
- **Recruiters** are responsible for sourcing and recruiting qualified candidates. They use Dynamics 365 Human Resources to manage recruitment projects and streamline communications between departments.
- **Hiring managers** request positions, participate in the recruitment process, and make final hiring decisions.
- The **IT team** is responsible for maintaining and supporting various IT systems, and for managing the IT hardware that employees receive.
- The **Finance team** is involved in defining and supporting finance-related processes, such as managing the general ledger and processing invoices and vendor payments.
- **Other department teams** are involved in managing different business processes for the customer, based on the industry (for example, supply chain or manufacturing processes).
- **Employees** are all the users who participate in the business process in a self-service capacity, by updating information that is related to themselves or approving work items that are assigned to them.
- **Managers** are the users who participate in the business process by managing a team and working with the team's information, such performance reviews, leave and absence, timesheets, and approvals.

## Terminate employee process flow

The following diagram illustrates the *Terminate employee* process area.

:::image type="content" source="media/hire-to-retire-onboard-terminate-employment.svg" alt-text="Diagram that shows four boxes with lists of steps, one for each main step of the process for terminating employment: prerequisites, defining approvals and checklists, terminating employment, and updating the worker position assignment." lightbox="media/hire-to-retire-onboard-terminate-employment.svg":::

1. Prerequisites for terminating an employment

    1. Define offboarding configurations.
    1. Define checklists for offboarding.
    1. Define reason codes for termination.
    1. Configure personal action types.

1. Define approval and checklists

    1. Define and set up approval based on business policy.
    1. Define checklists.

1. Terminate employment for an employee

    1. Provide a termination date, a reason, and other justifications.
    1. Terminate an employee.
    1. End benefits, fixed and variable compensation, and leaves.

1. Worker position assignment

    1. End all worker position assignments and all relevant affiliations.
    1. Terminate or keep the position for the organization.

1. End

## Implementing the process of terminating employment

Before you initiate the *Terminate employee* process, we recommend that you look into the Human Resources parameters and settings. The parameters can be configured either for the specific legal entity that you're associated with or as shared parameters across the organization. Their purpose is to govern specific behaviors in Human Resources features, in alignment with business policies.

The process of terminating employment includes capturing approval, completing checklists for follow-up, and ending benefits, compensation, and leave. In this way, you conclude all position assignments and employment affiliations for the worker. If termination occurs because of reorganization, the position itself can be terminated. Otherwise, the position becomes available for another employee or new hire as soon as it's vacated.

When employment is terminated for an employee, it can be displayed in the **Personnel management** workspace. You can set parameters such as a date range to define how you want to view exiting workers.

When you use the **Personnel management** workspace as a Human Resources admin or Human Resources assistant, the **Worker Changes** tab is available. This tab shows the complete list of *Terminate worker* actions that are pending or completed. You can enable the use of *worker actions* in Human Resources parameters.

When an employee is terminated, their access to company systems should be promptly revoked. The following list shows steps that might be relevant:

- Disable the employee's sign-in credentials for all company systems, including email, intranet, and other applications.
- Remove the employee's access to the company network. In this way, they can no longer access shared drives, databases, and other resources.
- Revoke access to any software licenses or tools that are associated with the employee.
- Collect any physical access cards, keys, or badges that were issued to the employee. Update security protocols to prevent unauthorized entry.
- Notify relevant teams (IT, Security, and Human Resources) about the termination. Ensure that those teams follow company procedures to secure data and prevent unauthorized access.

| Sequence | Configuration component | Required? | Product | Menu path |
|---|---|---|---|---|
| 1 | Configure employment types | No | Dynamics 365 Human Resources | Human Resources &gt; Setup &gt; Employment types |
| 2 | [Configure a workflow for termination](/dynamics365/fin-ops-core/fin-ops/organization-administration/overview-workflow-system?toc=%2Fdynamics365%2Fhuman-resources%2Ftoc.json) | No | Dynamics 365 Human Resources | Human Resources &gt; Setup &gt; Human resource workflows &gt; Terminate worker |
| 3 | [Configure personnel action types](/dynamics365/human-resources/hr-personnel-actions-faq) | Yes | Dynamics 365 Human Resources | <p>Human Resources &gt; Setup &gt; HR Personnel action types</p><p>**Note**: Before you can open the **Personnel action types** page, you must turn on personnel actions. Go to **Human Resources** &gt; **Setup** &gt; **Human resources parameters**, and then, on the **Personnel actions** tab, turn on *Worker actions*, *Position actions*, or both.</p> |
| 4 | Configure the offboarding setup | Yes | Dynamics 365 Human Resources | Human Resources &gt; Task Management &gt; Offboarding setup |
| 5 | [Configure the checklist for offboarding](/dynamics365/human-resources/hr-task-mgmt) | Yes | Dynamics 365 Human Resources | Human Resources &gt; Task Management &gt; Offboarding checklists |
| | Configure reason code for termination | Yes | Dynamics 365 Human Resources | Human Resources &gt; Setup &gt; Reason codes |

## Next steps

If you want to implement Dynamics 365 solutions to assist with your *Terminate employee* business processes, you can use the following resources and steps to learn more. (Links are added when the articles are ready.)

1. [Plan and recruit your workforce](hire-to-retire-plan-recruit-workforce-overview.md)
1. [Onboard and manage the employee lifecycle](hire-to-retire-onboard-manage-employee-lifecycle.md)

    - [Hire an employee](hire-to-retire-onboard-hire-employees.md)
    - [Onboard new hires](hire-to-retire-onboard-new-hires.md)
    - [Update employee records](hire-to-retire-update-employee-records.md)
    - Create and manage teams
    - Communicate issues and changes with HR
    - [Transfer employee](hire-to-retire-onboard-transfer-employees.md)
    - Generate employment verification letters
    - Employee relocation
    - *Terminate employee* (the article that you're currently reading)

1. [Manage occupational health and safety](hire-to-retire-manage-occupational-health-safety.md)
1. [Manage employee performance and growth](hire-to-retire-manage-employee-performance-growth.md)
1. [Manage worker compensation, benefits, and payroll](hire-to-retire-manage-employee-benefits-payroll.md)
1. [Manage employee time and attendance](hire-to-retire-manage-employee-time-attendance-overview.md)
1. [Manage travel and expenses](hire-to-retire-manage-travel-expenses.md)

## Related patterns

The following patterns are available to help guide your implementation of the *Terminate employee* business process. (Links are added when the articles are ready.)

- Eliminate a position
- Perform a mass involuntary (lay off) of workers
- Perform a voluntary termination of a worker
- Perform an involuntary termination of a worker

## Related resources

You can use the following resources to learn more about the *Terminate employee* process in Dynamics 365.

- [Personnel management workspace](/dynamics365/human-resources/hr-personnel-personnel-management-workspace)
- [Human resources overview](/dynamics365/fin-ops-core/fin-ops/hr/hr-landing-page#recruit-hire-and-motivate-employees)
- [Dynamics 365 Human Resources documentation](/dynamics365/human-resources/)
<!-- 
## Tags

*Industries:* Agriculture (01-09), Mining (10-14), Construction (15-17), Manufacturing (20-39), Transportation and Public Utilities (40-49), Wholesale Trade (50-51), Retail Trade (52-59), Finance, Insurance, Real Estate (60-67), Services (70-89), Public Administration (91-99)

*Stakeholders:* Finance, Human Resources

*Products:* Dynamics 365 Human Resources -->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors:*

Principal authors:

- [Geert-Jan Jansen](https://www.linkedin.com/in/geert-jan-jansen-b468b411) | Senior Solutions Manager
- [Kamal Radhakrishnaiah](https://www.linkedin.com/in/kamal-radhakrishnaiah-5816aa69/) | Solution Architect

Contributors:

- Ruchi Sharma | Senior Customer Solution Architect
- [Anisha Agrawal](https://www.linkedin.com/in/anisha-agrawal1/) | Senior Product Manager
