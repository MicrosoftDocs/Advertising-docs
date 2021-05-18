---
title: Associate an audience with an ad group or campaign
description: Once you create a remarketing list in Microsoft Advertising, you can associate it with an ad group/campaign.
ms.service: "Bing-Ads-Editor-v11"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Associate an audience with an ad group or campaign

A remarketing list is one type of audience and once you create the list in Microsoft Advertising, you can associate it with an ad group/campaign and set a bid adjustment in Microsoft Advertising Editor. This allows you to optimize your campaign for the specific audience. To learn more, see [What is remarketing?](./hlp_BAE_CONC_Remarketingv2WhatIs.md)

## Should I associate audiences to my ad groups or my campaigns?

|Scenario|You should associate audiences to|
|---|---|
|You're using different audiences and bids for different ad groups in the same campaign.|**Ad groups** : That way, you can manage and optimize each audience individually.|
|Your account is segmented at the ad group level, or you otherwise want to keep precise control over each ad group.|**Ad groups** : For example, you could test a particular audience in one ad group  before applying it to other ad groups.|
|You're using the same audience and bid for each ad group in your campaign.|**Campaigns** : You just need to set them up once, and don't have to create a new association each time you create a new ad group.|

## Create an association between an ad group/campaign and audience
1. Select **Audiences** under **Keywords and targeting** from the type list in the left panel.
1. In the data view, click **Add Audience Association**.
1. Click **Add ad group Audience Association** or **Add campaign Audience Association**.
1. Then select one or more ad groups/campaigns you want to associate the audiences with.
1. In the **Edit the selected Audience Associations** pane, enter the percentage you want to increase/decrease the bid amount for the remarketing list in the **Bid adjustment** box. You can increase the bid up to 900% and decrease by 90%.

> [!NOTE]
> Newly created audience associations inherit the targeting settings of the campaigns/ad groups they belong to. If they don’t belong to any campaigns or ad groups yet, they will be set to **Bid only** by default.

## Create an negative association between an ad group/campaign and audience
1. Select **Negative audiences** under **Keywords and targeting** from the type list in the left panel.
1. In the data view, click **Add Negative Audience Association**, and then click either **Add ad group Negative Audience Association** or **Add campaign Negative Audience Association**.
1. Then select one or more ad groups/campaigns you want to exclude the audiences with and click **OK**.
1. In **Choose audience**, select the audiences you want to exclude and click **OK**.

## How to adjust your audience targeting settings
1. In the tree view from the left panel, select the campaign in which you want to change the audience targeting setting.
1. Select **Ad groups** or **Campaigns** from the type list in the left panel.
1. In the **Edit the selected ad groups** pane, under the **Audience targeting** section, select **Target and bid**.

> [!NOTE]
> The targeting setting determines if an ad group/campaign must serve ads only to users in the associated audiences (Target and Bid option) or to all users (Bid only option).
> It is not logically possible for an ad group/campaign to be associated with one audience using the Target and Bid option and another using the Bid only option. Hence, the system enforces the same targeting setting across all the associations for a given ad group/campaign. This means if your ad group/campaign is associated with multiple types of audiences (remarketing and in-market), all of those audiences will have the same targeting setting.


