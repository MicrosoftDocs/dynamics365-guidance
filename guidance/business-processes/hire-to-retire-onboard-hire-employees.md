---
title: Overview of the Hire employees business process
description: Learn how the Hire employees business process can help you effectively bring new employees into your company and set them up as employees in Dynamics 365 Human Resources.
ms.date: 11/19/2024
ms.topic: concept-article
author: edupont04
ms.author: edupont
---

# Overview of the Hire employees business process

***Applies to: Dynamics 365 Human Resources***

This article describes the business process of hiring employees in Dynamics 365 Human Resources. Before you can hire new employees, you must define your organization's structure by using elements such as *departments*, *jobs*, and *positions*. After you configure these foundational elements in Dynamics 365 Human Resources, you can assign individual employees to positions that are associated with jobs.

After a candidate is selected for a position, Dynamics 365 Human Resources helps you capture all the employee data. It also supports dependent processes such as payroll and benefits management. After an employee is successfully onboarded, you can regularly maintain their information throughout the employee lifecycle.

The purpose of hiring employees in Dynamics 365 Human Resources is to make the hiring process more efficient, ensure the right fit for the job, and manage the employee's journey within the organization in the most efficient way. This approach not only saves time and resources, but also contributes to better employee performance and satisfaction.

Dynamics 365 Human Resources facilitates *mass hire projects*, which are useful when you must hire multiple workers at the same time (for example, to meet seasonal business needs). You can use *recruitment projects* to manage the content that is used in advertisements for open positions, and also to manage the applications for those positions. You can use *applications* in Dynamics 365 Human Resources to track responses to job postings for a specific recruitment project, track specific applicants, and hire or promote an applicant as a worker to fill an open position in the organization.

When you hire employees, you can define and maintain extensive worker information in Dynamics 365 Human Resources. As part of this process, you administer organizational structures, define and administer benefit and compensation plans, and enroll workers in those plans. You can use the *worker type* to define whether a new worker is an *employee* or a *contractor*.

The hiring process is a foundational process that influences many other processes in the organization, including Human Resources processes and processes in other areas. Therefore, it should be defined at the beginning of the Dynamics 365 Human Resources implementation.

## Stakeholders

Definition of the *Hire employees* business process in Dynamics 365 Human Resources involves several key stakeholders.

- **Human Resources managers** play a crucial role in defining the organizational structure, and in planning and managing the employee lifecycle. They define and manage hiring needs, employee benefits, compensation plans, and other Human Resources processes.
- **Recruiters** are responsible for sourcing and recruiting qualified candidates. They use Dynamics 365 Human Resources to manage recruitment projects and streamline communications between departments.
- **Hiring managers** request positions, participate in the recruitment process, and make final hiring decisions.
- The **IT team** is responsible for maintaining and supporting various IT systems, and for managing the IT hardware that employees receive.
- The **Learning and Development team** supports the goal and performance management process by creating performance reviews, tracking feedback, and setting up courses for employee learning.
- The **Finance team** is involved in defining and supporting finance-related processes, such as managing the general ledger and processing invoices and vendor payments.
- **Other department teams** are involved in managing different business processes for the customer, based on the industry (for example, supply chain or manufacturing processes).
- **Employees** are all the users who participate in the business process in a self-service capacity, by updating information that is related to themselves or approving work items that are assigned to them.
- **Managers** are the users who participate in the business process by managing a team and working with the team's information, such performance reviews, leave and absence, timesheets, and approvals.

## Hire employees process flow

The following diagram illustrates the *Hire employees* process area.

:::image type="content" source="media/hire-to-retire-onboard-hire-employees-process.svg" alt-text="Diagram that shows four boxes with lists of steps, one for each main step of the process for hiring employees: hiring an employee, adding employment details, creating worker actions, and finalizing the process." lightbox="media/hire-to-retire-onboard-hire-employees-process.svg":::

1. Hire a new employee

    1. Set the worker type to *Employee* or *Contractor*.
    1. Capture the complete name of the new hire.
    1. Request manager approval, based on the personnel action.

1. Add details about employment

    1. Capture the Social Security number or equivalent ID of the new hire.
    1. Capture the start date and end date of the employment.
    1. Specify the category and type of the employment.

1. Worker action created

    1. Select the position to assign to the new worker.
    1. Enter the start date and end date for the assignment of the position.
    1. Select the applicable onboarding checklist.

1. Finalize the hiring process

    1. Capture all details in the worker action.
    1. Define the level of compensation and compensation plan, and specify whether the new hire gets fixed compensation.
    1. Complete the worker action, or submit it for approval.

1. End

## Implement the Hire employees business process

Before you initiate the *Hire employees* process, we recommend that you look into the Human Resources parameters and settings. The parameters can be configured either for the specific legal entity that you're associated with or as shared parameters across the organization. Their purpose is to govern specific behaviors in Human Resources features, in alignment with business policies.

