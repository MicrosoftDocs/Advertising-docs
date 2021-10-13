---
title: Set up UET tags using BigCommerce
description: If you built your website on BigCommerce, read this article to learn how to set up UET tags on it.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Set up UET tags using BigCommerce

> [!NOTE]
> This article shows how to do a basic setup of UET tags using BigCommerce. Please refer to [BigCommerce Support](https://go.microsoft.com/fwlink?LinkId=2010484) for more information.
> Microsoft Advertising is not responsible for BigCommerce's processes or documentation, nor for changes made to BigCommerce's processes or documentation.

If you created and manage your website with BigCommerce, you can add and manage your UET tag there.

## Implementing UET using BigCommerce

1. In Microsoft Advertising, go to **Conversion Tracking**&nbsp;&gt;&nbsp;**UET tags** and copy your JavaScript UET tag tracking code.
1. Log in to your BigCommerce account.
1. From your BigCommerce dashboard, go to **Storefront**&nbsp;&gt;&nbsp;**Footer Scripts**.
1. Paste the Microsoft Advertising UET tracking code into the script box and click **Save**.

If you want to track completed purchases as conversions and report variable revenue, please refer to BigCommerce’s support page to learn how to set up the goals and track the conversions. Here's an example:

1. From your BigCommerce dashboard, go to **Advanced Settings**&nbsp;&gt;&nbsp;**Affiliate Conversion Tracking**.
1. Paste in your UET tracking code and then append the following code to the end of the UET tracking code:
```
<window.uetq = window.uetq || [];window.uetq.push({ 'revenue_value': '%%ORDER_AMOUNT%%'});>
```

1. Click **Save** to finish.

> [!NOTE]
> To validate that your BigCommerce UET tag is working, download and install [UET Tag Helper](./hlp_BA_CONC_UET_TagHelper.md). Go to your BigCommerce website and verify that a UET event is received and that the **Tag ID** matches the tag you selected in Step 1 (or defined in step 7).


