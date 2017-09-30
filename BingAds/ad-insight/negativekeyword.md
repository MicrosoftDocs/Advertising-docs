---
title: NegativeKeyword Data Object
ms.service: bing-ads-ad-insight
ms.topic: article
author: eric-urban
ms.author: eur
---
# NegativeKeyword Data Object
Defines a negative keyword with match type.

## Syntax
```xml
<xs:complexType name="NegativeKeyword" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="Id" nillable="true" type="xs:long" />
    <xs:element minOccurs="0" name="MatchType" type="q2:MatchType" xmlns:q2="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity" />
    <xs:element minOccurs="0" name="Text" nillable="true" type="xs:string" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="id"></a>Id|The Bing Ads identifier of the negative keyword.|**long**|
|<a name="matchtype"></a>MatchType|The match type of the negative keyword.|[MatchType](matchtype.md)|
|<a name="text"></a>Text|The negative keyword text.|**string**|

## Requirements
Service: [AdInsightService.svc v11](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity.Common  

## Used By
[CampaignEstimator](campaignestimator.md)  
