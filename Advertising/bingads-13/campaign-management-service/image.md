---
title: Image Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an image that can be added to an account's media library.
---
# Image Data Object - Campaign Management
Defines an image that can be added to an account's media library.

## Syntax
```xml
<xs:complexType name="Image" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:Media">
      <xs:sequence>
        <xs:element minOccurs="0" name="Data" nillable="true" type="xs:string" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

The [Image](image.md) object has the following elements: [Data](#data).

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="data"></a>Data|A base64 string that represents the image or icon to add to the library. The base64 string can contain a maximum of 102,400 characters.<br/><br/>For information about restrictions and supported data types, see [Remarks](#remarks) below.|**string**|

The [Image](image.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementsmedia"></a>Inherited Elements from Media
The [Image](image.md) object derives from the [Media](media.md) object, and inherits the following elements: [Id](#id), [MediaType](#mediatype), [Type](#type). The descriptions below are specific to [Image](image.md), and might not apply to other objects that inherit the same elements from the [Media](media.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="id"></a>Id|The unique Microsoft Advertising identifier of the media.<br/><br/>**Add:** Read-only|**long**|
|<a name="mediatype"></a>MediaType|The type of media to add to the library.<br/><br/>For media that will be used with an [ImageAdExtension](imageadextension.md), the supported values are *Image16x9*, *Image15x10*, *Image4x3*, and *Image12x10*.<br/><br/>For media that will be used with a [ResponsiveAd](responsivead.md), the supported values are *Image1x1*, *Image191x100*, and *Image4x1*.<br/><br/>For more information about supported aspect ratios, see the [Remarks](#remarks) section below.<br/><br/>**Add:** Required|**string**|
|<a name="type"></a>Type|The media type. For more information about media types, see the [Media Data Object Remarks](media.md#remarks).<br/><br/>**Add:** Read-only|**string**|

## <a name="remarks"></a>Remarks
The following MIME types are supported for the *Data* element of the *Image* data object.
- GIF  
- JPEG  
- PNG  

> [!TIP]
> The PNG images are converted to JPEG. If you are not satisfied with the quality after conversion, we recommend that you provide JPEG directly. 

Images with animation are not supported. 

### <a name="imageadextension"></a>Image Ad Extension Image Media
The following restrictions apply to [Media](media.md) types (aspect ratios) that can be used with an [ImageAdExtension](imageadextension.md).

|MediaType|Aspect Ratio|Minimum Dimension|Maximum Dimension|
|--------|----------------|---------------------|---------------------|
|Image16x9|16:9|640 width x 360 height, in pixels|1778 width x 1000 height, in pixels|
|Image15x10|1.5:1|300 width x 200 height, in pixels|1500 width x 1000 height, in pixels|
|Image4x3|4:3|100 width x 75 height, in pixels|1333 width x 1000 height, in pixels|
|Image12x10|1.2:1|300 width x 250 height, in pixels|1200 width x 1000 height, in pixels|

### <a name="responsivead"></a>Responsive Ad Image Media
The following restrictions apply to [Media](media.md) types (aspect ratios) that can be used with a [ResponsiveAd](responsivead.md). Although you can only add media with the below aspect ratios to your account level media library, you can use [ImageAsset](imageasset.md) crop settings to determine the effective aspect ratio in the context of each responsive ad. The aspect ratio of the stored image would be unchanged in the account level media library. For more information, see [ResponsiveAd Remarks](responsivead.md#remarks). 

|MediaType|Dimensions in pixels|
|--------|--------|--------|--------|
|Image191x100|**Minimum:** 703 width x 368 height<br/>**Maximum:** Aspect radio 1.91:1<br/>**Recommended:** 1200 width x 628 height|
|Image4x1|**Minimum:** 512 width x 128 height<br/>**Maximum:** Aspect radio 4:1<br/>**Recommended:** 1200 width x 300 height|
|Image1x1|**Minimum:** 300 width x 300 height<br/>**Maximum:** Aspect radio 1:1<br/>**Recommended:** 1200 width x 1200 height|
|Image1x1|**Minimum:** 128 width x 128 height<br/>**Maximum:** Aspect radio 1:1<br/>**Recommended:** 1200 width x 1200 height|

> [!NOTE]
> The maximum width and height in pixels are 2592 and 2048 independently, and you must still maintain one of the supported aspect ratios. For example if the image asset with sub type LandscapeImageMedia is 2592 in width, then the height must be 1357.

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

