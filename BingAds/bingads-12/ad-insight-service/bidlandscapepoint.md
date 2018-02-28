---
title: BidLandscapePoint Data Object - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an object that contains estimates of clicks, cost, and impressions  given the suggested bid.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change.

# BidLandscapePoint Data Object - Ad Insight
Defines an object that contains estimates of clicks, cost, and impressions  given the suggested bid.

> [!NOTE]
> The estimates are not a prediction or guarantee of future performance. Estimates are for search traffic only, and not based on performance for ads on the content network.

## Syntax
```xml
<xs:complexType name="BidLandscapePoint" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="Bid" type="xs:double" />
    <xs:element minOccurs="0" name="Clicks" nillable="true" type="xs:double" />
    <xs:element minOccurs="0" name="Impressions" type="xs:long" />
    <xs:element minOccurs="0" name="TopImpressions" nillable="true" type="xs:long" />
    <xs:element minOccurs="0" name="Currency" type="tns:Currency" />
    <xs:element minOccurs="0" name="Cost" nillable="true" type="xs:double" />
    <xs:element minOccurs="0" name="MarginalCPC" nillable="true" type="xs:double" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="bid"></a>Bid|The suggested bid value.|**double**|
|<a name="clicks"></a>Clicks|The estimated number of clicks.<br /><br /> This element will be nil if there is no estimate available.|**double**|
|<a name="cost"></a>Cost|The estimated cost.<br /><br /> This element will be nil if there is no estimate available.|**double**|
|<a name="currency"></a>Currency|The monetary unit of the suggested bid value and estimated performance statistics.|[Currency](currency.md)|
|<a name="impressions"></a>Impressions|The estimated number of impressions.|**long**|
|<a name="marginalcpc"></a>MarginalCPC|Reserved for future use.|**double**|
|<a name="topimpressions"></a>TopImpressions|The estimated number of impressions in the top or mainline ad results.<br /><br /> This element will be nil if there is no estimate available.|**long**|

## Requirements
Service: [AdInsightService.svc v11](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: http\://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity  

## Used By
[AdGroupBidLandscape](adgroupbidlandscape.md)  
[KeywordBidLandscape](keywordbidlandscape.md)  
