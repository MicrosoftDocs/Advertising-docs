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
* [App Install Ad](~/bulk-service/app-install-ad.md)

## <a name="campaign"></a>Campaign Management API for App Install Ads
The [AppInstallAd](~/campaign-management-service/appinstallad.md) object is derived from the [Ad](~/campaign-management-service/ad.md) base class and can be managed with any of the existing ad operations e.g. [AddAds](~/campaign-management-service/addads.md), [DeleteAds](~/campaign-management-service/deleteads.md), and [UpdateAds](~/campaign-management-service/updateads.md). 

You can include *AppInstallAd* as an [AdType](~/campaign-management-service/adtype.md) in the *AdTypes* request element of the following operations to retrieve app install ads.
* [GetAdsByAdGroupId](~/campaign-management-service/getadsbyadgroupid.md)
* [GetAdsByEditorialStatus](~/campaign-management-service/getadsbyeditorialstatus.md)
* [GetAdsByIds](~/campaign-management-service/getadsbyids.md)
