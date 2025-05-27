---
title: Overview of the Develop communication strategy business process
description: Learn how the Develop communication strategy business process can help you manage employee issues and changes in Dynamics 365 Human Resources.
ms.date: 05/22/2025
ms.topic: concept-article
author: vibhutinair23
ms.author: vibhutinair
---

# Overview of the Develop communication strategy business process within the Hire to retire end-to-end scenario

***Applies to: Dynamics 365 Human Resources***

This article describes the business process of communicating issue and changes with HR in Dynamics 365 Human Resources.

Communicating issues and changes with the Human Resources (HR) department is crucial for several reasons:

- **Issue resolution**: When employees face issues related to colleagues, work environment, or job responsibilities, the HR department steps in to mediate conflicts, provide guidance, and take necessary actions. Their goal is to ensure a positive work environment and address any concerns promptly and effectively.
- **Policy changes**: HR is responsible for communicating and implementing policy changes within the organization. If employees have suggestions or concerns about these policies, let HR know so they can make adjustments and keep everyone informed.
- **Personal changes**: When there are changes in an employee's personal circumstances, such as marital status, address, or emergency contact information, an employee must inform HR. Updating employee records ensures accurate information and helps the organization respond appropriately in an event of emergencies.
- **Benefits and compensation**: HR manages employee benefits and compensation. If employees have questions or issues related to benefits, payroll, or other compensation matters, HR is the right department to approach.

Moreover, workplace harassment is a serious issue that can significantly impact employees' well-being, productivity, and overall work environment. Some common types of workplace harassment that you must communicate to the organization are as follows:

- **Discriminatory harassment**: Discriminatory harassment occurs when someone targets an individual based on their membership in a protected class. These classes include gender, age, race, religion, color, national origin, and physical or mental ability.
- **Sexual harassment**: Sexual harassment involves unwelcome sexual advances, requests for sexual favors, or other verbal or physical conduct of a sexual nature.
- **Bullying and intimidation**: Workplace bullying involves behavior that makes someone feel intimidated or offended.
- **Racial harassment**: Racial harassment targets an individual based on their race, skin color, ancestry, or other perceived attributes related to ethnicity.
- **Religious harassment**: Religious harassment targets an individual based on their religious beliefs or practices.
- **Retaliation**: Retaliation occurs when an employer punishes an employee for reporting harassment or participating in an investigation.

## Stakeholders

Definition of the *Communicate issue and changes with HR* business process in Dynamics 365 Human Resources involves several key stakeholders.

- **Human Resources managers** play a crucial role in defining the organizational structure, and in planning and managing the employee lifecycle. They define and manage hiring needs, employee benefits, compensation plans, and other Human Resources processes.
- **Recruiters** are responsible for sourcing and recruiting qualified candidates. They use Dynamics 365 Human Resources to manage recruitment projects and streamline communications between departments.
- **Hiring managers** request positions, participate in the recruitment process, and make final hiring decisions.
- The **IT team** is responsible for maintaining and supporting various IT systems, and for managing the IT hardware that employees receive.
- The **Learning and Development team** supports the goal and performance management process by creating performance reviews, tracking feedback, and setting up courses for employee learning.
- The **Finance team** defines and supports finance-related processes, such as managing the general ledger and processing invoices and vendor payments.
- **Other department teams** manage different business processes for the customer, based on the industry (for example, supply chain or manufacturing processes).
- **Employees** are all the users who participate in the business process in a self-service capacity, by updating information that is related to themselves or approving work items assigned to them.
- **Managers** are the users who participate in the business process by managing a team and working with the team's information, such performance reviews, leave and absence, timesheets, and approvals.

## Communicate issue and changes with HR process flow

The following diagram illustrates the *Communicate issue and changes with HR* process area.

:::image type="content" source="media/hire-to-retire-communicate-issue-changes-with-hr-process-flow.svg" alt-text="Diagram that shows the process for communicating issue and changes with HR." lightbox="media/hire-to-retire-communicate-issue-changes-with-hr-process-flow.svg":::

1. Prerequisites for communicating issues and changes
   - Define Case categories
   - Define Case processes

2. Define security and approval for issues and changes
   - Define Case category security by role
   - Define workflows for approval of issues and changes

3. Ask questions
   - Ask questions about benefits
   - Ask questions about compensation
   - Ask questions about leave and absence

4. Communicate harassment and issues
   - Communicate about harassment issues to HR
   - Communicate safety issues with HR

5. End

## Implement the Communicate issue and changes with HR business process

Before you initiate the *Communicate issue and changes with HR* process, we recommend that you look into the Human Resources parameters and settings. You can configure these parameters either for the specific legal entity that you're associated with or as shared parameters across the organization. Their purpose is to govern specific behaviors in Human Resources features, in alignment with business policies.

Case management is often used to capture issues and queries with the following steps:

- Ask questions about benefits
- Ask questions about compensation
- Ask questions about leave and absence
- Communicate about harassment issues to HR
- Communicate safety issues with HR
- If you see something, say something

Case management captures different categories, and you can define approvals by using case workflow.