When *personnel actions* are enabled, it's essential that you define at least one *personnel action type* specifically for the hiring process. You can then use this personnel action type to capture specific behaviors that are related to hiring. Additionally, depending on business policies, it might be crucial that you define a workflow for the approval process that is associated with the personnel actions. In this way, you have a structured and efficient hiring process for new employees.

When you hire new employees, you can use the *checklist* functionality. Specifically, you can use an *onboarding checklist* in the **Task Management** workspace to outline the activities that are required as part of the comprehensive onboarding process. After you hire someone, you assign each activity to the relevant person in the organization. This approach ensures a smooth transition for the new hire and helps streamline the onboarding experience.

By configuring fixed compensation, you help streamline the hiring process and ensure accurate pay for new hires and alignment with organizational policies.

The following table explains the configuration components that support the *Hire employees* business process.

| Sequence | Configuration component | Required? | Product | Menu path |
|---|---|---|---|---|
| 1 | [Configure Human Resources parameters](/dynamics365/human-resources/hr-setup-parameters) | Yes | Dynamics 365 Human Resources | Human Resources &gt; Setup &gt; Human resources parameters |
| 2 | [Configure Human Resources shared parameters](/dynamics365/human-resources/hr-setup-shared-parameters) | Yes | Dynamics 365 Human Resources | Human Resources &gt; Setup &gt; Human resources shared parameters |
| 3 | [Choose a personnel action type](/dynamics365/human-resources/hr-personnel-actions-faq) | Yes | Dynamics 365 Human Resources | Human Resources &gt; Setup &gt; Personnel action types |
| 4 | [Choose and define the employment category](/dynamics365/human-resources/hr-benefits-setup-employment-categories) | No | Dynamics 365 Human Resources | Human Resources &gt; Setup &gt; Employment categories |
| 5 | Choose and define the employment type | No | Dynamics 365 Human Resources | Human Resources &gt; Setup &gt; Employment types |
| 6 | [Select and define the checklist](/dynamics365/human-resources/hr-task-mgmt) | No | Dynamics 365 Human Resources | Human Resources &gt; Task Management &gt; Onboarding checklist |
| 7 | [Define the fixed compensation for a new hire](/dynamics365/human-resources/hr-compensation-overview#compensation-events) | No | Dynamics 365 Human Resources | Human Resources &gt; Compensation &gt; Fixed compensation |

## Next steps

If you want to implement Dynamics 365 solutions to assist with your *Hire employees* business processes, you can use the following resources and steps to learn more. (Links are added when the articles are ready.)

1. [Plan and recruit your workforce](hire-to-retire-plan-recruit-workforce-overview.md)
1. [Onboard and manage the employee lifecycle](hire-to-retire-onboard-manage-employee-lifecycle.md)

    - *Hire an employee* (the article that you're currently reading)
    - [Onboard an employee](hire-to-retire-onboard-new-hires.md)
    - [Update employee records](hire-to-retire-update-employee-records.md)
    - Create and manage teams
    - Communicate issues and changes with HR
    - [Transfer employee](hire-to-retire-onboard-transfer-employees.md)
    - Generate employment verification letters
    - Employee relocation
    - [Terminate employee](hire-to-retire-onboard-terminate-employment.md)

1. [Manage occupational health and safety](hire-to-retire-manage-occupational-health-safety.md)
1. [Manage employee performance and growth](hire-to-retire-manage-employee-performance-growth.md)
1. [Manage employee time and attendance](hire-to-retire-manage-employee-time-attendance-overview.md)
1. [Manage travel and expenses](hire-to-retire-manage-travel-expenses.md)
1. [Manage employee benefits, compensation, and payroll](hire-to-retire-manage-employee-benefits-payroll.md)

## Related patterns

The following patterns are available to help guide your implementation of the *hire employees* business process. (Links are added when the articles are ready.)

- Convert applicants to employees
- Convert candidates to employees
- Hire contractors
- Import employees
- Manually create employees
- Hire part-time workers

## Related resources

You can use the following resources to learn more about the *Hire employees* process in Dynamics 365.

- [Personnel management workspace](/dynamics365/human-resources/hr-personnel-personnel-management-workspace)
- [Dynamics 365 Human Resources documentation](/dynamics365/human-resources/)

<!-- ## Tags

*Industries:* Agriculture (01-09), Mining (10-14), Construction (15-17), Manufacturing (20-39), Transportation and Public Utilities (40-49), Wholesale Trade (50-51), Retail Trade (52-59), Finance, Insurance, Real Estate (60-67), Services (70-89), Public Administration (91-99)

*Stakeholders:* Finance, Human Resources

*Products:* Dynamics 365 Human Resources -->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal authors:

- [Kamal Radhakrishnaiah](https://www.linkedin.com/in/kamal-radhakrishnaiah-5816aa69/) | Solution Architect
- [Geert-Jan Jansen](https://www.linkedin.com/in/geert-jan-jansen-b468b411/) | Senior Solutions Manager

Other contributors:

- Dina Salymzyanova | Senior Consultant
- [Ajit Chandran](https://www.linkedin.com/in/ajit-chandran-32757172/) | Senior Product Manager
