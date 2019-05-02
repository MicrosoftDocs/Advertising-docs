---
title: KeywordEstimatedPosition Data Object - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an object that contains the keyword and the estimated position in the search results for each match type.
---
# KeywordEstimatedPosition Data Object - Ad Insight
Defines an object that contains the keyword and the estimated position in the search results for each match type.

> [!NOTE]
> The estimates are not a prediction or guarantee of future performance.

## Syntax
```xml
<xs:complexType name="KeywordEstimatedPosition" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="Keyword" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="EstimatedPositions" nillable="true" type="tns:ArrayOfEstimatedPositionAndTraffic" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="estimatedpositions"></a>EstimatedPositions|An array of [EstimatedPositionAndTraffic](estimatedpositionandtraffic.md) data objects that contains the position in the search results corresponding to the specified maximum bid.<br/><br/>Each object also contains estimates of clicks, average cost per click (CPC), impressions, click-through rate (CTR), and total cost given the specified bid.<br/><br/>If there is no data available for a match type, the array will not include estimates for the match type.|[EstimatedPositionAndTraffic](estimatedpositionandtraffic.md) array|
|<a name="keyword"></a>Keyword|The keyword to which the estimates apply.|**string**|

## Requirements
Service: [AdInsightService.svc v12](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v12/AdInsightService.svc)  
Namespace: http\://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity  

## Used By
[GetEstimatedPositionByKeywords](getestimatedpositionbykeywords.md)  
[KeywordIdEstimatedPosition](keywordidestimatedposition.md)  
