---
title: KeywordAndConfidence Data Object - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an object that contains a suggested keyword and a confidence score.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# KeywordAndConfidence Data Object - Ad Insight
Defines an object that contains a suggested keyword and a confidence score. The confidence score indicates the probability that the keyword would match a user's search query.

## Syntax
```xml
<xs:complexType name="KeywordAndConfidence" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="SuggestedKeyword" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="ConfidenceScore" type="xs:double" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="confidencescore"></a>ConfidenceScore|A score from 0.0 to 1.0 that indicates the probability that the keyword would match a user's search query.|**double**|
|<a name="suggestedkeyword"></a>SuggestedKeyword|The suggested keyword.|**string**|

## Requirements
Service: [AdInsightService.svc v12](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v12/AdInsightService.svc)  
Namespace: http\://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity  

## Used By
[KeywordSuggestion](keywordsuggestion.md)  
[SuggestKeywordsForUrl](suggestkeywordsforurl.md)  
