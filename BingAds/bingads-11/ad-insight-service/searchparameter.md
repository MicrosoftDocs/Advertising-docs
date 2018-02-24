---
title: SearchParameter Data Object - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: This is the base class from which keyword idea search parameter objects derive.
---
# SearchParameter Data Object - Ad Insight
This is the base class from which keyword idea search parameter objects derive. 

Do not try to instantiate a [SearchParameter](/bingads/ad-insight-service/searchparameter.md). You can create one or more following objects that derive from it.
- [CategorySearchParameter](/bingads/ad-insight-service/categorysearchparameter.md)  
- [CompetitionSearchParameter](/bingads/ad-insight-service/competitionsearchparameter.md)  
- [DateRangeSearchParameter](/bingads/ad-insight-service/daterangesearchparameter.md)  
- [DeviceSearchParameter](/bingads/ad-insight-service/devicesearchparameter.md)  
- [ExcludeAccountKeywordsSearchParameter](/bingads/ad-insight-service/excludeaccountkeywordssearchparameter.md)  
- [IdeaTextSearchParameter](/bingads/ad-insight-service/ideatextsearchparameter.md)  
- [ImpressionShareSearchParameter](/bingads/ad-insight-service/impressionsharesearchparameter.md)  
- [LanguageSearchParameter](/bingads/ad-insight-service/languagesearchparameter.md)  
- [LocationSearchParameter](/bingads/ad-insight-service/locationsearchparameter.md)  
- [NetworkSearchParameter](/bingads/ad-insight-service/networksearchparameter.md)  
- [QuerySearchParameter](/bingads/ad-insight-service/querysearchparameter.md)  
- [SearchVolumeSearchParameter](/bingads/ad-insight-service/searchvolumesearchparameter.md)  
- [SuggestedBidSearchParameter](/bingads/ad-insight-service/suggestedbidsearchparameter.md)  
- [UrlSearchParameter](/bingads/ad-insight-service/urlsearchparameter.md)  

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
