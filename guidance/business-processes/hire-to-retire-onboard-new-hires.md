---
title: Onboard new hires
description: Discover how the Onboard new hires business process can help you optimize onboarding new employees and foster a productive work environment.
ms.date: 07/19/2024
ms.topic: conceptual
author: edupont04
ms.author: edupont
---
# Onboard new hires

***Applies to: Dynamics 365 Human Resources***

*Onboard new hires* is a business process for  human resources that focuses on giving a positive and empowering start for new employees joining the organization. At the same time, *onboard new hires* helps the organization streamline their steps to successfully onboard an employee.

In Dynamics 365 Human Resources, you manage the onboarding process primarily in the [Task management](/dynamics365/human-resources/hr-task-mgmt) workspace. Task management lets you create tasks that must be completed to hire (onboard), terminate (offboard), and transfer (transition) employees.

*Onboard new hires* involves the following areas of focus:

- Assigning actionable tasks to the new employees so that they feel comfortable with the various onboarding activities. These activities might include completing the mandatory compliance trainings, updating profile information on employee self-service, getting to know the team, and getting to know the internal systems used for various purposes, such as timesheets and expenses.

- Assigning actionable tasks to other team members such as having a buddy to help the new hire in the initial days at work, showing the new team member around the workplace, and having a coffee chat to make the new employee more comfortable at the office.

- Assigning tasks to team members in other departments, such as creating vendors for expense payments by the finance department, or getting the mobile phone and laptop ready to hand over to the new employee.

- Requesting the new employee to fill out additional information forms for any special requests such as accommodation and submit them to the right teams within the organization.

- Assigning actionable tasks to the HR team to plan for the employee onboarding sessions, meeting with the senior stakeholders for introduction.

The following list highlights some functional capabilities from task management in Dynamics 365 Human Resources:

- Checklist tasks can be assigned to task groups that help in parallel task assignment and processing of tasks. For example, you create an HR task group with 10 team members. You then assign a specific task to the HR task group, and a member can then pick the task and process it.

- A task library can be created to support a multicountry roll-out of the onboarding process. This is a set of tasks that can be reused to create multiple checklists.

- Each checklist is linked to a calendar that captures the working days, public holidays, and non-working days.

- Group assignments can be used to dynamically manage team members based on their positions rather than link to the users directly. This helps when current employees leave a specific position and a new employee is hired into that position.

- Tasks can be assigned in advance before the employee's start date using negative days for that task or in the future after the employee's start date.

## Stakeholders

The following list describes the stakeholders in the *Onboard new hires* business process:

- **Human resources managers** play a crucial role in defining the organizational structure, planning, and managing the employee lifecycle. They define and manage hiring needs, employee benefits, compensation plans, and other human resource processes.

- **Recruiters** are responsible for sourcing and recruiting qualified candidates. They use Dynamics 365 Human Resources to manage recruitment projects and streamline communications between departments.

- **Hiring managers** request positions, participate in the recruitment process, and make final hiring decisions.

- **IT team** is responsible for maintaining and supporting various IT systems and also manages the IT hardware that the employees receive.

- **Learning and development team** supports the goal and performance management process by creating performance reviews, tracking feedback, and setting up courses for employee learning.

- **Finance team members** are involved in defining and supporting finance-related processes such as managing the general ledger and processing invoices and vendor payments.

- **Other department team members** are involved in managing the different business processes of the customer based on the industry, such as supply chain, manufacturing, and so on.

- **Employees** are all the end users involved with the business process in self-service capacity, updating the information related to themselves or approving work items assigned to them.

- **Managers** are the end users involved with the business process in the capacity of managing a team and working with the team's information including performance reviews, leave and absence, timesheets, approvals, and more.

## Onboard new hires business process flow

:::image type="content" source="media/hire-to-retire-onboard-new-hires-flow.svg" alt-text="Shows four boxes with lists of steps, one for each main step of hire a new employee, start the onboarding process, process the onboarding, and manage the onboarding process." lightbox="media/hire-to-retire-onboard-new-hires-flow.svg":::

1. **Prerequisite step**

   The *Hire an employee* process has completed successfully, and now the applicable checklist was selected as part of the hire action. If this isn't done, the onboarding checklist can be manually applied to the employee.

2. **Start the onboarding process**

   Once the hire action has completed, the onboarding checklist with all the tasks is triggered to the relevant people with the defined due dates on the checklist tasks.

3. **Process the onboarding**

   All the checklist tasks that were triggered must be actioned upon by the relevant stakeholders across the organization to be completed.

4. **Manage the onboarding process**

   The HR team members keep track of the onboarding process and follow up on the delayed tasks.

## Implementing the onboard new hires business process

Implementing the *Onboard new hires* process involves configuring the Task management functionality in Dynamics 365 Human Resources. Task management uses a concept called checklists and lets you create tasks that must be completed for onboarding, offboarding, and transition-related processes.

The following list shows the configuration and use of task management in Dynamics 365 Human Resources:

- Task management workspace: It's a central overview of all the tasks that have been assigned to individuals in the onboarding, offboarding, and transition processes.

- The following activities can be completed on the Task management workspace by HR teams and managers:

  - Apply a checklist to an employee

  - Update the status of a task

  - Reassign a task

  - Update the due date of a task

- Tasks can be set up separately for processes that are related to onboarding, offboarding, and transition, and then applied to the checklists.

