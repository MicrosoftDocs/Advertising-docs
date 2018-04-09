---
title: AuctionInsightResult Data Object - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an auction insight result.
---
# AuctionInsightResult Data Object - Ad Insight
Defines an auction insight result.

> [!NOTE]
> Reserved for future use.

## Syntax
```xml
<xs:complexType name="AuctionInsightResult" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="Segment" nillable="true" type="tns:AuctionSegment" />
    <xs:element minOccurs="0" name="Entries" nillable="true" type="tns:ArrayOfAuctionInsightEntry" />
    <xs:element minOccurs="0" name="UsedImpressions" type="xs:double" />
    <xs:element minOccurs="0" name="UsedKeywords" type="xs:double" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="entries"></a>Entries|Reserved.|[AuctionInsightEntry](auctioninsightentry.md) array|
|<a name="segment"></a>Segment|Reserved.|[AuctionSegment](auctionsegment.md)|
|<a name="usedimpressions"></a>UsedImpressions|Reserved.|**double**|
|<a name="usedkeywords"></a>UsedKeywords|Reserved.|**double**|

## Requirements
Service: [AdInsightService.svc v12](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v12/AdInsightService.svc)  
Namespace: http\://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity  

## Used By
[GetAuctionInsightData](getauctioninsightdata.md)  
