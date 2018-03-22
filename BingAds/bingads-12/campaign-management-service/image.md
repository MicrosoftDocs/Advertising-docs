---
title: Image Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an image object that can be added to an account's media library.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# Image Data Object - Campaign Management
Defines an image object that can be added to an account's media library.

The *Image* object derives from the *Media* object. For a list of the inherited elements, see the [Media](media.md) object.

## Syntax
```xml
<xs:complexType name="Image" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:Media">
      <xs:sequence>
        <xs:element name="Data" nillable="true" type="xs:string" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="data"></a>Data|A base64 string that represents the image or icon to add to the library. The base64 string can contain a maximum of 102,400 characters.<br /><br />For information about restrictions and supported data types, see [Remarks](#remarks) below.|**string**|

The [Image](image.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementsmedia"></a>Inherited Elements from Media
The [Image](image.md) object derives from the [Media](media.md) object, and inherits the following elements. The descriptions below are specific to [Image](image.md), and might not apply to other objects that inherit the same elements from the [Media](media.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="id"></a>Id|The unique Bing Ads identifier of the media.<br/><br/>**Add:** Read-only|**long**|
|<a name="mediatype"></a>MediaType|The type of media to add to the library.<br /><br />For media that will be used with a [LocationAdExtension](locationadextension.md), the supported values are *Icon* and *Image*.<br /><br />For media that will be used with an [ImageAdExtension](imageadextension.md), the supported values are *Image16x9*, *Image15x10*, *Image4x3*, and *Image12x10*.<br /><br />For more information about supported aspect ratios, see the [Remarks](#remarks) section below.<br/><br/>**Add:** Required|**string**|
|<a name="type"></a>Type|The media type. For more information about media types, see the [Media Data Object Remarks](media.md#remarks).<br/><br/>**Add:** Read-only|**string**|

## <a name="remarks"></a>Remarks
The following MIME types are supported for the *Data* element of the *Image* data object.
-   GIF  
-   JPEG  
-   PNG  

Images with animation are not supported.

The following restrictions apply to [Media](media.md) that will be used with a [LocationAdExtension](locationadextension.md).

-   If the value of the *Type* element is *Icon*, the maximum supported icon size is 26X26.  
-   If the value of the *Type* element is *Image*, the maximum supported image size is 125X125.  

The following restrictions apply to [Media](media.md) types (aspect ratios) that will be used with an [ImageAdExtension](imageadextension.md).

|Type|Aspect Ratio|Minimum Dimension|Maximum Dimension|
|--------|----------------|---------------------|---------------------|
|*Image16x9*|16:9|640 width x 360 height, in pixels|1778 width x 1000 height, in pixels|
|*Image15x10*|1.5:1|300 width x 200 height, in pixels|1500 width x 1000 height, in pixels|
|*Image4x3*|4:3|100 width x 75 height, in pixels|1333 width x 1000 height, in pixels|
|*Image12x10*|1.2:1|300 width x 250 height, in pixels|1200 width x 1000 height, in pixels|

> [!NOTE]
> The maximum file size is 5 MB, but the recommended maximum file size is 1MB.

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

