---
title: TechTalk Tax calculation updates in 2024
description: Summary of TechTalk video that talks about the updates to tax calculation in Dynamics 365 Finance in 2024. 
ms.date: 10/07/2024
ms.topic: conceptual
author: edupont04
ms.author: edupont
ai-usage: ai-assisted
---

# TechTalk: Tax calculation updates in 2024

Tax calculation services continue to evolve in 2024, especially in Dynamics 365 Finance. This year's updates introduce several significant features, including enhanced integration options and new tools to streamline tax processing. Here's an overview of the latest developments in tax calculation.

We based this article on [a TechTalk](https://youtu.be/0VFeRi_S8r0) that you can find online in the Dynamics 365 channel on YouTube.  

:::image type="content" source="media/finance-updates-2024-slide.png" alt-text="Thumbnail of the first slide in the presentation." link="https://youtu.be/0VFeRi_S8r0":::

## New capabilities in 2024

Dynamics 365 has always prioritized user input, and the updates this year are a testament to that focus. One of the top-rated ideas on the idea portal, the introduction of more currency exchange rate types for tax calculation, is now a reality. This update allows businesses to use a different exchange rate for tax calculation than the one used for their standard accounting processes, which is a crucial need for companies operating across multiple currencies.

[Tax Calculation](/dynamics365/finance/localizations/global/global-tax-calcuation-service-overview?context=%2Fdynamics365%2Fcontext%2Ffinance) enables direct recalculation from the transaction currency to the tax currency. This not only ensures compliance with local tax reporting but also provides flexibility in adjusting amounts in the tax currency.  

For businesses looking to switch to this new system, enabling the feature in the **Feature Management** workspace and selecting it in the General Ledger parameters is a simple process. However, the system prompts users to recalculate taxes for any unposted documents to ensure accuracy.

## Expanding integration with project transactions

One of the significant focuses of this year's updates is the expanded integration of tax calculation with various transaction types, particularly transactions for project management accounting. As of version 10.0.38, tax calculation is now fully integrated with these transactions in modules in Dynamics 365 finance and operations apps.

Businesses can enable project transactions in the tax calculation parameters, allowing tax to be calculated based on the defined tax features. This update supports a wide array of project transactions, including project invoice proposals. It also supports various journal types, such as expense, item, and fee project partitions. For businesses that operate in India, Dynamics 365 provides enhanced support for GST, TDS, and TCS taxes for project accounting transactions, making tax compliance easier and more efficient.

## Integration with external tax solutions - Universal Tax Rate API

For enterprise customers operating in diverse tax jurisdictions, managing various tax rates and rules can be overwhelming. To address this challenge, the 2024 update introduces the Universal Tax Rate API, which allows businesses to integrate with external tax solution providers such as Vertex or Avalara.  

The following image is based on a slide that provides an overview of the Universal Tax Rate API. It outlines how this API, an extension of the existing Tax Calculation feature in Microsoft Dynamics 365 applications, connects to external tax services under a unified framework.  

:::image type="content" source="media/finance-updates-2024-universal-tax-rate-api.png" alt-text="The image includes three sections: an explanation of the Universal Tax Rate API, its business values, and a diagram illustrating the API's interaction between Microsoft business applications and external tax services. The diagram features flow arrows for API requests and returns that connect elements labeled as Microsoft business applications, Globalization Studio workspace, and external tax services with components like Tax Solution and Tax Rate Setup." lightbox="media/finance-updates-2024-universal-tax-rate-api.png":::

The API framework provides a seamless connection between Dynamics 365 and external tax providers, helping reduce the complexity of managing multiple tax rates and ensuring up-to-date compliance. When businesses use this integration, they can streamline their tax operations, minimizing the need for constant manual updates.

To start using this feature, businesses must enable the external tax solution provider for the tax calculation service in the **Feature Management** workspace. As of now, the API supports U.S.-based businesses, but the framework will likely expand to other regions in the future.

## Security and compliance with address validation and use tax accrual

One of the key updates this year is the introduction of an encrypted connection via Azure Key Vault, ensuring secure and private transmission of tax data to external tax solution providers. This is a critical feature for businesses dealing with sensitive financial data and operating in multiple jurisdictions.

Another notable feature is the address validation functionality, which helps businesses maintain accurate addresses within their global address book, crucial for ensuring precise tax calculations. This is especially useful for companies operating across various regions where tax rates and rules vary based on location.

Additionally, the use tax accrual feature, primarily for U.S.-based businesses, allows buyers to assess use tax liability when receiving vendor invoices. If the sales tax on the invoice is lower than expected, the Dynamics 365 automatically generates a use tax transaction to account for the difference. This feature ensures compliance with local tax laws, particularly in scenarios where sellers undercharge sales tax.

## A streamlined approach for tax calculation unification

The 2024 update also introduces a significant change with the unification of the tax calculation service directly into Dynamics 365 Finance. This move simplifies the tax calculation process by merging the regulatory configuration service (RCS) with Dynamics finance and operations apps, centralizing the setup and configuration for tax calculations in the **Globalization Studio** workspace.

The following image is based on a slide that illustrates the evolution of the tax calculation architecture for a financial system.  

:::image type="content" source="media/finance-updates-2024-tax-calculation-unification.png" alt-text="The image shows two diagrams side by side to indicate a transition from an older system to a newer one. The text after the image explains further details." lightbox="media/finance-updates-2024-tax-calculation-unification.png":::

In the image, the left diagram displays components such as the *Regulatory Configuration Service*, *Global Repository*, and external tax rate APIs that link to a central **Tax Calculation** module, which then connects to modules for **India GTE** and **Transaction Operations** in Dynamics 365 Finance. The right diagram refines this architecture by integrating these components into a more streamlined setup where the **Globalization Studio** workspace and **Dataverse Repository** are more centrally connected to the **Tax Calculation**, which still oversees **India GTE** and **Transaction Operations**. This visual representation highlights the system's strategic shift towards greater integration and simplification in handling tax calculations across different regions and platforms.

This unification means that businesses no longer need to rely on a separate tier-two environment for tax calculation. As a result, the process is more efficient with lower complexity of tax management. With this change, businesses can now maintain and manage their tax configurations directly in Dynamics 365 Finance.

## Looking ahead to future enhancements

As Dynamics 365 continues to evolve, the roadmap for tax calculation looks promising. The introduction of the Universal Tax Rate API marks the beginning of more advanced integrations. Microsoft's collaboration with ISVs such as Vertex and Avalara ensures that businesses continue to receive timely updates and support for their tax needs.

For companies operating in the European Union and other regions, future updates are expected to expand the scope of the API and provide more localized tax support. As tax regulations grow increasingly complex, these updates are crucial in helping businesses remain compliant and efficient in their operations.

## Related resources

You can use the following resources to learn more about Dynamics 365.

- [Tax Calculation overview](/dynamics365/finance/localizations/global/global-tax-calcuation-service-overview?context=%2Fdynamics365%2Fcontext%2Ffinance)  
- [Connect to an external tax solution provider via the Universal Tax Rate API](/dynamics365/finance/localizations/global/universal-tax-rate-api-overview?context=%2Fdynamics365%2Fcontext%2Ffinance)  
- [What are the Dynamics 365 TechTalk videos?](../roles/techtalk-videos.md)
- [TechTalk on the Dynamics Community website](https://community.dynamics.com/videos/)
- [Dynamics 365 channel on YouTube](https://www.youtube.com/channel/UC5QxCcXhFFixs1nfmOpJlvQ)
