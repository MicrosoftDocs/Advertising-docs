---
title: KeywordIdEstimatedPosition Data Object - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an object that contains the identifier of a keyword and the estimated search results position for the keyword and match type.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

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

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="keywordestimatedposition"></a>KeywordEstimatedPosition|An object that contains the keyword string and estimated position in the search results given the specified maximum bid.|[KeywordEstimatedPosition](keywordestimatedposition.md)|
|<a name="keywordid"></a>KeywordId|The identifier of the keyword to which the estimated position applies.|**long**|

## Requirements
Service: [AdInsightService.svc v12](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v12/AdInsightService.svc)  
Namespace: http\://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity  

## Used By
[GetEstimatedPositionByKeywordIds](getestimatedpositionbykeywordids.md)  
