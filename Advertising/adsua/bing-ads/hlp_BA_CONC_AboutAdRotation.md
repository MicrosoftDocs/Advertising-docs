---
title: Ad rotation explained
description: How the ad rotation setting helps determine how often ads are displayed in relation to others in the ad group.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Ad rotation explained

Ad rotation sets how often ads are served by Microsoft Advertising, if you have multiple ads within an ad group. Since no more than one ad from your account can show at a time, your setting for ad rotation determines how to prioritize the ads available to serve.

Ad rotation is an ad group setting. Here's how to change it:

1. From the main menu on the left, select **All campaigns**.
1. From the page menu, select **Ad groups**.
1. In the table, select the name of the ad group you want to edit.
1. From the page menu, select **Settings**.
1. Under **Advanced ad group settings**, in the **Other settings** section, select **Ad rotation**.
1. The rotation can be set two ways:
   1. **Optimize**: Prioritizes ads based on auction factors, such as keyword, search term, device, or location. This is the default setting.
      - Microsoft Advertising prioritizes the ad from the ad group that appears to have the best chance of performing well. Better-performing ads will show more frequently, and others will be served less often, if at all.

   1. **Rotate ads more evenly**: Provides more balance in rotation. That is, each ad has a similar chance of being displayed in response to a searcher's query. Ads are prioritized lower if they have lower [ad quality](./hlp_BA_CONC_AboutQualityScore.md), and therefore might display less often, in a lower position, or not at all.
      - This setting can allow lower-performing ads to display as often as better-performing ads.
      - This setting will be overridden if you use an automated bidding [bid strategy](./hlp_BA_CONC_BidStrategy.md), as these bid strategies prioritize better-performing ads.

1. **Save** your changes.

> [!NOTE]
> Ad rotation does not apply to product ads.


