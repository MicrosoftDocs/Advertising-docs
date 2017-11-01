---
title: KeywordAndMatchType Data Object - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: "article"
author: eric-urban
ms.author: eur
description: Defines an object that contains a keyword and corresponding match types.
---
# KeywordAndMatchType Data Object - Ad Insight
Defines an object that contains a keyword and corresponding match types.

## Syntax
```xml
<xs:complexType name="KeywordAndMatchType" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="KeywordText" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="MatchTypes" nillable="true" type="q1:ArrayOfMatchType" xmlns:q1="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="keywordtext"></a>KeywordText|The keyword text.|**string**|
|<a name="matchtypes"></a>MatchTypes|The corresponding match types for the keyword.|[MatchType](matchtype.md) array|

## Requirements
Service: [AdInsightService.svc v11](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Message  

## Used By
[GetEstimatedBidByKeywords](getestimatedbidbykeywords.md)  
