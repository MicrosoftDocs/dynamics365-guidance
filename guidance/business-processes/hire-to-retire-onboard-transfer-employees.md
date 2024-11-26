---
title: Overview of the Transfer employees business process
description: Learn how the Transfer employees business process can help you optimize the transfer of employees from one legal entity to another in Dynamics 365 Human Resources.
ms.date: 11/19/2024
ms.topic: concept-article
author: edupont04
ms.author: edupont
---

# Overview of the Transfer employees business process

***Applies to: Dynamics 365 Human Resources***

This article explains how to transfer employees in Dynamics 365 Human Resources. Organizations can move employees from one position to another to update their workforce structure. The scenarios involve setting up departments, jobs, and positions in Dynamics 365 Human Resources, and then assigning employees to positions that are linked to jobs.

Internal transfers gives employees opportunities for growth and development. By moving to different positions in the organization, employees can broaden their skills and experiences. Additionally, employees might seek transfers so that they can explore new roles, work on different teams, or take on other responsibilities. Employee transfers can also accommodate an update in the compensation structure.

Organizations often move employees to different positions to adapt to the changing needs of their business. Here are some examples:

- **Skill gaps**: If a team or a business unit lacks specific skills, an employee who has those skills can be moved there.
- **Unbalanced workload**: A change in an employee's position can help balance the workload among other teams.
- **Project assignments**: An employee who is brought onto a specific project might change their position accordingly.
- **Seasonal work**: An employee might be moved to another position to help manage seasonal work.

Employee transfers within an organization can serve various purposes, depending on the specific context and goals of each company. For example, transfers can help the organization address skill gaps, promote talent development, enhance diversity, and foster cross-functional collaboration. A well-managed transfer process can enhance employee satisfaction. It shows that the organization values employee development and career progression. In general, effective employee transfers play a crucial role in promoting organizational agility, boosting employee engagement, and contributing to long-term success.

Employee transfers can also be crucial for succession planning. Through skill mapping, organizations can identify potential successors for critical roles. They can then transfer employees to relevant positions to prepare them for future responsibilities that match their ambition.

## Stakeholders

The following list describes the stakeholders in the *Transfer employees* business process:

- **Human Resources managers** play a crucial role in defining the organizational structure, and in planning and managing the employee lifecycle. They define and manage hiring needs, employee benefits, compensation plans, and other Human Resources processes.
- **Recruiters** are responsible for sourcing and recruiting qualified candidates. They use Dynamics 365 Human Resources to manage recruitment projects and streamline communications between departments.
- **Hiring managers** request positions, participate in the recruitment process, and make final hiring decisions.
- **Employees** are all the users who participate in the business process in a self-service capacity, by updating information that is related to themselves or approving work items that are assigned to them.
- **Managers** are the users who participate in the business process by managing a team and working with the team's information, such performance reviews, leave and absence, timesheets, and approvals.
- The **IT team** is responsible for maintaining and supporting various IT systems, and for managing the IT hardware that employees receive.
- The **Learning and Development team** supports the goal and performance management process by creating performance reviews, tracking feedback, and setting up courses for employee learning.
- The **Finance team** is involved in defining and supporting finance-related processes, such as managing the general ledger and processing invoices and vendor payments.
- **Other department teams** are involved in managing different business processes for the customer, based on the industry (for example, supply chain or manufacturing processes).

## Transfer employee process flow

The following diagram illustrates the *Transfer employee* process area.

:::image type="content" source="media/hire-to-retire-onboard-transfer-employee-flow.svg" alt-text="Diagram that shows four boxes with lists of steps, one for each main step of the process for transferring employees: prerequisites, defining approval and checklists, transferring employee from legal entity A, and then transferring them to legal entity B." lightbox="media/hire-to-retire-onboard-transfer-employee-flow.svg":::

1. Fulfill the prerequisites for transferring an employee

    1. Define the compensation structure that applies to the position.
    1. Define relevant reason codes that might apply to the transfer.

1. Define approval and checklists

    1. Define and set up the approval, based on the business policy.
    1. Define task management for transitions.

1. Transfer an employee from legal entity A

    1. Transfer an employee by doing maintenance directly on the employee.
    1. Transfer an employee by doing maintenance directly on the position.

1. Transfer an employee to legal entity B

    1. Terminate the employment and worker position assignment in legal entity A.
    1. Hire the employee and add a worker position assignment in legal entity B.

## Implement the Transfer employees business process

Before you initiate the *Transfer employee* process, look into the Human Resources parameters and settings. The parameters can be configured either for the specific legal entity that you're associated with or as shared parameters across the organization. Their purpose is to govern specific behaviors in Human Resources features, in alignment with business policies.

As you work with Human Resources, you decide how your organization is structured through elements such as departments, jobs, and positions. These foundational elements play a crucial role in the management of employee transfers.

Several options are available for transferring an employee:

- Use the workflow capability in Dynamics 365 Human Resources to manage employee information.

    For example, you can associate an approval workflow with employee transfers from one position to another. Then, when a transfer is initiated for an employee, the workflow is started, and approval is required before the updated worker position assignment can be saved. The movement of an employee from one position to another can be done through either the relevant employee or the position itself.

