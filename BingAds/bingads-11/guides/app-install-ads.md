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

App Install Ads automatically detect the customer’s mobile device and operating system, sending them to the corresponding Apple App Store or Google Play. You can also track conversions with the same conversion tracking partners as [App Ad Extensions](bingads/guides/ad-extensions.md): AppsFlyer, Kochava, Tune, Apsalar, and Adjust. To learn more, see the Bing Ads help article [What is an App Install Ad?](https://help.bingads.microsoft.com/#apex/3/en/56836/0)

Create an app install ad if your intention is to drive app downloads, and not necessarily to direct leads to a web site. If you want to direct leads to a web site in addition to driving app downloads, then you should create an expanded text ad with app ad extensions.

> [!NOTE]
> Bing Ads only supports *EN-US* apps. App Install Ads are only available in the United States and on iOS and Android only.

## <a name="bulk"></a>Bulk API for App Install Ads
The following Bulk record is available for managing app install ads.
* [App Install Ad](bingads/bulk-service/app-install-ad.md)

## <a name="campaign"></a>Campaign Management API for App Install Ads
The [AppInstallAd](bingads/campaign-management-service/appinstallad.md) object is derived from the [Ad](bingads/campaign-management-service/ad.md) base class and can be managed with any of the ad operations e.g. [AddAds](bingads/campaign-management-service/addads.md), [DeleteAds](bingads/campaign-management-service/deleteads.md), [GetAdsByAdGroupId](bingads/campaign-management-service/getadsbyadgroupid.md), and [UpdateAds](bingads/campaign-management-service/updateads.md). 