Dynamics 365 HR provides a comprehensive case management solution that you can use for communicating issues and changes as an employee. You can use case management with the following options:

- **Cases**: A case in Dynamics 365 represents a single incident of service. It could be anything that requires some type of resolution or answer. A single employee can have multiple cases associated with them at any time.
- **Activities**: An activity is an interaction with a customer, like a phone call. A single case can have multiple activities associated with it.
- **Entitlements**: Entitlements specify how much support a customer gets. They work like support contracts.
- **Knowledge articles**: The knowledge base is a repository of informational articles that help customer service representatives resolve cases.
- **Queues**: A queue is a place to organize and store activities and cases that are waiting to be processed.
- **Service-level Agreements (SLAs)**: Service-level agreements track and define what happens when a case is opened, such as how long it takes to respond to a customer.
- **Record creation and update rules**: Apply record creation and update rules to different activity types to automatically create Dynamics 365 records.

These components let employees communicate their issues and changes effectively with the HR department. The HR department can use the same system to track issues, assign them to the appropriate personnel, and resolve them quickly. This improves efficiency and creates a better employee experience.

The following table explains the configuration components that support the *Communicate issue and changes with HR* business process.

| Sequence | Configuration component | Required? | Product | Menu path |
|----------|-------------------------|-----------|---------|-----------|
| 1 | [Configure Case categories](/dynamics365/fin-ops-core/dev-itpro/organization-administration/plan-case-management?context=%2Fdynamics365%2Fcontext%2Fcommerce#case-categories) | Yes | Dynamics 365 Human Resources | Organization administration &gt; Setup &gt; Cases &gt; Case categories |
| 2 | [Configure Case category security by role](/dynamics365/fin-ops-core/dev-itpro/organization-administration/plan-case-management?context=%2Fdynamics365%2Fcontext%2Fcommerce#case-category-security-by-role) | No | Dynamics 365 Human Resources | Organization administration &gt; Setup &gt; Cases &gt; Case categories type security |
| 3 | [Configure Case processes](/dynamics365/fin-ops-core/dev-itpro/organization-administration/plan-case-management?context=%2Fdynamics365%2Fcontext%2Fcommerce#case-processes) | Yes | Dynamics 365 Human Resources | Organization administration &gt; Setup &gt; Cases &gt; Case processes |
| 4 | [Configure Case workflow](/dynamics365/fin-ops-core/fin-ops/organization-administration/overview-workflow-system?context=%2Fdynamics365%2Fcontext%2Fcommerce) | No | Dynamics 365 Human Resources | Organization administration &gt; Setup &gt; Cases &gt; Case workflow |

## Next steps

If you want to implement Dynamics 365 solutions to assist with your *Communicate issue and changes with HR* business processes, you can use the following resources and steps to learn more. (Links are added when the articles are ready.)

1. *Develop people strategy*
    1. *Define organizational structure*  
    1. *Define operating hours and schedule*  
    1. *Define human resources policies*  
    1. *Develop code of conduct*  
    1. *Define expense policies*  
    1. *Plan workforce*  
    1. *Develop communication strategy* (the article you're currently reading)
1. [Recruit and onboard talent](hire-to-retire-onboard-manage-employee-lifecycle.md)  
1. [Manage workplace compliance](hire-to-retire-manage-occupational-health-safety.md)
1. [Manage performance and growth](hire-to-retire-manage-employee-performance-growth.md)
1. [Manage time and attendance](hire-to-retire-manage-employee-time-attendance-overview.md)
1. [Manage compensation and benefits](hire-to-retire-manage-employee-benefits-payroll.md)  
1. [Offboard talent](hire-to-retire-onboard-terminate-employment.md)  
1. *Analyze HR programs*

## Related patterns

The following patterns are available to help guide your implementation of the *Communicate issue and changes with HR* business process. (Links are added when the articles are ready.)

- Ask questions about benefits
- Ask questions about compensation
- Ask questions about leave and absence
- Communicate about harassment issues to HR
- Communicate safety issues with HR
- If you see something, say something

## Related resources

You can use the following resources to learn more about the *Communicate issue and changes with HR* process in Dynamics 365.

- [Human resources overview - Human Resources](/dynamics365/fin-ops-core/fin-ops/hr/hr-landing-page?source=recommendations#recruit-hire-and-motivate-employees)
- [Dynamics 365 Human Resources documentation](/dynamics365/human-resources/)

<!-- ## Tags

*Industries:* Agriculture (01-09), Mining (10-14), Construction (15-17), Manufacturing (20-39), Transportation and Public Utilities (40-49), Wholesale Trade (50-51), Retail Trade (52-59), Finance, Insurance, Real Estate (60-67), Services (70-89), Public Administration (91-99)

*Stakeholders:* Finance, Human Resources

*Products:* Dynamics 365 Human Resources -->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal authors:

- [Geert-Jan Jansen](https://www.linkedin.com/in/geert-jan-jansen-b468b411/) | Senior Solutions Manager
- [Kamal Radhakrishnaiah](https://www.linkedin.com/in/kamal-radhakrishnaiah-5816aa69/) | Solution Architect
