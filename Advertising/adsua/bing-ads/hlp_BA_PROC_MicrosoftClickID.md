---
title: Auto-tagging of Microsoft Click ID
description: When a customer clicks your ad, Microsoft Advertising automatically appends a unique click ID to the landing page URL when Auto-tagging of Microsoft Click ID is enabled.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Auto-tagging of Microsoft Click ID

When auto-tagging of Microsoft Click ID (MSCLKID) is enabled, Microsoft Advertising will automatically add a unique click ID to the landing page URL. This click ID will be included in all subsequent UET events fired whenever the same customer visits your page, thereby allowing you to track the conversion from this customer on your site.

> [!NOTE]
> As of December 11, 2017, Microsoft Advertising automatically enables auto-tagging of Microsoft Click ID when you create a new conversion goal. You may, however, have older conversions goals in which auto-tagging of Microsoft Click ID is not yet enabled. Below, you can learn the benefits of Microsoft Click ID and how to enable it if you haven’t already.

## Why should I enable auto-tagging of Microsoft Click ID?
Auto-tagging of Microsoft Click ID makes sure that no conversion tracking falls through the cracks. The [UET tag](./hlp_BA_CONC_UETv2WhatIsTag.md) on your website reports user activity, including the Microsoft cookie, to Microsoft Advertising. In some cases, the Microsoft cookie can't be returned due to browser settings (for example, third-party cookie blocking) or browser type. If you don't have auto-tagging of Microsoft Click ID enabled, these conversions aren't tracked.

[Learn more about the data UET collects](https://go.microsoft.com/fwlink?LinkId=867295)

## How do I enable auto-tagging of Microsoft Click ID?
In order to ensure that both URL tracking and conversion tracking are accurate, it's important to review your URL options and enable auto-tagging of Microsoft Click ID (MSCLKID).
1. In the left navigation pane, click **Shared Library** and then **Account level options** (or from the main menu on the left, click **All campaigns**, then **Settings**, and then **Account settings**).
1. Select the **Add Microsoft Click ID (MSCLKID) to URLs to allow conversion tracking** checkbox.
1. Click **Save**.


