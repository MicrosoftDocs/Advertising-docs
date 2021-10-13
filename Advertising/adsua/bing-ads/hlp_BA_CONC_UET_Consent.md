---
title: Setting up UET for consent mode
description: Consent mode allows you to adjust UET cookie access based on consent status.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Setting up UET for consent mode

[!INCLUDE [OpenBeta](./includes/OpenBeta.md)]
UET consent mode lets you adjust UET cookie access based on the consent status of your users. This enhances the privacy capabilities of UET and gives you control over whether first and third-party cookies are stored.

For the purposes of UET consent mode, first-party cookies are those created by the advertiser domain (your website), and third-party cookies are created by Microsoft Advertising (Bing.com).

> [!IMPORTANT]
> If you are using the [UET - Clarity integration](./hlp_BA_CONC_UET_Clarity.md), you must set the consent setting for Clarity separately. [Learn more about Clarity cookie consent.](https://go.microsoft.com/fwlink?LinkId=2174133)
> It is up to you to comply with local regulations when collecting and managing consent.

## How it works

Consent mode is set via a property in UET called **ad_storage**. The possible values for **ad_storage** are:

|Value for **ad_storage**|Description|
|---|---|
|**granted**|First and third-party cookies may be read and written for UET. If no default is set, UET uses **granted** by default.|
|**denied**|First-party cookies are not read nor written for UET. Third-party cookies are not written. Third-party cookies are read-only for fraud and spam purposes—not for advertising purposes.|

## Example setup for consent mode

1. Set your default consent setting on every page of your website
   1. Use the following code on each page load to set your default consent setting:
```
// UET tag is added here// You can set default consent mode right after the UET tag  <script>window.uetq = window.uetq || [];window.uetq.push('consent', 'default', {    'ad_storage': 'denied'    });</script>
```

   1. You can set **ad_storage** to **granted** or **denied** by default. In this example, consent is denied by default.

1. Once the user provides or denies consent, update the consent setting on every page:
   1. Use the following code on each page to update the **ad_storage** property:
```
<script>window.uetq = window.uetq || [];window.uetq.push('consent', 'update', {    'ad_storage': 'granted'    });</script>
```

   1. Call this script on subsequent pages for as long as the consent applies.

> [!NOTE]
> We recommend that you use the consent script in your &lt;head&gt; tags so that the consent mode is set by default and updated when a user updates their consent settings.
> You can prevent UET from sending events to Microsoft by setting the **_uetmsdns** cookie to a value of 1. [Learn more](./hlp_BA_CONC_UET_FAQ_2.md)
> 
> [!IMPORTANT]
> You must set the consent setting on every page of your website. If it is not set, then UET uses **granted** by default.


