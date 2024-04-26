---
title: Overview of the hire to retire end-to-end business process flow
description: Learn about the hire to retire end-to-end business process with a flow diagram and learn about the relationship with other processes in Dynamics 365 solutions.
ms.date: 12/12/2023
ms.topic: conceptual
author: edupont04
ms.author: riblack
---

# Overview of the hire to retire business process flow and its relationship to other processes

***Applies to: Dynamics 365 Commerce, Dynamics 365 Finance, Dynamics 365 Human Resources, Dynamics 365 Project Operations, Dynamics 365 Supply Chain Management***

This article describes the *hire to retire* end-to-end business process flow and its relationship to other business processes that can be used within Dynamics 365.

## Hire to retire process relationship

The following diagram shows the relationship of other processes and products/features for the *hire to retire* process.

:::image type="content" source="media/hire-to-retire-relationships.svg" alt-text="Business process relationships with upstream and downstream processes that are explained in the next paragraphs." lightbox="media/hire-to-retire-relationships.svg":::

The upstream processes for the *hire to retire* process include the following list:

- **Acquire to dispose**  

  Many organizations have various assets that are loaned to employees. In Dynamics 365 Finance, the definition of the assets must exist first, before you can loan the assets to the employees.

- **Case to resolution**  

  Many organizations use a case management process to help track requests for the human resources department. This can also be used for IT type requests such as hardware requests for a new hire.

- **Concept to market**  

  In service-based organizations where humans are part of the service offering, you must define the services before you can define the human aspect of the service. This is especially true when you use routes for production and need a human resource to be used in the production process.

- **Forecast to plan**  

  The forecast to plan process includes strategic and operational planning. This is where organizations plan for the structure of the business, forecast revenue and growth, and plan for staffing to support those operational goals.

- **Inventory to deliver**  

  When you use advanced warehouse management with Dynamics 365 Supply Chain Management, you create workers, and you define security access on the shop floor.

- **Order to cash:**  

  In retail organizations, especially those with brick-and-mortar store fronts, the process of planning stores and staffing requirements comes before the actual recruitment and staffing of the stores.

- **Plan to produce**  

  When a manufacturing organization plans production, they must plan for the staff and shifts that will manufacture the products. The production plan is typically put in place before the workforce is hired, and put to work.

- **Procure to pay**  

  In organizations that outsource work or use staffing agencies, the procurement process is upstream to the *hire to retire* process. The procurement process can also be used for outsourcing or using vendors to help with various aspects of the *hire to retire* process such as processing payroll, sourcing benefit providers, using third-party recruiters, and more.

- **Project to profit**  

  In service-based organization, the project needs are often determined before the *hire to retire* process begins. The customer needs define the resources needs, and then the hiring or project staffing process begins.

- **Record to report**  

  Before an organization typically hires, there's a need to define a budget for employees and their related expenses. Benefits and compensation budgets are typically reviewed and approved on a minimum of an annual basis. These budgets are often done before any actual expenses or hiring can take place.

- **Service to cash**  

  In service-based organizations, the definition of the service typically exists before you start to hire employees to perform the service. This can includes the policies, procedures, and so on, that are part of the service to cash process in an organization.

The *hire to retire* end-to-end process is broken down into the following component business process areas including:

- Plan and recruit your workforce

- Onboard and manage the employee lifecycle

- Manage occupational health and safety

- Manage employee performance and growth

- Manage employee time and attendance

- Manage travel and expenses

- Manage employee benefits, compensation, and payroll


For information about the business process areas, see [Hire to retire business process areas](hire-to-retire-areas.md).

The third column in the diagram displays the downstream business process including the following processes:

- **Acquire to dispose**  

  Once you've hired workers, you can begin to loan items that are tracked in Dynamics 365 Finance to those workers in Dynamics 365 Human Resources.

- **Case to resolution**  

  In any organization, you can use the *case to resolution* process to handle requests or issues that workers or employees report throughout the employee lifecycle. Dynamics 365 Human Resources includes case management functionality to support specific scenarios such as Family Medical Leave and Absences (FMLA) requests, safety incidents related to injury or illness, and more.

- **Concept to market**  

  Once you hired the workers, you can link those workers to resources and the services that you offer. For production and services that are skills-based, you must maintain the skills, certifications, and training, for example, of those workers on an ongoing basis to continue the process.

- **Inventory to deliver**  

  When you use advanced warehouse management with Dynamics 365 Supply Chain Management, you must create workers and define security access on the shop floor.

- **Order to cash**  

  Retail organizations, especially those with brick-and-mortar store fronts, must define the schedule, and track the time worked by the staff that they hire. Additionally, in commission-based sales organizations, the *order to cash* process creates the orders that the system then uses to calculate the amount of commission to be paid. That amount is then handled by the *hire to retire* process to pay the employees.

