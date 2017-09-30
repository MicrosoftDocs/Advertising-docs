---
title: ImageMediaRepresentation Data Object
ms.service: bing-ads-campaign-management
ms.topic: article
author: eric-urban
ms.author: eur
---
# ImageMediaRepresentation Data Object
Defines an image media representation with height and width.

## Syntax
```xml
<xs:complexType name="ImageMediaRepresentation" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:MediaRepresentation">
      <xs:sequence>
        <xs:element minOccurs="0" name="Height" type="xs:int" />
        <xs:element minOccurs="0" name="Width" type="xs:int" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="height"></a>Height|The height of the image in pixels. For more information, see [Remarks](#remarks) below.|**int**|
|<a name="width"></a>Width|The width of the image in pixels. For more information, see [Remarks](#remarks) below.|**int**|

The [ImageMediaRepresentation](imagemediarepresentation.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementsmediarepresentation"></a>Inherited Elements from MediaRepresentation
The [ImageMediaRepresentation](imagemediarepresentation.md) object derives from the [MediaRepresentation](mediarepresentation.md) object, and inherits the following elements. The descriptions below are specific to [ImageMediaRepresentation](imagemediarepresentation.md), and might not apply to other objects that inherit the same elements from the [MediaRepresentation](mediarepresentation.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="name"></a>Name|The name of the media representation.<br /><br />For [ImageMediaRepresentation](../campaign-management/imagemediarepresentation.md), the possible values are *Preview*, *Thumbnail*, and *Original*.|**string**|
|<a name="type"></a>Type|The type of the media representation. This value is *ImageMediaRepresentation* when you retrieve a image media representation. |**string**|
|<a name="url"></a>Url|The media download URL.|**string**|

## <a name="remarks"></a>Remarks
Bing Ads stores three representations for each image media of varying height and width.

|Description|Width|Height|
|---------------|---------|----------|
|Thumbnail|120|68|
|Preview|160|90|
|Original size that you uploaded using the [AddMedia](../campaign-management/addmedia.md) service operation.|For dimension restrictions, please see [Image](../campaign-management/image.md).|For dimension restrictions, please see [Image](../campaign-management/image.md).|.

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https://bingads.microsoft.com/CampaignManagement/v11  

