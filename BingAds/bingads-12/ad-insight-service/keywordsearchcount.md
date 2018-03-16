---
title: KeywordSearchCount Data Object - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an object that contains a list of search counts for each device and network where the keyword was included in a search query.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# KeywordSearchCount Data Object - Ad Insight
Defines an object that contains a list of search counts for each device and network where the keyword was included in a search query. The data is aggregated based on the attributes specified in the request.

## Syntax
```xml
<xs:complexType name="KeywordSearchCount" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="Keyword" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="SearchCountsByAttributes" nillable="true" type="tns:ArrayOfSearchCountsByAttributes" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="keyword"></a>Keyword|The keyword to which the search count data applies.|**string**|
|<a name="searchcountsbyattributes"></a>SearchCountsByAttributes|An array of [SearchCountsByAttributes](searchcountsbyattributes.md) objects that contain search counts for each device and network where the keyword was included in a search query.<br /><br />For each requested keyword that has no available data, the [SearchCountsByAttributes](searchcountsbyattributes.md) element will be nil.|[SearchCountsByAttributes](searchcountsbyattributes.md) array|

## Requirements
Service: [AdInsightService.svc v12](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v12/AdInsightService.svc)  
Namespace: http\://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity  

## Used By
[GetHistoricalSearchCount](gethistoricalsearchcount.md)  