- **Plan to produce**  

  In a manufacturing organization, resources are assigned to the production orders to perform the work. Time is often tracked using the production floor execution devices. The data is then fed to the human resources systems to pay the workers for their time. In organizations where workers are paid based on piece-work, the quantity of items produced also feeds the *hire to retire* process.

- **Procure to pay**  

  In organizations that outsource work or use staffing agencies, the procurement process is also downstream to the *hire to retire* process. The staffing agencies often need to report timesheets in order to pay the outsourced workers. There's also often a need to train the outsourced employees or onboard them into your systems, for example, after they were hired.

- **Project to profit**  

  After workers are hired in service-based organization, the project work begins and the details are often tracked. When employees spend time and incur expenses, amounts are tracked against the project, and the employees are paid for their time and expenses through the *hire to retire* processes.

- **Record to report**  

  In any organization, the *hire to retire* process has many downstream touchpoints. Each time an expense is incurred related to an employee, the cost must be tracked in the general ledger to create accurate financial statements. Often the employee expenses are also allocated to other business processes, for example, to production as overhead costs.

- **Service to cash**  

  In service-based organizations, once employees are hired, the new staff starts work. In pay-for-performance based organizations, the customer satisfaction related to the work performed can affect the pay of the employee.

## Featured capabilities

There are product specific capabilities offered that interact with the *hire to retire* to process including, but not limited to, the following list:

- **Audit trails**  

  Dynamics 365 Human Resources includes capabilities for position and worker actions to track changes to the data and drive customized workflows to get approval for changes, while keeping track of the original values and new values. You can also use customizable business process flows to perform periodic audits on human resources data to ensure compliance and accuracy of your HR related data.

- **Date effectivity**  

  Dynamics 365 Human Resources uses date effectivity to track the values and dates when information changes. Users can easily manage and view changes to records right from the application. You can even make changes future dated to allow your HR staff to stay productive and plan for upcoming events like life events and benefits enrollments.

- **Benefits management**  

  You can easily manage various benefits plans including employee self-service capabilities for enrolling in benefits with open enrollment. You can easily manage life-events that change benefits eligibility and easily integrate with benefit providers using the Power Platform.

- **Employee and manager self-service**  

  Streamline human resources process by enabling your workforce to be self-sufficient and provide guided experiences for interacting with the back office HR team on common issues and requests.

- **Skills and competencies**  

  In many organizations, especially service-based organizations, the ability to track and schedule resources based on skills and other competencies such as certifications, tests, and more is critical in the sales, production, and delivery processes. Dynamics 365 Human Resources includes robust capabilities such as employee self-service to maintain information with integration with other applications, such as Project Operations for services, Supply Chain Management for production, and Customer Service and Sales for daily operations.

- **Leave and absence management**  

  In Dynamics 365 Human Resources, employees can easily view time-off balances and submit leave requests in Microsoft Teams with integration to Outlook. integration with Viva Insights makes the process seamless and keeps your workers productive.

