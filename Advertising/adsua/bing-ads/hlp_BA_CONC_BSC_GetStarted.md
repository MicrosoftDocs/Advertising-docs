---
title: Get started with Microsoft Shopping Campaigns
description: Learn about what you need to do to get started with shopping campaigns.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Get started with Microsoft Shopping Campaigns

## Background

To fully understand shopping campaigns, first make sure you understand [product ads](./hlp_BA_CONC_AboutProductAds.md) and [Microsoft Merchant Center](./hlp_BA_CONC_AboutBingMerchantCenter.md) catalogs. Products ads are created from products in your catalog and include custom images, pricing, and seller details.

## Get started

If you’ve never used Microsoft Advertising product ads or Google shopping campaigns, you'll need to create a shopping campaign from scratch. [Here are instructions to get started.](./hlp_BA_PROC_CreateProductTargetAndAd.md)

However, if you've already used product ads, either in Microsoft Advertising or Google Ads, you have two other options for getting started with Microsoft Shopping Campaigns:

## Import your shopping campaign from Google Ads
Import your Google Ads shopping campaigns just as you would a standard search campaign. [Here's more information on the import process.](./hlp_BA_PROC_ImportCampaign.md)

> [!IMPORTANT]
> Prior to importing, make sure your feed file is compatible with Microsoft Shopping Campaigns. Not all of Google's feed attributes are supported by Microsoft Advertising. [Here's a list of differences.](./hlp_BA_CONC_BMCGoogleAttributes.md)

## Create a new Microsoft Shopping Campaign to run in parallel with your existing product ad campaign
If you already have product ads set up in Microsoft Advertising, you can create a new Microsoft Shopping Campaigns that uses your existing catalog feed file. The new shopping campaign will not replace your existing product ad campaigns, but will instead be a new campaign that runs alongside the others. Here are the steps you need to follow:

1. First update your catalog feed as necessary:
   - Consider adding custom labels. For more information on custom labels, see [How is the catalog feed organized](./hlp_BA_CONC_AboutBingMerchantCenterCatalogFile.md). If you are using Microsoft Advertising Labels and Microsoft Advertising groups for your product ad campaigns, you will need to switch these to custom labels in your shopping campaign.
   - Consider using the improved Bing and product categories. [Here’s the full list of categories](https://go.microsoft.com/fwlink?LinkId=620783).

1. Next, follow the [ steps for creating a shopping campaign](./hlp_BA_PROC_CreateProductTargetAndAd.md). Because you are already using product ads, you have probably already completed the first three steps and will only need to complete step four.
Pay particular attention to the following settings in your new campaign:

   - **Campaign priority** : Campaign priority handles cases where the same product ad could be displayed from multiple campaigns, such as from your existing product ads campaign and your new shopping campaign. The ad from the campaign with the highest priority will take precedence over the same ads from other campaigns, regardless of bids. Generally, you want to ensure your shopping campaign has a higher priority than your product ads campaign. If there are multiple campaigns with different priorities targeting the same product, the campaign priority still holds true – High takes precedence over Medium, which takes precedence over Low. However, if the product gets filtered out by any business rules, like location targeting, minimum bids, etc., the campaign priority is applied to the non-filtered product. For example, let’s say you have a High and Medium campaign targeting the same product, and this product is selected to serve. But after applying location targeting, the product from the High campaign is filtered, which means the non-filtered product from the Medium campaign will serve.
Campaign priority can also be useful if you want to create campaigns around specific events, like sales or promotions, without changing bids across the campaigns.

   - **Store ID** : As you set up your shopping campaign, you will be asked to link your campaign to an existing store. Make sure to link your campaign to the correct store because you will not be able to change the store once  you save your campaign. After that, the only way to link to a new store is to delete the campaign and start over.
   - **Product filters** : By default, all products in your Microsoft Merchant Center Store will be included in the campaign. Use product filters if you want to include only a subset of your products in the campaign.

1. Once your shopping campaign is created, your final step is to [create one or more product groups](./hlp_BA_CONC_BSC_AboutProductGroups.md).

 

