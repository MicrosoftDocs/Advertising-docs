---
title: What are view-through conversions?
description: Learn about how to track audience ad impressions as conversions even if the customer doesn't click the ad.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# What are view-through conversions?

> [!NOTE]
> To use this feature, you will need to have Universal Event Tracking (UET) set up. [Learn more about UET](./hlp_BA_CONC_UETv2WhatIsTag.md).

With view-through conversions, when an audience ad plants the idea of your product or service in a customer's mind, that ad gets credit for the eventual conversion, even if the customer never clicked the ad. An audience ad impression counts as a conversion when this happens:

1. Your audience ad appears on a webpage that a potential customer visits.
1. Within a time period that you have defined, the same customer makes a purchase or other conversion on your website, without clicking your ad in the interim.

## Key things to keep in mind

- If customers click on any of your ads across Microsoft Advertising, they'll automatically be excluded from your view-through conversion metric so they won't be counted twice.
- View-through conversions are tracked for both [audience campaign](./hlp_BA_CONC_AboutMSAN.md) ads and [search ads extended to the Microsoft Audience Network](./hlp_BA_CONC_NativeAds.md).
- This performance metric appears in the **View-through conversions** column of your tables and reports. View-through conversions are attributed to the last impression and are reported at the time of the impression.

## Including view-through conversions in the All conv. column

By default, view-through conversions are counted the same as other conversions, and are therefore included in the figure you see in the **All conv.** column of your tables and reports. To change this setting:

1. Click **Campaigns** at the top of the page, and then on the left pane, click **Shared Library** and then **Account level options** (or from the main menu on the left, click **All campaigns**, then **Settings**, and then **Account settings**).
1. For **View-through conversions**, unselect or reselect the checkbox next to **Include view-through conversions from the Microsoft Audience Network in your "All conv." columns**.
1. Click **Save**.

> [!NOTE]
> Not everyone has the **All conv.** column yet. If you don't, don't worry—it's coming soon! [Learn more about "Conversions" versus "All conversions"](./hlp_BA_CONC_ConvsVsAllConvs.md).

## Setting your view-through conversion window

The view-through conversion window is the time between an impression and the last moment you want this impression to count towards a view-through conversion.

By default, all UET-based conversion goals are set with a view-through conversion window of 1 day. For new conversion goals, you can change this setting on the **Goal details** page when you create the goal. To change this setting for existing conversion goals:

1. Click **Campaigns** at the top of the page, and then on the left pane, click **Conversion Tracking** and then **Conversion goals** (or from the global menu at the top of the page, click **Tools** and then **Conversion goals**).
1. Select the conversion goal you want to edit.
1. Click **Edit**&nbsp;&gt;&nbsp;**Edit goal**.
1. Click **Next** to get to the **Goal details** page.
1. For **View-through conversion window**, enter a new time period.
1. Click **Save**.


