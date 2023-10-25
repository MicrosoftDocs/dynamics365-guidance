---
title: Regression testing tooling options
description: Learn how to keep track of the impact of Microsoft's service updates to Dynamics 365 on your solution.
author: edupont04
ms.author: dudona
ms.topic: conceptual
ms.collection: #Required; leave the value blank.
ms.date: 09/26/2023
ms.custom: bap-template #Required; don't change.
# CustomerIntent: As an admin, I want some suggestions of available tools for testing so that I can keep up with Microsoft.
---

<!-- suggest shortening the title to "Options for regression testing" -->

# What are the options for regression testing?

As Microsoft releases Dynamics 365 service updates, you must reduce the risk of introducing regressions into production. Regressions can negatively impact internal users, but they may also impact the service you provide to your customers. While Microsoft does its own regression testing, the data composition, specific customer configurations, and unique extensions mean customers must perform their own regression testing in their own environment. By automating this testing, you can reduce the overall effort from days or weeks to hours.  

## Suggested solutions

The following illustration provides an overview of suggested solutions that you can use for regression testing. But there are other solutions out there, so choose one that works for your project.

:::image type="content" source="media/regression-test-tooling-options.svg" alt-text="Matrix table of solutions from Microsoft and other providers to help with regression testing." lightbox="media/regression-test-tooling-options.svg":::

Learn more about each solution at the following locations:

- [TheTestMart](https://appsource.microsoft.com/en-US/product/dynamics-365-for-operations/360testinglimited1633924951153.the-test-mart?tab=Overview)  
- [Leapwork Test Automation](https://azuremarketplace.microsoft.com/en-us/marketplace/apps/leapwork1651672519978.leapwork_azure?tab=Overview)  
- [Microsoft Regression suite automation tool (RSAT)](/dynamics365/fin-ops-core/dev-itpro/perf-test/rsat/rsat-overview)  
- [Microsoft Easy Repro](https://github.com/microsoft/EasyRepro)  
- [Microsoft Playwright](https://github.com/microsoft/playwright)  
- [Selenium](https://www.selenium.dev/)  
- [Tricentis Tosca](https://azuremarketplace.microsoft.com/en-us/marketplace/apps/tricentis.testing_sap_automation_oracle_devops?tab=Overview)  
- [Executive Automats 365](https://appsource.microsoft.com/en-US/product/SaaS/xplus_sa.xpl_executiveautomats)  

## Subscriptions versus free of charge

Review each of the solution capabilities to ensure the return on investment, *ROI*, fits your business need. We recommend you review solution installation, test case creation, product support, and ongoing maintenance of the test cases. The total cost of ownership, *TCO*, may be lower for a paid solution, depending on your environment's complexity and size. 

## No recommendations from Microsoft

Each organization has a unique environment and profile. That's why we can't recommend one solution over another. We recommend that you evaluate the capabilities of each of the solutions against your business needs. Use the provided links for more information.  

## Related resources

Use the following resources to learn more about regression testing:

- [Types of tests in Dynamics 365 implementations](testing-strategy-test-types.md#regression-testing)  
- [Types of Software Testing – javatpoint](https://www.javatpoint.com/types-of-software-testing)  

  At this external website, you can find more information about the different types of software testing, including Whitebox and Blackbox.   

## Request updates

If you see something on the list or in this article that needs an update, let us know at *RTChartFeedback@microsoft.com*.  

> [!NOTE]
> We can't respond to all requests, although we make every effort to review all requests in a timely manner.

## Next steps

[Testing strategy in Dynamics 365 implementation projects](testing-strategy.md)
