---
title: Options for regression testing for Dynamics 365 solutions
description: Learn about some of the tools that you can use for automating regression testing of your Dynamics 365 solution and how to evaluate them for your needs.
author: edupont04
ms.author: dudona
ms.topic: concept-article
ms.date: 09/26/2025
ms.update-cycle: 1095-days
ms.custom:
  - evergreen
  - ai-seo-date: 01/23/2024
  - ai-gen-docs-bap
  - ai-gen-title
  - ai-gen-desc
content_well_notification: AI-contribution
---

# Options for regression testing

After each Dynamics 365 update from Microsoft, you must make sure that your solution still works as expected. You don't want to introduce any bugs or errors that could affect your users or customers. Microsoft does regression testing, but the data composition, specific customer configurations, and unique extensions mean customers must perform their own regression testing in their own environment.

But regression testing can take a lot of time and effort if you do it manually. You can save time and resources by automating your regression testing with a tool. Many tools are available for regression testing, both from Microsoft and other providers. How do you choose the best one for your needs?

## Compare different tools for regression testing

The following table shows some of the tools that you can use for regression testing. It also shows whether they're free or paid, and whether they support different types of testing, such as web, desktop, or mobile.

:::image type="content" source="media/regression-test-tooling-options.svg" alt-text="Matrix table of solutions from Microsoft and other providers to help with regression testing." lightbox="media/regression-test-tooling-options.svg":::

Learn more about each tool:

- [TheTestMart](https://appsource.microsoft.com/en-US/product/dynamics-365-for-operations/360testinglimited1633924951153.the-test-mart?tab=Overview)  

  TheTestMart is a cloud-based code-free test automation platform that focuses on scaling up automation coverage and productivity across  core business platforms by applying command-driven techniques.  
- [Elevaite365​ Test Automation](https://azuremarketplace.microsoft.com/en-us/marketplace/apps/elevaite365.e365ta?tab=Overview)  

  Elevaite Test Automation is an AI-powered platform purpose-built for Microsoft Dynamics 365. The solution empowers organizations to automate and optimize their testing processes, delivering enterprise-grade quality assurance with unmatched efficiency​.
- [Leapwork Test Automation](https://azuremarketplace.microsoft.com/marketplace/apps/leapwork1651672519978.leapwork_azure?tab=Overview)  

  Leapwork Test Automation automates testing across Dynamics 365, Azure, or Power Platform along with the rest of the tech stack. Build, maintain, and scale automation faster with its AI-powered visual test automation platform.  

- [Microsoft Regression suite automation tool (RSAT)](/dynamics365/fin-ops-core/dev-itpro/perf-test/rsat/rsat-overview)  

  Microsoft RSAT significantly reduces the time and cost of user acceptance testing (UAT) of finance and operations apps. RSAT is fully integrated with Microsoft Azure DevOps for test execution, reporting, and investigation.  
- [Microsoft Easy Repro](https://github.com/microsoft/EasyRepro)  

  Microsoft EasyRepro is a library with tools to facilitate automated UI testing for projects with Dynamics 365 Online version 9.0 or 9.2. These APIs provide an easy to use set of commands that make setting up UI testing quick and easy.  
- [Microsoft Playwright](https://github.com/microsoft/playwright)  

  Microsoft Playwright is a framework for web testing and automation. It allows testing Chromium, Firefox, and WebKit with a single API. Playwright is built to enable cross-browser web automation.  
- [Selenium](https://www.selenium.dev/)  

  Selenium is an umbrella project for a range of tools and libraries that enable and support the automation of web browsers. Primarily used for front-end testing of websites, it's a browser user agent library.  
- [Tricentis Tosca](https://azuremarketplace.microsoft.com/marketplace/apps/tricentis.testing_sap_automation_oracle_devops?tab=Overview)  

  Tricentis Tosca helps enterprises plan, construct, stabilize, and execute resilient automated regression tests for Microsoft Dynamics 365 apps.  
- [Executive Automats 365](https://appsource.microsoft.com/en-US/product/SaaS/xplus_sa.xpl_executiveautomats)  

  Executive Automats 365 from XPLUS SA allows you to significantly shorten the test procedure and increase its accuracy. Executive Automats 365 offers fully repeatable, customizable, 100% codeless, and cross-platform testing that translates into tangible benefits for the company.  

- [Alithya Rapid QA](https://marketplace.microsoft.com/en-us/product/saas/fullscope.rapid_qa?tab=Overview) 

  Rapid QA is a product-agnostic automated testing solution that accelerates Dynamics 365 upgrades and validation, offering prebuilt end-to-end scenarios, which can be customized and enhanced, covering full breadth of the D365 deployment, including integrations and 3rd party solutions. Includes RSAT Test converter for easy migration of existing RSAT test assets. It includes AI-enabled accelerators and multi-language support to enhance quality and efficiency across environments. 

Before you decide on a tool, you should evaluate how well it meets your business needs. You should consider the following factors:

- The installation and setup of the tool
- The ease and speed of creating and updating test cases
- The product support and documentation available
- The ongoing maintenance and updates of the tool

Some tools are free, but they might require more technical skills or manual work. Some tools are paid, but they might offer more features or support. You should compare the total cost of ownership (TCO) and the return on investment (ROI) of each tool for your scenario. The best tool for you might not be the cheapest one&mdash;or the most expensive.

## Make your own choice based on your situation

Every organization has a unique environment and profile. That's why Microsoft doesn't recommend one tool over another. You should choose the tool that works best for your solution, your budget, and your goals. You can use the information and links in this article as a starting point for your research.

## Give us your feedback

If you have any suggestions or corrections for this article or the list of tools, let us know at `RTChartFeedback@microsoft.com`.

We can't reply to all messages, but we appreciate your feedback, and we'll review it as soon as possible.

## Next steps

- Review the Success by Design [checklist](testing-strategy-checklist.md) of the key steps and tasks for your testing process
- Read a [case study](testing-strategy-case-study.md) of how an organization implemented a testing strategy for its Dynamics 365 solution
