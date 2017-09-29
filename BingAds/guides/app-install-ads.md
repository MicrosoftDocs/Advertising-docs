---
title: "App Install Ads"
ms.service: "bing-ads"
ms.topic: "article"
---
# App Install Ads
Create an app install ad if your intention is to drive app downloads, and not necessarily to direct leads to a web site. If you want to direct leads to a web site in addition to driving app downloads, then you should create a text ad with app ad extensions.

> [!NOTE]
> Before you can use app install ads, you must upgrade to Final Urls. For more information, see [URL Tracking with Upgraded URLs](~/guides/url-tracking-upgraded-urls.md).
>
> Bing Ads only supports *EN-US* apps.

## <a name="bulk"></a>Bulk API for App Install Ads
The following Bulk record is added for managing app install ads.
* [App Install Ad](~/bulk/app-install-ad.md)

## <a name="campaign"></a>Campaign Management API for App Install Ads
The [AppInstallAd](~/campaign-management/appinstallad.md) object is derived from the [Ad](~/campaign-management/ad.md) base class and can be managed with any of the existing ad operations e.g. [AddAds](~/campaign-management/addads.md), [DeleteAds](~/campaign-management/deleteads.md), and [UpdateAds](~/campaign-management/updateads.md). 

You can include *AppInstallAd* as an [AdType](~/campaign-management/adtype.md) in the *AdTypes* request element of the following operations to retrieve app install ads.
* [GetAdsByAdGroupId](~/campaign-management/getadsbyadgroupid.md)
* [GetAdsByEditorialStatus](~/campaign-management/getadsbyeditorialstatus.md)
* [GetAdsByIds](~/campaign-management/getadsbyids.md)
