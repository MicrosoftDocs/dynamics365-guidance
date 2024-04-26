---
title: Copilot in Dynamics 365 Customer Service architecture
description: View the architecture diagram to understand how Copilot works in Dynamics 365 Customer Service, including overviews on dataflows and components.
author: neeranelli
ms.author: nenellim
ms.topic: conceptual
ms.reviewer: edupont
ms.custom: bap-template
ms.date: 12/18/2023
ms.collection:
---

# Copilot in Dynamics 365 Customer Service architecture

The following architecture diagram provides a visual representation of how Microsoft Copilot for Customer Service works. This solution is a generalized architecture pattern, which can be used for many different scenarios and industries.  

## Architecture

:::image type="content" source="../media/architecture-copilot-dynamics365-customer-service.svg" alt-text="A architecture diagram with a Customer Service environment, Azure Open AI Services, and arrows for prompts and responses." lightbox="../media/architecture-copilot-dynamics365-customer-service.svg":::

<!--Download a PowerPoint file with this architecture.-->

### Dataflow

All requests are encrypted through HTTPS, which is illustrated with the :::image type="icon" source="../media/https-icon.svg" border="false"::: icon in the diagram. 

1. A user in Dynamics 365 Customer Service submits a prompt that is sent to Copilot  
2. Copilot accesses Dataverse and Semantic Index for preprocessing  
3. Copilot sends meta prompt, user prompt, and contextual data to Large Language Model (LLM)  
4. Copilot receives LLM response  
5. Copilot accesses Dataverse and Semantic Index for post-processing
6. Copilot sends the response 

### Components

- [Dynamics 365 Customer Service](/dynamics365/customer-service/)  
- [Manage Copilot features in Customer Service](/dynamics365/customer-service/administer/configure-copilot-features)  
- [Microsoft Dataverse](/power-apps/maker/data-platform/)  
- [Azure OpenAI service](/azure/ai-services/openai/)  

<!-- ## Scenario details

**add scenarios** -->

<!-- ## Considerations -->

<!-- *REQUIRED STATEMENT: Include the following statement to introduce this section:* -->

<!-- These considerations help implement a solution that includes Dynamics 365. Learn more at [Dynamics 365 guidance documentation](/dynamics365/guidance/).
 -->
<!-- **add considerations** -->

### Cost optimization

<!-- *REQUIRED: This section is required. Cost is of the utmost importance to our customers.* -->

Cost optimization is about looking at ways to reduce unnecessary expenses and improve operational efficiencies. Learn more at [Overview of the cost optimization pillar](/azure/architecture/framework/cost/overview).

<!-- **add guidance**

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

**Principal authors:**

- 

**Other contributors:**  

- 

> [!TIP]
> To see non-public LinkedIn profiles, sign in to LinkedIn. -->

## Next step

- [Dynamics 365 Customer Service implementation optimization resources](../resources/cs-index.yml)  


## Related resources

Review the following related architecture guides, solutions, and other guidance content:

- [Artificial intelligence (AI) - Architectural overview](/azure/architecture/data-guide/big-data/ai-overview)
