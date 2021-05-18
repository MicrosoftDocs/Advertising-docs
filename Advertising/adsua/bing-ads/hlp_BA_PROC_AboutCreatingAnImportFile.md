---
title: Import data using a file
description: You can import your campaigns from other advertising programs using a file.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Import data using a file

If you already have campaigns in other online advertising programs, you can import the data into Microsoft Advertising using a file. We provide an import template that you can manually fill out with your campaign info and then import into Microsoft Advertising.

## Few things to know about the file

- It must be an Excel or CSV (comma-separated values) file.
- Imported column headers must be in Google Ads or Microsoft Advertising format in order to be recognized.
- Duplicative keywords will be skipped during import. For example, "Apple" and "apple" will appear as duplicates, and therefore be skipped.
- Words like “gambling” or “firearms” that may require further inspection, will either be editorially reviewed and skipped during an import, or editorially reviewed after the import.

## Create the file using a Microsoft Advertising template
First you need to download the template from Microsoft Advertising and then you need to add your data.

1. At the top of the page, click **Import Campaigns**, and then click **Import from file** (or from the global menu at the top of the page, click **Import** and then click **Import from file**).
1. Click **Download the import template**.
1. Click **Save** and then **Open**.
1. Fill the template out with your campaign data.
1. Select **File** and then **Save as**.
1. Type a name for the import template. Use quotation marks around the name and include .csv at the end. For example, "YourFileName.csv". The quotation marks will not appear in your final file name but are used to prevent Excel from adding ".txt".
1. Select Unicode Text, and then click **Save**.

## Import the file into Microsoft Advertising
1. At the top of the page, click **Import Campaigns**, and then click **Import from file** (or from the global menu at the top of the page, click **Import** and then click **Import from file**).
1. If you have imported from a file in the past 90 days, you will see a table that tells you the **Date/Time** and          **Uploaded file** that was imported along with:
|Column Name|Description|
|---|---|
|Summary|Shows how many entities were imported successfully and how many had errors. Click the ellipsis ![ellipse](../images/BA_ScreenCap_DeliveryDetails.png) to see details.|
|Actions|If you had errors, you will see a link to download the error file which you can review.|

1. Click  **Browse** and select the import file you've created, then click **Continue**.
1. Use the drop-down lists to adjust any Microsoft Advertising column headings to match those in your import file, then click **Continue**.
1. Under **Choose Import Options**, do the following:
   - Choose the appropriate options for **What to import**, **Bids and budgets**, **Landing page URL**, **Tracking template**, **Ad extensions**, and **Microsoft Merchant Center**.

1. Click **Import**.
1. Review the **Import summary** to see what entities were newly added, updated or couldn't be imported (skipped).
1. If you want to review the details of the campaigns and make changes, click **View imported campaigns**.

> [!NOTE]
> Unmatched columns will not be imported.
> You can optionally edit destination URLs and choose to share identical sets of ad extensions between campaigns.
> You cannot update or delete existing ad extensions through file import.


