---
title: Why do I see discrepancy between Microsoft Advertising conversion counts and those from Google Analytics and Google Ads (or my own logs)?
description: Find out why you may see discrepancies between Microsoft Advertising and Google Ads/Google Analytics conversion counts.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Why do I see discrepancy between Microsoft Advertising conversion counts and those from Google Analytics and Google Ads (or my own logs)?

There could be several reasons why conversions may not match. Keep in mind that Microsoft Advertising doesn't expose conversion data to any third-party platform, and each system uses its own logic and goal setup to track conversions. Microsoft Advertising reports conversions on the date of the **ad click**, whereas some other reporting tools attribute them to the date of the **conversion**. As such, some level of discrepancies are expected.

## Why Microsoft Advertising may not be counting conversions

Here are some things to consider:

- Did you install the UET tag across your website (or at least on the conversion pages)?
- Did you verify that the criteria you used in conversion goal definition matches the conversion pages? Spelling mistakes, incorrect page URL values etc. in the goal definitions cause the UET events on those conversion pages to not match the conversion goal definition. When there is no match, conversions will not be counted.
- Do you have a reasonably sized conversion window? Small conversion windows should be used wisely since users generally spend a few days before making a purchase.
- If you are using Custom Event type goals or tracking Variable Revenue, are you actually customizing the UET tag to send in the custom events/variable revenues and are you using the correct values in the goal definition?
- Are you sure users are actually going to the conversion pages? If testing, note that Microsoft Advertising does not count a conversion unless a user clicks on an advertiser ad before converting on advertiser website.
- See **How can I validate my set-up of conversion tracking** below to validate conversion tracking is set up properly.

## Why Microsoft Advertising may be over-counting

- Did you verify that there is no duplication of the UET tag installation on the site (specially on the conversion pages)? If you have install the same UET tag twice on conversion pages, conversions will be double counted.
- Did you verify that there are no duplicate goals? It is also possible that multiple goals match with the one user event thus increasing #conversions.
- Did you verify that the goal definitions are the same across all the platforms being compared? Are the conversion windows similar?
- Do you have test/fraudulent/duplicate conversions being generated on your site? Microsoft Advertising does currently does not filter those out.
- Are you using the same counting method (Unique vs All) in your comparisons?
- Note that Microsoft Advertising includes any cross-device conversions that it is able to identify as part of the conversion count. Google Ads reports those via estimated conversion columns. Google Analytics has a custom solution for cross-device that most advertisers may not be using.
- When comparing, note that Google Analytics does cross-channel attribution which means that some of the conversions that Microsoft Advertising (or Google Ads) take credit for may be attributed to other channels by Google Analytics.

## Why Microsoft Advertising may be under-counting

- Did you verify that UET tag is present across the site (or at least on the relevant conversion pages)?
- Did you verify that goal definitions are not too restrictive such that they don't count all conversions?
- Is your conversion window too small?
- Are you counting Unique conversions (and comparing to All conversion counts in Google Ads etc)?
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


