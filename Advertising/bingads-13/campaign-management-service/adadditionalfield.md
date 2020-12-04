---
title: AdAdditionalField Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Reserved.
---
# AdAdditionalField Value Set - Campaign Management
Reserved.

## Syntax
```xml
<xs:simpleType name="AdAdditionalField" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:list>
    <xs:simpleType>
      <xs:restriction base="xs:string">
        <xs:enumeration value="ImpressionTrackingUrls" />
      </xs:restriction>
    </xs:simpleType>
  </xs:list>
</xs:simpleType>
```

## <a name="values"></a>Values

The [AdAdditionalField](adadditionalfield.md) value set has the following values: [ImpressionTrackingUrls](#impressiontrackingurls).

|Value|Description|
|-----------|---------------|
|<a name="impressiontrackingurls"></a>ImpressionTrackingUrls|Reserved.|

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

## Used By
[GetAdsByAdGroupId](getadsbyadgroupid.md)  
[GetAdsByEditorialStatus](getadsbyeditorialstatus.md)  
[GetAdsByIds](getadsbyids.md)  
