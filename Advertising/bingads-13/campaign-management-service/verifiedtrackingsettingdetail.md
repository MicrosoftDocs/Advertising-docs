---
title: VerifiedTrackingSettingDetail Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the VerifiedTrackingSettingDetail Data Object.
---
# VerifiedTrackingSettingDetail Data Object - Campaign Management
Defines the VerifiedTrackingSettingDetail Data Object.

## Syntax
```xml
<xs:complexType name="VerifiedTrackingSettingDetail" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="VerifiedTrackingData" nillable="true" type="q8:ArrayOfKeyValuePairOfstringstring" xmlns:q8="http://schemas.datacontract.org/2004/07/System.Collections.Generic" />
    <xs:element minOccurs="0" name="VerifiedTrackingVendor" nillable="true" type="xs:string" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

The [VerifiedTrackingSettingDetail](verifiedtrackingsettingdetail.md) object has the following elements: [VerifiedTrackingData](#verifiedtrackingdata), [VerifiedTrackingVendor](#verifiedtrackingvendor).

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="verifiedtrackingdata"></a>VerifiedTrackingData|Reserved.|[KeyValuePairOfstringstring](keyvaluepairofstringstring.md) array|
|<a name="verifiedtrackingvendor"></a>VerifiedTrackingVendor|Reserved.|**string**|

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

## Used By
[VerifiedTrackingSetting](verifiedtrackingsetting.md)  
