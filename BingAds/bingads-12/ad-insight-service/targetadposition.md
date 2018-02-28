---
title: TargetAdPosition Value Set - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the possible positions where you can target an ad to appear in the search results or on a content-based webpage.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change.
# TargetAdPosition Value Set - Ad Insight
Defines the possible positions where you can target an ad to appear in the search results or on a content-based webpage.

## Syntax
```xml
<xs:simpleType name="TargetAdPosition" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="MainLine1" />
    <xs:enumeration value="MainLine" />
    <xs:enumeration value="SideBar" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="mainline"></a>MainLine|Target the second, third, and fourth positions at the top of the search results page.|
|<a name="mainline1"></a>MainLine1|Target the first position at the top of the search results page.|
|<a name="sidebar"></a>SideBar|Target any position on the right side of the search results page.|

## Requirements
Service: [AdInsightService.svc v11](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: Microsoft.Advertiser.AdInsight.Api.Service.V11  

## Used By
[GetEstimatedBidByKeywordIds](getestimatedbidbykeywordids.md)  
[GetEstimatedBidByKeywords](getestimatedbidbykeywords.md)  
