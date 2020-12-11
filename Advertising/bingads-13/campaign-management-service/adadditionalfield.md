---
title: AdAdditionalField Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a list of optional ad properties that you can request when calling GetAdsByAdGroupId, GetAdsByEditorialStatus, and GetAdsByIds.
---
# AdAdditionalField Value Set - Campaign Management
Defines a list of optional ad properties that you can request when calling [GetAdsByAdGroupId](getadsbyadgroupid.md#returnadditionalfields), [GetAdsByEditorialStatus](getadsbyeditorialstatus.md#returnadditionalfields), and [GetAdsByIds](getadsbyids.md#returnadditionalfields). The additional field values enable you to get the latest features using the current version of Campaign Management API, and in the next version the corresponding properties will be included in the ad by default.  

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
|<a name="impressiontrackingurls"></a>ImpressionTrackingUrls|Request that the [ImpressionTrackingUrls](responsivead.md#impressiontrackingurls) element be included within each returned [ResponsiveAd](responsivead.md) object.|

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

## Used By
[GetAdsByAdGroupId](getadsbyadgroupid.md)  
[GetAdsByEditorialStatus](getadsbyeditorialstatus.md)  
[GetAdsByIds](getadsbyids.md)  
