---
title: SearchParameter Data Object - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: This is the base class from which keyword idea search parameter objects derive.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change.

# SearchParameter Data Object - Ad Insight
This is the base class from which keyword idea search parameter objects derive. 

Do not try to instantiate a [SearchParameter](searchparameter.md). You can create one or more following objects that derive from it.
- [CategorySearchParameter](categorysearchparameter.md)  
- [CompetitionSearchParameter](competitionsearchparameter.md)  
- [DateRangeSearchParameter](daterangesearchparameter.md)  
- [DeviceSearchParameter](devicesearchparameter.md)  
- [ExcludeAccountKeywordsSearchParameter](excludeaccountkeywordssearchparameter.md)  
- [IdeaTextSearchParameter](ideatextsearchparameter.md)  
- [ImpressionShareSearchParameter](impressionsharesearchparameter.md)  
- [LanguageSearchParameter](languagesearchparameter.md)  
- [LocationSearchParameter](locationsearchparameter.md)  
- [NetworkSearchParameter](networksearchparameter.md)  
- [QuerySearchParameter](querysearchparameter.md)  
- [SearchVolumeSearchParameter](searchvolumesearchparameter.md)  
- [SuggestedBidSearchParameter](suggestedbidsearchparameter.md)  
- [UrlSearchParameter](urlsearchparameter.md)  

## Syntax
```xml
<xs:complexType name="SearchParameter" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence />
</xs:complexType>
```

## <a name="elements"></a>Elements

## Requirements
Service: [AdInsightService.svc v11](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: http\://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity.SearchParameters  

## Used By
[GetKeywordIdeas](getkeywordideas.md)  
