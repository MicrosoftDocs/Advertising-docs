---
title: DistanceUnit Value Set
ms.service: bing-ads-campaign-management
ms.topic: article
author: eric-urban
ms.author: eur
---
# DistanceUnit Value Set
Defines the possible distance units of a geographical location.

## Syntax
```xml
<xs:simpleType name="DistanceUnit" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:annotation>
    <xs:appinfo>
      <ActualType Name="short" Namespace="http://www.w3.org/2001/XMLSchema" xmlns="http://schemas.microsoft.com/2003/10/Serialization/" />
    </xs:appinfo>
  </xs:annotation>
  <xs:restriction base="xs:string">
    <xs:enumeration value="Miles" />
    <xs:enumeration value="Kilometers" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="kilometers"></a>Kilometers|The distance of the specified geographical location is specified in kilometers.|
|<a name="miles"></a>Miles|The distance of the specified geographical location is specified in miles.|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[RadiusCriterion](radiuscriterion.md)  
