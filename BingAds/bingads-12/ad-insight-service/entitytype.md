---
title: EntityType Value Set - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the entity types for retrieving auction insights.
---
# EntityType Value Set - Ad Insight
Defines the entity types for retrieving auction insights.

> [!NOTE]
> Reserved for future use.

## Syntax
```xml
<xs:simpleType name="EntityType" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="Account">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">1</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="Campaign">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">2</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="AdGroup">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">3</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="Keyword">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">4</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="account"></a>Account|Request account level auction insight data.|
|<a name="adgroup"></a>AdGroup||Request ad group level auction insight data.|
|<a name="campaign"></a>Campaign||Request campaign level auction insight data.|
|<a name="keyword"></a>Keyword||Request keyword level auction insight data.|

## Requirements
Service: [AdInsightService.svc v12](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v12/AdInsightService.svc)  
Namespace: Microsoft.Advertiser.AdInsight.Api.Service.V12  

## Used By
[GetAuctionInsightData](getauctioninsightdata.md)  
