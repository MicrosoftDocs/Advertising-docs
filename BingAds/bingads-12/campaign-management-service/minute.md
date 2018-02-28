---
title: Minute Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the possible minute values for ad extension scheduling or day and time criterion.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change.

# Minute Value Set - Campaign Management
Defines the possible minute values for ad extension scheduling or day and time criterion.

## Syntax
```xml
<xs:simpleType name="Minute" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:annotation>
    <xs:appinfo>
      <ActualType Name="short" Namespace="http://www.w3.org/2001/XMLSchema" xmlns="http://schemas.microsoft.com/2003/10/Serialization/" />
    </xs:appinfo>
  </xs:annotation>
  <xs:restriction base="xs:string">
    <xs:enumeration value="Zero" />
    <xs:enumeration value="Fifteen" />
    <xs:enumeration value="Thirty" />
    <xs:enumeration value="FortyFive" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="fifteen"></a>Fifteen|The starting or ending minute of the hour range is fifteen.|
|<a name="fortyfive"></a>FortyFive|The starting or ending minute of the hour range is forty-five.|
|<a name="thirty"></a>Thirty|The starting or ending minute of the hour range is thirty.|
|<a name="zero"></a>Zero|The starting or ending minute of the hour range is zero.|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[DayTime](daytime.md)  
[DayTimeCriterion](daytimecriterion.md)  
