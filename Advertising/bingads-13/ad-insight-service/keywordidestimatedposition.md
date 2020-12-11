---
title: KeywordIdEstimatedPosition Data Object - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an object that contains the identifier of a keyword and the estimated search results position for the keyword and match type.
---
# KeywordIdEstimatedPosition Data Object - Ad Insight
Defines an object that contains the identifier of a keyword and the estimated search results position for the keyword and match type.

> [!NOTE]
> The estimates are not a prediction or guarantee of future performance.

## Syntax
```xml
<xs:complexType name="KeywordIdEstimatedPosition" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="KeywordId" type="xs:long" />
    <xs:element minOccurs="0" name="KeywordEstimatedPosition" nillable="true" type="tns:KeywordEstimatedPosition" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

The [KeywordIdEstimatedPosition](keywordidestimatedposition.md) object has the following elements: [KeywordEstimatedPosition](#keywordestimatedposition), [KeywordId](#keywordid).

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="keywordestimatedposition"></a>KeywordEstimatedPosition|An object that contains the keyword string and estimated position in the search results given the specified maximum bid.|[KeywordEstimatedPosition](keywordestimatedposition.md)|
|<a name="keywordid"></a>KeywordId|The identifier of the keyword to which the estimated position applies.|**long**|

## Requirements
Service: [AdInsightService.svc v13](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v13/AdInsightService.svc)  
Namespace: https\://bingads.microsoft.com/AdInsight/v13  

## Used By
[GetEstimatedPositionByKeywordIds](getestimatedpositionbykeywordids.md)  
