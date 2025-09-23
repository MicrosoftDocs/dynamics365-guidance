---
title: Overview of the Update worker information business process 
description: Discover how the Update worker information business process can help you optimize and foster a productive work environment.
ms.date: 09/23/2025
ms.topic: concept-article
author: edupont04
ms.author: edupont
---
# Overview of the Update worker information business process within the Hire to retire end-to-end scenario

***Applies to: Dynamics 365 Human Resources***

This article describes the background of *Update worker information* in Dynamics 365 Human Resources. The first step in the hiring process involves structuring your organization using elements such as departments, jobs, and positions. These foundational elements are configured in Dynamics 365 Human Resources, and individual employees are assigned to positions associated with jobs.

Once a candidate is selected and hired, Dynamics 365 Human Resources helps in maintaining all relevant worker information from the point of hire until the employee leaves your organization.

The purpose of the *Update worker information* process is to have all employee data available that is required based on relevancy and business policy. In Dynamics 365 Human Resources, you can manage the employee's journey in the organization in an efficient way. This not only saves time and resources but also contributes to better employee performance and satisfaction. When employees are hired, Dynamics 365 Human Resources helps you maintain worker information from *hire to retire*, including organizational structure, benefits and compensation plans, and worker enrollment.  

## Stakeholders

Defining the business process for *Update worker information* in Dynamics 365 Human Resources involves several key stakeholders.

- Human resources managers play a crucial role in defining the organizational structure, planning, and managing the employee lifecycle. They define and manage hiring needs, employee benefits, compensation plans, and other human resource processes.

- Recruiters are responsible for sourcing and recruiting qualified candidates. They use Dynamics 365 Human Resources to manage recruitment projects and streamline communications between departments.

- Hiring managers request positions, participate in the recruitment process, and make the final hiring decisions.

- The IT team is responsible for maintaining and supporting various IT systems and also managing the IT hardware that employees receive.

- The learning and development team supports the goal and performance management process by creating performance reviews, tracking feedback, and setting up courses for employee learning.

- Finance team members are involved in defining and supporting finance-related processes such as managing the general ledger and processing invoices and vendor payments.

- Other department team members are involved in managing different business processes of the customer based on the industry, such as supply chain, manufacturing, and so on.

- Employees are all the end users involved with the business process in a self-service capacity, updating information related to themselves or approving work items assigned to them.

- Managers are the end users involved with the business process in the capacity of managing a team and working with the team's information, including performance reviews, leave and absence, timesheets, approvals, and more.

## Update worker information process flow

The following diagram illustrates the *Update worker information* business process with the **HR Manager** as the user role.

:::image type="content" source="media/hire-to-retire-update-worker-information-flow.svg" alt-text="Flow diagram with steps for the process that is explained further in the next paragraphs." lightbox="media/hire-to-retire-update-worker-information-flow.svg":::

1. *Receive update request*.
1. *Verify update request*.
1. *Update information*.
1. *Document updates*.
1. *Communicate updates*.
1. End.

<!-- :::image type="content" source="media/hire-to-retire-update-employee-records-flow.svg" alt-text="Shows four boxes with lists of steps as outlined after the flow diagram." lightbox="media/hire-to-retire-update-employee-records-flow.svg"::: -->

<!-- '1. Update worker information

    1. Complete and capture address information
    2. Complete and capture contact and family information
    3. Add and maintain identification numbers
1. Update employment records

    1. Update the employment-effective dates
    2. Update probation period
    3. Add and maintain financial dimensions that are maintained at the position level. Employment financial dimensions can be used to account for time in timesheets and also support complex multilegal entity scenarios.

1. Update worker position assignment
    1. Add new worker position assignment and define primary position

1. Update personal data
    1. Add and maintain family information
    2. Add and maintain name details' -->

## Implementing the Update worker information process

Before you start the *Update worker information* process, we advise that you look into the HR parameters and settings. These parameters can be configured either for the specific legal entity you're associated with or as shared parameters across the organization. Their purpose is to govern specific behaviors within HR features, aligned with business policies.

From an HR business process perspective, employee records are updated when the employee is going through a lifecycle change. Such changes include promotion, position change, change in personal information such as address change, bank account change, marital status change, and others.

Several options are available for updating employee records:

- You can use **Open in Excel** to modify the content of a date entry and publish the changes. An Excel workbook is generated with the columns from the data entity. The needed and updated fields can be added by design. You can edit the extracted records or add new records and publish the changes.

- You can use workflows to manage changes to various types of employee information. You can also associate a workflow with a specific position action.

- Employees can also modify their own records through the employee self-service. Self-service can be linked to a workflow that you then route for approval before committing the updated information into Dynamics 365.

- An HR admin or HR assistant who uses the **Personnel Management workspace** can also access the **Employee Changes** tab in the workspace. On this tab, you can see the complete list of all worker personnel actions that are pending or completed. You can enable the use of worker actions on HR parameters.

Other notifications or cross application/business domain-based approvals can be triggered using Power Automate, which can help extend the standard functionality based on the business needs of the customer.

