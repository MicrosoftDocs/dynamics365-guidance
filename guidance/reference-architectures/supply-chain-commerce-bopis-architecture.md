---
title: Implement BOPIS with Dynamics 365 Commerce
description: Learn how to implement a seamless Buy Online, Pickup In-Store (BOPIS) solution with Dynamics 365 Commerce, Supply Chain Management, and Azure Logic Apps.
#customer intent: As an IT architect, I want to integrate Dynamics 365 Commerce with third-party e-commerce platforms so that I can enable seamless data flow between systems.
author: edupont04
ms.author: edupont
ms.reviewer: edupont
ms.date: 09/26/2025
ms.topic: reference-architecture
---
# Architecture for buy online, pickup at store with Dynamics 365 Commerce and Dynamics 365 Supply Chain Management

***Applies to***: ***Dynamics 365 Commerce, Dynamics 365 Supply Chain Management, Azure Logic Apps***

This solution combines Dynamics 365 Commerce, Dynamics 365 Supply Chain Management, Azure Logic Apps, and any e-commerce solution to support the *buy online and pickup at store* (BOPIS) scenario. It applies to organizations that implement BOPIS with an external e-commerce service.

## Use cases and industries for BOPIS

Key use cases:

- **Order Fulfillment:** BOPIS is ideal for retailers who want to streamline order fulfillment by letting customers pick up online orders in store.
- **Inventory Management:** It helps manage inventory more efficiently by integrating online and offline stock.
- **Customer Experience:** It improves customer satisfaction by offering a convenient shopping option that combines online browsing with quick in-store pickup.

Key industries:

- **Retail:** Particularly helpful for fashion, electronics, groceries, and home improvement sectors.
- **Pharmacy:** Lets customers order prescriptions online and pick them up when it's convenient.
- **Automotive:** Useful for auto parts retailers where customers can order parts online and pick them up in store.

Define the reference architecture for BOPIS during the initial planning phase. This approach makes sure all necessary components, like inventory management systems, order processing, and customer communication channels, are integrated from the start. Early definition aligns technical and business requirements, and helps ensure a smoother implementation process.

## Stakeholders

Key stakeholders in this solution architecture:

- Retail operations managers make sure the solution fits store operations and customer service standards.

- IT and system architects connect the BOPIS system with existing IT infrastructure and make sure data moves between online and offline systems.

- Supply chain managers handle inventory and logistics, and make sure products are ready for pickup.

- Marketing teams promote the BOPIS option and make sure it fits the overall customer experience strategy.

- Customer service representatives help with any issues or questions about BOPIS orders.

## Architecture

This section shows the solution architecture.

