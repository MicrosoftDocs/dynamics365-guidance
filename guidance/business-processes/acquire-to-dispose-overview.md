---
title:  Acquire to dispose overview
description: Read about how Dynamics 365 supports the acquire to dispose business process.
ms.date: 04/05/2023
ms.topic: conceptual
author: edupont04
ms.author: archanap

---

# Acquire to dispose end-to-end overview

***Applies to: Dynamics 365 Field Service, Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Guides, Dynamics 365 Remote Assist***

This article describes the *acquire to dispose* end-to-end business process flow and its relationship to other business processes that can be used within Dynamics 365.

## Acquire to dispose process relationship

The following diagram shows the relationship of other processes and products/features for the inventory to deliver process.

:::image type="content" source="media/acquire-to-dispose-process.png" lightbox="media/acquire-to-dispose-process.png" alt-text="Business process relationships with upstream and downstream processes that are explained in the next paragraphs.":::

The upstream processes for the *acquire to dispose* process include the following.

- **Case to resolution**  

  When you want to closely manage the request process for a new asset, consider the use of Case management or Dynamics 365 Customer Service to help you model your business process. Cases can be useful to track the requests, approvals, and actions that must take place from the time the request takes place to the time the request or issue is resolved or completed.

- **Forecast to plan**  

  The forecasting process is upstream from the *acquire to dispose* process because a detailed plan for the required inventory and assets is typically defined before an organization starts to purchase the materials and assets. This is especially true for production operations where expensive machinery or equipment is used in the production process. Most organizations have detailed and stringent processes for making capital investments into new buildings or equipment to support operations.

- **Procure to pay**  

  Many types of assets may require the procurement of multiple items and/or services to create a single asset that is usable by the organization. The procurement process in Dynamics 365 Supply Chain Management supports this process and the conversion to fixed assets when the items are put into service.

- **Product and service lifecycle management**  

  Products or services that need to be procured to either build the fixed asset or for the repair of these internal assets need to be defined as part of the product and service lifecycle management in Dynamics 365 Supply Chain Management. You will need to carefully consider if the materials you are purchasing and consuming for operating or maintaining the assets are considered hazardous. The handling of hazardous materials and material safety data sheets, for example, are handled in the upstream product and service lifecycle management process.

- **Project to profit**  

  When you have large or complex assets that require multiple purchases, services, and span a long amount of time to develop or create the asset, you may want to consider using projects to accumulate all the costs into, say, a "construction in process" account before you start making purchases. This allows you to track the costs and time more effectively. You can also use projects to track the ongoing maintenance of an asset.

- **Record to report**  

  It is important to have good financial policies in place including capitalization thresholds before you start acquiring assets. Many organizations have strict budgeting requirements with respect to capital spend, which is handled in the Budgeting module in Dynamics 365 Finance as part of the record to report process.

The inventory to deliver end-to-end process is broken down into the following business process areas:

- Plan and budget assets

- Acquire assets

- Manage internal assets

- Manage and report on asset financials

- Maintain and repair internal assets

- Retire and dispose of assets

For more information about the business process areas, see [*Acquire to dispose* business process areas](acquire-to-dispose-areas.md)

The downstream processes for the inventory to deliver process include the following.

- **Case to resolution**  

  After an asset is installed and being tracked in the system, you may use cases to track and report issues, or initiate requests for maintenance, asset replacement or leasehold improvements. The Case management process or Dynamics 365 Customer Service can help you internally monitor the requests and follow through issues to resolution.

- **Hire to retire**  

  Many organizations track assets such as computers or vehicles, which may be loaned to an employee. Dynamics 365 Human Resources supports the tracking of loaned items along with the expected return date to help streamline the inventory process of your internal assets. Additionally, when you acquire new equipment to be used in manufacturing processes, for example, you will need to train users on the safe use and operations of the equipment. When workers become ill or injured because of an asset, you will want to track the safety incident information as well, which is covered in the downstream hire to retire process.

