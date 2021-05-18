---
title: Let Microsoft Advertising manage your bids with bid strategies
description: Learn how Microsoft Advertising can handle bidding for you using bid strategies such as Enhanced CPC, Maximize Clicks, Maximize Conversions, and Target CPA.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Let Microsoft Advertising manage your bids with bid strategies

With bid strategies, you can have Microsoft Advertising manage your bids using our deep analysis of patterns in searches, clicks, and conversions. We can make sure you're bidding effectively, automatically. Whichever bid strategy you use, Microsoft Advertising will always respect your budget limit.

## How would you like Microsoft Advertising to manage your bids?

## Enhanced CPC
> [!IMPORTANT]
> Enhanced CPC is available:
> - For search ad and dynamic search ad campaigns worldwide.
> - For Microsoft Shopping Campaigns wherever Microsoft Shopping Campaigns are available.

Enhanced CPC (cost per click) is the default bid strategy setting when you create a new campaign. With Enhanced CPC, you set your ad group and keyword bids, and Microsoft Advertising automatically adjusts your bids in real time to increase your chances for a conversion. Your bid will go higher on searches that are more likely to convert and lower on searches less likely to convert (up or down, this change will be made after we apply any bid adjustments you have set). Over the long haul, though, we will try to make sure that your average CPC is not higher than your bid.

If you haven't optimized your campaign yet, Enhanced CPC should reduce your cost per conversion and increase your total conversion count while respecting your current budget.

> [!NOTE]
> For the best results, we strongly recommend using Enhanced CPC in conjunction with [conversion tracking](./hlp_BA_CONC_UETv2WhatIsCT.md) (a UET tag and a conversion goal).
> Enhanced CPC will not break third-party bid management tools. Enhanced CPC will always use the bids set by your bid management tool as a starting point before applying any adjustment.

## Manual CPC
With the Manual CPC bid strategy, Microsoft Advertising uses these bids every time.
## Maximize Clicks
> [!IMPORTANT]
> Maximize Clicks is available only for search ad, dynamic search ad, and Microsoft Shopping Campaigns.

With Maximize Clicks, Microsoft Advertising automatically sets your bids in real time to get as many clicks as possible within your budget.

Microsoft Advertising will always respect your overall budget limit, but if you want greater control over your bids while using Maximize Clicks, you can also set a maximum CPC (cost per click). This is an optional limit you can set to make sure that Microsoft Advertising never charges more than a certain amount for each individual click.

You cannot change bids for keywords that are using Maximize Clicks. This means that automated rules and third-party bid management tools will **not** affect these keywords. With Maximize Clicks, Microsoft Advertising will have full and final control over optimizing your bids. That said, any bid adjustments you have set (or that you set in the future) can be used to inform your Maximize Clicks automated bids. Note that bid adjustments may cause your bid to go higher than your maximum CPC, if you have one set.

> [!NOTE]
> [!INCLUDE [AutoBidOverride](./includes/AutoBidOverride.md)]

## Maximize Conversions
With Maximize Conversions, Microsoft Advertising automatically sets your bids in real time to get as many conversions as possible within your budget.

Microsoft Advertising will always respect your overall budget limit, but if you want greater control over your bids while using Maximize Conversions, you can also set a maximum CPC (cost per click). This is an optional limit you can set to make sure that Microsoft Advertising never charges more than a certain amount for each individual click.

You need to have [conversion tracking](./hlp_BA_CONC_UETv2WhatIsCT.md) (either a UET tag + an active conversion goal, or offline conversions) set up in order to use the Maximize Conversions bid strategy. We recommend giving the bid strategy enough time to accumulate at least 30 conversions before evaluating its performance.

You cannot change bids for keywords that are using Maximize Conversions. This means that automated rules and third-party bid management tools will **not** affect these keywords. With Maximize Conversions, Microsoft Advertising will have full and final control over optimizing your bids. That said, any bid adjustments you have set (or that you set in the future) can be used to inform your Maximize Conversions automated bids. Note that bid adjustments may cause your bid to go higher than your maximum CPC, if you have one set.

> [!NOTE]
> [!INCLUDE [AutoBidOverride](./includes/AutoBidOverride.md)]
> [!INCLUDE [SharedBudgetException](./includes/SharedBudgetException.md)]

## Target CPA
With Target CPA (cost per acquisition), you set your budget and your target 30-day average CPA, and Microsoft Advertising automatically sets your bids in real time to get you to this average. Some conversions may cost more than your target and some may cost less, but Microsoft Advertising will try to make sure your average cost per conversion is in line with your target.

