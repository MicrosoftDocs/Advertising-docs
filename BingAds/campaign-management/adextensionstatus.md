---
title: AdExtensionStatus Value Set
ms.service: bing-ads-campaign-management
ms.topic: article
author: eric-urban
ms.author: eur
---
# AdExtensionStatus Value Set
Defines the possible status values of an ad extension.

## Syntax
```xml
<xs:simpleType name="AdExtensionStatus" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="Active" />
    <xs:enumeration value="Deleted" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="active"></a>Active|The ad extension is active. You can associate an active ad extension with a campaign or ad group.|
|<a name="deleted"></a>Deleted|The ad extension is deleted. This status is for internal use only. The Get operations will not include deleted extensions.|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[AdExtension](adextension.md)  