- **Inventory to deliver**  

  When you use Dynamics 365 Supply Chain Management to procure assets or parts to maintain assets, the inventory to deliver process is used to receive, track, and consume (or issue) the items to the system.

- **Order to cash**  

  If you sell fixed assets when they reach the end of service, you can use Dynamics 365 Finance to sell the asset through a free text invoice as a mechanism to dispose of the asset in your system.

- **Plan to produce**  

  When you purchase manufacturing equipment, for example, the assets will begin to be used in the production process after they are put into service. Dynamics 365 Supply Chain Management allows you to configure the resources to be used in routes and track the machine usage throughout the production lifecycle.

- **Procure to pay**  

  After fixed assets are put into service, you may begin to perform maintenance or purchase consumables for the assets. Additionally, you may make leasehold improvements which require materials or services to be purchased. These purchases can be tracked against the fixed asset as asset additions.

- **Project to profit**  

  When you use projects to manage your assets, the ongoing maintenance, support, and improvements to the assets can be tracked in a project to help you monitor the overall costs of your assets.

- **Record to report**  

  Each time you acquire an asset, perform write ups or write downs, and depreciate your assets, and so on, the financial impact of these transactions is posted to the fixed asset and asset leasing sub ledger and the general ledger automatically. You can then use the financial data to create financial statements and analyze the asset data.

- **Service to cash**  

  You can use the Service management or Asset management module in Dynamics 365 Supply Chain Management or Dynamics 365 Field Service to track your work orders and maintenance and repair of your assets after they are put into service.

## Featured capabilities

There are product specific capabilities offered that interact with the *acquire to dispose* to process including, but not limited to, the following:

- **Fixed assets**  

  Fixed assets in Dynamics 365 Finance can be utilized to set up and enter acquisition information for fixed assets, and then manage the assets by depreciating them and setting a capitalization threshold to determine depreciation. You can calculate adjustments to the fixed assets, and also dispose them. When you use General ledger together with Fixed assets, you can view the current value of all fixed assets.

- **Asset leasing**  

  Asset leasing captures and processes information about the leases and helps generate journal entries throughout the lifecycle of the lease, from initial recognition, monthly journal entries, to impairment and termination of the lease. Asset leasing integrates with General ledger to ensure that all posted lease transactions update your chart of accounts, with Accounts payable to track lessor invoices in Accounts payable and take future payments from there & with Fixed assets to track leases in the fixed assets register and post right-of-use assets transactions.

- **Maintenance management**  

  Use the Asset management module in Dynamics 365 Supply Chain Management to run preventive, corrective, and predictive maintenance on production equipment and other assets. It includes a mobile app which allows users to request maintenance and review and update work orders on the fly.

- **Internet of Things (IoT) device connectivity**  

  Using Sensor Data Intelligence for Dynamics 365 Supply Chain Management, manufacturers can leverage IoT devices to receive real-time signals on the machine downtime or status. Sensor data notifies the stakeholders to drive predictive maintenance and thus ensure operational efficiency by mitigating potential delays.

- **Dynamics 365 Remote Assist**  

  Remote assist product, used in conjunction with Dynamics 365 Field Service, empower onsite technicians to collaborate with remote collaborators to receive guidance on maintenance and repair of assets and for inspectors to conduct remote inspection on the assets without needing to be physically onsite.

- **Dynamics 365 Guides**  

  Asset management module in Microsoft Dynamics 365 Supply Chain Management with Dynamics 365 Guides provides a worker with the advantage of using mixed-reality guides in their day-to-day service and maintenance workflows. The worker can check the guide associated with a work order's maintenance checklist in the Supply Chain Management mobile app and open the guide in Dynamics 365 Guides HoloLens app.

## Acquire to dispose business process flow

The following diagram shows the high-level flow of the *acquire to dispose* business process. Each solid rectangle on the diagram represents an end-to-end business process area. The sub-processes shown in the diagram are shown for the *acquire to dispose* business process. The arrows on the diagram show the flow of the business process in an organization. If a sub-process can lead to more than one other sub-process, the parallel sub-processes are shown as branches.

