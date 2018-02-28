---
title: AdRotation Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an object that specifies the type of ad rotation to apply to the ad group.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change.

# AdRotation Data Object - Campaign Management
Defines an object that specifies the type of ad rotation to apply to the ad group.

## Syntax
```xml
<xs:complexType name="AdRotation" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="EndDate" nillable="true" type="xs:dateTime" />
    <xs:element minOccurs="0" name="StartDate" nillable="true" type="xs:dateTime" />
    <xs:element minOccurs="0" name="Type" nillable="true" type="tns:AdRotationType" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="enddate"></a>EndDate|Reserved for future use only. Must be null.|**dateTime**|
|<a name="startdate"></a>StartDate|Reserved for future use only. Must be null.|**dateTime**|
|<a name="type"></a>Type|The type of ad rotation to apply to the ad group.<br /><br />Possible values are *OptimizeForClicks* and *RotateAdsEvenly*.<br/><br/>**Add:** Optional. If not specified, the default value is *OptimizeForClicks*.<br/>**Update:** Optional|[AdRotationType](adrotationtype.md)|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[AdGroup](adgroup.md)  
