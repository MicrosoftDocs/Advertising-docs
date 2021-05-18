---
title: Ways to use automated rules
description: Microsoft Advertising can save you time by automatically making changes to your campaigns based on criteria you define. These are called automated rules. Here are a few ways to use the rules to help with campaign management.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Ways to use automated rules

Microsoft Advertising can save you time by automatically making changes to your campaigns based on criteria you define. These are called automated rules. Here are a few ways to use the rules to help with campaign management (the settings provided are for example only — adjust yours as appropriate for your own campaign and advertising goals):

## Start and stop a campaign for a special event, such as New Year's Day
Want to display ads for a limited-time-only sale without getting up at midnight to enable that special-event campaign? You can enable the campaign through an automated rule. You can also create a second rule to stop the campaign at the end of the day.

Before creating the rules, you need to create your special-event campaign, complete with keywords and ads. Set that campaign to Paused. Once you've got your campaign ready, create the first rule to start the campaign and the second rule to pause it again at the end of the day:
1. From the main menu on the far left, click **All campaigns**.
1. From the page menu, click **Campaigns**.
1. Click **Automate** and select **Enable campaign when...**.
1. Set the following:
   - **Apply to: Selected campaigns**
   - **Do this: Enable campaign**
   - **How often: Once, January 1, 12 AM**

1. To create a second automated rule for your campaign, from the main menu on the far left, click **All campaigns**.
1. From the page menu, click **Campaigns**.

## Avoid costs on poor performing keywords or ads
Sometimes certain ads or keywords just don't work out. Maybe your ad is getting lots of impressions, but no clicks, or you're getting clicks but no conversions. That's costing you money you don't need to spend. Here's an example of how you can pause ads based on performance criteria.
1. From the main menu on the far left, click **All campaigns**.
1. From the page menu, click **Ads and extensions**.
1. Click **Automate** and select **Pause ads when...**.
1. Set the following:
   - **Apply to: All enabled ads in all campaigns**
   - **Do this: Pause ad**
   - **                  When: CTR &gt; 2%                **
   - **                  (Add another) When: Conversions &lt; 2%                **
   - **How often: Daily, 7 AM, using data from Previous day**
   - **Email results: Only if there are changes or errors**

## Keep your ads on the first page
If you've got some keywords and ads that are performing well and want to make sure they are consistently seen by as many searchers as possible, try this:
1. From the main menu on the far left, click **All campaigns**.
1. From the page menu, click **Keywords**.
1. Click **Automate** and select **Increase to estimated top of page bid when...**.
1. Set the following:
   - **Apply to: All enabled ads in all campaigns**
   - **Do this: Increase to estimated top of page bid**
   - Optional: Check **max bid** and enter a maximum bid you are comfortable with.
   - **                  When: Avg. pos. &gt; 4                **
   - **How often: Daily, 7 AM, using data from Previous day**
   - **Email results: Only if there are changes or errors**

## Avoid letting your budget stop your best performing campaigns
It's your best-performing campaign: Clicks are high and so are conversions.  Then suddenly all the clicks stop. What happened? It might be as simple as running out of budget. Now you're losing customers because your ads have stopped displaying. You can automatically increase your budget for that star campaign.
1. From the main menu on the far left, click **All campaigns**.
1. From the page menu, click **Campaigns**.
1. Click **Automate** and select **Change budget when...**.
1. Set the following:
   - **Apply to: All campaigns**
   - **Do this: Increase daily budget by 10%**
   - Optional: Check **max budget** and enter a maximum budget you are comfortable with.
   - **                  When: CTR &gt; 2%                **
   - **                  (Add another) When: Conversions &gt; 3%                **
   - **How often: Daily, 7 AM, using data from Previous week**
   - **Email results: Only if there are changes or errors**

> [!NOTE]
> Keyword bid automated rules and [bid adjustments](./hlp_BA_CONC_AboutAdvancedBidding.md) work independently of each other. If the criteria for both are met on a keyword bid, then both will be applied.
> If the author of an automated rule deletes his/her account, the automated rule will stop running.

## Notify me when

You can also set an automated rule to notify you by email -- but not to make any changes -- when certain criteria are met.

1. From the Campaigns, Ad Groups, Ads, or Keywords tab, click **Automate** and then **Notify me when** (or from the main menu on the left, click **All campaigns** and select either **Campaigns**, **Ad groups**, or **Keywords**. Then click **Automate**).
1. Create a rule as outlined above.
1. Click **Save**

When the criteria are met, we will send you an email notifying you. You can edit, pause, or delete this rule the same as any other rule (see [this article](./hlp_BA_PROC_AutoRuleManage.md) for more information).

> [!NOTE]
> These emails will only be sent to the author of the rule. If more than one person with access to the same campaign wishes to receive the same notification, each person will need to create his/her own rule.