Microsoft Advertising will always respect your overall budget limit, but if you want greater control over your bids while using Target CPA, you can also set a maximum CPC (cost per click). This is an optional limit you can set to make sure that Microsoft Advertising never charges more than a certain amount for each individual click.

You need to have [conversion tracking](./hlp_BA_CONC_UETv2WhatIsCT.md) (either a UET tag + an active conversion goal, or offline conversions) set up in order to use the Target CPA bid strategy. We recommend giving the bid strategy enough time to accumulate at least 30 conversions before evaluating its performance.

You cannot change bids for keywords that are using Target CPA. This means that automated rules and third-party bid management tools will **not** affect these keywords. With Target CPA, Microsoft Advertising will have full and final control over optimizing your bids. That said, any bid adjustments you have set (or that you set in the future) can be used to inform your Target CPA automated bids (while still striving to achieve your Target CPA). Note that bid adjustments may cause your bid to go higher than your maximum CPC, if you have one set.

> [!NOTE]
> Target CPA is a campaign-level target. Individual ad groups may have different CPAs, and those CPAs may vary over time, while the campaign target CPA is met. Different devices may see different CPAs as well.
> [!INCLUDE [AutoBidOverride](./includes/AutoBidOverride.md)]
> [!INCLUDE [SharedBudgetException](./includes/SharedBudgetException.md)]

## Target impression share
With Target impression share, you set your budget, where you want ads to appear, and your target impression share, and Microsoft Advertising automatically sets your bids.

Microsoft Advertising will always respect your overall budget limit, but if you want greater control over your bids while using Target impression share, you can also set a maximum CPC (cost per click). This is an optional limit you can set to make sure that Microsoft Advertising never charges more than a certain amount for each individual click.

## Target ROAS
With Target ROAS (return on ad spend), you set your budget and your target 30-day average ROAS, and Microsoft Advertising automatically sets your bids in real time to get you to this average.

Microsoft Advertising will always respect your overall budget limit, but if you want greater control over your bids while using Target ROAS, you can also set a maximum CPC (cost per click). This is an optional limit you can set to make sure that Microsoft Advertising never charges more than a certain amount for each individual click.

You need to have [conversion tracking](./hlp_BA_CONC_UETv2WhatIsCT.md) (either a UET tag + an active conversion goal, or offline conversions) set up and have positive revenue tracked in order to use the Target ROAS bid strategy. We recommend giving the bid strategy enough time to accumulate at least 50 conversions before evaluating its performance.

You cannot change bids for keywords that are using Target ROAS. This means that automated rules and third-party bid management tools will **not** affect these keywords. With Target ROAS, Microsoft Advertising will have full and final control over optimizing your bids. That said, any bid adjustments you have set (or that you set in the future) can be used to inform your Target ROAS automated bids (while still striving to achieve your Target ROAS). Note that bid adjustments may cause your bid to go higher than your maximum CPC, if you have one set.

> [!NOTE]
> Target ROAS is a campaign-level target. Individual ad groups may have different ROAS values, and those ROAS values may vary over time, while the campaign target ROAS is met. Different devices may see different ROAS values as well.
> [!INCLUDE [AutoBidOverride](./includes/AutoBidOverride.md)]
> [!INCLUDE [SharedBudgetException](./includes/SharedBudgetException.md)]

 
## Comparing bid strategies

|Bid strategy|Do I set bids myself?|Can I use a third-party bid management tool?|Do I need conversion tracking?|Campaign type supported|
|---|---|---|---|---|
|Enhanced CPC|![Yes](../images/Global_Icon_CheckMark.png)|![Yes](../images/Global_Icon_CheckMark.png)|![No](../images/Global_Icon_Xmark.png)|Search, dynamic search ad, shopping|
|Manual|![Yes](../images/Global_Icon_CheckMark.png)|![Yes](../images/Global_Icon_CheckMark.png)|![No](../images/Global_Icon_Xmark.png)|Audience|
|Maximize Clicks|![No](../images/Global_Icon_Xmark.png)|![No](../images/Global_Icon_Xmark.png)|![No](../images/Global_Icon_Xmark.png)|Search, dynamic search ad, shopping|
|Maximize Conversions|![No](../images/Global_Icon_Xmark.png)|![No](../images/Global_Icon_Xmark.png)|![Yes](../images/Global_Icon_CheckMark.png)|Search, dynamic search ad|
|Target CPA|![No](../images/Global_Icon_Xmark.png)|![No](../images/Global_Icon_Xmark.png)|![Yes](../images/Global_Icon_CheckMark.png)|Search, dynamic search ad|
|Target impression share|![No](../images/Global_Icon_Xmark.png)|![No](../images/Global_Icon_Xmark.png)|![No](../images/Global_Icon_Xmark.png)|Search, dynamic search ad|
|Target ROAS|![No](../images/Global_Icon_Xmark.png)|![No](../images/Global_Icon_Xmark.png)|![Yes](../images/Global_Icon_CheckMark.png)|Search, dynamic search ad, shopping|

 
## Share a portfolio bid strategy with other campaigns

