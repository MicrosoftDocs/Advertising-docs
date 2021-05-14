---
title: Why track variable revenue
description: Find out the benefit of tracking revenue value with each conversion goal.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Why track variable revenue

When creating a goal, you can specify a revenue value to be associated with each conversion for that goal.   ![Conversion tracking menu](../images/BA_ScreenCap_ConvTrack_Revenue.png)

Revenue can be any value from 0 to 999999999999 with 3 decimal fields, and can be defined as any supported currency. To see the complete list of currencies available for conversion goals, see [Conversion Goal Revenue Currencies](https://go.microsoft.com/fwlink?LinkId=834524). If the currency for the revenue value is different from the account currency—and your UET  the revenue value will be converted to the account currency using the average daily foreign exchange rate.

When you choose to report revenue, you can either associate a fixed revenue for each conversion or report revenue for each conversion when it happens. In order to report variable revenue, you must make sure that you choose the "The revenue of this conversion action may vary" option for revenue setting.

At this point, you can also specify a default value and default currency to be assigned to the conversion if no revenue is reported at conversion time. Note that these defaults will be used for each conversion if you do not also modify your UET tag tracking code to pass back both a revenue value and a currency. For more information on modifying your UET tag tracking code for variable revenue reporting, see [How to report variable revenue with UET](./hlp_BA_CONC_UETv2RevenueVariables.md).

> [!NOTE]
> Variable revenue is only applicable for Destination URL and Custom Event type goals.


