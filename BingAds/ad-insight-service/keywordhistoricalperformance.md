---
title: KeywordHistoricalPerformance Data Object - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an object that contains the key performance index data for the specified keyword.
---
# KeywordHistoricalPerformance Data Object - Ad Insight
Defines an object that contains the key performance index data for the specified keyword.

## Syntax
```xml
<xs:complexType name="KeywordHistoricalPerformance" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="Keyword" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="KeywordKPIs" nillable="true" type="tns:ArrayOfKeywordKPI" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="keyword"></a>Keyword|The keyword to which the keyword performance data applies.|**string**|
|<a name="keywordkpis"></a>KeywordKPIs|An array of [KeywordKPI](../ad-insight-service/keywordkpi.md) objects that contains the performance data.<br /><br />For each requested keyword that has no available data, the [KeywordKPI](../ad-insight-service/keywordkpi.md) element will be nil.<br /><br />If the request specified a specific target position, the array will contain only one item per requested keyword. If the request specified All for the target position, then for each requested keyword the array will contain an item for each possible position in the search results.|[KeywordKPI](keywordkpi.md) array|

## Requirements
Service: [AdInsightService.svc v11](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: ```http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity```  

## Used By
[GetHistoricalKeywordPerformance](gethistoricalkeywordperformance.md)  
