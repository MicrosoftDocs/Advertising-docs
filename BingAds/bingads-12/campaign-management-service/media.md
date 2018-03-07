---
title: Media Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the base object of media.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change.

# Media Data Object - Campaign Management
Defines the base object of media.

Do not try to instantiate a *Media*. You can create the following object that derives from it.
-   [Image](image.md)  

## Syntax
```xml
<xs:complexType name="Media" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="Id" nillable="true" type="xs:long" />
    <xs:element minOccurs="0" name="MediaType" nillable="true" type="xs:string" />
    <xs:element name="Type" nillable="true" type="xs:string" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="id"></a>Id|The unique Bing Ads identifier of the media.<br/><br/>**Add:** Read-only|**long**|
|<a name="mediatype"></a>MediaType|The media type. For more information about media types, see [Remarks](#remarks) below.<br/><br/>**Add:** Read-only|**string**|
|<a name="type"></a>Type|The type of media to add to the media library.<br /><br />For media that will be used with a [LocationAdExtension](locationadextension.md), the supported values are *Icon* and *Image*.<br /><br />For media that will be used with an [ImageAdExtension](imageadextension.md), the supported values are *Image16x9*, *Image15x10*, *Image4x3*, and *Image12x10*.<br /><br />For more information about supported aspect ratios, see the [Image Data Object Remarks](image.md#remarks).<br/><br/>**Add:** Required|**string**|

## <a name="remarks"></a>Remarks
For Java and the .NET languages, do not set the *MediaType* element because the value is determined when you instantiate an image.

If you generate the SOAP manually, use the *type* attribute of the `<Media>` node as shown in the following example, to specify that the media is an image.

> [!NOTE]
> Images and icons are both created as [Image](image.md) objects. 

```xml
<Media xmlns:i="http://www.w3.org/2001/XMLSchema-instance">
  <Media i:type="Image">
    <Id i:nil="true" />
    <MediaType>Image</MediaType>
    <Type>Icon</Type>
    <Data>IconDataGoesHere</Data>
  </Media>
  <Media i:type="Image">
    <Id i:nil="true" />
    <MediaType>Image</MediaType>
    <Type>Image15x10</Type>
    <Data>ImageDataGoesHere</Data>
  </Media>
</Media>
```

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[AddMedia](addmedia.md)  
[GetMediaByIds](getmediabyids.md)  
