---
title: AuctionInsightResult Data Object - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the auction insight results from calling the GetAuctionInsightData operation.
---
# AuctionInsightResult Data Object - Ad Insight
Defines the auction insight results from calling the [GetAuctionInsightData](getauctioninsightdata.md) operation.

## Syntax
```xml
<xs:complexType name="AuctionInsightResult" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="Segments" nillable="true" type="tns:ArrayOfAuctionSegment" />
    <xs:element minOccurs="0" name="Entries" nillable="true" type="tns:ArrayOfAuctionInsightEntry" />
    <xs:element minOccurs="0" name="UsedImpressions" type="xs:double" />
    <xs:element minOccurs="0" name="UsedKeywords" type="xs:double" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="entries"></a>Entries|One or more auction insight entries i.e., one result per domain that you competed with in the auction.|[AuctionInsightEntry](auctioninsightentry.md) array|
|<a name="segments"></a>Segments|The segments if any were specified via one or more [AuctionSegmentSearchParameter](auctionsegmentsearchparameter.md) in the [GetAuctionInsightData](getauctioninsightdata.md) request.|[AuctionSegment](auctionsegment.md) array|
|<a name="usedimpressions"></a>UsedImpressions|The percent of impressions that were used to generate the auction insight entries.<br/><br/>The value can range from 0 to 1.0, for example 0.8 indicates that 80 percent of impressions were used.|**double**|
|<a name="usedkeywords"></a>UsedKeywords|The number of keywords that were used to generate the auction insight entries.|**double**|

## Requirements
Service: [AdInsightService.svc v12](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v12/AdInsightService.svc)  
Namespace: http\://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity  

## Used By
[GetAuctionInsightData](getauctioninsightdata.md)  
