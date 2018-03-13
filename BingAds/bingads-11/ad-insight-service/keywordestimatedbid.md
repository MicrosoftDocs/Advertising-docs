---
title: KeywordEstimatedBid Data Object - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an object that contains the keyword and the estimated bid value for each match type.
---
# KeywordEstimatedBid Data Object - Ad Insight
Defines an object that contains the keyword and the estimated bid value for each match type.

> [!NOTE]
> The estimates are not a prediction or guarantee of future performance.

## Syntax
```xml
<xs:complexType name="KeywordEstimatedBid" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="Keyword" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="EstimatedBids" nillable="true" type="tns:ArrayOfEstimatedBidAndTraffic" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="estimatedbids"></a>EstimatedBids|A list of [EstimatedBidAndTraffic](estimatedbidandtraffic.md) data objects that contains the suggested bid value for the keyword and match type. If there is data available for the keyword, the [EstimatedBidAndTraffic](estimatedbidandtraffic.md) object will provide an estimated bid value. Otherwise, if no data is available the *EstimatedBids* element will be null.<br /><br />Each object also contains estimates of clicks, average cost per click (CPC), impressions, click-through rate (CTR), and total cost given the suggested bid.<br /><br />If there is no data available for a match type, the array will not include estimates for the match type.<br /><br /> Some returned elements of the [EstimatedBidAndTraffic](estimatedbidandtraffic.md) may be NULL.|[EstimatedBidAndTraffic](estimatedbidandtraffic.md) array|
|<a name="keyword"></a>Keyword|The keyword to which the estimates apply.|**string**|

## Requirements
Service: [AdInsightService.svc v11](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: http\://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity  

## Used By
[GetEstimatedBidByKeywords](getestimatedbidbykeywords.md)  
[KeywordIdEstimatedBid](keywordidestimatedbid.md)  
