---
author: edupont04
ms.topic: include
ms.date: 11/24/2023
ms.author: edupont
---

It's important for an organization to consider carefully how it categorizes, segments, and merchandises the products and services it offers. During the implementation of a business solution, an organization often already has a way of doing this already. It's important to consider if the current mechanism for categorizing products and services meets all the business requirements, because the implementation of a new technology solution is often a good time to consider making a change. The organization might want to consider questions such as the following list:

- How do you drive downstream business processes and automation?

- How do you report and analyze your data including operational reporting and financial reporting?

- How has your business grown since the original mechanism of categorization, segmentation, or merchandising was developed?

- How do you anticipate your business will grow in the future?

The answers to these questions should help inform your process for defining the way you implement a technology solution to support the categorization of products and services. This business process area should always be considered early in a Dynamics 365 implementation project. Also consider the number of changes that might be happening to the data in this area as well. This can make integrations, data migration, and other aspects of your project more complex.

When an organization starts a Dynamics 365 implementation, it's important to carefully consider how you define the product lines in the system. This includes tasks like setting up item groups and product categories in Dynamics 365 Supply Chain Management and product families in Dynamics 365 Sales. The business process areas for categorizing either products or services also include the definition of product policies. We recommend that you group similar items together based on the expected behaviors they need in the system. This includes settings like item model groups, reservations, storage, and tracking dimensions, and more in Dynamics 365 Supply Chain Management.

Also, if your organization offers multiple types of products or services, you should define the rules and configurations for each type of product or service that you offer. For example, in the chemical or food and beverage industry, you might use catch weight items. In some industries, consigned inventory is common and requires more setup, configuration, and considerations. Similarly, the service industry has considerations to make for the services that they offer, including warranties, installation, and so on. Many organizations also charge extra fees or service charges for tangible items that are sold which might require more considerations. Dynamics 356 supports various flexible configurations to support many types of products, services, and extra fees and charges that might be charges to customers or imposed by suppliers.

Once you have a basic definition for organizing products or services, you can categorize and build hierarchical structures and catalogs or assortments for the downstream processes. Dynamics 365 Supply Chain Management and Commerce support multiple flexible hierarchies for procurement, sales, channel management, and more. In Dynamics 365 Sales, you can create hierarchies of products or services with *product families*. Dynamics 365 Commerce uses *assortments* to define product mix for a retail channel such as the call center, retail store, or online store. One or more assortments are then combined and assigned to a catalog for each retail channel. This process often uses product attributes that further describe the product. However, attributes can describe categories or retail channels as well, for example.

When you group common or similar items together into categories, you can more easily manage the attributes. Attributes serve an important function in merchandising and for customers to find products that meet their requirements. Attributes can be easily added at any time, but starting with a good baseline for your project to help you meet reporting requirements is critical to downstream analytics. With tools to mass update attribute values, you can easily manage the values at any time and adapt to the changing customer needs and supply chain.

With Dynamics 365 Customer Service, you can create and manage *subjects* to manage complex hierarchies that can represent products, brands, or types of issues that are reported by your customers, for example. With Dynamics 365 Customer Insights, segments help you organize customers into groups based on their buying habits and one common segment is typically related to the products customers purchase. However, organizations can define many segments based on many different attributes of the products that are purchased.