:::image type="content" source="media/acquire-to-dispose-flow.png"  lightbox="media/acquire-to-dispose-flow.png" alt-text="*Acquire to dispose* business end-to-end process flow diagram":::

The following steps are illustrated in the *acquire to dispose* end-to-end business process flow diagram.

1. Start

2. *Acquire to dispose* end-to-end process

    1. Plan and budget assets

    2. Acquire assets

        Parallel branches from this subprocess are d. Manage and report on asset financials and Inventory to deliver on the right.

3. Manage internal assets

    Parallel branches from this subprocess are e. Maintain and repair internal assets and Hire to retire

4. Manage and report on asset financials

    Parallel branches from this subprocess are f. Retire and dispose of assets and Record to report

5. Maintain and repair internal assets

    Parallel branches from this subprocess are c. Manage internal assets, Case to resolution, Plan to produce, Procure to pay, Project to profit, Service to cash

6. Retire and dispose of assets

    Parallel branch from this subprocess is Order to cash

3. End

Parallel branches from Start include the following:

1. Record to report connects to a. Plan and budget assets, c. Manage internal assets and e. Maintain and repair internal assets

2. Case to resolution connects to a. Plan and budget assets, c. Manage internal assets and e. Maintain and repair internal assets

3. Forecast to plan connects to a. Plan and budget assets, c. Manage internal assets and e. Maintain and repair internal assets

4. Project to profit connects to a. Plan and budget assets, c. Manage internal assets and e. Maintain and repair internal assets

5. Procure to pay connects to b. Acquire assets

6. Product and service lifecycle management connects to e. Maintain and repair internal assets

The following end-to-end downstream processes have connections to End:  

- Hire to retire  
- Inventory to deliver  
- Case to resolution  
- Plan to produce  
- Procure to pay  
- Project to profit  
- Service to cash  
- Record to report  
- Order to cash  

## Next steps

If you want to implement Dynamics 365 solutions to assist with the *acquire to dispose* business processes, use the following resources and steps to learn more.

- Define the goals and objectives of implementing an *acquire to dispose* technology solution. Learn more at [Implementation strategy](../implementation-guide/implementation-strategy.md).

- Define the business process scope of your project. Learn more at [Process-focused solution](../implementation-guide/process-focused-solution.md)

- Get a demo of Dynamics 365 solutions for the *acquire to dispose* process. For more information, see [Request a demo](https://dynamics.microsoft.com/)

- Sign up for a trial of Dynamics 365. For more information, see [Start a Free Trial for Microsoft Dynamics 365](https://dynamics.microsoft.com/dynamics-365-free-trial/)

## Related resources

You can use the following resources to learn more about the *acquire to dispose* process in Dynamics 365.

- [Asset Management in Dynamics 365 Supply Chain Management Series](https://community.dynamics.com/blogs/post/?postid=cd219602-2708-4b4a-9d62-3af9b4e63e10)

- [Asset management overview](/dynamics365/supply-chain/asset-management/)

- [Asset leasing home page](/dynamics365/finance/asset-leasing/asset-leasing-homepage)

- [Fixed assets home page](/dynamics365/finance/fixed-assets/fixed-assets)

- [Get started with Asset Management for Dynamics 365 Supply Chain Management](/training/modules/get-started-asset-management/)

- [Microsoft Certified: Dynamics 365 Fundamentals (ERP)](/certifications/d365-fundamentals-finance-and-operations-apps-erp/)

- [Microsoft Certified: Dynamics 365 Finance Functional Consultant Associate](/certifications/d365-functional-consultant-financials/)

<!--## Tags
*Stakeholders:* Accounts payable, Accounts receivable, Administrative, Audit, Customer services, Finance, Human resources, Merchandising, Operations, Production, Project management, Purchasing, Retail store operations, Service operations, Treasury

*Products:* Dynamics 365 Field Service, Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Guides, Dynamics 365 Remote Assist
