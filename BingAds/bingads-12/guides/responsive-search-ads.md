---
title: "Responsive Search Ads"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: Setup responsive search ads with the Bing Ads API.
---
# Responsive Search Ads
Responsive search ads in the Search network allow you to set between 3-15 unique ad headlines (a.k.a. "titles") and 2-4 ad descriptions within a single ad. From there, Bing will select the most relevant headline and description combination for each given query and corresponding search user. By allowing Bing AI to select the most relevant headline and description for each query, we ensure that the right message lands for each of your potential customers, at the right time, across all possible intent signals. 

> [!NOTE]
> Not everyone has this feature yet. If you don't, don't worry. It's coming soon. 

> [!WARNING]
> As of November 1st, 2018 responsive search ads can be managed via the Bing Ads API. The Bing Ads web application enables a limited set of operations e.g., view, pause, and unpause responsive search ads. Feature parity between the web application and API will be rolled out from Q4 calendar year 2018 through Q1 calendar year 2019. 

> [!NOTE]
> Editorial rejection reasons and appeals are not yet supported for responsive search ads. Support will be added in a future release e.g., Q1 calendar year 2019. p

The responsive ads shown to users appear identical to expanded text ads i.e., up to 3 headlines (title parts via expanded text ads) and 2 descriptions (text parts via expanded text ads). Two headlines and one description will always be shown in the ad. However, depending on the screen size, your ad may show without the third headline or second description.

## <a name="bulk"></a>Bulk API for Responsive Search Ads
The [Responsive Search Ad](../bulk-service/responsive-search-ad.md) Bulk record is available for managing responsive search ads i.e., you can upload or download data in this format.

## <a name="campaign"></a>Campaign Management API for Responsive Search Ads
The [ResponsiveSearchAd](../campaign-management-service/responsivesearchad.md) object is derived from the [Ad](../campaign-management-service/ad.md) base class and can be managed with any of the existing ad operations e.g. [AddAds](../campaign-management-service/addads.md), [DeleteAds](../campaign-management-service/deleteads.md), [GetAdsByAdGroupId](../campaign-management-service/getadsbyadgroupid.md), and [UpdateAds](../campaign-management-service/updateads.md). 

## See Also
[Countdown Customizers](countdown-customizers.md)  