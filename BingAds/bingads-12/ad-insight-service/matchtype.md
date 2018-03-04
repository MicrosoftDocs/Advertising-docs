---
title: MatchType Value Set - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the possible keyword match type values.
---
# MatchType Value Set - Ad Insight
Defines the possible keyword match type values.

## Syntax
```xml
<xs:simpleType name="MatchType" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="Exact" />
    <xs:enumeration value="Phrase" />
    <xs:enumeration value="Broad" />
    <xs:enumeration value="Content" />
    <xs:enumeration value="Aggregate" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="aggregate"></a>Aggregate|Aggregates the data across all match types.|
|<a name="broad"></a>Broad|A broad match results when words in the keyword are present in the user's search query; however, the word order can vary.|
|<a name="content"></a>Content|A content match results when the keywords extracted from the content webpage match the keywords in the user's search query by using an exact match comparison. An exact match results when all of the words in the keyword exactly match the user's query.|
|<a name="exact"></a>Exact|An exact match results when all of the words in the keyword exactly match the user's search query.|
|<a name="phrase"></a>Phrase|A phrase match results when all of the words in the keyword are present in the user's search query and are in the same order.|

## Requirements
Service: [AdInsightService.svc v11](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: Microsoft.Advertiser.AdInsight.Api.Service.V11  

## Used By
[EstimatedBidAndTraffic](estimatedbidandtraffic.md)  
[EstimatedPositionAndTraffic](estimatedpositionandtraffic.md)  
[GetEstimatedPositionByKeywords](getestimatedpositionbykeywords.md)  
[GetHistoricalKeywordPerformance](gethistoricalkeywordperformance.md)  
[Keyword](keyword.md)  
[KeywordAndMatchType](keywordandmatchtype.md)  
[KeywordKPI](keywordkpi.md)  
[NegativeKeyword](negativekeyword.md)  
