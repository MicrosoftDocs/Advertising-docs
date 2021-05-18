---
title: Understand and use product groups
description: Product groups are used to specify which products from your Microsoft Merchant Center feed should be included in a particular ad group. In this article will explain more and give a detailed example.
ms.service: "Bing-Ads-Editor-v11"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Understand and use product groups

## What are product groups?

Product groups are used to specify which products from your Microsoft Merchant Center feed should be included in a particular ad group.

> [!NOTE]
> In order to understand product groups, first make sure you are familiar with both [product ads](./hlp_BAE_CONC_AboutProductAds.md) and [shopping campaigns](./hlp_BAE_CONC_BSC_GetStarted.md).

After you create a shopping campaign, you want to create an ad group. That ad group includes a product group containing all of the products in your Microsoft Merchant Center feed. However, you don't typically want an ad group to contain all products. Instead, you likely want each ad group to contain only very closely related products in order more effectively manage which ads show, and when. With product groups you can narrow down that default group to a customized list of specific products.

You can use the following attributes from your feed to choose the specific products you want to include in any particular product group.

- Category (Up to five for each offer)
- Brand
- Condition
- Item ID (Also known as Merchant Product Identifier
- Product type
- Custom label (Up to five for each offer)

You can use multiple attributes to narrow your group even further. For example, you can create a product group based on brand and condition.

## An example

The best way to understand product groups is to see an example.

Let's say Matt is the owner of a small toy store and his feed includes the following items:

|Merchant Product Identifier|Title|Brand|Category 1|Category 2|Product Type|Custom Label 0|
|---|---|---|---|---|---|---|
|1111|Toy 1|Tailspin Toys|Toys &amp; Games|Indoor|Paint|Ages 1-5|
|2222|Toy 2|Wingtip Toys|Toys &amp; Games|Indoor|Stickers|Ages 1-5|
|3333|Toy 3|Tailspin Toys|Toys &amp; Games|Outdoor|Chalk|Ages 6-12|
|4444|Toy 4|Wingtip Toys|Toys &amp; Games|Indoor|Glitter|Ages 6-12|
|5555|Toy 5|Tailspin Toys|Media|Indoor|DVD|Teens|
|6666|Toy 6|Wingtip Toys|Toys &amp; Games|Outdoors|Sports|Teens|
|7777|Toy 7|Tailspin Toys|Media|Indoor|Books|Ages 1-5|
|8888|Toy 8|Wingtip Toys|Toys &amp; Games|Indoor|Paint|Ages 6-12|

He wants his ad group to contain only toys for ages 1-5. To do that he would simply narrow the default product group down to a product group where Custom label = Ages 1 -5.

As another example, assume that Matt wants to create an ad group that contains only toys from Tailspin Toys for ages 1-5. He simply needs to create a product group where Brand = Tailspin Toys and Custom label = Ages 1-5.

## How do I create product ads?

## Create a product ad
1. In the type list from the left panel, select **Product ads** under **Ads and extensions**, and then the ad group in which you want to create a new ad.
1. Click **Add product ad**.
1. In the edit panel, enter the required information for your ad.

## Create multiple product ads
1. In the type list from the left panel, select **Product ads** under **Ads and extensions**, and then the ad group in which you want to create new ads.
1. In the data view, click **Make multiple changes** &nbsp; &gt; &nbsp; **Add/update multiple product ads**.
1. In the **Make multiple changes** dialog box, under **Add product ad data**, do one of the following:      [!INCLUDE [MCWEnterData_Ads](./includes/MCWEnterData_Ads.md)]
1. Click **Next**.
1. [!INCLUDE [MCWImportCompleted](./includes/MCWImportCompleted.md)]

> [!NOTE]
> There is a 1 to 1 relationship between ad groups and product groups. In other words, each ad group has one product group and vice versa.
> Remember to "exclude" items that you don't want to be in your product group.


