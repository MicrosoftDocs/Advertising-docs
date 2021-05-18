---
title: Edit all your ad extensions in a spreadsheet
description: Save time and effort by using Microsoft Advertising Editor to export all of your ad extensions to a CSV file, edit them in Microsoft Excel, and save your changes.
ms.service: "Bing-Ads-Editor-v11"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Edit all your ad extensions in a spreadsheet

With Microsoft Advertising Editor, you can export data from a campaign or ad group as a comma-separated values (CSV) file, which you can then edit in Microsoft Excel.   If you need to edit ad extensions (phone numbers, addresses, websites) and the extension is associated with hundreds of campaigns, there are hundreds of edits to make.   Luckily, you can assign IDs to extensions and use a spreadsheet to edit the details all at once, rather than one at a time.

## Add new extensions using the spreadsheet
1. Create new extensions in Microsoft Advertising Editor:
   - Select the campaign to which you want to add the extension to from the tree view in the left panel.
   - Select the ad extension under **Ads and extensions** in the left navigation panel.
   - In the data view, click **Add extension**.

1. Open extensions data in Excel:
   - In the data view, click **Copy to CSV**, which will automatically open in Excel.
   - In Excel, assign your new extension a temporary ID by entering any negative number (for example, -11111) in the **ID** column in the spreadsheet.

Microsoft Advertising Editor recognizes the negative number as a temporary ID and will later re-assign it a permanent ID (a positive number) after you **Post Changes** to Microsoft Advertising online.

1. Assign a Type and Parent ID in the spreadsheet:
   - The ad extension record types you can add to the **Type** column are: Campaign/Ad Group Sitelink Ad Extension, Campaign Location Ad Extension, Campaign Call Ad Extension, and Campaign Product Ad Extension.
   - Enter the campaign ID you want to associate the extension with in the **Parent ID** column.

1. Save the CSV file and then click **Account**, then **Import** and select **Import from a file** in the toolbar to move the data back into Microsoft Advertising Editor.
1. From the **Import from file** dialog box, select the CSV file and click **Next**.
1. Confirm that the appropriate Microsoft data field is selected and click **Next**. If you want to change any of the data field selections, select from the dropdown options.
1. Check to make sure everything is correct from the **Select your import options** dialog box and click **Next**.
1. Confirm that the changes are complete in the **Import completed** dialog box and click **Close**.

The next time you click **Get Changes**, Microsoft Advertising will assign a permanent ID (replacing the negative number you originally created)   to your new extension the next time you Get Changes and export the data as a CSV file.

## Edit extensions and associations using the spreadsheet
- To edit details, change the cell for: Location Ad Extension, Call Ad Extension, Sitelink Ad Extension, and Product Ad Extension.        Changes you make to the details here will be applied to all campaigns and ad groups associated with the extension ID.
- To edit associations, change the ID and Parent ID for: Campaign/Ad Group Sitelink Ad Extension, Campaign Location Ad Extension,        Campaign Call Extension, or Campaign Product Ad Extension.

## Delete extensions or associations using the spreadsheet
- In the **Status** column, delete "Active" and type "Deleted."

After you import the changes back into Editor from the CSV and **Post Changes** to Microsoft Advertising online, the next time you download data into Editor,      the deleted extensions and association records will be gone.