- **Payroll integration APIs**  

  Integrate with payroll providers like Ceridian Dayforce using [Dynamics 365 Finance](https://dynamics.microsoft.com/finance/overview/) and Human Resources

- **Application Tracking System APIs**  

  Find the right candidates by integrating with existing talent acquisition systems (TAS), like Dynamics ATS, iCIMS, and more.

- **Learning management system APIs**  

  Use APIs to connect to various learning management (LMS) or content management systems (CMS) quickly and easily. The data easily integrates into Dynamics 3656 Human Resources for seamless employee self-service experience and reporting using Power BI.

- **Dynamics 365 Customer Voice**  

  Capture employee sentiment using survey insights from Dynamics 365 Customer Voice.

## Hire to retire business process flow

The following diagram shows the high-level flow of the *hire to retire* business process. [!INCLUDE [daf-business-process-e2e-flow-def](~/../shared-content/shared/guidance-includes/daf-business-process-e2e-flow-def.md)]

:::image type="content" source="media/hire-to-retire-flow.svg" alt-text="Flow diagram for the end-to-end business process that is explained in the following paragraphs." lightbox="media/hire-to-retire-flow.svg":::

The following steps are illustrated in the *hire to retire* end-to-end business process flow diagram.

1. Start

2. *Hire to retire*

3. *Plan and recruit your workforce*

    Parallel branches connect to the following end-to-end processes: *forecast to plan*, *case to resolution*, *acquire to dispose*, *plan to produce*, and *project to profit*.

4. *Onboard and manage the employee lifecycle*

    A parallel branch connects to the *case to resolution* and *acquire to dispose* end-to-end processes.

    1. *Manage employee performance and growth*

        Unshown parallel branches connect to the following end-to-end processes: *Case to resolution*, *order to cash*, *plan to produce*, and *project to profit*.

    2. *Manage occupational health and safety*

        Parallel branches connect to the following end-to-end processes: *design to retire*, *inventory to deliver*, *record to report*, and *project to profit*.

    3. *Manage employee time and attendance*
       Parallel branches connect to 5. Manage employee benefits, compensation, and payroll and unshown connections to *order to cash*, *plan to produce*, *project to profit*, and *service to cash* end-to-end processes. 

    4. *Manage travel and expenses*

        Parallel branches connect to 5. Manage employee benefits, compensation, and payroll and unshown connections to *plan to produce*, *project to profit*, and *record to report*.

5. *Manage employee benefits, compensation, and payroll*

    Parallel branches connect to 5. Pay employees and the following end-to-end processes: *procure to pay*, *plan to produce*, *project to profit*, and *record to report*.

6. End

Parallel branches from Start include the following end-to-end processes:

1. *Acquire to dispose*, which connects to 3. *Plan and recruit your workforce* and 4. *Onboard and manage the employee lifecycle*.

2. *Case to resolution*, which connects to b. *Plan and recruit your workforce*.

3. *Concept to market*, which connects to 3. *Plan and recruit your workforce*.
 
4. *Forecast to plan*, which hconnects to 3. *Plan and recruit your workforce*.

5. *Inventory to deliver*, which connects to 3. *Plan and recruit your workforce*.

6. *Order to cash*, which connects to 3. *Plan and recruit your workforce*.

7. *Plan to produce*, which has parallel branches to 3. *Plan and recruit your workforce*, 4. *Onboard and manage the employee lifecycle*.

8. *Procure to pay*, which has unshown parallel branches that connect to 3. *Plan and recruit your workforce* and *Manage travel and expenses*.

9. *Project to profit*, which has unshown parallel branches connect to 3. *Plan and recruit your workforce*, 4. *Onboard and manage the employee lifecycle*, and 4.iv. *Manage travel and expenses*.

10. *Record to report*, which connects to 3. *Plan and recruit your workforce*.

11. *Service to cash*, which has unshown parallel branches connect to 3. *Plan and recruit your workforce*, 4. *Onboard and manage the employee lifecycle*, and 4.iv. *Manage travel and expenses*.

The following end-to-end downstream processes also connect to End:

- *Acquire to dispose*

- *Case to resolution*

- *Forecast to plan*

- *Inventory to deliver*

- *Order to cash*

- *Plan to produce*

- *Procure to pay*

- *Design to retire*

- *Project to profit*

- *Record to report*

- *Service to cash*

## Next steps

If you want to implement Dynamics 365 solutions to assist with your *hire to retire* business processes, use the following resources and steps to learn more.

1. Define the goals and objectives of implementing a *hire to retire* technology solution. Learn more at [Implementation strategy](../implementation-guide/implementation-strategy.md).

2. Define the business process scope of your project. Learn more at [Process-focused solution](../implementation-guide/process-focused-solution.md).

3. Request a demo or a free trial of Dynamics 365 solutions for the *hire to retire* process. For more information, see [Request a demo](https://dynamics.microsoft.com/dynamics-365-free-trial/).

4. Review the [Hire to retire introduction](hire-to-retire-introduction.md)  

5. Learn more about [Hire to retire business process areas](hire-to-retire-areas.md)

## Related resources

You can use the following resources to learn more about the *hire to retire* process in Dynamics 365.

- TechTalks [HR Functional Series - Microsoft Dynamics Blog](https://community.dynamics.com/blogs/post/?postid=56329c48-c155-48ed-821b-4d0eb52b2d3b)

- [Get started and use functionality in Microsoft Dynamics 365 Human Resources](/training/paths/get-started-use-human-resources/)

- [Learn the fundamentals of Dynamics 365 Human Resources](/training/paths/learn-fundamentals-microsoft-dynamics-365-human-resources/)

- [Human Resources home page](/dynamics365/human-resources/)

- [Microsoft Certified: Dynamics 365 Fundamentals (ERP)](/certifications/d365-fundamentals-finance-and-operations-apps-erp/)

<!--## Tags
*Stakeholders:* Administrative, Finance, Human Resources, IT, Operations, Project management, Retail store operations, Service operations

*Products:* Dynamics 365 Commerce, Dynamics 365 Customer Service, Dynamics 365 Customer Voice, Dynamics 365 Finance, Dynamics 365 Field Service, Dynamics 365 Human Resources, Dynamics 365 Project Operations, Dynamics 365 Sales, Dynamics 365 Supply Chain Management