:::image type="content" source="media/supply-chain-commerce-bopis-architecture.svg" alt-text="Diagram that shows the supply chain commerce BOPIS architecture." lightbox="media/supply-chain-commerce-bopis-architecture.svg":::
<!-- 
Download a PowerPoint file with this architecture:
[bopis-reference-architecture.pptx](https://1drv.ms/p/s!AlcJpScipXYClYJNhNDJZDmSFRhVaA?e=rfUWws) -->

## Dataflow

:::image type="content" source="media/supply-chain-commerce-bopis-architecture-flow.png" alt-text="Screenshot of a BOPIS dataflow diagram that shows the steps from order placement to order completion in Dynamics 365 Commerce." lightbox="media/supply-chain-commerce-bopis-architecture-flow.png":::

1. Customer places order

    - The customer selects items in the online store and chooses the BOPIS option at checkout.

1. Order processing

    - The e-commerce platform checks if the items are available in the selected store's inventory.
    - If the items are available, the system confirms the order and sends a confirmation message to the customer.
    - The system sends the order details to Dynamics 365 Commerce HQ.

1. Inventory update

    - The store's inventory system updates the reservation in Dynamics 365 Commerce HQ inventory for the BOPIS order.
    - The system syncs inventory data across all sales channels to prevent overselling.

1. Order preparation

    - Store staff get a notification to prepare the order for pickup at Dynamics 365 POS.
    - Store staff pick the items from the shelves and package them for the customer.
    - Store staff mark the order lines as ready for pickup.

1. Customer notification

    - When the order is ready, the customer gets a notification by email, SMS, or app that the order is ready for pickup.

1. In-store pickup

    - The customer arrives at the store and provides order details or a confirmation code.
    - Store staff check the order and give the items to the customer.

1. Order completion

    - Store staff update the order status to 'picked up' in Dynamics 365 Commerce POS.
    - The system completes the transaction and adjusts the inventory in Dynamics 365 Commerce HQ.

This data flow ensures seamless integration between e-commerce, Dynamics 365 Commerce, and the store, providing a smooth and efficient BOPIS experience for both the retailer and the customer.

## Components

The following components are used in the reference architecture.

:::image type="content" source="media/supply-chain-commerce-bopis-architecture-components.png" alt-text="Screenshot of the architecture components." lightbox="media/supply-chain-commerce-bopis-architecture-components.png":::

Here are the key components of a BOPIS system:

1. E-commerce platform

    - Lets customers shop online and place orders.
    - Connects to inventory and order management systems.

1. [Dynamics 365 Commerce and Supply Chain Management](https://www.microsoft.com/dynamics-365/products/commerce)

    - Tracks stock levels in real time across online and physical stores.
    - Shows accurate availability information for customers.
    - Manages the order lifecycle from placement to fulfillment.
    - Coordinates online orders and in-store pickups.
    - Sends alerts to customers by email, SMS, or app when their order is ready for pickup.

1. [Dynamics 365 Commerce Store Commerce app](/dynamics365/commerce/dev-itpro/store-commerce)

    - Processes payments and updates order status.
    - Notifies store staff to prepare orders for pickup.
    - Shows order status updates and pickup instructions.
    - Lets store employees manage and fulfill BOPIS orders.
    - Provides tools for order picking, packing, and customer verification.

1. [Logic Apps](/azure/logic-apps/)

    - When a customer places an order online, the e-commerce platform triggers a Logic App workflow to create the order in Dynamics 365.
    - Provides real-time order updates at e-commerce for customers.

1. Designated pickup location

    - A specific area in the store, such as a counter, curbside spot, or  automated locker, where customers can collect their orders.
    - Ensures a smooth and efficient pickup process.

## Scenario details

- Business problem

  Retailers face challenges with meeting customer expectations for convenience and speed in order fulfillment. Traditional online shopping often involved long delivery times and shipping costs, which could deter customers. Additionally, managing inventory across online and physical stores was complex and inefficient. The BOPIS model helps to address these issues by combining the convenience of online shopping with the immediacy of in-store pickup. This approach aimed to enhance the customer experience, reduce shipping costs, and streamline inventory management.

- Reason for BOPIS

  The rise of e-commerce and changing consumer behaviors prompted retailers to adopt BOPIS. Customers increasingly demanded faster fulfillment options and the ability to avoid shipping fees. The  COVID-19 pandemic further accelerated the need for contactless shopping options, making BOPIS an essential service for many retailers

- Services used in building the solution

  To implement a BOPIS solution, retailers typically use a combination of the following services:

  - An e-commerce platform that facilitates online shopping and order placement.

  - Dynamics 365 Supply Chain Management and Dynamics 365 Commerce that track stock levels in real-time across all channels and manages the order lifecycle from placement to  fulfillment.

  - Dynamics 365 Commerce Store Commerce to process payments and updates order status.

  - Azure Logic Apps that integrate systems and automates workflows/status updates for seamless operation and customer experience

### Scenario addressed

1. Customer places order: A customer orders a product online and selects the BOPIS option.

1. Order processing: The order is processed, and inventory is checked.

1. Order preparation: Store staff prepare the order for pickup.

1. Customer notification: The customer is notified when the order is ready.

1. In-store pickup: The customer picks up the order from the designated location.

### Customer goals

Customers that choose the BOPIS approach typically aim to achieve the following:

- Save time so that they avoid waiting for delivery and pick up orders at their convenience.

- Reduce costs by not paying shipping fees.

- Ensure availability because the store confirms product availability and that the item is ready for pickup before the customer visits the store.

- Enhanced convenience by combining online browsing with quick in-store pickup

### Benefits of implementing BOPIS

For retailers, the benefits of implementing BOPIS include:

- Increased sales because they can drive additional in-store purchases when customers pick up orders.

- Improved customer satisfaction when the store offers a convenient and flexible shopping experience.

- Reduced shipping costs by saving on last-mile delivery expenses.

- Better inventory management because they can optimize stock levels across online and physical stores.

- Enhanced competitive edge that differentiates them from competitors by offering a popular fulfillment option

- Additional in-store purchases because the customers can browse and make additional purchases when they visit the store to pick up their orders.

- Enhanced shopping experience that combines the ease of online shopping with the immediacy of in-store pickup and allows customers to inspect products before taking them home, ensuring satisfaction.

- Enhanced pick-up experience where customers can inspect products before taking them home, ensuring satisfaction.

- Speed because orders are often ready for pickup within a few hours, providing a faster alternative to standard shipping. Ideal for urgent purchases or last-minute needs.

### Potential use cases

This solution was primarily designed for a retail industry. You can use this solution to:

1. Fashion retail

    Customers can order clothing and accessories online and pick them up in-store, allowing them to try on items and make exchanges or returns immediately if needed.

1. Electronics

    Shoppers can purchase gadgets, appliances, and other electronics online and pick them up the same day, ensuring they get the latest products quickly.

1. Grocery stores

    Customers can order groceries online and pick them up at a designated time, saving time and avoiding crowded stores.

1. Home improvement

    DIY enthusiasts can order tools, materials, and supplies online and pick them up in-store, ensuring they have everything they need for their projects.

1. Pharmacies

    Patients can order prescriptions and over-the-counter medications online and pick them up at their convenience, reducing wait times.

1. Automotive parts

    Car owners can order parts and accessories online and pick them up in-store, ensuring they get the right items quickly.

1. Books and media

    Customers can order books, movies, and music online and pick them up in-store, often taking advantage of special promotions or discounts.

1. Furniture and home decor

    Shoppers can order furniture and home decor items online and pick them up in-store, allowing them to see and feel the products before taking them home.

1. Sporting goods

    Athletes and outdoor enthusiasts can order equipment and gear online and pick them up in-store, ensuring they have the right items for their activities.

## Considerations

These considerations help implement a solution that includes Dynamics 365. Learn more at [Dynamics 365 guidance documentation](../index.yml).

1. Store readiness

    - **Space and Logistics:** Ensure each store has the space and logistics to hold packages for customer pickup.  
    - **Curbside Pickup:** Decide if curbside pickup will be offered and plan for designated parking spots and clear signage

1. Inventory management

    - **Real-Time Updates:** Implement a system that provides real-time inventory updates to avoid overselling.  
    - **Safety Stock:** Maintain a threshold or safety stock to account for discrepancies and ensure availability

1. Security

    - **Data Protection:** Ensure that all customer and transaction data is encrypted both in transit and at rest using Logic App as a middleware. This helps protect sensitive information from unauthorized access.  
    - **Access Control:** Implement role-based access control (RBAC) to restrict access to sensitive data and functionalities based on user roles in Dynamics 365 Commerce HQ and POS. This ensures that only authorized personnel can access critical systems and data.  
    - **Compliance:** Ensure that the implementation complies with relevant industry standards and regulations, such as GDPR, HIPAA, or PCI-DSS, depending on the nature of business using Microsoft components like Azure Logic Apps and Dynamics 365.  
    - **Audit and Monitoring:** Regularly audit and monitor system activities to detect and respond to any suspicious activities or security breaches promptly with help of Logic Apps and Application Insights.

1. Order processing

    - **Efficient Workflow:** Develop a clear process for routing orders to stores, including order picking, packing, and marking them as ready for pickup.  
    - **In-Store Systems:** Equip store associates with tools to manage and fulfill BOPIS orders, such as in-store apps or access to the OMS

1. Customer Communication

    - **Notifications:** Set up a robust notification system to inform customers when their orders are ready for pickup.  
    - **Pickup Instructions:** Provide clear instructions on where and how to pick up their orders

1. Technology Integration

    - **POS and E-commerce Integration:** Ensure seamless integration between the e-commerce platform, POS system, and inventory management system. Dynamics 365 has fully integrated SCM, commerce and POS system which can help achieving BOPIS architecture natively.  
    - **Automation:** Use tools like Azure Logic Apps to automate order integration and status updates. This can also be used for notifications.

1. Staff training

    - **Training Programs:** Train store associates, call center agents, and other relevant staff on the BOPIS process and customer service expectations.  
    - **Customer Interaction:** Prepare staff to handle customer inquiries, returns, and other interactions related to BOPIS orders

1. Performance and scalability

    - **Scalability:** Ensure the system can handle increased order volumes, especially during peak shopping seasons. Performing a performance test before the season will help planning for the peak season.  
    - **Performance Monitoring:** Regularly monitor system performance and make necessary adjustments to maintain efficiency.  
    - **Real-Time Inventory Updates**: Implement real-time inventory updates to avoid overselling and ensure accurate availability by integrating with Headless commerce and Third-party eCommerce Application.  
    - **Efficient Workflow:** Optimize routing orders to stores, including order picking, packing, and marking them as ready for pickup.  
    - **Technology Integration:** Ensure seamless integration between the e-commerce platform, POS system, and inventory management system using Headless commerce. Dynamics 365 has fully integrated SCM, commerce, and POS systems which can help achieve BOPIS architecture natively.  
    - **Performance Monitoring:** Regularly monitor system performance on Azure Logic Apps and make necessary adjustments to maintain efficiency.

1. Customer experience

    - **Convenience:** Focus on providing a convenient and hassle-free pickup experience for customers.  
    - **Feedback:** Collect and analyze customer feedback to continuously improve the BOPIS process

### Cost optimization

Cost optimization is about looking at ways to reduce unnecessary expenses and improve operational efficiencies. Learn more at [Overview of the cost optimization pillar](/azure/architecture/framework/cost/overview).

1. Efficient inventory management

    - **Real-Time Inventory Updates:** Implement systems that provide real-time inventory updates to avoid overstocking or stockouts. This reduces holding costs and ensures accurate availability   
    - **Centralized Inventory:** Use a centralized inventory system to manage stock across multiple locations, optimizing stock levels and reducing excess inventory

1. Streamlined order processing

    - **Automated Workflows:** Use tools like Azure Logic Apps to automate order processing workflows, reducing manual intervention and associated labor costs.  
    - **Order Batching:** Batch orders for pickup to minimize the number of trips store associates need to make, saving time and labor costs.

1. Optimized Pickup Logistics

    - **Designated Pickup Areas:** Create designated pickup areas or curbside spots to streamline the pickup process and reduce congestion in the store.  
    - **Clear Signage and Instructions:** Provide clear signage and instructions for customers to ensure a smooth and quick pickup experience, reducing the time staff spend assisting customers

1. Staff Training and Utilization

    - **Dedicated BOPIS Staff:** Assign dedicated staff to handle BOPIS orders, ensuring they are well-trained and efficient in managing pickups.  
    - **Cross-Training:** Cross-train staff to handle both in-store and BOPIS orders, allowing for flexible staffing based on demand.

1. Customer Communication

    - **Timely Notifications:** Send timely notifications to customers about their order status and pickup readiness to reduce wait times and improve customer satisfaction.  
    - **Self-Service Options:** Implement self-service options like automated lockers for order pickups, reducing the need for staff involvement.

1. Technology Integration

    - **Seamless Integration:** Ensure seamless integration between e-commerce platforms, inventory management systems, and POS systems to streamline operations and reduce errors.  
    - **Scalable Solutions:** Use scalable technology solutions that can handle increased order volumes during peak times without significant additional costs

#### Benefits of cost optimization

- Reduced operational costs

     Efficient processes and automation reduce labor and operational costs.

- Improved customer satisfaction

    Faster and smoother pickups  enhance the customer experience, leading to repeat business.

- Increased sales

    Optimized BOPIS systems can drive additional in-store purchases when customers come to pick up their orders.

- Better resource utilization

    Effective staff training and utilization ensure that resources are used efficiently, reducing waste

Resources for Applications cost estimation:

1. [/azure/logic-apps/plan-manage-costs](/azure/logic-apps/plan-manage-costs)

2. [Microsoft Dynamics 365 \| Microsoft Licensing Resources](https://www.microsoft.com/Licensing/product-licensing/dynamics365)

## Deploying BOPIS

To configure the BOPIS follow these steps.

1. E-commerce platform: Set up or configure the e-commerce platform to support BOPIS functionality.

1. Inventory management system: Implement or integrate an inventory management system that provides real-time stock updates.

1. Dynamics 365 Supply Chain Management and Commerce: Configure the OMS to handle BOPIS orders, including order processing and fulfillment.

1. Point of sale system: Ensure the POS system can process BOPIS orders and update order status.

1. Azure Logic Apps: Use Azure Logic Apps to automate order integration and status updates.

1. Configuration: Configure all systems according to the requirements and integration plan.

## Implementing BOPIS

1. Provision and configure the environment

  1. Provision  the environment: Ensure your Dynamics 365 Commerce sandbox environment is provisioned and configured. Follow the guidelines for provisioning and configuring your environment

  1. Configure the POS: Set up the Point of Sale (POS) system to support BOPIS scenarios. This includes configuring the hardware station for credit card payments and ensuring the POS client is paired with a shared hardware station if using Store Commerce for web

1. Set up store commerce

  1. Install Store Commerce: Download and install the **Store Commerce** app for Windows, Android, or iOS platforms

  1. Activate Store Commerce: Activate the Store Commerce app by following the activation guidelines

  1. Enable BOPIS in Store Commerce: Sign in to Store Commerce, configure the hardware station, and ensure the system is ready to handle BOPIS orders

1. Configure E-commerce platform

  1. Create storefront order: Set up your e-commerce platform to allow customers to place orders online and select the in-store pickup option

  1. Inventory management: Ensure real-time inventory updates are integrated with the e-commerce platform to reflect accurate stock levels

1. Order processing and fulfillment

  1. Order notification: Configure the system to notify store staff when a BOPIS order is placed. This includes sending alerts to prepare the order for pickup.

  1. Order preparation: Store staff pick and pack the items for the BOPIS order and mark them as ready for pickup.

1. Customer communication

  1. Send notifications: Set up automated notifications to inform customers when their order is ready for pickup. This can include emails, SMS, or app notifications.

  1. Provide pickup instructions: Ensure customers receive clear instructions on where and how to pick up their orders.

1. In-store pickup

  1. Customer verification: When the customer arrives at the store, verify their order details and hand over the items.

  1. Update order status: Update the order status to 'picked up' in the system to complete the transaction.

1. Post-implementation monitoring

  1. Monitor performance: Continuously monitor the performance of the BOPIS system to ensure it meets business objectives.

  1. Collect feedback: Gather customer feedback to identify areas for improvement and make necessary adjustments.

## Related resources

Review the following related architecture guides, solutions, and other guidance content:

- [Unlock the Power of Dynamics 365 Commerce Supporting Buy Online Pickup in Store Curbside - TechTalk](https://www.youtube.com/watch?v=Al3upio3dPU#:~:text=View%20this%20session%20to%20discover%20existing%20capabilities%20and,In-Store%20order%20processing%20flow%20with%20Dynamics%20365%20Commerce.)
- [Configure BOPIS in a Dynamics 365 Commerce sandbox environment - Commerce](/dynamics365/commerce/cpe-bopis)  

<!-- ## Tags

*Industries:* Retail Trade (52-59)

*Stakeholders:* Accounts receivable, Customer services, Retail store operations, Sales, Warehouse

*Products:* Dynamics 365 Commerce, Dynamics 365 Customer Insights – Data, Dynamics 365 Customer Insights - Journeys, Dynamics 365 Customer Service, Dynamics 365 Finance, Dynamics 365 Fraud Protection, Dynamics 365 Supply Chain Management, Azure Logic Apps -->

## Contributors

*This article is maintained by Microsoft. It was originally written by the following contributors.*

Principal author:

- [Vetrivel Chandranath](https://www.linkedin.com/in/vetrivelchandranath/) \|  Solution Architect
