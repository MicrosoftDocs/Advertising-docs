---
title: Increase bids based on customer age, gender, location, time of day, or day of the week
description: Use incremental bidding in Microsoft Advertising Editor to pay the extra bid amount only for clicks that come from your targeted customers.
ms.service: "Bing-Ads-Editor-v11"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Increase bids based on customer age, gender, location, time of day, or day of the week

You can incrementally increase your bids at the campaign or ad group level to target customers. When you use incremental bidding, your ads are displayed to all customers, but you pay the extra bid amount only for clicks that come from your targeted customers.

You can also add targeting to control when your ads are displayed. For more information, see [Target customers by location, day of the week, time of day, device, or by network distribution](./hlp_BAE_PROC_Targeting.md).

**What you need to know**:
- Bid adjustments are rounded down to the nearest cent.
- Bid adjustments for most variables can ranges, in 1% increments, from -90% to +900%.
- As per above, negative bid adjustments for most targets can go to -90%. However, if you're using a negative bid adjustment for tablet or smartphones, you can go to -100%. Using -100% for one of these devices would effectively opt you out of displaying your ads on that device.
- When you place a bid adjustment for geographical location, day of the week, or time of day, you can use targeting to choose whether to display your ads only to target customers or to all customers. When you place a bid adjustment for age or gender, your ads are displayed to all customers, but your adjusted bid can increase the likelihood of your ad being displayed to the specified gender and age segments. In all cases, you pay the adjusted bid only when one or more of the target criterion is met and your ad is clicked.

## Increase bids on certain days of the week
> [!IMPORTANT]
> Once you add an ad schedule, your ads will only serve on the day and time you select, and will not serve on any other day and time. For example, if you add a new ad schedule for Mondays from 9 am to 12 pm, your ads will only serve then and not on any other day. If you want your ads to serve for the remaining days as well, be sure to add an ad schedule for all other days.

1. Select the campaigns or ad groups from the tree view in the left panel that you want to add targeting to.
1. Click **Ad schedules** under **Keywords and targeting** from the left panel.
1. In the **Edit the selected ad schedule** pane, select the **Targeted day** and enter the percentage by which you want to increase the bid for that day in the **Bid adjustment** box. Leave the **Start time** and **End time** as-is so your ads will serve all day for your selected day.

## Increase bids at certain times of day
> [!IMPORTANT]
> Once you add an ad schedule, your ads will only serve on the day and time you select, and will not serve on any other day and time. For example, if you add a new ad schedule for Mondays from 9 am to 12 pm, your ads will only serve then and not on any other day. If you want your ads to serve for the remaining days as well, be sure to add an ad schedule for all other days.

1. Select the campaigns or ad groups from the tree view in the left panel that you want to add targeting to.
1. Click **Ad schedules** under **Keywords and targeting** from the type list in the left panel.
1. In the **Edit the selected ad schedule** pane, select the **Targeted day**, **Start time**, **End time**, and enter the percentage by which you want to increase the bid for that day in the **Bid adjustment** box.

## Increase bids based on customer location
1. Select the campaigns or ad groups from the tree view in the left panel that you want to add targeting to.
1. Click **Locations** under **Keywords and targeting** from the type list in the left panel.
1. In the **Edit the selected location target** pane, select the locations that you want to target. You can use the **Edit/find location** box to find locations.
1. For each location, in the **Bid adjustment** box, enter the percentage by which you want to increase the bid for that location.

## Increase bids based on customer gender
1. Select the campaigns or ad groups from the tree view in the left panel that you want to add targeting to.
1. Click **Gender** under **Keywords and targeting** from the type list in the left panel.
1. In the **Edit the selected gender** pane, enter the percentage by which you want to increase the bid for that gender.

## Increase bids based on customer age
1. Select the campaigns or ad groups from the tree view in the left panel that you want to add targeting to.
1. Click **Age** under **Keywords and targeting** from the type list in the left panel.
1. In the **Edit the selected age** pane, enter the percentage by which you want to increase the bid for that age.

> [!NOTE]
> Location targeting is available by country, region, state, metropolitan area, and city; it is not available by postal code.


