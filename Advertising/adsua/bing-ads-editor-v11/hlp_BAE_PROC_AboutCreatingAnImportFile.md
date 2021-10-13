---
title: Import data using a file
description: You can import your campaigns from other advertising programs using a file.
ms.service: "Bing-Ads-Editor-v11"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Import data using a file

If you already have campaigns in other online advertising programs, you can import the data into Microsoft Advertising using a file. We provide an import template that you can manually fill out with your campaign info and then import into Microsoft Advertising.

## Few things to know about the file

- It must be a Excel or .csv (comma-separated values) file.
- It must be closed before you try to import it.
- The data must be in the correct order. If you download information from Google AdWords or another online advertising program, copy the information into the template, save it, and then import the saved file.
- We recommend that you remove duplicate keywords in the import file—for example, "Apple" and "apple" will appear as duplicates.
- We recommend that you remove keywords that are not allowed—for example, "gambling" and "firearms."

## Create the file using a Microsoft Advertising template
First, you need to download the template and then you need to add your data.

1. Fill the template out with your campaign data.
1. Select **File** and then **Save as**.
1. Type a name for the import template. Use quotation marks around the name and include .csv at the end. For example, "YourFileName.csv". The quotation marks will not appear in your final file name but are used to prevent Excel from adding ".txt".
1. Select Unicode Text, and then click **Save**.

## Import the file into Microsoft Advertising Editor
1. In Microsoft Advertising, click **Import Campaigns**, and then click **Import from file**.
1. If you have imported from a file in the past 90 days, you will see a table that tells you the **Date/Time** and     **Uploaded file** that was imported along with:
|Column Name|Description|
|---|---|
|Summary|Shows how many entities were imported successfully and how many had errors. Click the ellipsis ![ellipse](../images/BA_ScreenCap_DeliveryDetails.png) to see details.|
|Actions|If you had errors, you will see a link to download the error file which you can review.|

1. Click **Browse** and select the import file you've created, then click **Continue**.
1. Use the drop-down lists to adjust any Microsoft Advertising column headings to match those in your import file, then click **Continue**.
1. Under **Choose Import Options**, do the following:
   - Choose the appropriate options for **What to import**, **Bids and budgets**, **Landing page URL**, **Tracking template**, **Ad extensions**, and **Microsoft Advertising**.

1. Click **Import**.
1. Review the **Import summary** to see what entities were newly added, updated or couldn't be imported (skipped).
1. If you want to review the details of the campaigns and make changes, click **View imported campaigns**.

> [!NOTE]
> Unmatched columns will not be imported.
> You can optionally edit destination URLs and choose to share identical sets of ad extensions between campaigns.
> You cannot update or delete existing ad extensions through file import.