Portfolio bid strategy manages bidding across multiple campaigns that are all working toward the same goal. A campaign can either have its own bid strategy or it can share a portfolio bid strategy with other campaigns.

In a portfolio bid strategy we automatically adjust your bids to balance under- and over-performing campaigns that share the same strategy, whether to maximize conversions, clicks, target impression share, or other performance goals. Portfolio bid strategies could be a great option for advertisers who want to make sure their entire budgets are spent efficiently.

Learn more: [Portfolio bid strategies: Auto-bidding for performance goals](./hlp_BA_CONC_BidStrategy_Portfolio.md)

## Working with bid strategies

## Setting a campaign's bid strategy
You can set the bid strategy at the campaign level. To change a campaign's bid strategy:

1. [!INCLUDE [AllCampaignsOverview](./includes/AllCampaignsOverview.md)]
1. In the table, select the name of the campaign you want to edit.
1. From the menu on the left, select **Settings**.
1. [!INCLUDE [CampaignSettingsBidStrat](./includes/CampaignSettingsBidStrat.md)]
1. [!INCLUDE [SelectSave](./includes/SelectSave.md)]

> [!NOTE]
> Your bids will start changing automatically within two hours of turning on a bid strategy. However, a bid strategy needs to run for about two weeks to build up enough data to bid optimally. Changing your bid strategy setting, campaign budget, or conversion settings — or adding or removing ad groups or keywords — will restart this learning period.

## Tips for using Maximize Clicks with Microsoft Shopping Campaigns
- Shopping campaigns that use Maximize Clicks should be kept at the highest priority.
- Avoid creating overlapping product offers in multiple shopping campaigns that use Maximize Clicks.

## Best practices for Maximize Conversions and Target CPA
- **Requirements** : In order to turn on Maximize Conversions or Target CPA, your campaign:
   - Must have [conversion tracking](./hlp_BA_CONC_UETv2WhatIsCT.md) (either a UET tag + an active conversion goal, or offline conversions) set up. We recommend giving the bid strategy enough time to accumulate at least 30 conversions before evaluating its performance.
   - Cannot use a shared budget, except within a [portfolio bid strategy](./hlp_BA_CONC_BidStrategy_Portfolio.md).

- **How to make sure Maximize Conversions and Target CPA work optimally** : Maximize Conversions and Target CPA need time to work. For best results, keep this timeline in mind:
1. **Getting set up: 30 days** &nbsp;— We recommend having at least 30 conversions in the previous 30 days. When setting up Target CPA, we suggest basing your target on your actual CPA from the previous 30 days. For new campaigns, we suggest basing your target on your account's performance.
1. **Learning period: 1-2 weeks** &nbsp;—  Our platform usually needs two weeks to acquaint itself with your campaign. Avoid changing budgets or conversion goals during this period, as this may cause the learning period to start over. We recommend **not** evaluating the bid strategy's performance based on these two weeks.
1. **Run campaign: 2-4 weeks** &nbsp;— Let your campaign run for two to four weeks after the learning period (avoiding changing budgets or conversion goals, as this may cause the learning period to start over) and then start evaluating the bid strategy's performance. Keep your conversion goal window in mind while evaluating performance.
1. **Evaluate and adjust: Going forward** &nbsp;— Review the campaign's performance since the learning period in aggregate and make adjustments as needed. For Target CPA, we recommend keeping adjustments within 20%, up or down.

- **Timing of conversions** :	When conversions occur more than seven days after the associated clicks, it's harder for Maximize Conversions and Target CPA to make effective bids. If most of your conversions occur more than seven days after the associated clicks, we recommend not using Maximize Conversions or Target CPA.
- **Offline conversions** : If you don't or can't upload offline conversions on a daily basis, we recommend not using Maximize Conversions or Target CPA.	For best results, upload offline conversions within two days of the conversion.
- **Audience Ads** : Turning on any conversion-based bid strategy, such as Maximize Conversions, Target CPA, or Target ROAS, will make your search ads ineligible to be turned into [Microsoft Audience Ads](./hlp_BA_CONC_NativeAds.md).

 
> [!NOTE]
> Want expert advice on your ads? [Schedule a no-cost session with a personal Microsoft Advertising consultant](https://go.microsoft.com/fwlink?LinkId=837456)


