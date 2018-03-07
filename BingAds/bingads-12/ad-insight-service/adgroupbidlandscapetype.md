---
title: AdGroupBidLandscapeType Value Set - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the possible values that indicate whether all or a subset of an ad group's existing keywords are used to determine the bid landscape.
---
# AdGroupBidLandscapeType Value Set - Ad Insight
Defines the possible values that indicate whether all or a subset of an ad group's existing keywords are used to determine the bid landscape.

## Syntax
```xml
<xs:simpleType name="AdGroupBidLandscapeType" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="Uniform" />
    <xs:enumeration value="DefaultBidOnly" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="defaultbidonly"></a>DefaultBidOnly|Only existing keywords that use the ad group's default bid are used to determine the bid landscape.|
|<a name="uniform"></a>Uniform|All of an ad group's existing keywords are used to determine the bid landscape.|

## Requirements
Service: [AdInsightService.svc v12](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: Microsoft.Advertiser.AdInsight.Api.Service.V12  

## Used By
[AdGroupBidLandscape](adgroupbidlandscape.md)  
[AdGroupBidLandscapeInput](adgroupbidlandscapeinput.md)  
