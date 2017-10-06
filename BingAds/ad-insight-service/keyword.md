---
title: Keyword Data Object
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a keyword with match type.
---
# Keyword Data Object
Defines a keyword with match type.

## Syntax
```xml
<xs:complexType name="Keyword" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="Id" nillable="true" type="xs:long" />
    <xs:element minOccurs="0" name="MatchType" type="q1:MatchType" xmlns:q1="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity" />
    <xs:element minOccurs="0" name="Text" nillable="true" type="xs:string" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="id"></a>Id|The Bing Ads identifier of the keyword.|**long**|
|<a name="matchtype"></a>MatchType|The match type of the keyword.|[MatchType](matchtype.md)|
|<a name="text"></a>Text|The keyword text.|**string**|

## Requirements
Service: [AdInsightService.svc v11](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity.Common  

## Used By
[IdeaTextSearchParameter](ideatextsearchparameter.md)  
[KeywordEstimate](keywordestimate.md)  
[KeywordEstimator](keywordestimator.md)  
