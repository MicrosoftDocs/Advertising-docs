---
title: About dynamic search ads page feeds
description: Learn how to upload relevant URLs for your dynamic search ad campaigns with page feeds.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# About dynamic search ads page feeds

[!INCLUDE [ComingSoon](./includes/ComingSoon.md)]
Page feeds allow you to easily upload all the relevant URLs for your dynamic search ads in a spreadsheet format. This ensures maximum website coverage and enables the labeling and targeting of specific URLs via custom labels.

## The benefits of using page feeds for dynamic search ads

- **Improve page freshness** . Each time a feed is uploaded, the pages in the feed are automatically recrawled; so, if the pages aren’t already in the Bing index of your website, they’ll be added. This allows the most current version of your website to be shown in dynamic search ads.
- **Fine-tune auto-targets and ad copy** . You have full control over what pages are included in an auto-target and, as a result, can be more descriptive in your ad copy to drive further engagement.

## Country/region availability

Dynamic search ads are available in Australia, Austria, Belgium, Canada, Denmark, Finland, France, Germany, Ireland, Italy, Netherlands, New Zealand, Norway, Spain, Sweden, Switzerland, United Kingdom, and United States.

## Create a page feed file

You can download the page feed template or create a .csv, .tsv, .xls, or .xlsx file that contains the following two columns:

|Column|What it is|What you need to know|
|---|---|---|
|Page URL|Contains the URLs of your website to include in the feed.|Enter one URL per row. URLs must start with **https://** or **http://**.|
|Custom label (optional)|Labels that allow you to group the URLs within the feed.|Enter one or more labels per row, separated by a semicolon.       A maximum of 10 custom labels can be added per feed item (row).|
|Ad title (optional)|Static headline that is shown instead of Microsoft's dynamically generated headline.|Enter an ad title (maximum 63 characters) for the page feed item. You can include one ad title per feed item.|

**Note** : You can have 100 feeds per account (this maximum number includes all feed types) and the maximum number of feed items (rows) per account is 5 million.

## Upload a page feed file

1. [!INCLUDE [BusinessDataDynamicDataFeeds](./includes/BusinessDataDynamicDataFeeds.md)]
1. Select **Upload**.
1. Enter the **Name** of your feed file and choose the file to upload.
1. Select **Upload and apply**.

## Associate a page feed

Page feeds can be associated at the campaign level, which also applies to all the ad groups within the campaign.

1. From the collapsible menu on the left, select **Search campaigns** > Settings.
1. In the table, select the campaign you want to apply a page feed to.
1. In the Campaign settings window, under **Dynamic search ads**, select the checkbox to **Enable dynamic search ads**.
1. Under **Targeting source**, choose one off the following:
   - **Use Bing's index of my website** . This is the default behavior of dynamic search ad campaigns on Bing.
   - **Use URLs from my page feed only** . Only URLs specified in the feed file will be served from this campaign. We recommend using this option for highly specific campaigns with tailored ad copy.
   - **Use URLs from both Bing’s index of my website and my page feed** . Pages from both sources will be used but URLs within the feed file will be given priority.

1. Search for and select the page feed you want to apply.
1. Select **Save**.

## Create custom label auto targets

1. [!INCLUDE [DynamicAdTargets](./includes/DynamicAdTargets.md)]
1. Select **Create ad targets**.
1. Choose an ad group from the **Select an ad group** dropdown menu.
1. Select the target webpages.
1. Enter a bid or leave it blank to use the default ad group bid.
1. Select **Save &amp; create new**.


