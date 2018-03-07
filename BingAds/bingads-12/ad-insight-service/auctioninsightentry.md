---
title: AuctionInsightEntry Data Object - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an auction insight entry.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change.

# AuctionInsightEntry Data Object - Ad Insight
Defines an auction insight entry.

> [!NOTE]
> Reserved for future use.

## Syntax
```xml
<xs:complexType name="AuctionInsightEntry" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="DisplayDomain" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="AggregatedKpi" nillable="true" type="tns:AuctionInsightKpi" />
    <xs:element minOccurs="0" name="SegmentedKpis" nillable="true" type="tns:ArrayOfAuctionInsightKpi" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="aggregatedkpi"></a>AggregatedKpi|Reserved.|[AuctionInsightKpi](auctioninsightkpi.md)|
|<a name="displaydomain"></a>DisplayDomain|Reserved.|**string**|
|<a name="segmentedkpis"></a>SegmentedKpis|Reserved.|[AuctionInsightKpi](auctioninsightkpi.md) array|

## Requirements
Service: [AdInsightService.svc v12](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: http\://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity  

## Used By
[AuctionInsightResult](auctioninsightresult.md)  
