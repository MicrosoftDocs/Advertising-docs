---
title: GeoPoint Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an object that contains the longitude and latitude coordinates of a geographical location.
---
# GeoPoint Data Object - Campaign Management
Defines an object that contains the longitude and latitude coordinates of a geographical location.

## Syntax
```xml
<xs:complexType name="GeoPoint" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element name="LatitudeInMicroDegrees" type="xs:int" />
    <xs:element name="LongitudeInMicroDegrees" type="xs:int" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="latitudeinmicrodegrees"></a>LatitudeInMicroDegrees|The latitude specified in micro degrees. The latitude must be greater than or equal to -85000000 and less than or equal to +85000000.|**int**|
|<a name="longitudeinmicrodegrees"></a>LongitudeInMicroDegrees|The longitude specified in micro degrees. The longitude must be greater than or equal to -180000000 and less than or equal to +180000000.|**int**|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[LocationAdExtension](locationadextension.md)  
