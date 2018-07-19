---
title: "App Install Ads"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: Setup App Install ads with the Bing Ads API.
---
# App Install Ads
App Install Ads are similar to expanded text ads but provide direct links to your apps with a button, sending customers directly to the applicable store to download the application. This is an ideal solution for advertisers wanting to manage and drive downloads of their apps, rather than website traffic.

App Install Ads automatically detect the customer’s mobile device and operating system, sending them to the corresponding Apple App Store or Google Play. You can also track conversions with the same conversion tracking partners as [App Ad Extensions](ad-extensions.md): AppsFlyer, Kochava, Tune, Singular, and Adjust. To learn more, see the Bing Ads help article [What is an App Install Ad?](https://help.bingads.microsoft.com/#apex/3/en/56836/0)

Create an app install ad if your intention is to drive app downloads, and not necessarily to direct leads to a web site. If you want to direct leads to a web site in addition to driving app downloads, then you should create an expanded text ad with app ad extensions.

> [!NOTE]
> App Install Ads are available in the United States, Australia, Canada, Germany, France, India, United Kingdom, and on iOS and Android only. For Android apps, Bing Ads only supports apps available in the United States Google Play store.
> 
> Not everyone has this feature yet. If you don’t, don’t worry. It’s coming soon.

## <a name="bulk"></a>Bulk API for App Install Ads
The [App Install Ad](../bulk-service/app-install-ad.md) Bulk record is available for managing app install ads.

## <a name="campaign"></a>Campaign Management API for App Install Ads
The [AppInstallAd](../campaign-management-service/appinstallad.md) object is derived from the [Ad](../campaign-management-service/ad.md) base class and can be managed with any of the ad operations e.g. [AddAds](../campaign-management-service/addads.md), [DeleteAds](../campaign-management-service/deleteads.md), [GetAdsByAdGroupId](../campaign-management-service/getadsbyadgroupid.md), and [UpdateAds](../campaign-management-service/updateads.md). 
