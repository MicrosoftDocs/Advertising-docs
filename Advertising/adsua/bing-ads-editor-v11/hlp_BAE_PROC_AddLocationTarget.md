---
title: How do I add a location target?
description: When determining if your ads are eligible to be displayed, Microsoft Advertising Editor uses both your ad language and location target settings. Both criteria must be met in order for an ad to display.
ms.service: "Bing-Ads-Editor-v11"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# How do I add a location target?

Getting your ad in front of the right people is what targeting is all about. When you target by location, you can choose to show ads to potential customers in all available countries/regions:

- Selected cities and metro areas within the U.S., Canada, U.K., France, and Australia
- Counties within the U.S.
- Postal codes
- County (U.S. only)
- State/Province
- Countries/Regions
- A specified radius around a zip/postal code, coordinates, landmark, or area

Note: Not everyone can target United States counties yet. If you don’t have this feature, don’t worry. It’s coming soon.

Although location targeting is most often used to designate the specific locations where you want to show your ads, Microsoft Advertising also lets you target locations you specifically want to exclude from seeing your ads. (Note: You cannot exclude using radius targeting.)

Not only does Microsoft Advertising let you target customers in a specific location, you can also show ads to customers searching about a specific location. This option is in the **Campaign** tab as **Targeting method**. Take a look at the following examples:

## Example 1

- **Who should see your ads?**    **People in your targeted locations**
- **Target location defined in your campaign:**  London
- **Keyword:**  Hotels

|Searcher’s physical location|Search term|Ad eligible for display?|
|---|---|---|
|Florida|London hotels|**No** , **not** located in target location|
|London|Hotels|**Yes** , located **in** target location|
|London|New York hotels|**Yes** , located **in** target location|

## Example 2

- **Who should see your ads?**    **People searching for or viewing pages about your targeted locations**
- **Target location defined in your campaign:**  London
- **Keyword:**  Hotels

|Searcher’s physical location|Search term|Ad eligible for display?|
|---|---|---|
|Florida|London hotels|**Yes** , searching **about** target location|
|London|Hotels|**No** , not searching for pages **about** target location|
|London|New York hotels|**No** , not searching for pages **about** target location|

## Example 3

- **Who should see your ads?**    Both **People in your targeted locations** and **People searching for or viewing pages about your targeted locations**
- **Target location defined in your campaign:**  London
- **Keyword:**  Hotels

|Searcher’s physical location|Search term|Ad eligible for display?|
|---|---|---|
|Florida|London hotels|**Yes** , searching **about** target location|
|London|Hotels|**Yes** , located **in** target location|
|London|New York hotels|**Yes** , located **in** target location|

## How do I add a new location target?
1. Select the campaigns or ad groups from the tree view in the left panel that you want to add targeting to.
1. Click **Locations** under **Keywords and targeting** from the type list in the left panel.
1. In the data view, click **Add location target** and select **Add campaign location target** or **Add ad group location target**.
1. Choose the campaign or ad group you want to add a location target to and click **OK**.
1. In the **Edit the selected locations** pane:
   - Specify the location for this entry. Click **Edit/find location** and you can specify the location by **Area targeting** (narrow your location target by country/region or city) or by **Radius targeting** (narrow your location to a single mile or kilometer, or expand it to a larger circle).
   - Enter bid adjustment.

The details you input will automatically populate the new row in the main grid.

## How do I import location targets with a file?
If location targets are already available in Microsoft Advertising Editor:

1. Select the campaigns or ad groups from the tree view in the left panel that you want to add targeting to.
1. Click **Locations** under **Keywords and targeting** from the type list in the left panel.
1. Select the targets you want to edit in the grid.
1. In the data view, click **Export to .csv file**.
1. After making the necessary changes, import your .csv file back to Microsoft Advertising Editor. [Learn more](./hlp_BAE_PROC_Import.md)

If no location targets are available in Microsoft Advertising Editor:

- If you have targets in Google AdWords Editor and want to import them into Microsoft Advertising Editor, export location targets from Google AdWords Editor and import your .csv or Excel file back to Microsoft Advertising Editor. [Learn more](./hlp_BAE_PROC_Import.md)
- Create a new file by downloading the .csv location targets template and import it back to Microsoft Advertising Editor. [Learn more](./hlp_BAE_PROC_Import.md)


