---
title: SearchParameter Data Object
ms.service: bing-ads-ad-insight
ms.topic: article
author: eric-urban
ms.author: eur
---
# SearchParameter Data Object
This is the base class from which keyword idea search parameter objects derive. 

Do not try to instantiate a [SearchParameter](../ad-insight/searchparameter.md). You can create one or more following objects that derive from it.
- [CategorySearchParameter](../ad-insight/categorysearchparameter.md)  
- [CompetitionSearchParameter](../ad-insight/competitionsearchparameter.md)  
- [DateRangeSearchParameter](../ad-insight/daterangesearchparameter.md)  
- [DeviceSearchParameter](../ad-insight/devicesearchparameter.md)  
- [ExcludeAccountKeywordsSearchParameter](../ad-insight/excludeaccountkeywordssearchparameter.md)  
- [IdeaTextSearchParameter](../ad-insight/ideatextsearchparameter.md)  
- [ImpressionShareSearchParameter](../ad-insight/impressionsharesearchparameter.md)  
- [LanguageSearchParameter](../ad-insight/languagesearchparameter.md)  
- [LocationSearchParameter](../ad-insight/locationsearchparameter.md)  
- [NetworkSearchParameter](../ad-insight/networksearchparameter.md)  
- [QuerySearchParameter](../ad-insight/querysearchparameter.md)  
- [SearchVolumeSearchParameter](../ad-insight/searchvolumesearchparameter.md)  
- [SuggestedBidSearchParameter](../ad-insight/suggestedbidsearchparameter.md)  
- [UrlSearchParameter](../ad-insight/urlsearchparameter.md)  

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
