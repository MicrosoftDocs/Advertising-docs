---
title: What's my audience targeting status?
description: Learn how to check the status of your audience targeting and what the statuses mean.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# What's my audience targeting status?

You can check the status of your audience targeting in the **Audiences** table:

1. In the left pane, click **Shared Library** and then **Audiences** (or from the global menu at the top of the page, click **Tools** and then **Audiences**).
1. Check the **Audience status** column.

## Possible audience statuses

- **Ready**: No issues—audience targeting is working fine.
- **Missing tag on your website**: Microsoft Advertising hasn't received any user activity data from the UET tag on your website. It can take up to 24 hours for Microsoft Advertising to verify a new tag. After that point, if you see this status, you either have not added the UET tag tracking code to your website or there is an issue with the setup that you need to fix.
- **No activity in the past 24 hrs**:  Microsoft Advertising hasn't received any user activity data from the UET tag in the last 24 hours. Make sure that the UET tag tracking code is still on your website.
- **Missing custom events on the tag**: Microsoft Advertising hasn't received any custom event data required for this audience. Make sure that you have updated your UET tag tracking code correctly to report back custom event parameters.
- **Building the audience**: It takes 24 hours for an audience to be built after you create a new audience or update an existing audience.
- **Audience too small**: The number of people in this audience doesn't meet the minimum number of users required for this audience to be eligible to serve on either the search or audience network. Make sure your list definition is accurate and not too narrow.
- **Ready for search campaigns, but too small for audience campaigns**: This audience is eligible to serve on the search network but not on the Microsoft Audience Network.
- **Ready for audience campaigns, but too small for search campaigns**: This audience is eligible to serve on the Microsoft Audience Network but not on the search network.
- **Recalculating audience size**: You have edited your audience, and Microsoft Advertising is in the process of determining its size. This process can take 24 hours.
- **Possible UET tag issue**: There are zero people in your dynamic remarketing list, so it's likely that there is a problem with your UET tag. We recommend you make sure that:
   - You have modified your UET tag on all pages of your website for this dynamic remarketing list.
   - Your modified UET tag refers to the correct page type and product ID.
   - The product ID referred to in your UET tag matches an ID in your Microsoft Merchant Center store.

- [Learn more about dynamic remarketing lists and modifying your UET tag](./hlp_BA_CONC_Audiences_ProductAudience.md).
- **The tag is no longer available**: The account no longer has access to the UET tag.
   - Permissions to a UET tag in another manager account may have been removed.
   - This account may have had access to a UET tag under a previous manager account before it was transferred to its current manager account.

- **Missing component audience**: The account no longer has access to an audience that had been used in the combined list.
   - Permissions to an audience in another manager account may have been removed.
   - This account may have had access to an audience under a previous manager account before it was transferred to its current manager account.

> [!NOTE]
> [Learn more about your audience targeting options](./hlp_BA_CONC_Audiences_Options.md).


