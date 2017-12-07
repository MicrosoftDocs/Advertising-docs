---
title: KeywordLocationResult Data Object - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an object that contains the locations where users were located when they searched for the specified keyword.
---
# KeywordLocationResult Data Object - Ad Insight
Defines an object that contains the locations where users were located when they searched for the specified keyword.

## Syntax
```xml
<xs:complexType name="KeywordLocationResult" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="Keyword" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="KeywordLocations" nillable="true" type="tns:ArrayOfKeywordLocation" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="keyword"></a>Keyword|The keyword.|**string**|
|<a name="keywordlocations"></a>KeywordLocations|An array of [KeywordLocation](../ad-insight-service/keywordlocation.md) objects that contains the geographical locations and the percentage of times that users searched for the keyword from that location.|[KeywordLocation](keywordlocation.md) array|

## Requirements
Service: [AdInsightService.svc v11](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: http\://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity  

## Used By
[GetKeywordLocations](getkeywordlocations.md)  