The following table explains the configuration components involved in supporting the *Update worker information* business process.

| **Seq** | **Configuration component** | **Req?** | **Product** | **Menu path** |
|--|--|--|--|--|
| 1 | [Configure Reason codes](/dynamics365/human-resources/hr-benefits-setup-reason-codes) | Yes | Dynamics 365 Human Resources | Human Resources &gt; Setup &gt; Reason codes |
| 2 | [Configure Identification types](/dynamics365/human-resources/hr-setup-shared-parameters#settings) | Yes | Dynamics 365 Human Resources | Human Resources &gt; Setup &gt; Identification types |
| 3 | [Configure Name title and suffix](/dynamicsax-2012/appuser-itpro/add-personal-titles-and-suffixes) | Yes | Dynamics 365 Human Resources | Organization Administration &gt; Global Address book &gt; Name title and suffix |
| 4 | Configure Display as (Name sequences) | No | Dynamics 365 Human Resources | Organization Administration &gt; Global Address book &gt; Name sequences |
| 5 | Configure Relationship types | No | Dynamics 365 Human Resources | Organization Administration &gt; Global Address book &gt; Relationship types |
| 6 | Configure Calendars | No | Dynamics 365 Human Resources | Organization Administration &gt; Setup &gt; Calendars &gt; Calendars |
| 7 | [Configure Address setup](/dynamics365/fin-ops-core/dev-itpro/organization-administration/global-address-book-address-setup?toc=/dynamics365/human-resources/toc.json) | No | Dynamics 365 Human Resources | Organization Administration &gt; Global Address book &gt; Addresses &gt; Address setup |

Find content about setting up your HR processes in Dynamics 365 Human Resources at [Organization administration home page](/dynamics365/fin-ops-core/fin-ops/organization-administration/organization-administration-home-page?toc=%2Fdynamics365%2Fhuman-resources%2Ftoc.json).

## Next steps

If you want to implement Dynamics 365 solutions to assist with your *Update worker information* business processes, you can use the following resources and steps to learn more. (Links are added when the articles are ready.)

- [Develop people strategy](/dynamics365/guidance/business-processes/hire-to-retire-plan-recruit-workforce-overview)

- [Recruit and onboard talent](/dynamics365/guidance/business-processes/hire-to-retire-onboard-manage-employee-lifecycle)

- [Manage workplace compliance](/dynamics365/guidance/business-processes/hire-to-retire-manage-occupational-health-safety)

  - *Document safety protocols*

  - *Audit workplace for safety*

  - *Report an injury or illness*

  - *Verify employment*

  - *Update worker information* (the article you're currently reading)

  - [Manage cases and requests](hire-to-retire-manage-cases-requests.md)

- [Manage performance and growth](/dynamics365/guidance/business-processes/hire-to-retire-manage-employee-performance-growth)

- [Manage time and attendance](/dynamics365/guidance/business-processes/hire-to-retire-manage-employee-time-attendance-overview)

- [Manage compensation and benefits](/dynamics365/guidance/business-processes/hire-to-retire-manage-employee-benefits-payroll)

- *Offboard talent*

- *Analyze HR programs*

<!-- ## Related patterns

The following patterns are available to help guide your implementation of the *Update worker information* business process. (Links are added when the articles are ready.)

- Change an employee's location

- Change an employee's title

- Hours/shifts/work from home

- Make changes directly to a worker record

- Promote employee

- Request a worker transfer

- Request compensation changes

- Request new worker

- Request to recruit for a new position -->

## Related information

You can use the following resources to learn more about the *Update worker information* process in Dynamics 365:

- [Personnel management workspace](/dynamics365/human-resources/hr-personnel-personnel-management-workspace)     <!--WAS (/dynamics365/fin-ops-core/fin-ops/hr/hr-landing-page#recruit-hire-and-motivate-employees)-->

- [Dynamics 365 Human Resources documentation](/dynamics365/human-resources/)
<!-- 
## Tags

*Industries:* Agriculture (01-09), Mining (10-14), Construction (15-17), Manufacturing (20-39), Transportation and Public Utilities (40-49), Wholesale Trade (50-51), Retail Trade (52-59), Finance, Insurance, Real Estate (60-67), Services (70-89), Public Administration (91-99)

*Stakeholders:* Finance, Human Resources

*Products:* Dynamics 365 Human Resources -->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [Kamal Radhakrishnaiah](https://www.linkedin.com/in/kamal-radhakrishnaiah-5816aa69/) \| Solution Architect

- [Geert-Jan Jansen](https://www.linkedin.com/in/geert-jan-jansen-b468b411/) \| Senior Solutions Manager

Other contributors:

- [Ajit Chandran](https://www.linkedin.com/in/ajit-chandran-32757172/) \| Senior Product Manager

- [Priyanka Sinha](https://www.linkedin.com/in/priyanka-sinha-726b1314/) \| Senior Solution Architect

- Viacheslav Drobkov \| Senior Consultant
