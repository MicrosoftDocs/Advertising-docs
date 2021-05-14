---
title: Automatic Item Update
description: Enable Automatic Item Update to reduce mismatches between your Microsoft Merchant Center offers and your site.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Automatic Item Update

> [!IMPORTANT]
> This feature is available only in the United States.

Keep your offers up and serving with Automatic Item Update. This feature automatically syncs your Microsoft Merchant Center feeds to your site's [ price and availability microdata](./hlp_BA_CONC_BMC_StructuredDataMarkup.md).

## What's in it for you

The products in your Microsoft Merchant Center feed have several attributes, including title, description, availability, and price. The last two attributes can fluctuate based on demand.

Commonly, you may run out of inventory on your site, but your Microsoft Merchant Center feed still incorrectly shows product availability. This mismatch can lead to a poor experience where a customer clicks on your product ad, only to find the product sold out on your site. Traditionally, Microsoft Merchant Center rejects an offer when a mismatch occurs.

Automatic Item Update allows you to keep serving offers because the feature will automatically update price and inventory data during the normal course of a business day.

## How it works

When you enable Automatic Item Update for your feed, you are sourcing price and availability info directly from your site microdata. If your site is out of inventory or if prices change, you can choose to automatically update an item in your Microsoft Merchant Center with:

- Price only
- Availability only
- Both price and availability

You can also opt to update these attributes automatically if you encounter the opposite scenario: Your site microdata shows product availability, but your feed shows the product as out of stock. You can override your feed with an optional setting in Automatic Item Update. Also, don’t forget that for items being sold in bulk, the price must be for the minimum quantity sold. For example, if you sell paper cups in quantities of 100, the price should be for the 100 paper cups, and not as a single paper cup in both the feed and landing page.

Keep in mind that Automatic Item Update only pulls in new data, and not for impressions. As such, automatic item update is not a substitute for updating your data feed. You should continue to [update your feed file daily](./hlp_BA_CONC_BMCWhatIsCatalog.md), be it manually, automatically, or via FTP.

## Enabling Automatic Item Update
1. On the top menu, click **Tools** and then click ** Microsoft Merchant Center**  (or from the global menu at the top of the page, click **Tools** and then **Microsoft Merchant Center**).
1. Select the Microsoft Merchant Center store you want to edit.
1. Click **Settings** and then click **Automatic Item Update**.
1. Slide the switch to the right to turn **On** this feature.           You'll need to select an option from the list: Update an item's **Price only**, **Availability only**, or **Both price and availability** when there's a discrepancy.           Also, you can opt to update an item's price and availability if it's out of stock in the feed, but it is in-stock on the site. If you wish to do this, check the box next to: **If an offer is out of stock in the feed, override it and update availability directly from the site**.
1. Click **Save**.

## Disabling Automatic Item Update
1. On the top menu, click **Tools** and then click ** Microsoft Merchant Center**  (or from the global menu at the top of the page, click **Tools** and then **Microsoft Merchant Center**).
1. Select the Microsoft Merchant Center store you want to edit.
1. Click **Settings** and then click **Automatic Item Update**.
1. Slide the switch to the left to turn **Off** this feature.
1. Click **Save**.

## Restarting Automatic Item Update after a system pause

Mismatches can still occur with Automatic Item Update, which is why it's important to keep your data feed up to date. Microsoft Merchant Center will monitor the number of mismatches on offers with Automatic Item Update. If there is a high rate of mismatches, Automatic Item Update will be disabled, and all offers will be rejected.

If this happens, you will need to review your offers and clean up the data mismatches. Microsoft Merchant Center will automatically resume Automatic Item Update once the mismatch rate drops.

> [!IMPORTANT]
> Please note, if you enable Automatic Item Update for your feed, Microsoft Advertising is not responsible for incorrect data updates. For example, be sure that any marked-up data on your website's landing page is accurate.


