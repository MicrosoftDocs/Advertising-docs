---
title: KeywordIdeaAttribute Value Set - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: "article"
ms.date: 11/01/2017
author: eric-urban
ms.author: eur
description: Determines which properties of the KeywordIdea object you want returned when calling the [GetKeywordIdeas](../ad-insight-service/getkeywordideas.md) operation.
---
# KeywordIdeaAttribute Value Set - Ad Insight
Determines which properties of the [KeywordIdea](../ad-insight-service/keywordidea.md) object you want returned when calling the [GetKeywordIdeas](../ad-insight-service/getkeywordideas.md) operation.

## Syntax
```xml
<xs:simpleType name="KeywordIdeaAttribute" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="AdGroupId" />
    <xs:enumeration value="AdGroupName" />
    <xs:enumeration value="Keyword" />
    <xs:enumeration value="Source" />
    <xs:enumeration value="MonthlySearchCounts" />
    <xs:enumeration value="SuggestedBid" />
    <xs:enumeration value="Competition" />
    <xs:enumeration value="Relevance" />
    <xs:enumeration value="AdImpressionShare" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="adgroupid"></a>AdGroupId|Include the ad group identifier.|
|<a name="adgroupname"></a>AdGroupName|Include the ad group name.|
|<a name="adimpressionshare"></a>AdImpressionShare|Include the ad impression share.|
|<a name="competition"></a>Competition|Include the competition.|
|<a name="keyword"></a>Keyword|Include the keyword.|
|<a name="monthlysearchcounts"></a>MonthlySearchCounts|Include the monthly search counts.|
|<a name="relevance"></a>Relevance|Include the relevance.|
|<a name="source"></a>Source|Include the source.|
|<a name="suggestedbid"></a>SuggestedBid|Include the suggested bid.|

## Requirements
Service: [AdInsightService.svc v11](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: Microsoft.Advertiser.AdInsight.Api.Service.V11  

## Used By
[GetKeywordIdeas](getkeywordideas.md)  
