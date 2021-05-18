---
title: Get started with shopping campaigns
description: Learn about what you need to do to get started with shopping campaigns.
ms.service: "Bing-Ads-Editor-v11"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Get started with shopping campaigns

## Background

To fully understand shopping campaigns, first make sure you understand [product ads](./hlp_BAE_CONC_AboutProductAds.md) and [Microsoft Merchant Center](./hlp_BAE_CONC_AboutBingMerchantCenter.md) feeds. Products ads are created from products in your feed and include custom images, promotional text, pricing, and seller details.

## Get started

Here are two options for getting started with Microsoft Shopping Campaigns:

## Import your shopping campaign from Google Ads in Microsoft Advertising
Import your Google Ads shopping campaigns just as you would a standard search campaign. [Here's more information on the import process.](./hlp_BAE_PROC_Import.md)

> [!IMPORTANT]
> Prior to importing, make sure your feed file is compatible with Microsoft Shopping Campaigns. Not all of Google’s feed attributes are supported by Microsoft Advertising. [Here's a list of differences.](https://go.microsoft.com/fwlink?LinkId=823411)

## Create a new Microsoft Shopping Campaigns to run in parallel with your existing product ad campaign
If you already have product ads set up in Microsoft Advertising, you can create a new Microsoft Shopping Campaigns that uses your existing feed file. The new shopping campaign will not replace your existing product ad campaigns, but will instead be a new campaign that runs alongside the others. Here are the steps you need to follow:

1. First update your feed as necessary:
   - Consider adding custom labels. For more information on custom labels, see [How is the feed organized](https://go.microsoft.com/fwlink?LinkId=823412). If you are using Microsoft Advertising Labels and Microsoft Advertising groups for your Product Ad campaigns, you will need to switch these to custom labels in your shopping campaign.
   - Consider using the improved Bing and product categories. [Here’s the full list of categories](https://go.microsoft.com/fwlink?LinkId=620783).

1. Next, follow the steps for creating a shopping campaign.
   - In the data view, click **Add campaign**.
   - In the edit panel, for **Campaign type**, select **Shopping**.
   - Click on the **Shopping settings** tab.
   - Enter the **Store ID** and select the **Country of Sale** and **Campaign priority**.

Pay particular attention to the following settings in your new campaign:

   - **Store ID** : As you set up your shopping campaign, you will be asked to link your campaign to an existing store. Make sure to link your campaign to the correct store because you will not be able to change the store once you save your campaign. After that, the only way to link to a new store is to delete the campaign and start over.
   - **Campaign priority** : Campaign priority handles cases where the same product ad could be displayed from multiple campaigns, such as from your existing product ad campaign and your new shopping campaign. The ad from the campaign with the highest priority will take precedence over the same ads from other campaigns, regardless of bids. Generally, you want to ensure your shopping campaign has a higher priority than your product ads campaign.
Campaign priority can also be useful if you want to create campaigns around specific events, like sales or promotions, without changing bids across the campaigns.

1. Once your shopping campaign is created, your final step is to [create one or more product groups](./hlp_BAE_CONC_BSC_AboutProductGroups.md).


