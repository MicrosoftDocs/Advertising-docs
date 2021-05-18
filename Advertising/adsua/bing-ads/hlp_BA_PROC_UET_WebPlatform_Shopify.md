---
title: Set up UET tags using Shopify
description: If you built your website on Shopify, read this article to learn how to set up UET tags on it.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Set up UET tags using Shopify

> [!NOTE]
> This article shows how to do a basic setup of UET tags using Shopify. Please refer to the [Shopify Help Center](https://go.microsoft.com/fwlink?LinkId=2010843) for more information.
> Microsoft Advertising is not responsible for Shopify's processes or documentation, nor for changes made to Shopify's processes or documentation.
> By installing the Microsoft Advertising  app for Shopify, UET tags are automatically created and added to every page of your website. Go to the [Install an app](https://go.microsoft.com/fwlink?LinkId=2109447) page and follow the prompts to get your Microsoft Advertising  app for Shopify set up.

If you created and manage your website with Shopify, you can add and manage your UET tag there.

## Implementing UET using Shopify

1. In Microsoft Advertising, go to **Conversion Tracking**&nbsp;&gt;&nbsp;**UET tags** and copy your JavaScript UET tag tracking code.
1. Log in to your Shopify account.
1. In Shopify, go to **Settings**&nbsp;&gt;&nbsp;**Themes**.
1. Find the theme you’re currently using and then click **Actions**&nbsp;&gt;&nbsp;**Edit code** to access your website's code.
1. Select **theme.liquid** and scroll down to the end of your website's code.
1. Paste your UET tracking code above the "&lt;/body&gt;" HTML tag and click **Save**.
1. Go to **Settings**&nbsp;&gt;&nbsp;**Checkout** to add your UET tag to your site's checkout page.
1. Paste the UET tracking code in the **Order Processing**&nbsp;&gt;&nbsp;**Additional scripts** text box and click **Save**.
1. If you want to report variable revenue, add one of the following code snippets below the UET tracking code you pasted in the previous step:
   1. Use this code if you want to exclude taxes and shipping:
```
<script>   window.uetq = window.uetq || [];    window.uetq.push('event', '', { 'revenue_value': {{ subtotal_price | money_without_currency }}, 'currency': '{{ shop.currency }}' }); </script>
```

   1. Use this code if you want to include taxes and shipping:
```
<script>   window.uetq = window.uetq || [];    window.uetq.push('event', '', { 'revenue_value': {{ total_price | money_without_currency }}, 'currency': '{{ shop.currency }}' }); </script>
```

> [!NOTE]
> To validate that your Shopify UET tag is working, download and install [UET Tag Helper](./hlp_BA_CONC_UET_TagHelper.md). Go to your Shopify website and verify that a UET event is received and that the **Tag ID** matches the tag you selected in Step 1.


