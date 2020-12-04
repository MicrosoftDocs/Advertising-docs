---
title: AuctionInsightKpiAdditionalField Value Set - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Reserved.
---
# AuctionInsightKpiAdditionalField Value Set - Ad Insight
Reserved.

## Syntax
```xml
<xs:simpleType name="AuctionInsightKpiAdditionalField" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:list>
    <xs:simpleType>
      <xs:restriction base="xs:string">
        <xs:enumeration value="AbsoluteTopOfPageRate" />
      </xs:restriction>
    </xs:simpleType>
  </xs:list>
</xs:simpleType>
```

## <a name="values"></a>Values

The [AuctionInsightKpiAdditionalField](auctioninsightkpiadditionalfield.md) value set has the following values: [AbsoluteTopOfPageRate](#absolutetopofpagerate).

|Value|Description|
|-----------|---------------|
|<a name="absolutetopofpagerate"></a>AbsoluteTopOfPageRate|Reserved.|

## Requirements
Service: [AdInsightService.svc v13](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v13/AdInsightService.svc)  
Namespace: https\://bingads.microsoft.com/AdInsight/v13  

## Used By
[GetAuctionInsightData](getauctioninsightdata.md)  
