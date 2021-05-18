---
title: Importing and exporting with Microsoft Advertising Editor
description: Importing and exporting with Microsoft Advertising Editor
ms.service: "Bing-Ads-Editor-v11"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Importing and exporting with Microsoft Advertising Editor

Use Microsoft Advertising Editor to quickly:

- **Import data from other online advertising programs.**  Get Microsoft Advertising campaigns up and running quickly by exporting accounts, campaigns, and ads from Google, Yahoo, or other programs, and then importing them into Microsoft Advertising Editor.
- **Bulk-edit Microsoft Advertising data in a spreadsheet.**  If you prefer to edit data in a Microsoft Excel spreadsheet, export it as a comma-separated values (.csv) file, edit it in Excel, and then import the data into Microsoft Advertising Editor.
- **Base a new campaign on an existing one.**  To create a new campaign from an existing campaign, export the campaign, change the campaign name and edit the data, and then import the new campaign into Microsoft Advertising Editor. You can also do this with ad groups but be sure to change the ad group name.

> [!NOTE]
> The file must be an Excel or .csv (comma-separated values) file and must be closed before you try to import it.
> If you are importing location targets see [this article](./hlp_BAE_PROC_GeogLocationCode.md) for information on how to find location IDs.

## How do I import campaigns from Google Ads?
Using your Google Ads account credentials and the Google API, Microsoft Advertising Editor can retrieve all of your Google Ads campaign data, letting you skip the spreadsheets.

## Import Google Ads campaign data with your Google credentials

1. In the toolbar, click **Import**, then select **Import from Google Ads**.
1. If not already selected, click **Import Google Ads campaign data directly from your Google account** and click **Sign in to Google**.
1. Sign in to your Google account and allow Microsoft Advertising to access your Google Ads account.
1. Copy the provided code and paste it into Microsoft Advertising Editor.
1. You can import all campaigns within an account, or, if your account is very large, only selected campaigns. Click **Next**.
1. Review the steps to import from Google Ads and post directly to the server, then click **Next**.
1. Set your import options. **Note** : What you import here will get posted directly to the server, so be sure to check the import options you want.
1. Click **Next**.
1. Schedule your import to run now, once at a later date and time, or on a recurring basis.
1. Click **Import and post to server**.
1. Once the inport is complete, you can view any import errors on a spreadsheet.

- Unmatched columns will not be imported.
- You can optionally edit destination URLs and choose to share identical sets of ad extensions between campaigns.

## How do I import campaigns from a file?
There are three ways to import campaign data with a file:

- Create a new file using a Microsoft Advertising template.
- Export data from Microsoft Advertising Editor, make changes, and import the file back in to Microsoft Advertising Editor.
- Export data from Google Ads, make changes, and import file back in to Microsoft Advertising Editor.

Campaign data can be imported in .csv, .txt, .tsv, .xls, or .xlsx files.

## Create a new file using a Microsoft Advertising template and import the file back

1. Download the template from Microsoft Advertising. The template contains examples for your reference. Replace the data in the template with your campaign data.
1. Select **File** and then**Save as**.
1. Type a name for the import template. Use quotation marks around the name and include .csv at the end. For example, "YourFileName.csv". The quotation marks will not appear in your final file name but are used to prevent Excel from adding ".txt".
1. Select Unicode Text, and then click **Save**.
1. Click **Import** from the toolbar and select **Import from a file**.
1. Select the previously saved file and click **OK**.
1. Use the drop-down lists to adjust any Microsoft Advertising column headings to match those in your import file, then click **Next**.
1. Review the default settings and click **Next**.
1. Review the Import summary to see what entities were newly added, updated or couldn't be imported (skipped).
1. If you want to review the details of the campaigns and make changes, click the link next to **Download the details**.

**Things to note** :
- Unmatched columns will not be imported.
- You can optionally edit destination URLs and choose to share identical sets of ad extensions between campaigns.
- For details on how to add location targets, see [How do I add a location target?](./hlp_BAE_PROC_AddLocationTarget.md)

> [!IMPORTANT]
> Dynamic search ads are currently available only in France, Germany, the United States, and the United Kingdom. Microsoft Shopping Campaigns and product ads are available only in the United States, Canada, United Kingdom, Australia, France, Germany, and India.

## Export data from Microsoft Advertising Editor and import the file back
1. Select the campaigns or ad groups from the tree view in the left panel that you want to edit and import back.
1. Click **Export** from the toolbar and select **Export selected campaigns and ad grous**.
1. After making necessary changes to the exported file, save the file.
1. Click **Import** from the toolbar and select **Import from a file**.
1. Select the previously saved file and click **OK**.
1. Use the drop-down lists to adjust any Microsoft Advertising column headings to match those in your import file, then click **Next**.
1. Review the **Import summary** to see what entities were newly added, updated or couldn't be imported (skipped).
1. If you want to review the details of the campaigns and make changes, click the link next to **Download the details**.

**Things to note** :
- Unmatched columns will not be imported.
- You can optionally edit destination URLs and choose to share identical sets of ad extensions between campaigns.

## Export data from Google Ads Editor and import the file back
1. Sign in to your Google Ads Editor account.
1. Select the campaign or ad group you want to export.
1. Under the **Account** menu, click **Export** and select **Export the selected campaigns and ad groups**.
1. Save the .csv file.
1. Make any necessary changes and save the file.
1. In Microsoft Advertising Editor, click **Import** from the toolbar and select **Import from Google.**
1. Select the previously saved file and click **OK**.
1. Use the drop-down lists to adjust any Microsoft Advertising column headings to match those in your import file, then click **Next**.
1. Review the **Import summary** to see what entities were newly added, updated or couldn't be imported (skipped).
1. If you want to review the details of the campaigns and make changes, click the link next to **Download the details**.

**Things to note** :
- Unmatched columns will not be imported.
- You can optionally edit destination URLs and choose to share identical sets of ad extensions between campaigns.

## How to preview my campaigns before posting them to Microsoft Advertising
Let’s say you’re ready to import your Google Ads campaign data, but want to preview it before posting directly to Microsoft Advertising. You can do so by modifying your Google Ads import settings.

1. From the top of the page, click **Tools** and select **Options**.
1. Click **Defaults**.
1. Under **Google Ads import settings** select **Download locally**.
1. Click **OK**.


