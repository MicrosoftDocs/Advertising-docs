---
title: VideoAsset Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the VideoAsset Data Object.
---
# VideoAsset Data Object - Campaign Management
Defines the VideoAsset Data Object.

## Syntax
```xml
<xs:complexType name="VideoAsset" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:Asset">
      <xs:sequence>
        <xs:element minOccurs="0" name="DefaultThumbnailUrl" nillable="true" type="xs:string" />
        <xs:element minOccurs="0" name="DownloadUrl" nillable="true" type="xs:string" />
        <xs:element minOccurs="0" name="DurationInMilliseconds" nillable="true" type="xs:int" />
        <xs:element minOccurs="0" name="Height" nillable="true" type="xs:int" />
        <xs:element minOccurs="0" name="Status" nillable="true" type="xs:string" />
        <xs:element minOccurs="0" name="SubType" nillable="true" type="xs:string" />
        <xs:element minOccurs="0" name="ThumbnailImage" nillable="true" type="tns:ImageAsset" />
        <xs:element minOccurs="0" name="Url" nillable="true" type="xs:string" />
        <xs:element minOccurs="0" name="Width" nillable="true" type="xs:int" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

The [VideoAsset](videoasset.md) object has the following elements: [DefaultThumbnailUrl](#defaultthumbnailurl), [DownloadUrl](#downloadurl), [DurationInMilliseconds](#durationinmilliseconds), [Height](#height), [Status](#status), [SubType](#subtype), [ThumbnailImage](#thumbnailimage), [Url](#url), [Width](#width).

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="defaultthumbnailurl"></a>DefaultThumbnailUrl|Reserved.|**string**|
|<a name="downloadurl"></a>DownloadUrl|Reserved.|**string**|
|<a name="durationinmilliseconds"></a>DurationInMilliseconds|Reserved.|**int**|
|<a name="height"></a>Height|Reserved.|**int**|
|<a name="status"></a>Status|Reserved.|**string**|
|<a name="subtype"></a>SubType|Reserved.|**string**|
|<a name="thumbnailimage"></a>ThumbnailImage|Reserved.|[ImageAsset](imageasset.md)|
|<a name="url"></a>Url|Reserved.|**string**|
|<a name="width"></a>Width|Reserved.|**int**|

The [VideoAsset](videoasset.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementsasset"></a>Inherited Elements from Asset
The [VideoAsset](videoasset.md) object derives from the [Asset](asset.md) object, and inherits the following elements: [Id](#id), [Name](#name), [Type](#type). The descriptions below are specific to [VideoAsset](videoasset.md), and might not apply to other objects that inherit the same elements from the [Asset](asset.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="id"></a>Id|Reserved.|**long**|
|<a name="name"></a>Name|Reserved.|**string**|
|<a name="type"></a>Type|Reserved.|**string**|

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

