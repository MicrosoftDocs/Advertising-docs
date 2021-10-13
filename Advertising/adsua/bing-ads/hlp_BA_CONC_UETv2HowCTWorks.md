---
title: How does conversion tracking work?
description: Find out how conversion tracking attributes credit for a conversion for one or more conversion goals.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# How does conversion tracking work?

With [conversion tracking](./hlp_BA_CONC_UETv2WhatIsCT.md), you can track what people do once they get to your website. First, you define the action you want to track as a [conversion goal](./hlp_BA_CONC_UETv2CTGoalType.md) (for example, sign up for a newsletter). Then, once someone visits your website and signs up, Microsoft Advertising can count it as a conversion. Before Microsoft Advertising can count the action as a conversion, it checks to see if the person clicked on your ad first.

Microsoft Advertising will not count any user activity as a conversion, even if it matches a conversion goal, unless it is able to find that the user clicked on an ad before completing the action. If the user clicked on more than one ad before completing the action on your website, the last ad clicked will be counted as the conversion and the other ad clicks will be counted as an assist to the conversion. This process of attributing the credit of one or more conversions to your ad campaigns, ad groups, and keywords is referred to as **conversion attribution**.

There are multiple models used when attributing conversions to ad clicks. These are referred to as **attribution models**. Microsoft Advertising uses the last ad click attribution, meaning if the someone clicks on multiple ads before doing the action your website, the last (most recent) click before the conversion gets credit for the conversion. Some of the other models include last click, first click, linear, time decay, etc.

> [!IMPORTANT]
> For conversion tracking to work, Microsoft Advertising needs to be able to collect data from your website. This requires [Universal Event Tracking (UET)](./hlp_BA_CONC_UETv2WhatIsTag.md).

## Configuring the conversion attribution process

Microsoft Advertising allows advertisers to configure the conversion attribution process using the following settings:

- **Conversion window** : A conversion window is the period of time after the user completed the action that Microsoft Advertising uses to record conversion data. You can set a conversion window, for each goal you define, to be any value ranging from 1 minute to 90 days. The default is 30 days. You can also change the conversion window as often as you like.
- **Counting option** : You have the flexibility to count conversions according to your business needs. When creating a goal, you can choose to count the following:
**All conversions** : Microsoft Advertising counts all conversions (per tracked goal) that happen after an ad click. This the default option and a good choice if the advertiser wants to track sales. If a user makes 3 purchases, Microsoft Advertising would count 3 conversions and attribute them to the ad click.

**Unique conversions** : Microsoft Advertising counts only unique conversions that happen after an ad click. This is a good choice if the advertiser is not interested in the number of sales, but instead whether or not a certain kind of lead was generated.

Note: If you change the counting option or conversion window setting, the change only applies to the conversion goal going forward and doesn't impact the conversion goal data before the change.

**Sharing** : You set if the goal applies to all accounts or a specific account. If you select all accounts, you won't be able to set the currency of the revenue value. The currency of the revenue value shown in reporting will be determined based on the account currency to which the conversion was attributed.

