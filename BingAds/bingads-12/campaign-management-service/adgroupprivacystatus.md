---
title: AdGroupPrivacyStatus Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Reserved.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change.
# AdGroupPrivacyStatus Value Set - Campaign Management
Reserved.

## Syntax
```xml
<xs:simpleType name="AdGroupPrivacyStatus" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="Unknown" />
    <xs:enumeration value="Active" />
    <xs:enumeration value="TargetingTooNarrow" />
    <xs:enumeration value="Pending" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="active"></a>Active|Reserved.|
|<a name="pending"></a>Pending|Reserved.|
|<a name="targetingtoonarrow"></a>TargetingTooNarrow|Reserved.|
|<a name="unknown"></a>Unknown|Reserved.|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[AdGroup](adgroup.md)  
