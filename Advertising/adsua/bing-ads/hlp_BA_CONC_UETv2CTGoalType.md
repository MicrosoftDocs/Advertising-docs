---
title: What are conversion goals and goal types?
description: Learn about the types of conversion goals that you can create to track different types of conversions.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# What are conversion goals and goal types?

One of the biggest value propositions of [conversion tracking](./hlp_BA_CONC_UETv2WhatIsCT.md) with UET is that the UET tag on your website can track multiple types of conversions.   Once the UET tag tracking code is added to your website, Microsoft Advertising can log page visits and any custom events (such as document downloads, signups for a newsletter, etc.).

However, not all actions are created equal. You probably have a subset of actions that you consider more important to a successful advertising campaigns.   These may include making purchases, filling out a lead form, or watching a video. This is where conversion goals can help. Conversion goals allow you to   specify which actions (as recorded by UET) to count as conversions.

The types of conversion goals are:

## Destination URL
Count user visits to specific webpages as conversions.

Examples: Confirmation page after purchase, Thank you page after lead generation.

## Duration
Count every time someone stays on a website for longer than a certain amount of time as a conversion.

Example: 10 minutes or longer spent on a blog or playing a game on the webpage.

## Pages viewed per visit
Count every time someone visits more than a specified number of pages on your website as a conversion.

Example: 5 pages viewed on a support site or product catalog.

## Events
Count every time someone completes a specific action, such as signing up for a newsletter or downloading a document, as a conversion.

To set this up, you must customize your UET tag tracking code to report the values for one or more of the custom event parameters **in addition to** creating conversion goals in Microsoft Advertising to track those events. To learn more, see [How to track custom events with UET](./hlp_BA_CONC_UETv2CustomEvent.md).

Examples: Downloading a document, watching a video, signing up for a newsletter.

## Mobile app install
Count every time someone installs your app as a conversion. To learn more, see [Track mobile app installs as conversions](./hlp_BA_PROC_UETv2MobileApp.md).

Example: Installation of your app on Android devices.

## Offline conversions
Track when your ad leads to a conversion outside of your website. To learn more, see [Tracking offline conversions](./hlp_BA_CONC_UETv2OfflineConversion.md).

Example: A search ad leads to an over-the-phone purchase.

 
## Next steps

- [Create a conversion goal](./hlp_BA_PROC_UETv2CreateGoal.md)
- [Set up UET](./hlp_BA_CONC_UET_Setup_Master.md)


