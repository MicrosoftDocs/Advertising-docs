---
title: Using a final URL suffix
description: Learn about the final URL suffix and how to set one up.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Using a final URL suffix

A final URL suffix is a set of [tracking parameters](./hlp_BA_CONC_UpgradeURL_URLParameters.md) to be added to the end of your landing page URL. Having these parameters in a final URL suffix means that these parameters are always sent to the landing page.

## What parameters can I use in a final URL suffix?

Each suffix can contain one of the following types of values: a static URL parameter, a value that references a Microsoft Advertising URL parameter, or any parameter listed in [What tracking or URL parameters can I use?](./hlp_BA_CONC_UpgradeURL_URLParameters.md)

Keep in mind:
- Suffix values can't begin with ?, &amp;, or # (though &amp; can be used to separate parameters).
- Suffix values can't contain {lpurl}, {ignore}, {escapeurl}, or other variations of a final URL placeholder. For more information, see [What tracking or URL parameters can I use?](./hlp_BA_CONC_UpgradeURL_URLParameters.md)
- A final URL suffix needs to appear after the final URL but before any # (URL fragment symbol).

## How do I set a final URL suffix?

## Set a final URL suffix at the account level
1. In the left navigation pane, click **Shared Library** and then **Account level options** (or from the main menu on the left, click **All campaigns**, then **Settings**, and then **Account settings**).
1. For **Final URL suffix**, enter your parameter or parameters.
1. Click **Save**.

## Set a final URL suffix at the campaign level
1. From the **Campaigns** page, click the **Campaigns** tab (or from the main menu on the left, click **All campaigns** and then **Campaigns**).
1. Select the appropriate campaign.
1. Click **Settings**.
1. Under **Campaign URL options**, click **Final URL suffix** and enter your parameter or parameters.
1. Click **Save**.

## Set a final URL suffix at the ad group, keyword level, or dynamic ad target level
1. From the **Campaigns** page, click the **Ad Groups**, **Keywords**, or **Auto Targets** tab (or from the main menu on the left, click **All campaigns** and then **Ad groups**, **Keywords**, or **Auto Targets**).
1. Make sure that the **Final URL suffix** column is visible. If it isn't:
   1. Click **Columns**&nbsp; &gt; &nbsp;**Modify columns**.
   1. Click **Attributes**.
   1. Next to **Final URL suffix**, click **Add**.
   1. Click **Apply**.

1. For the appropriate ad group or keyword, hover over the **Final URL suffix** column and click the pencil icon.
1. Enter your parameter or parameters.
1. Click **Save**.

## Set a final URL suffix at the ad level
1. From the **Campaigns** page, click the **Ads** tab (or from the main menu on the left, click **All campaigns** and then **Ads**).
1. Hover over the appropriate ad and click the pencil icon when it appears.
1. Click **Ad URL options**.
1. Enter your parameter or parameters in the **Final URL suffix** box.
1. Click **Save**.

## Set a final URL suffix at the product group level (product ads only)
1. From the **Campaigns** page, click the **Ad Groups** tab (or from the main menu on the left, click **All campaigns** and then **Ad groups**).
1. Click the name of the appropriate ad group.
1. Click the **Product Groups** tab.
1. Make sure that the **Final URL suffix** column is visible. If it isn't:
   1. Click **Columns**&nbsp; &gt; &nbsp;**Modify columns**.
   1. Click **Attributes**.
   1. Next to **Final URL suffix**, click **Add**.
   1. Click **Apply**.

1. Click **All products**.
1. For the appropriate product group, hover over the **Final URL suffix** column and click the pencil icon.
1. Enter your parameter or parameters.
1. Click **Save**.

> [!NOTE]
> You can set a final URL suffix at any level, but if you've set different ones at multiple levels, we'll default to the lowest level available. We don't combine values from different levels.


