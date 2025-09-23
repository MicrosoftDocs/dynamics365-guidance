---
title: Manage cases and requests in Dynamics 365
description: Discover how Dynamics 365 Human Resources helps HR teams resolve employee issues, implement policy changes, and manage benefits and compensation effectively.
#customer intent: As an implementor, I want to understand the business process for case management so that I can configure the Dynamics 365 solution to provide consistent and accurate resolutions for HR professionals.
author: edupont04
ms.author: prsinha
ms.reviewer: edupont
ms.date: 09/23/2025
ms.topic: concept-article
---

# Overview of the Manage cases and requests business process within the Hire-to-retire end-to-end scenario

***Applies to***: ***Dynamics 365 Human Resources***

This article describes the background of manage cases and requests in business solutions. The article uses Dynamics 365 Human Resources to illustrate the business process. The purpose of cases and requests is to develop efficient resolutions that the organization can then use for similar issues by planning, tracking, and analyzing cases.

Managing cases and requests with the human resources (HR) department is crucial because:

- Resolve issues  

  When employees face problems related to colleagues, the work environment, or job responsibilities, HR mediates conflicts, gives guidance, and takes action to ensure a positive workplace and address concerns promptly.

- Policy changes  

  HR is responsible for communicating and implementing policy changes within the organization. If employees have suggestions or concerns about these policies, it's essential to communicate them to HR so that HR can make necessary adjustments and keep everyone informed.

- Personal changes  

  When an employee's personal information changes, such as marital status, address, or emergency contact information, HR needs to know. Updating employee records ensures accurate information and helps the organization respond appropriately in emergencies.

- Benefits and compensation  

  HR manages employee benefits and compensation. If employees have questions or issues related to benefits, payroll, or other compensation matters, contacting HR directly is the recommended approach.

Workplace harassment significantly affects employees' well-being, productivity, and the work environment. Common types of workplace harassment to report to your organization include the following list:

- *Discriminatory harassment* occurs when someone targets an individual based on their membership in a protected class. These classes include sex/gender, age, race, religion, color, national origin, and physical or mental ability.

- *Sexual harassment* involves unwelcome sexual advances, requests for sexual favors, or other verbal or physical conduct of a sexual nature.

- *Bullying and intimidation* involves behavior that intimidates or offends someone.

- *Racial harassment* targets an individual based on their race, skin color, ancestry, or other perceived attributes related to ethnicity.

- *Religious harassment* targets an individual based on their religious beliefs or practices.

- *Retaliation* occurs when an employer punishes an employee for reporting harassment or participating in an investigation.

## Stakeholders

The *Manage cases and requests* business process in Dynamics 365 Human Resources involves several key stakeholders.

- Human resources managers define the organizational structure, plan and manage the employee lifecycle. They define and manage hiring needs, employee benefits, compensation plans, and other human resource processes.

- Hiring managers request positions, participate in the recruitment process, and make final hiring decisions.

- The IT team maintains and supports IT systems and manages the IT hardware employees receive.

- Employees are the end users that use self-service to update their information or approve assigned work items.

- Managers manage a team and handle the team's information, including performance reviews, leave, timesheets, and approvals.

## Manage cases and requests process flow

The following diagram illustrates the flow of the *Manage cases and requests* business process with the **HR Manager** as the user role.

:::image type="content" source="media/hire-to-retire-manage-cases-requests-flow.svg" alt-text="Flow diagram with steps for the process that is explained further in the next paragraphs." lightbox="media/hire-to-retire-manage-cases-requests-flow.svg":::

1. *Receive a case or request*.  
1. *Document the case or request*.  
1. *Investigate the case or request*.  
1. *Implement the resolution*.  
1. *Communicate the resolution*.
1. End  

## Implement the business process for managing cases and requests

The *Manage cases and requests* business process relies on the *Human resources parameters* and settings, so make sure they're part of the implementation project. You can configure these parameters either for the specific legal entity you're associated with or as shared parameters across the organization. Their purpose is to govern specific behaviors within HR features, aligned with business policies.

Dynamics 365 Human Resources offers a complete case management system that lets employees communicate issues and changes effectively. Here are options for managing cases:

- A *case* in Dynamics 365 Human Resources represents a single incident of service. It can be anything that needs a resolution or answer. You can associate multiple cases with a single employee at any time. Typical issues and questions you track with cases include:

  - Questions about benefits
  - Questions about compensation
  - Questions about leave and absence
  - Reporting harassment issues to HR
  - Reporting safety issues to HR
  - Reporting concerns (if you see something, say something)  
- *Activities* typically represent an interaction with an employee, like a phone call. You can associate multiple activities with a single case.

- *Entitlements* specify the number of support services an employee can use. They're like support contracts.

- *Knowledge articles* in the knowledge base help employee service representatives resolve cases.

- A *queue* organizes and stores activities and cases that are waiting to be processed.

