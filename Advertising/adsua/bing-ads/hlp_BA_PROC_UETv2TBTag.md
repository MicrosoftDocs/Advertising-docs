---
title: Troubleshoot UET tag
description: You can troubleshoot the UET tag by using the tracking status in Microsoft Advertising or the UET Tag Helper browser extension.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Troubleshoot UET tag

If your UET tag has been on your webpage for more than 24 hours, you can review the UET tracking status in Microsoft Advertising to see if the tag is active or inactive and then you can use the UET Tag Helper to check to see if your UET tag is working or not.

Once you know that you have an issue with your UET tag, you can use UET Tag Helper to find out what the issue is and how to fix it. To learn more, see [Test conversion goals and audiences with UET Tag Helper](./hlp_BA_CONC_UET_TagHelper.md).

## Review UET tracking status column in Microsoft Advertising
1. In the left navigation pane, click **Conversion Tracking** and then **UET tags** (or from the global menu at the top of the page, click **Tools** and then **UET tags**).
1. Review the **Tracking status** column.
## Unverified
What it is: Microsoft Advertising has not received any user activity data from the UET tag on your website. It can take up to 24 hours for Microsoft Advertising to verify. If you still see this status, you either have not added the UET tag tracking code to your website or there is an issue with the setup that you need to fix.

What to do: Nothing

## Tag active
What it is: Microsoft Advertising has seen your UET tag, but haven't recorded any conversions in the last 7 days. This is most likely because you either have created the goal incorrectly, have not tagged your entire website, especially the pages that have the conversion action or you don't have any users converting on your site.

What to do: Nothing

## Tag inactive
What it is: Microsoft Advertising has not received any user activity data from the UET tag in the last 24 hours. Make sure that the UET tag tracking code is still on your website.

What to do: Validate with UET Tag Helper

**Limitations of tracking status column** : While we believe the tracking status will help you validate your setup, we do want to call out that the following cannot be verified from the tracking status column:

- Whether or not the UET tag has been installed across the site: Microsoft Advertising reports status of the UET tag as **Tag active** as long as at least one UET event was logged (from any part of your website).
- Whether or not custom events/variable revenue values are being reported: As explained above Microsoft Advertising does not distinguish between page load events (logged by default) or custom events reported when the tracking status column.

## Install and use the UET Tag Helper browser extension
UET Tag Helper is a browser extension that validates the implementation of the Microsoft Advertising UET tag on any given webpage. To learn how to install and use the UET Tag Helper to validate UET tags, see [Test conversion goals and audiences with UET Tag Helper](./hlp_BA_CONC_UET_TagHelper.md).


