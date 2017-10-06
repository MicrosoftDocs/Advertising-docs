---
title: SearchParameter Data Object
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: This is the base class from which keyword idea search parameter objects derive.
---
# SearchParameter Data Object
This is the base class from which keyword idea search parameter objects derive. 

Do not try to instantiate a [SearchParameter](../ad-insight-service/searchparameter.md). You can create one or more following objects that derive from it.
- [CategorySearchParameter](../ad-insight-service/categorysearchparameter.md)  
- [CompetitionSearchParameter](../ad-insight-service/competitionsearchparameter.md)  
- [DateRangeSearchParameter](../ad-insight-service/daterangesearchparameter.md)  
- [DeviceSearchParameter](../ad-insight-service/devicesearchparameter.md)  
- [ExcludeAccountKeywordsSearchParameter](../ad-insight-service/excludeaccountkeywordssearchparameter.md)  
- [IdeaTextSearchParameter](../ad-insight-service/ideatextsearchparameter.md)  
- [ImpressionShareSearchParameter](../ad-insight-service/impressionsharesearchparameter.md)  
- [LanguageSearchParameter](../ad-insight-service/languagesearchparameter.md)  
- [LocationSearchParameter](../ad-insight-service/locationsearchparameter.md)  
- [NetworkSearchParameter](../ad-insight-service/networksearchparameter.md)  
- [QuerySearchParameter](../ad-insight-service/querysearchparameter.md)  
- [SearchVolumeSearchParameter](../ad-insight-service/searchvolumesearchparameter.md)  
- [SuggestedBidSearchParameter](../ad-insight-service/suggestedbidsearchparameter.md)  
- [UrlSearchParameter](../ad-insight-service/urlsearchparameter.md)  

## Syntax
```xml
<xs:complexType name="SearchParameter" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence />
</xs:complexType>
```

## <a name="elements"></a>Elements

## Requirements
Service: [AdInsightService.svc v11](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity.SearchParameters  

## Used By
[GetKeywordIdeas](getkeywordideas.md)  
