---
title: ImportEntityType Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Reserved.
---
# ImportEntityType Value Set - Campaign Management
Reserved.

## Syntax
```xml
<xs:simpleType name="ImportEntityType" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="Unknown" />
    <xs:enumeration value="Campaign" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

The [ImportEntityType](importentitytype.md) value set has the following values: [Campaign](#campaign), [Unknown](#unknown).

|Value|Description|
|-----------|---------------|
|<a name="campaign"></a>Campaign|Reserved.|
|<a name="unknown"></a>Unknown|Reserved.|

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

## Used By
[GetImportEntityIdsMapping](getimportentityidsmapping.md)  
