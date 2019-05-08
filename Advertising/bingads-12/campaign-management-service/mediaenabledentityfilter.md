---
title: MediaEnabledEntityFilter Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the possible values representing entities that are enabled for media such as images.
---
# MediaEnabledEntityFilter Value Set - Campaign Management
Defines the possible values representing entities that are enabled for media such as images.

## Syntax
```xml
<xs:simpleType name="MediaEnabledEntityFilter" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:list>
    <xs:simpleType>
      <xs:restriction base="xs:string">
        <xs:enumeration value="ImageAdExtension" />
        <xs:enumeration value="ResponsiveAd" />
      </xs:restriction>
    </xs:simpleType>
  </xs:list>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="imageadextension"></a>ImageAdExtension|The media enabled entity is an [ImageAdExtension](imageadextension.md).|
|<a name="responsivead"></a>ResponsiveAd|The media enabled entity is an [ResponsiveAd](responsivead.md).|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

## Used By
[GetMediaAssociations](getmediaassociations.md)  
[GetMediaMetaDataByAccountId](getmediametadatabyaccountid.md)  
[MediaAssociation](mediaassociation.md)  
