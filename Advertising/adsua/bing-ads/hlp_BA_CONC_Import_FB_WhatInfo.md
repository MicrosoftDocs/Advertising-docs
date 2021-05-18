---
title: What gets imported from Facebook Ads
description: Most of the information in your campaigns is included when you import it from Facebook Ads. Here's a list of what gets imported, as well as some exceptions.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# What gets imported from Facebook Ads

[!INCLUDE [ComingSoon](./includes/ComingSoon.md)]
Before proceeding to [Import campaigns directly from Facebook Ads](./hlp_BA_PROC_Import_FB_Campaign.md), make sure to review the details below.

Not all information will be imported from Facebook Ads, and that doesn’t mean it’s not supported within Microsoft Advertising. Some specific situations require special attention during import.

After you’ve imported your campaigns from Facebook Ads, you can check the status of your import, review error logs, and edit, pause, or delete your import schedule. You should also make sure the campaigns were imported as expected, add then make updates as needed. To learn more, see [Edit your scheduled imports and review import history and results](./hlp_BA_CONC_ImportScheduleHistory.md).

## Campaigns

Facebook Ads campaigns will be imported to Microsoft Advertising as audience campaigns.

We will import Active, Paused, Deleted, and Archived Facebook Ads campaigns. If the Facebook Ads campaign status is Archived, we will pause the imported campaign.
## Campaign name

Each Microsoft Advertising campaign can contain up to 128 characters while Facebook Ads campaign names can be longer.

If the campaign name is longer than 128 characters, we will truncate the name and follow the below naming pattern.  Each Facebook Ads campaign name will be imported as “{Facebook campaign name inserted here} + Delimiter (hyphen) + FB + {Facebook campaign ID inserted here}”.

For example, if the original campaign name is “Subscribe and Save. Buy X, Get Y at 20% discount” and campaign ID is 2345678910. Then the imported campaign name will be saved in Microsoft Advertising as “Subscribe and Save. Buy X, Get Y - FB2345678910”.

## Ad group name

Facebook Ads ad-sets are imported as Microsoft Advertising ad groups.

After import, the Microsoft Advertising ad group name will use the same pattern of delimiters as the imported campaign name.  Each Facebook Ads ad-set name will be imported as “{Facebook ad-set Name inserted here} + Delimiter (hyphen) + FB + {Facebook ad-set ID inserted here}”.

For example, if the original ad-set name is “Subscribe and Save. Buy X, Get Y at 20% discount” and ad-set ID is 2345678910. Then the imported ad-set name will be saved in Microsoft Advertising as “Subscribe and Save. Buy X, Get Y - FB2345678910”.

## Ads

We will import single image format ads. Other Facebook Ads ad formats like carousel and videos won’t be imported.  Ads without a website URL will not be imported.

Facebook Ads ad names will not be imported, since Microsoft Advertising does not have ad names.

## Budgets

Facebook Ads supports campaign and ad-set (ad group) level budgets, but Microsoft Advertising does not support ad group level budgets.

Daily budget if available will transfer as-is at the campaign level.

If the Facebook Ads lifetime budget is used with start and stop dates, the daily budget will be calculated with a proration to the number of days. Campaigns won’t be imported if the budget remaining is zero.

Campaigns with shared budgets won’t be imported.

## Schedule

If the Facebook Ads campaigns have a start time and end time, Microsoft Advertising will import them.

If the end time is in the past, the campaigns will be imported as paused.

If the start time is in the past, the start date will be set to the import date.

## Bids and bid strategy

Facebook Ads supports auto bidding strategies such as lowest cost without cap, lowest cost with bid cap, target cost, cost cap, etc.

If the Facebook Ads bid strategy is not supported in Microsoft Advertising, we will set the imported campaign's bid strategy to Manual CPC.

Bid amounts are imported when available. If a bid is not available for example, lowest cost without cap, a default bid of $1 will be set.

## Location targeting

We will import locations from Facebook Ads that are also supported in Microsoft Advertising.   If none of the imported location targets are supported by Microsoft Advertising, the campaign or ad group will be paused.

## Age targeting

Facebook Ads uses min and max age while Microsoft Advertising has predefined ranges. Import will use the FB age range and map to the MSA ranges. For example, if the age range is 18-40 in Facebook Ads, import will set the target age ranges to 18-24, 25-34, 35-49 in Microsoft Advertising.

## Gender targeting

Gender will be mapped correspondingly as male and female. If **All** is selected in Facebook Ads, the import will map to both male and female in Microsoft Advertising.

## Other targeting

Facebook Ads language and connections targets will not be imported.