When attributing conversions to clicks for all accounts, Microsoft Advertising looks at user`s ad clicks across all the accounts under the manager account in order to find the ad click that is closest to the conversion. In most cases, this approach yields correct results because your ads lead the user to the same website. However, there are also instances where you set up multiple accounts with ads that lead users to different websites. In those cases, looking at ad clicks across accounts leads to incorrect attribution. As an example, if you had two accounts – A1 managing Website1 and A2 managing Website2, it is possible that conversions that happen on Website2 can be attributed to clicks coming from A1. Because of this, Microsoft Advertising allow you to optionally associate a goal to a specific account. When a goal is configured as account level, all conversions of its type will be attributed to clicks from that account only. Note that once selected, this property can't be changed.

**Revenue** : Not all conversions are equal. Some are worth more to your business than others. You can assign numeric values to their conversions, thereby see the total value driven by their advertising across different conversions, rather than simply the number of conversions that have happened. Revenue can be any value from 0 to 9999999 with 3 decimal fields and you can set the currency if sharing is set to a specific account. You have three revenue options when creating a goal:
1. Each time it happens, the conversion has the same revenue. This setting assigns a constant revenue value for every conversion for that goal.
1. The revenue of this conversion action may vary. You can customize their UET tag to report a different revenue value per conversion (for example, based on the product purchased). When choosing this option, you will need to specify a default value for the conversion if the variable revenue value is not defined at the time of the conversion.
1. Don't assign a revenue.

> [!NOTE]
> To see the complete list of currencies available for conversion goals, see [Conversion Goal Revenue Currencies](https://go.microsoft.com/fwlink?LinkId=834524). If the currency for the conversion is different from account currency, the revenue value will be converted to the account currency using the average daily foreign exchange rate.

## Conversion tracking FAQ

## What is UET and how do I set it up?
Take a look at [this article](./hlp_BA_CONC_UETv2WhatIsTag.md).
## What are conversion goals and why do I need to create them in addition to creating and installing the UET tag on my website?
Conversion goals and UET tags work together so you can track the actions people take on your website:

- **UET tags:** Record what customers do on your website (actions) and sends that information to Microsoft Advertising.
- **Conversion goals:** Define the actions you want to track as conversions in Microsoft Advertising.

So the UET tag gathers the information that the conversion goal uses to track conversions in Microsoft Advertising. To learn more, see [What is conversion tracking?](./hlp_BA_CONC_UETv2WhatIsCT.md)

## How does Microsoft Advertising count and attribute conversions? ​
Once you install the UET tag on your website, the tag reports user activity on your website to Microsoft Advertising. When a visitor performs an action that matches one of your conversion goals, the action will be counted as a conversion if we determine that the visitor clicked on your ad before performing the action. If the visitor clicked on more than one of your ads before converting on your website, then the closest ad click is credited with the conversion and the remaining ad clicks are said to have assisted the conversion.

## Does Microsoft Advertising detect fraudulent/duplicate conversions reported via UET?
Microsoft Advertising does not currently include any functionality to detect or eliminate test, fraudulent or duplicate conversions.

> [!NOTE]
> De-duplication/fraud detection should not to be confused with "Unique" conversions. Setting a conversion goal to report unique conversions basically tells Microsoft Advertising to count only 1 conversion of that goal type for an ad click. It does eliminate duplicates but does not detect fraudulent conversions. Further "Unique" conversions is not always a good choice for several goal types such as purchases.

## Why do I see discrepancy between Microsoft Advertising conversion counts and those from Google Analytics and Google Ads (or my own logs)?
There could be several reasons why conversions may not match. Keep in mind that Microsoft Advertising doesn't expose conversion data to any third-party platform, and each system uses its own logic and goal setup to track conversions. As such, some level of discrepancies are expected.

Why Microsoft Advertising may not be counting conversions

- Did you install the UET tag across your website (or at least on the conversion pages)?
- Did you verify that the  criteria you used in conversion goal definition matches the conversion pages? Spelling mistakes, incorrect page URL values etc in the goal definitions cause the UET events on those conversion pages to not match the conversion goal definition. When there is no match, conversions will not be counted.
- Do you have a reasonably sized conversion window? Small conversion windows should be used wisely since users generally spend a few days before making a purchase.
- If you are using Custom Event type goals or tracking Variable Revenue, are you actually customizing the UET tag to send in the custom events/variable revenues and are you using the correct values in the goal definition?
- Are you sure users are actually going to the conversion pages? If testing, note that Microsoft Advertising does not count a conversion unless the user clicks on an advertiser ad in Microsoft Advertising before converting on advertiser website.
- See **How can I validate my set-up of conversion tracking** below to validate conversion tracking is set up properly.

Why Microsoft Advertising may be overcounting

- Did you verify that there is no duplication of the UET tag installation on the site (specially on the conversion pages)? If you have install the same UET tag twice on conversion pages, conversions will be double counted.
- Did you verify that there are no duplicate goals? It is also possible that multiple goals match with the one user event thus increasing #conversions.
- Did you verify that the goal definitions are the same across all the platforms being compared? Are the conversion windows similar?
- Do you have test/fraudulent/duplicate conversions being generated on your site? Microsoft Advertising currently does not filter those out.
- Are you using the same counting method (Unique vs All) in your comparisons?
- Note that Microsoft Advertising includes any cross-device conversions that it is able to identify as part of the conversion count. Google Ads reports those via estimated conversion columns. Google Analytics has a custom solution for cross-device that most advertisers may not be using.
- When comparing with Google Analytics (GA), note that GA does cross-channel attribution which means that some of the conversions that Microsoft Advertising (or Google Ads) take credit for may be attributed to other channels by GA.

Why Microsoft Advertising may be undercounting

- Did you verify that UET tag is present across the site (or at least on the relevant conversion pages)?
- Did you verify that goal definitions are not too restrictive such that they don't count all conversions?
- Is your conversion window too small?
- Are you counting Unique conversions (and comparing to All conversion counts in Google Ads, etc.)?
- Note that if your users are converting directly or via other channels, Microsoft Advertising will not count conversions. They are reported in Google Analytics and Google Ads (if Google Ads determines conversion was caused by their ad click).

> [!NOTE]
> If you still have questions about the discrepancy, here is a checklist of things you need to verify:
> - [UTM auto-tagging](./hlp_BA_CONC_AutoTag.md) for [URL tracking](./hlp_BA_CONC_UpgradeURL_WhatIsTracking.md) is working properly
> - Same number of conversion goals are created and goal criteria are the exact same in both Microsoft Advertising and Google Ads/Google Analytics
> - Conversion goal criteria are the exact same in both Microsoft Advertising and Google Ads
> - Microsoft Advertising and Google Ads/Google Analytics tag associated with the conversion goal is added to the same pages of your website
> - Conversion window and counting (Unique vs. All) settings are exactly the same
> - Time zone for reporting is the same
> If you still want to contact support, you need to have the following information:
> - Tag name and the website pages you put the tags on for the conversion goals you are comparing
> - Goal name and criteria for the conversions goals you are comparing
> - Column names for the data you are comparing and where this information is located in the product
> - Report name for the reports you are comparing
> - Screenshot of the goal setting from Google Ads/Google Analytics

## How can I see conversion counts by goal name?
You can view aggregate conversion counts for each goal in the **Conversion goals** page. Further, you can run the Goals reports in Microsoft Advertising or using the API to segment that data by accounts, campaigns, ad groups, and keywords.

## How long before conversions show up in Reports?
Within 2 hours of UET conversions and 5 hours of non-UET conversions. For Mobile App Install type conversions that we track with the help of certified partners, please consult that partner you use for their SLA on reporting app install actions back to Microsoft Advertising. [Learn more](./hlp_BA_CONC_DataFreshness.md).

## How can I validate my setup of conversion tracking?
1. Create and add the UET tag to all pages of your website.
1. On the **UET tags** page, make sure the tag is **Tag active**.
1. On the **Conversion goals** page, create a conversion goal.
1. Trigger an ad on Bing, click the ad, and then convert on the site.
1. In three hours, revisit the **Conversion Goals** page to see that the goal is counting conversions.

## Are destination URL and custom event goals case sensitive?
No. When Microsoft Advertising matches UET logs with conversion goals to count conversions, it isn't case sensitive.


