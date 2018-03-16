---
title: MediaMetaData Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a media meta data object.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# MediaMetaData Data Object - Campaign Management
Defines a media meta data object. The meta data includes download Urls for one or more media representations.

## Syntax
```xml
<xs:complexType name="MediaMetaData" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element name="Id" type="xs:long" />
    <xs:element minOccurs="0" name="MediaType" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="Representations" nillable="true" type="tns:ArrayOfMediaRepresentation" />
    <xs:element minOccurs="0" name="Type" nillable="true" type="xs:string" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="id"></a>Id|The system identifier of the media meta data.|**long**|
|<a name="mediatype"></a>MediaType|The name of the media subclass.<br /><br />For an [ImageMediaRepresentation](imagemediarepresentation.md), the *MediaType* is *Image*.|**string**|
|<a name="representations"></a>Representations|An array of *MediaRepresentation*-derived objects, for example [ImageMediaRepresentation](imagemediarepresentation.md), that each include download Urls for one or more media representations. The number of representations depends on the type of media. For example media for image ad extensions  have multiple height and width representations, and you can access each individually. For more information see [MediaEnabledEntityFilter](mediaenabledentityfilter.md).|[MediaRepresentation](mediarepresentation.md) array|
|<a name="type"></a>Type|The type of media in the library.<br /><br />For an [ImageMediaRepresentation](imagemediarepresentation.md),  the only possible value is *Image*.|**string**|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

## Used By
[GetMediaMetaDataByAccountId](getmediametadatabyaccountid.md)  
[GetMediaMetaDataByIds](getmediametadatabyids.md)  
