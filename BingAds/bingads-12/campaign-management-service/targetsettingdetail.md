---
title: TargetSettingDetail Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Reserved.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change.
# TargetSettingDetail Data Object - Campaign Management
Reserved.

## Syntax
```xml
<xs:complexType name="TargetSettingDetail" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="CriterionTypeGroup" type="tns:CriterionTypeGroup" />
    <xs:element minOccurs="0" name="TargetAll" type="xs:boolean" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="criteriontypegroup"></a>CriterionTypeGroup|Reserved.|[CriterionTypeGroup](criteriontypegroup.md)|
|<a name="targetall"></a>TargetAll|Reserved.|**boolean**|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[TargetSetting](targetsetting.md)  