- *Service-level agreements* (SLAs) track and define what happens when a case is opened, like how long it should take to respond to an employee.

- *Rules for creating and updating records* apply to different activity types to automatically create Dynamics 365 records.

These components let employees communicate issues and changes to the HR department. The HR department uses the same system to track issues, assign them to the right personnel, and make sure they're resolved quickly. This process improves efficiency and the employee experience.

The following table explains the configuration components that support the *Manage cases and requests* business process. The table uses the acronym *DMF* for the *data management framework* in finance and operations apps.

| **Process step** | **Process stage** | **Process modifier** | **Application: Navigation and Entity** |
|---|---|---|---|
| [Configure Case categories](/dynamics365/fin-ops-core/dev-itpro/organization-administration/plan-case-management#case-categories) | Initialize; Base; Configuration | Gold; At least one | FIN: Organization administration > Setup > Case categories<br>DMF: CaseCategoryHierarchyDetailEntity |
| [Configure Case category security by role](/dynamics365/fin-ops-core/dev-itpro/organization-administration/plan-case-management#case-category-security-by-role) | Initialize; Base; Configuration | Gold; At least one | FIN: Organization administration > Setup > Case category type security<br>DMF: CaseCategoryTypeSecurityEntity |
| [Configure Case processes](/dynamics365/fin-ops-core/dev-itpro/organization-administration/plan-case-management#case-processes) | Initialize; Base; Configuration | Gold; At least one | FIN: Organization administration > Setup > Case process<br>DMF: NA |
| [Configure Case workflow](/dynamics365/fin-ops-core/fin-ops/organization-administration/overview-workflow-system) | Initialize; Base; Configuration | Gold; At least one | FIN: Organization administration > Setup > Case workflow<br>DMF: NA |

## Next steps

If you want to implement Dynamics 365 solutions to assist with your *Manage cases and requests* business processes, you can use the following resources and steps to learn more. (Links are added later, when the articles are ready.)

- [Develop people strategy](hire-to-retire-plan-recruit-workforce-overview.md)

- [Recruit and onboard talent](hire-to-retire-onboard-manage-employee-lifecycle.md)

- [Manage workplace compliance](hire-to-retire-manage-occupational-health-safety.md)

  - *Document safety protocols*
  - *Audit workplace for safety*
  - *Report an injury or illness*
  - *Verify employment*
  - [Update worker information](hire-to-retire-update-employee-records.md)
  - *Manage cases and requests* (the article you're currently reading)

- [Manage performance and growth](hire-to-retire-manage-employee-performance-growth.md)

- [Manage time and attendance](hire-to-retire-manage-employee-time-attendance-overview.md)

- [Manage compensation and benefits](hire-to-retire-manage-employee-benefits-payroll.md)

- *Offboard talent*

- *Analyze HR programs*

## Related patterns

These patterns can help you implement the *Manage cases and requests* business process.

- *Use cases in Dynamics 365 Human Resources to manage requests*
- *Use cases in Dynamics 365 Customer Service to manage requests*
- *Use SharePoint to manage requests*
- *Use Copilot to manage requests*

## Related resources

Use the following resources to learn more about the *Manage cases and requests* business process in Dynamics 365.

- [Configure Human resources parameters](/dynamics365/human-resources/hr-setup-parameters)  
- [Configure shared parameters](/dynamics365/human-resources/hr-setup-shared-parameters)  
- [Case management overview](/dynamics365/fin-ops-core/dev-itpro/organization-administration/cases?toc=%2Fdynamics365%2Fhuman-resources%2Ftoc.json)
- [Human resources overview](/dynamics365/fin-ops-core/fin-ops/hr/hr-landing-page?toc=%2Fdynamics365%2Fhuman-resources%2Ftoc.json)  
- [Dynamics 365 Human Resources documentation](/dynamics365/human-resources/)  
<!-- 
## Tags

*Industries:* Agriculture (01-09), Mining (10-14), Construction (15-17), Manufacturing (20-39), Transportation and Public Utilities (40-49), Wholesale Trade (50-51), Retail Trade (52-59), Finance, Insurance, Real Estate (60-67), Services (70-89), Public administration (91-99)

*Stakeholders:* Finance, Human Resources

*Products:* Dynamics 365 Human Resources -->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors:*

Principal authors:

- [Geert-Jan Jansen](https://www.linkedin.com/in/geert-jan-jansen-b468b411/)\| Senior Solutions Manager

- [Kamal Radhakrishnaiah](https://www.linkedin.com/in/kamal-radhakrishnaiah-5816aa69/) \|Solution Architect

Contributors:

- [Ruchi Sharma](https://www.linkedin.com/in/ruchi-sharma-90a49089/) \| Senior Customer Solution Architect

- [Ramappa Magadum](https://www.linkedin.com/in/rammagadum/) \| Senior Product Manager
