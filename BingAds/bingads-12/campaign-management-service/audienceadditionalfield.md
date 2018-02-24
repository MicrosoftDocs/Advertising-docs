---
title: AudienceAdditionalField Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a list of optional Audience properties that you can request when calling GetAudiencesByIds.
---
# AudienceAdditionalField Value Set - Campaign Management

> [!IMPORTANT]
> This v12 preview documentation is subject to change.

Defines a list of optional [Audience](/bingads/campaign-management-service/audience.md) properties that you can request when calling [GetAudiencesByIds](/bingads/campaign-management-service/getaudiencesbyids.md). This set of flags enables you to get the latest features using the current version of Bing Ads Campaign Management API, and in the next version the corresponding propertys will be included in the [Audience](/bingads/campaign-management-service/audience.md) object by default.

## Syntax
```xml
<xs:simpleType name="AudienceAdditionalField" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:list>
    <xs:simpleType>
      <xs:restriction base="xs:string">
        <xs:enumeration value="SearchSize" />
      </xs:restriction>
    </xs:simpleType>
  </xs:list>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="searchsize"></a>SearchSize|Request that the *SearchSize* element be included within each returned [Audience](/bingads/campaign-management-service/audience.md) object.|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[GetAudiencesByIds](getaudiencesbyids.md)  