- Manually follow the steps in the correct order.

    To transfer someone from one legal entity in the organization to another, you must first terminate the employment in the original legal entity. You then rehire the person in the new legal entity. This approach ensures that all data, including information that is related to leave and absence, benefits, and performance, is correctly captured. It also ensures that employment data is consistent.

- Use Power Automate to set up an approval flow for employee transfers as a custom solution.

    The flow can be activated whenever an employee's lifecycle status is changed. The approval process works as intended, and worker position assignment records are updated. This approach ensures that the relevant employee data is accurately captured according to organizational policies, and that it's kept up to date.

When you use the **Personnel management** workspace as a Human Resources admin or Human Resources assistant, the **Position Changes** tab is available. This tab shows the complete list of position personnel actions that are pending or completed. You can enable the use of *position actions* in Human Resources parameters.

You can control the behavior of worker position assignment through parameters. Select **Always** to allow assignment to new positions when they are created. Select **Never** to require manual assignment after positions are created. If a worker is assigned to a position that reports to another position, a reporting relationship is established between the workers who are assigned to the two positions.

The following table explains the configuration components that support the *Transfer employees* business process.

| Sequence | Configuration component | Required? | Product | Menu path |
|---|---|---|---|---|
| 1 | [Configure reason codes](/dynamics365/human-resources/hr-benefits-setup-reason-codes) | No | Dynamics 365 Human Resources | Human Resources &gt; Setup &gt; Reason codes |
| 2 | [Configure the workflow for transfers](/dynamics365/fin-ops-core/fin-ops/organization-administration/overview-workflow-system?toc=%2Fdynamics365%2Fhuman-resources%2Ftoc.json) | No | Dynamics 365 Human Resources | Human Resources &gt; Setup &gt; Human Resources Workflows |
| 3 | [Configure personnel action types](/dynamics365/human-resources/hr-personnel-actions-faq) | Yes | Dynamics 365 Human Resources | Human Resources &gt; Setup &gt; Human Resources Personnel action types |
| 4 | [Configure the checklist for transitions](/dynamics365/human-resources/hr-task-mgmt) | No | Dynamics 365 Human Resources | Personnel Management &gt; Links &gt; Transitions &gt; Transitions setup |
| 5 | [Configure your workforce](/dynamics365/human-resources/hr-personnel-departments-jobs-positions) | Yes | Dynamics 365 Human Resources | Personnel Management &gt; Links &gt; Organizations |

## Next steps

If you want to implement Dynamics 365 solutions to assist with your *Transfer employees* business processes, you can use the following resources and steps to learn more. (Links are added when the articles are ready.)

1. [Plan and recruit your workforce](hire-to-retire-plan-recruit-workforce-overview.md)
1. [Onboard and manage the employee lifecycle](hire-to-retire-onboard-manage-employee-lifecycle.md)

    - [Hire an employee](hire-to-retire-onboard-hire-employees.md)
    - [Onboard an employee](hire-to-retire-onboard-new-hires.md)
    - [Update employee records](hire-to-retire-update-employee-records.md)
    - Create and manage teams
    - Communicate issues and changes with HR
    - *Transfer employee* (the article that you're currently reading)
    - Generate employment verification letters
    - Employee relocation
    - [Terminate employee](hire-to-retire-onboard-terminate-employment.md)

1. [Manage occupational health and safety](hire-to-retire-manage-occupational-health-safety.md)
1. [Manage employee performance and growth](hire-to-retire-manage-employee-performance-growth.md)
1. [Manage employee time and attendance](hire-to-retire-manage-employee-time-attendance-overview.md)
1. [Manage travel and expenses](hire-to-retire-manage-travel-expenses.md)
1. [Manage worker compensation, benefits, and payroll](hire-to-retire-manage-employee-benefits-payroll.md)

## Related patterns

The following patterns are available to help guide your implementation of the *Transfer employee* business process. (Links are added when the articles are ready.)

- Transfer an employee to a new department
- Transfer an employee to a new legal entity
- Transfer an employee to a new location
- Transfer an employee to a new position

## Related resources

You can use the following resources to learn more about the *Transfer employee* process in Dynamics 365.

- [Personnel management workspace](/dynamics365/human-resources/hr-personnel-personnel-management-workspace)
- [Dynamics 365 Human Resources documentation](/dynamics365/human-resources/)

<!-- ## Tags

*Industries:* Agriculture (01-09), Mining (10-14), Construction (15-17), Manufacturing (20-39), Transportation and Public Utilities (40-49), Wholesale Trade (50-51), Retail Trade (52-59), Finance, Insurance, Real Estate (60-67), Services (70-89), Public Administration (91-99)

*Stakeholders:* Finance, Human Resources

*Products:* Dynamics 365 Human Resources -->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [Geert-Jan Jansen](https://www.linkedin.com/in/geert-jan-jansen-b468b411/) | Senior Solutions Manager

Other contributors:

- [Kamal Radhakrishnaiah](https://www.linkedin.com/in/kamal-radhakrishnaiah-5816aa69/) | Solution Architect
- [Priyanka Sinha](https://www.linkedin.com/in/priyanka-sinha-726b1314/) | Senior Solution Architect
- Dina Salymzyanova | Senior Consultant
