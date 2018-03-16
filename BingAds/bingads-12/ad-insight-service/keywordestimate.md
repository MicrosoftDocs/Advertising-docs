---
title: KeywordEstimate Data Object - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: A suggested keyword with minimum and maximum traffic estimates.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# KeywordEstimate Data Object - Ad Insight
A suggested keyword with minimum and maximum traffic estimates. Traffic estimates include average CPC, average position, clicks, CTR, impressions, and total cost.

> [!NOTE]
> The estimates are not a prediction or guarantee of future performance. The estimates can vary depending on the filter criteria you provide in the [GetKeywordTrafficEstimates](getkeywordtrafficestimates.md) service request.

## Syntax
```xml
<xs:complexType name="KeywordEstimate" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="Keyword" nillable="true" type="q7:Keyword" xmlns:q7="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity.Common" />
    <xs:element minOccurs="0" name="Maximum" nillable="true" type="tns:TrafficEstimate" />
    <xs:element minOccurs="0" name="Minimum" nillable="true" type="tns:TrafficEstimate" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="keyword"></a>Keyword|The suggested keyword.|[Keyword](keyword.md)|
|<a name="maximum"></a>Maximum|The maximum traffic estimate.<br/><br/>Traffic estimates include average CPC, average position, clicks, CTR, impressions, and total cost.|[TrafficEstimate](trafficestimate.md)|
|<a name="minimum"></a>Minimum|The minimum traffic estimate.<br/><br/>Traffic estimates include average CPC, average position, clicks, CTR, impressions, and total cost.|[TrafficEstimate](trafficestimate.md)|

## Requirements
Service: [AdInsightService.svc v12](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v12/AdInsightService.svc)  
Namespace: http\://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity  

## Used By
[AdGroupEstimate](adgroupestimate.md)  
