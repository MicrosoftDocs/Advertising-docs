---
title: How does the account time zone impact data?
description: Learn about your account, campaign and reports time zone and how they impact data.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# How does the account time zone impact data?

When you create your Microsoft Advertising account, you set your account time zone. Most people select the time zone of their business location.

## Where do I find the time zone?

After you've created a Microsoft Advertising account, you can find your time zone on the Account settings page. To learn more, see [Billing Summary in depth](./hlp_BA_CONC_BillingTab.md).

![Account settings with time zone highlighted](../images/BA_ScreenCap_AccountTimeZone.png)
When you create your Microsoft Advertising account, you set your account time zone. Most people select the time zone of their business location. We encourage you to pick your time zone carefully so that your campaign and reporting data always remain consistent.

## What does the account time zone impact?

The account time zone affects the Campaigns page date range and the default time zone for your reports.

**Date range**

The date range you select in the upper-right corner of the Campaigns page is based on the account time zone.

![Campaigns page with date range highlighted](../images/BA_ScreenCap_DateRange.png)
**Reports**

The account time zone is also the time zone selected when you create a report. You can change the report time zone if you want to scope your data   differently and the change only applies to that report.

![Reports page showing time zone](../images/BA_ScreenCap_ReportTimeZone.png)
## Time zones in reporting

When you create a report request, specify the date range time period based on the time zone of the campaign. The report data is stored in the time zone of the campaign. For example, if the time zone of the campaign is Pacific Time and a click occurs at 12:00 PM Eastern Time, the time of the click is recorded as 9:00 AM. If you request a report for the campaign using hourly aggregation, the report data will include a click that occurred at 9:00 AM (the report data is not adjusted based on the local time zone of your campaign).

## Changing your account time zone

It is possible to switch to a different time zone, but you should understand the impacts when you make that update. See [Changing your account time zone](./hlp_BA_CONC_ChangeTimeZone.md) for more details.

> [!NOTE]
> Time zones only impact data and don't affect the locations where your ad may show. To learn more, see [How can I get my ads in front of my customers?](./hlp_BA_CONC_Targeting.md)


