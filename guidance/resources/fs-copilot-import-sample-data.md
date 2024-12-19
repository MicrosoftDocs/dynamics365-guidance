---
title: Use Copilot to create sample data for Field Service
description: Generate relevant sample data in Dynamics 365 for Field Service using Copilot. Follow steps to create and import Account and Contact data, ensuring privacy with fake addresses.
ms.date: 12/19/2024
ms.topic: conceptual
author: edupont04
ms.author: edupont
ms.custom:
  - ai-gen-docs-bap
  - ai-gen-desc
  - ai-seo-date:12/13/2024
---

# Use Copilot to create sample data for Field Service

As an organization, you might want to create sample data in Dynamics 365 that is relevant to your business and location. With Copilot, you can now easily generate relevant sample data in Dynamics 365. This article goes through the steps to create *Account* and *Contact* data that you can use for demonstrations of Dynamics 365 Field Service environments. We show you how you can extend the process to use other entity tables in Dataverse.  

> [!NOTE]
> Don't use these steps for real customer data or in production environments.

## Define a central location

Typically, Field Service organizations separate their work into geographic areas or territories. Let's use a city as an example. First, we define the central location of the region where our organization does business. Then we can create sample data that's relevant to that region, such as accounts, contacts, and work orders. 

Start by picking the central spot of the region on a map. You need the latitude and longitude of this spot to pinpoint the central location. Using a map such as [Bing Maps](https://www.bing.com/maps/), find your chosen location, and then copy the coordinates. For example, you're in New York City, and you choose Times Square as your central location. In this scenario, you view and copy the coordinates (40.757500, -73.985830) as shown in the following screenshot.

:::image type="content" source="media/fs-copilot-import-sample-data-map.png" alt-text="Screenshot of a digital map of New York City that shows the context menu for the geographical location of Times Square." lightbox="media/fs-copilot-import-sample-data-map.png":::

## Use Copilot to generate sample data for accounts

We can now generate account sample data using Microsoft 365 Copilot. Navigate to [https://copilot.microsoft.com](https://copilot.microsoft.com). A *prompt* is a question or query that you ask Copilot. Copy the snippet and paste it into the prompt on the Copilot webpage so that you replace the latitude and longitude with your central location coordinates.  

```plaintext
Create a CSV format list of 20 accounts with the following fields: fake account name = Name, fake street name and number = Address1_Line1, real city = Address1_City, real state abbreviation = Address1_StateorProvince, real zip code = Address1_PostalCode, real latitude = Address1_Latitude, real longitude = Address1_Longitude within 50 miles of <latitude>, <longitude>
```

When you submit this query, Copilot provides a response output list of 20 fake accounts with fake street addresses. We use fake addresses to respect privacy rules. But even though the street address is fake, we use real latitudes and longitudes, so the data shows on the map when you use it in Dynamics 365 Field Service.

If we continue our example with Times Square, then the prompt would look like this example:

```plaintext
Create a CSV format list of 20 accounts with the following fields: fake account name = Name, fake street name and number = Address1_Line1, real city = Address1_City, real state abbreviation = Address1_StateorProvince, real zip code = Address1_PostalCode, real latitude = Address1_Latitude, real longitude = Address1_Longitude within 50 miles of 40.757500, -73.985830
```

> [!TIP]
> You can add something like the following sentence to your prompt: `Each latitude and longitude must be in a location that is drivable to the prompt to make sure the locations provided are accessible by car.`

Copilot returns something like the following snippet:

:::image type="content" source="media/fs-copilot-import-sample-data-prompt.png" alt-text="Screenshot of a prompt to Copilot with a response from Copilot." lightbox="media/fs-copilot-import-sample-data-prompt.png":::

You can also extend this prompt to include more default fields such as:

- Include **Currency** with a default value of *USD*.
- Include **Relationship** with a default value of *Customer*.
- Include **Price List** with a default value relevant to your data, such as *Default Price List*.
- Include **Service Territory** with a default value relevant to your data, such as *Territory1.*
- Fake **Phone Number**
- Fake **Email Address**

> [!TIP]
> You can use Copilot to generate sample data for any field you want. You can also hard-code fields, such as when you use default entity reference data.

Choose the **Copy** action in the top right corner of the Copilot results and paste the data into a text file, such as Notepad. And then save the text file as *Accounts.txt*.

## Use Copilot to generate sample data for contacts

We create two types of contacts in the system:

1. Contacts that are frontline workers. These contacts are bookable resources that can use the Field Service mobile app to complete work orders.
2. Contacts that are account contacts. These contacts are affiliated with **Account** records in the system.

### Generate contacts used as frontline worker resources

Let's generate contact sample data. Run the following prompt in Copilot.

```plaintext
Create a CSV format list of contacts using fake first name=FirstName, last name=LastName, address=Address1_Line1, with a real city=Address1_City, state= Address1_StateOrProvince, zipcode= Address1_PostalCode, a real latitude=Address1_Latitude, a real longitude=Address1_Longitude that is no closer than 5 miles to any of the accounts.
```

Copilot returns a response like the following sample:

:::image type="content" source="media/fs-copilot-import-sample-data-prompt-contacts.png" alt-text="Screenshot of a prompt to Copilot with a response from Copilot with contacts.":::

> [!TIP]
> You can further define the geographical scope by adding additional parameters to the prompt such as `no closer than 5 miles to any of the accounts but no further than 50 miles from a service account latitude and longitude`.

Next, copy the data into a Notepad file and save it as *Contacts.txt*.

### Generate contacts used as account contacts

Let's now create contacts related to an account record.

> [!NOTE]
> We add an additional field to the prompt that uses an account that we generated in the previous account prompt. When we import this into Dynamics 365, this contact record will be linked with the associated account.

```plaintext
Create a CSV format list of contacts using fake first name=FirstName, last name=LastName, address=Address1_Line1, with a real city=Address1_City, state= Address1_StateOrProvince, zipcode= Address1_PostalCode, a real latitude=Address1_Latitude, a real longitude=Address1_Longitude that is no closer than 5 miles to any of the accounts, ServiceAccount=Name of the account.
```

Repeat the steps you took in the previous section, and save the generated contact records as a new text file with the name *ContactsWithAccounts.txt*.

## Import the sample into Dynamics 365

Now that we generated sample data, we can import it into Dynamics 365.

> [!NOTE]
> This article uses the out-of-the-box **Data import wizard**. Learn more at [Import data (all record types) from multiple sources](/power-platform/admin/import-data-all-record-types).

1. In your Dynamics 365 org, where you're signed in as an admin, choose the **Settings**>**Advanced Settings** actions.
2. Go to **Data Management** > **Imports**.

We can now import our data.

### Import accounts

1. Choose the **Import Data** action.
2. In the dialog that opens, select the *Accounts.txt* file that you created earlier, and then choose the **Next** action.
3. Review the settings, and then choose the **Next** action.
4. In the **Map Record Types** window, specify that you want to map the **Account** data to the **Account** record type, and then choose the **Next** button.
5. Map the fields as shown in the following table, and then choose the **Next** action.

    | Source       | Destination               |
    |--------------|---------------------------|
    | Account Name | Name                      |
    | Street       | Address1\_Line1           |
    | City         | Address1\_City            |
    | State        | Address1\_StateorProvince |
    | ZIP          | Address1\_PostalCode      |
    | Latitude     | Address1\_Latitude        |
    | Longitude    | Address1\_Longitude       |

6. Review the mapping summary, and then choose the **Next** action.
7. Optionally, provide a name for the data map, and then choose the **Submit** action:

The import takes time to run. You can review the progress and results to help make sure that the data is imported successfully.  

> [!IMPORTANT]
> If you re-run this process, you might get import failures due to data duplication.

### Import contacts used as frontline worker resources

Repeat the steps in the previous section for importing the sample data in the *Contacts.txt* file. Keep the settings the same apart from the field mapping, so that you map *Contacts* to *Contacts*.

The following table illustrates how you can map the fields:

| Source                    | Destination               |
|---------------------------|---------------------------|
| LastName                  | Last Name                 |
| Address1\_Line1           | Address1: Street 1        |
| Address1\_City            | Address1: City            |
| Address1\_StateorProvince | Address1: State/Province  |
| Address1\_PostalCode      | Address1: ZIP/Postal Code |
| Address1\_Latitude        | Address1: Latitude        |
| Address1\_Longitude       | Address1: Longitude       |

### Import contacts related to accounts

> [!NOTE]
> If you want to link contact to accounts, you must import accounts before you import the contacts that are related to those accounts so that you can make the proper links.

To import the contacts that are related to accounts, follow the same steps as in the previous sections with the following exceptions:

1. Map the file to the **Contacts** table.
2. Map the files as shown in the following table:

    | Source                    | Destination               |
    |---------------------------|---------------------------|
    | LastName                  | Last Name                 |
    | Address1\_Line1           | Address1: Street 1        |
    | Address1\_City            | Address1: City            |
    | Address1\_StateorProvince | Address1: State/Province  |
    | Address1\_PostalCode      | Address1: ZIP/Postal Code |
    | Address1\_Latitude        | Address1: Latitude        |
    | Address1\_Longitude       | Address1: Longitude       |
    | ServiceAccount            | Company Name(Lookup)      |

3. Map the **ServiceAccount** field as shown in the following screenshot:

    :::image type="content" source="media/fs-copilot-import-sample-data-prompt-contacts-map.png" alt-text="Screenshot of how the fields for contacts are mapped.":::

## View the sample data in Dynamics 365

Once you imported the sample data, go to Dynamics 365, and then browse to **Accounts** where you see the new sample data. Then browse to **Contacts** where you see both types of contacts that were imported: contacts without accounts and contacts with accounts.

## Enhancements

Now that your sample data is in Dynamics 365, you can use it to demonstrate the capabilities in the solution. You can also create sample data for other tables, such as **Work Orders**, **Bookable Resources**, or **Agreements**. You can even try functionality such as scheduling these new resources with bookings.

## Support

This sample data generation and import is provided as-is. Bugs, feature addition/modification requests, and other changes are the responsibility of the end-user. Always thoroughly test these features in a nonproduction environment.

## Related information

- [Import data (all record types) from multiple sources](/power-platform/admin/import-data-all-record-types)  
- [Select a data map](/power-platform/admin/select-data-map)  
- [Field mapping for schedule board settings in Dynamics 365 Field Service](fs-schedule-board-settings-field-mapping.md)  
- [Schedule board settings management control in Universal Resource Scheduling for Dynamics 365 Field Service](fs-schedule-board-settings-management-control.md)
- [Dynamics 365 Field Service implementation optimization resources](fs-index.yml)  