- Tasks can be edited once created, or deleted. The deletion of a task won't work if the task is associated with any checklist. The task must be removed from the checklist first using a separate action.

- Task links are used to provide a navigation path to an external webpage or a page in a Dynamics 365 app. This is helpful for the individuals responsible for carrying out the task.

- Assignment types are used to configure how a specific task will be distributed. These options are available:

  - Worker – assigns the task to a specific employee within the organization.

  - Position – assigns the task to a specific position; this is dynamic and helps when an employee in a specific position leaves the organization.

  - Group – assigns the task to a group of positions.

  - Manager – assigns the task to the manager of the employee who is being hired, terminated, or transferred.

  - Employee – assigns the task to the employee who is being hired, terminated, or transferred.

The following table explains the configuration components that support the *Onboard new hires* business process.

| **Seq** | **Configuration component** | **Req?** | **Product** | **Menu path** |
|--|--|--|--|--|
| 1 | Tasks | Yes | Dynamics 365 Human Resources | Human Resources &gt; Task Management &gt; Onboarding setup &gt; Task library |
| 2 | Task links | Yes | Dynamics 365 Human Resources | Human Resources &gt; Task Management &gt; Onboarding setup &gt; Task library |
| 3 | Assignment types | Yes | Dynamics 365 Human Resources | Human Resources &gt; Task Management &gt; Onboarding setup &gt; Task library |
| 4 | Task due dates and the due date offset | Yes | Dynamics 365 Human Resources | Human Resources &gt; Task Management &gt; Onboarding setup &gt; Task library |
| 5 | Instructions | Yes | Dynamics 365 Human Resources | Human Resources &gt; Task Management &gt; Onboarding setup &gt; Task library |
| 6 | Checklists | Yes | Dynamics 365 Human Resources | Human Resources &gt; Task Management &gt; Onboarding setup &gt; Checklists |
| 7 | Assignment groups | No | Dynamics 365 Human Resources | Human Resources &gt; Task Management &gt; Group assignment |
| 8 | Task groups | No | Dynamics 365 Human Resources | Human Resources &gt; Task Management &gt; Group assignment |

Find content about setting up your HR processes in Dynamics 365 Human Resources at [Organization administration home page](/dynamics365/fin-ops-core/fin-ops/organization-administration/organization-administration-home-page?toc=%2Fdynamics365%2Fhuman-resources%2Ftoc.json).

## Next steps

If you want to implement Dynamics 365 solutions to assist with your *onboard new hires* business processes, you can use the following resources and steps to learn more. (Links are added when the articles are ready.)

1. [Plan and recruit your workforce](hire-to-retire-plan-recruit-workforce-overview.md)  

2. [Onboard and manage the employee lifecycle](hire-to-retire-onboard-manage-employee-lifecycle.md)  

    - Hire an employee

    - *Onboard new hires* (the article you're currently reading)

    - [Update employee records](hire-to-retire-update-employee-records.md)  

    - Create and manage teams

    - Communicate issue and changes with HR

    - Transfer employee

    - Generate employment verification letters

    - Employee relocation

    - Terminate employee

3. [Manage occupational health and safety](hire-to-retire-manage-occupational-health-safety.md)  

4. [Manage employee performance and growth](hire-to-retire-manage-employee-performance-growth.md)  

5. [Manage worker compensation, benefits, and payroll](hire-to-retire-manage-employee-benefits-payroll.md)  

6. [Manage employee time and attendance](hire-to-retire-manage-employee-time-attendance-overview.md)  

7. [Manage travel and expenses](hire-to-retire-manage-travel-expenses.md)  

## Related patterns

The following patterns are available to help guide your implementation of the *onboard new hires* process. (Links are added when the articles are ready.)

- Assign tasks to new employees

- Complete forms and essential paperwork

- Coordinate tasks with other departments for new hires

- Notify internal departments of new hires

- Process requests for accommodations

- Welcome new employees

## Related information

You can use the following resources to learn more about the *onboard new hires* and other processes in Dynamics 365 Human Resources:

- [Organize your workforce by using departments, jobs, and positions](/dynamics365/human-resources/hr-personnel-departments-jobs-positions)  
- [Human Resources overview](/dynamics365/human-resources/hr-admin-overview)
- [Dynamics 365 Human Resources documentation](/dynamics365/human-resources/)  
<!-- 
## Tags

*Industries:* Agriculture (01-09), Mining (10-14), Construction (15-17), Manufacturing (20-39), Transportation and Public Utilities (40-49), Wholesale Trade (50-51), Retail Trade (52-59), Finance, Insurance, Real Estate (60-67), Services (70-89), Public Administration (91-99)

*Stakeholders:* Finance, Human Resources

*Products:* Dynamics 365 Human Resources -->

## Contributors

This article is maintained by Microsoft. It was originally written by the following contributors.

Principal author:

- Kamal Radhakrishnaiah ([LinkedIn](https://www.linkedin.com/in/kamal-radhakrishnaiah-5816aa69)) | Solution Architect

- Geert-Jan Jansen ([LinkedIn](https://www.linkedin.com/in/geert-jan-jansen-b468b411)) | Senior Solutions Manager

Other contributors:

- Dina Salymzyanova | Senior Consultant

- Ajit Chandran | Senior Product Manager
