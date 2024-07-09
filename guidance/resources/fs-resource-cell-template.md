---
title: Add crew information to resource cells
description: Get sample code to help you customize information and how it shows in the schedule board in Dynamics 365 Field Service.
ms.date: 07/08/2024
ms.topic: conceptual
author: edupont04
ms.author: jwride
---

# Add crew information to resource cells

***Applies to: Dynamics 365 Field Service***

The schedule board is a key tool for dispatchers that want to book and manage frontline workers and other resources in Dynamics 365 Field Service. It can be extended and customized to address business-specific use cases. This article explains how to customize the schedule board to show additional information for each resource.

In this sample template, the resource card shows if the resource is a member of a specific crew by showing the crew's name. If a resource is a member of more than one crew, it shows instead the number of crews that they're a member of. The sample solution also considers the schedule board date range while evaluating crew membership for the resources.

> [!NOTE]
> You might have to refresh the schedule board to reflect changes made after the schedule board has loaded, such as when the date range is modified.

## Prerequisites

- Prepare the environment.

  You must create your resources and crews and ensure membership of resources within those crews is configured for this customization to work. Find links to articles that can help you set up resources or crews in the [Related resources](#related-resources) section.

- Understand *handlebar expressions* since that helps you understand how the sample code works. You can find many references and tutorials online if needed, including one in the [Related resources](#related-resources) section.

- Understand FetchXml to query data and Unified FetchXml (UFX) queries (FetchXml + XPath) to dynamically query data to extend the schedule board and schedule assistant. The [Related resources](#related-resources) section has links related to FetchXML and UFX.

## Use case

For certain business scenarios, crew members can move between crews on a frequent basis. A *dispatcher* or *scheduler* wants to understand which crew a resource belongs to as they review available capacity and then schedule work.

The schedule board shows where a resource is allocated to a team by blocking out their time; however, in certain scenarios, dispatchers or schedulers want to see this information against the resource card for easy access.

You can achieve this visualization through a simple customization.

## Sample code

> [!NOTE]
> In both steps, don't edit the default templates. Instead, copy the template and use it as a starting point to add the code snippets or other customizations.

### Step 1: Modify the Retrieve Resource query

To show information on the resource card relating to crew membership, you must first retrieve the information about the resources and crews.

To insert the code:

1. In the schedule board, navigate to [scheduler settings](/dynamics365/field-service/schedule-board-tab-settings), choose the link to open **All board settings**, and then, on the **Other** tab, choose the [Retrieve resource query](/dynamics365/field-service/schedule-board-tab-settings#retrieve-resources-query) field.

2. Open the default query that is already specified in the **Retrieve resource query** field by choosing the pencil icon, and then copy the contents of the query.

3. Create a new query template using the copied code as a base.

4. Edit the new query and after the last `</link-entity>` element but before the `</entity></fetch>` element, insert the following code snippet:

    ```html
    <!-- Get crew count -->
    <link-entity name="bookableresourcegroup" from="childresource" to="bookableresourceid" alias="bgcount" link-type="outer">
        <attribute name="name" aggregate="countcolumn" alias="crewcount" />
        <filter type="and">
          <!-- The resource group's From date should be before or on the End date. -->
          <condition attribute="fromdate" operator="le">
            <ufx:value select="$input/ScheduleBoard/EndDate" attribute="value" />
          </condition>
          <!-- The resource group's To date should be on or after the Start date. -->
          <condition attribute="todate" operator="ge">
            <ufx:value select="$input/ScheduleBoard/StartDate" attribute="value" />
          </condition>
        </filter>
    </link-entity>
    <!-- Get crew info (if there's only one crew)-->
    <link-entity name="bookableresourcegroup" from="childresource" to="bookableresourceid" alias="bg" link-type="outer">
        <filter type="and">
          <!-- The resource group's From date should be before or on the End date.  -->
          <condition attribute="fromdate" operator="le">
            <ufx:value select="$input/ScheduleBoard/EndDate" attribute="value" />
          </condition>
          <!-- The resource group's To date should be on or after the Start date.-->
          <condition attribute="todate" operator="ge">
            <ufx:value select="$input/ScheduleBoard/StartDate" attribute="value" />
          </condition>
        </filter>
        <link-entity name="bookableresource" from="bookableresourceid" to="parentresource" alias="parentresource" link-type="outer">
          <attribute name="name" alias="crewname" groupby="true" />
        </link-entity>
    </link-entity>
    ```

5. Also, inside the `<bag>` element, add the following snippet:

    ```html
    <multipleCrews ufx:select="crewcount > 1" />
    <singleCrew ufx:select="crewcount = 1" />
    ```

6. Choose the **Save as new** action. Your new query is now set as the value of the **Retrieve resource query** field.

#### What this code does

- Get crew count

  The CrewCount UFX joins the **Resource** table with the `bookableresourcegroup` entity that defines a crew, and it retrieves the number of crews associated with that resource through an aggregate `countcolumn`.

  > [!NOTE]
  > The crews retrieved are filtered to only include the crews that the resource is a member between the start and end date as defined on the schedule board's time window. (with the code `$input/ScheduleBoard/StartDate` and `$input/ScheduleBoard/EndDate`, respectively).

  > [!IMPORTANT]
  > The resource card may not automatically update when start and end dates change, so it might be necessary for users to refresh the board to see potential changes when the dates are changed.

- Get crew name

  Another join of the requirement to the `bookableresource` in the UFX retrieves the name of the crew name associated with a resource.

  As with the crew count, this retrieval is filtered to be within the schedule board's start and end dates.

- Property bag for detecting `multipleCrews` and `singleCrew`.

  The goal is to be able to identify if a resource belongs to many crews and then display the number of crews they belong to. To include this logic in the resource cell template, two conditional logic properties are created:

  - *singleCrew* is true if the bookable resource belongs to only one crew within the time window.

  - *MultipleCrews* is true if the bookable resource belongs to only one crew within the time window.

### Step 2: Modify the resource cell template

After applying the query to retrieve resources, it's time to modify the resource cell template. 

To insert the code:

1. In the schedule board, navigate to scheduler settings, choose the link to open **All board settings**, and then, on the **Other** tab, choose the **Resource cell template** field.
2. Open the default template that is already specified in the **Resource cell template** field by choosing the pencil icon, and then copy the contents of the template.
3. Create a new template using the copied code as a base.
4. Add the following code to the new template so that it'll show the crew information. Learn more at [Modify the resource cell template](/dynamics365/field-service/extend-schedule-board-custom-resource-attribute#step-3-modify-the-resource-cell-template).  

    ```html
    <!-- Add crew information. -->
            {{#if singleCrew}}
    <div class='resource-name primary-text ellipsis' title='{{crewname}}' style="color:blue"><i class="fa fa-users" ></i> {{crewname}}</div>
            {{/if}}
              {{#if multipleCrews }}
    <div class='resource-name primary-text ellipsis' title='{{crewcount}}' style="color:blue"><i class="fa fa-users" ></i> In {{crewcount}} crews</div>
            {{/if}}
    <!-- End of customization -->
    ```

The following screenshot illustrates this type of customization.

:::image type="content" source="media/fs-resource-cells.png" alt-text="Screenshot of a list of resources where three are tagged as being part of one or more crews.":::

In this example, we use a user group icon from [Font Awesome](https://fontawesome.com/v4/icons/) to represent a crew. Dynamics 365 Field Service currently supports v4 icons.  

All values used by the handlebar come from the property bag from the query that retrieves resources and then uses logic to determine what information to show on the card.

Where you place the code snippet in the template determines how the information is displayed on the resource card.

This also demonstrates the supported use of style sheets to make adjustments such as changing colors and backgrounds.

You can also add a custom web resource and use an image in place of Font Awesome icons used in this example.

## Related resources

- [Set up bookable resources](/dynamics365/field-service/set-up-bookable-resources)

- [Group resources in crews](/dynamics365/field-service/resource-crews)

- [Schedule board tab settings](/dynamics365/field-service/schedule-board-tab-settings)

- [Use FetchXml to query data in Power Apps](/power-apps/developer/data-platform/fetchxml/overview)

- [Extend Universal Resource Scheduling with Universal FetchXML](/dynamics365/common-scheduler/developer/universal-fetchxml)

- [https://fontawesome.com/v4/icons/](https://fontawesome.com/v4/icons/)

- [Introduction \| Handlebars (handlebarsjs.com)](https://handlebarsjs.com/guide/#simple-expressions)

- [XPath Tutorial (w3schools.com)](https://www.w3schools.com/xml/xpath_intro.asp)

<!-- ## Tags

*Field Service Features:* Schedule Board, Scheduling, Bookings, Crews, Resources

*Products:* Dynamics 365 Field Service, O25-FieldService -->
