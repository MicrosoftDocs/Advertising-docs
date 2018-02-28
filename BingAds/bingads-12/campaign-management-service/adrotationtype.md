---
title: AdRotationType Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the possible ad rotation types that you can apply to an ad group.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change.
# AdRotationType Value Set - Campaign Management
Defines the possible ad rotation types that you can apply to an ad group. For ad groups with more than one ad, these options determine how the ads are rotated into the auction.

## Syntax
```xml
<xs:simpleType name="AdRotationType" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="OptimizeForClicks" />
    <xs:enumeration value="RotateAdsEvenly" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="optimizeforclicks"></a>OptimizeForClicks|Favor the best performing ads.<br /><br />This is the default.|
|<a name="rotateadsevenly"></a>RotateAdsEvenly|Rotate ads evenly into the auction.|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[AdRotation](adrotation.md)  
