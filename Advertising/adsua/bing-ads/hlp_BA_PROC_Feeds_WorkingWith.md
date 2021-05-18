---
title: Setting up and managing feeds
description: Learn how to upload, update, and manage your feeds.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Setting up and managing feeds

Microsoft Advertising feeds—such as [ad customizer feeds](./hlp_BA_CONC_Feeds_AdCustomizers.md)—are managed in the Business data section of your Shared Library.

## Uploading a feed file

1. Click **Shared Library** in the left navigation pane (or from the global menu, click **Tools** > **Business data**).
1. Click **Business data** and then select the type of feed you want to upload.
1. Click the **Upload** button.
1. Give your feed a unique name.
1. Click **Browse** to find your feed file. Note: This file must be saved as one of the following formats: .csv, .tsv, or .xlsx.
1. You can then either **Upload and preview** (allowing you to review and fix any errors before applying) or **Upload and apply**.

## Managing feeds after uploading

To see the feeds you've uploaded:

1. Click **Shared Library** in the left navigation pane (or from the global menu, click **Tools** > **Business data**).
1. Click **Business data** and then select the type of feed you want to review.

You can then make changes to one of these feeds by re-uploading an edited version of the feed:

## Update: Add, change, or remove **some** of your feed's items
1. Click on the name of a feed.
1. For your updates to match up correctly, make sure the **Item ID** column is present in the feed's table. If it is not shown by default, you will need to add it:
   1. Click **Columns**&nbsp; &gt; &nbsp;**Modify columns**.
   1. Click **Attributes**.
   1. Next to **Item ID**, click **Add**.
   1. Click **Apply**.

1. Click **Download** to get the feed in spreadsheet form.
1. Remove any feed item rows from the spreadsheet that you don't want to update. Feed items that aren't listed in your edited feed will not be affected by the upload.
1. Add an **Action** column to the spreadsheet. This column tells us what to do:
   - Enter ```**Add**``` in a blank row to add a new feed item. The **Item ID** column should be empty for added feed items.
   - Enter ```**Set**``` in the row of a feed item you want to change and then edit the information in any column except the **Item ID** column.
   - Enter ```**Remove**``` in the row of a feed item you want to remove. For feed items to be removed, the only required columns are the **Action** and **Item ID** columns.

> [!IMPORTANT]
> Your edited feed file must not contain any columns that aren't present in your previous feed.

1. In Microsoft Advertising, click **Upload spreadsheet**.
1. Select **Update**.
1. Click **Browse** to find the edited feed file. Note: This file must be saved as one of the following formats: .csv, .tsv, or .xlsx.
1. Click either **Upload and preview** (allowing you to review and fix any errors before applying) or **Upload and apply**.

## Replace: Replace **all** of your feed's items
1. Click on the name of a feed.
1. Click **Upload spreadsheet**.
1. Select **Replace** .
1. Click **Browse** to find your new feed file. Note: This file must be saved as one of the following formats: .csv, .tsv, or .xlsx.
> [!IMPORTANT]
> Your new feed file must not contain any columns that aren't present in your previous feed.

1. Click either **Upload and preview** (allowing you to review and fix any errors before applying) or **Upload and apply**.

## Schedule: Set schedules to update your feeds
You can schedule feed uploads to keep your feed data up to date.

**What you need to know:**
- Feed schedules can be created only for ad customizers, Dynamic Search Ads, and Dynamic Data Extensions.
- Updates can be made every 6 hours, every 12 hours, daily, weekly, or monthly.
- You can set only one schedule per feed.

**Create a feed schedule**
1. Click on the name of a feed.
1. Click on the **Schedules** tab and then **Schedule feed uploads**.
1. Select the **Frequency**  and **URL** .
1. **Optional** : Enter **Username** and **Password**.
1. Click **Save**.

**Edit a feed schedule**
1. Click on the name of a feed.
1. Click on the **Schedules** tab and then select one of the following options:
   - **Edit**  to change schedule fields.
   - **Pause**  current schedule.
   - **Remove**  current schedule.
   - **Update now**  to manually update feed immediately.

**View upload history**
1. Select the feed type.
1. Click on the **Upload history** tab.
1. Click **Download all results** or **Download errors only** to view upload details.

**View schedule settings** 					 					Select the feed type and from the table, you can see the **Schedule** and **Last run time** for each feed.

**Use Google Sheets feed** 				   				  You can also download your feed file from Google Docs. Keep in mind that we only accept .csv or .tsv formats for feed files from Google.
1. Open your feed file in Google Docs.
1. Click File and select Publish to the web.
1. Select either Comma-separated values (.csv) or Tab-separated values (.tsv).
1. Click Publish.
1. Copy the generated link and use the link as your automatic download URL.


