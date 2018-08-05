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

> [!NOTE]
> Not everyone is enabled for Audience campaigns in the Microsoft Audience Network yet. If you don't, don't worry. It's coming soon. 

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
|<a name="imageadextension"></a>ImageAdExtension|The media enabled entity is an [ImageAdExtension](imageadextension.md).<br/><br/>When you call [GetMediaMetaDataByAccountId](getmediametadatabyaccountid.md) or [GetMediaMetaDataByIds](getmediametadatabyids.md), the service will return exactly three [ImageMediaRepresentation](imagemediarepresentation.md) objects with varying height and width properties.|
|<a name="responsivead"></a>ResponsiveAd|The media enabled entity is an [ResponsiveAd](responsivead.md).<br/><br/>When you call [GetMediaMetaDataByAccountId](getmediametadatabyaccountid.md) or [GetMediaMetaDataByIds](getmediametadatabyids.md), the service will return exactly one [ImageMediaRepresentation](imagemediarepresentation.md) object.|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[GetMediaAssociations](getmediaassociations.md)  
[GetMediaMetaDataByAccountId](getmediametadatabyaccountid.md)  
[MediaAssociation](mediaassociation.md)  
