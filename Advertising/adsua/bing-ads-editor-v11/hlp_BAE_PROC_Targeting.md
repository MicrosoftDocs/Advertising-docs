---
title: Target customers by location, day of the week, time of day, device, or by network distribution
description: Add targeting at the campaign or ad group level with Microsoft Advertising Editor.
ms.service: "Bing-Ads-Editor-v11"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Target customers by location, day of the week, time of day, device, or by network distribution

You can add targeting at the campaign or ad group level.
You can also increase your bids to target customers. For more information, see [Increase bids based on customer age, gender, location, time of day, or day of the week](./hlp_BAE_PROC_IncrementalBid.md).

## Target by customer location
1. Select the campaigns or ad groups from the tree view in the left panel that you want to add targeting to.
1. Click **Locations** under **Keywords and targeting** from the type list in the left panel.
1. In the **Edit the selected location target** section:
   - Specify the location for this entry. Click **Edit/find location** and you can specify the location by **Area targeting** (narrow your location target by country/region, city, or U.S. counties) or by **Radius targeting** (narrow your location to a single mile or kilometer, or expand it to a larger circle).
   - Enter bid adjustment.

1. The details you input will automatically populate the new row in the main grid.

**What you need to know**: 
- To select where you want to show your ad, go to **Campaigns** or **Ad groups** in the left panel and select from **Targeting method** in the edit pane.
- Targeting by device and by network distribution is still accessible by clicking **Additional targeting** on the **Campaigns** tab. (See last two menus below.)
- You can set multiple radius targets for the same location with different radius values and have different bid adjustments for each target.
- You can target at the county level for U.S. markets only.

## Target by day of the week and time of day
1. Select the campaigns or ad groups from the tree view in the left panel that you want to add targeting to.
1. Click **Add ad schedule** from the type list in the left panel.
1. In the **Edit the selected ad schedule** pane, input values for targeted day, start time, end time, and bid adjustment. The details you input here will automatically populate the new row in the main grid.

**What you need to know**:
- You can increase bid adjustments up to 900% and decrease them by as much as 90%.
- When targeting by time, you are targeting the searcher's local time zone.
- Start times and end times are available for you to choose in 15-minute increments only. Please consider this if you're working in a spreadsheet and need to import ad schedules into Microsoft Advertising Editor.

## Target by device
> [!IMPORTANT]
> Details for device targeting, except for bid adjustments, cannot be updated after it’s been created. If you want to change the targeting details, you must delete it and then create a new one.

1. Under **Keywords and targeting**, select **Device**.
1. In the data view, click **Add device** and select **Device**.
1. Select the campaign or ad group.
1. In the **Edit the selected device**, enter the **Bid Adjustment** and select **Device**.

**What you need to know**:      You can target desktop computers (bid adjustments -100% to +900%), tablets (-100% to +900%), or smartphones (-100% to +900%).

## Target by network distribution
1. Select the campaigns or ad groups from the tree view in the left panel that you want to add targeting to.
1. In the **Edit the selected ad groups** pane, select the networks you want to target from the **Network distribution**.
> [!NOTE]
> The ad distribution options **Only Bing, AOL, and Yahoo websites** and **Only Bing, AOL, and Yahoo syndicated search partners** apply to websites located in the **United States**, **Canada**, **United Kingdom**, **Ireland**, **Australia**, **France**, **Germany**, and **Norway**. All other websites will use **All Bing, AOL, and Yahoo Search networks and syndicated search partners** even if the other two options are selected. When you run the Publisher Performance report, you'll see websites based on these ad distribution rules.

## Target by gender
1. Select the campaigns or ad groups from the tree view in the left panel that you want to add targeting to.
1. Click **Genders** under **Keywords and targeting** from the type list in the left panel.
1. In the **Edit the selected gender** pane, enter the percentage by which you want to increase the bid for that gender.

**What you need to know**:
- You can increase bid adjustments up to 900% and decrease them by as much as 90%.
- When you apply bid adjustments to gender, your ads will appear more frequently for the targeted demographic but will still also appear for non-targeted demographics.

## Target by age
1. Select the campaigns or ad groups from the tree view in the left panel that you want to add targeting to.
1. Click **Ages** under **Keywords and targeting** from the type list in the left panel.
1. In the **Edit the selected age** pane, enter the percentage by which you want to increase the bid for that age.

**What you need to know**:
- You can increase bid adjustments up to 900% and decrease them by as much as 90%.
- When you apply bid adjustments to age group, your ads will appear more frequently for the targeted demographic but will still also appear for non-targeted demographics.

> [!NOTE]
> When you target by location, you choose to show ads to potential customers in specific countries/regions, states/provinces, metro areas, or cities. For example, if you own a car repair service in Oakland, California, you might want to target your customers in the Oakland metro area, which includes the surrounding cities. That way, most of the people who see your ad are within range of your service. Use the **Locations** options in your campaign settings to define the physical location you want to target.
> [!INCLUDE [AdGroupTargeting](./includes/AdGroupTargeting.md)]
> Device targeting is available only for campaigns and ad groups running in the U.S. and Canada markets.


