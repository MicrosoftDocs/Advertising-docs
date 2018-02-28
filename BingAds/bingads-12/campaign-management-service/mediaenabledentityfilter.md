---
title: MediaEnabledEntityFilter Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the possible values representing entities that are enabled for media such as images.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change.

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
|<a name="imageadextension"></a>ImageAdExtension|The media enabled entity is an [ImageAdExtension](../campaign-management-service/imageadextension.md).<br /><br />When you call [GetMediaMetaDataByAccountId](../campaign-management-service/getmediametadatabyaccountid.md) or [GetMediaMetaDataByIds](../campaign-management-service/getmediametadatabyids.md), the service will return exactly three [ImageMediaRepresentation](../campaign-management-service/imagemediarepresentation.md) objects with varying height and width properties.|
|<a name="responsivead"></a>ResponsiveAd|Reserved.|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[GetMediaAssociations](getmediaassociations.md)  
[GetMediaMetaDataByAccountId](getmediametadatabyaccountid.md)  
[MediaAssociation](mediaassociation.md)  
