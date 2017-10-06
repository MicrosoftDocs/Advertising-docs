---
title: KeywordAndConfidence Data Object
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an object that contains a suggested keyword and a confidence score.
---
# KeywordAndConfidence Data Object
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
|<a name="suggestedkeyword"></a>SuggestedKeyword|The suggested keyword.|**string**|
|<a name="confidencescore"></a>ConfidenceScore|A score from 0.0 to 1.0 that indicates the probability that the keyword would match a user's search query.|**double**|

## Requirements
Service: [AdInsightService.svc v11](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity  

## Used By
[KeywordSuggestion](keywordsuggestion.md)  
[SuggestKeywordsForUrl](suggestkeywordsforurl.md)  
