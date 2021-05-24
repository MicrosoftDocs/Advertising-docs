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
        <xs:element minOccurs="0" name="SubType" nillable="true" type="xs:string" />
        <xs:element minOccurs="0" name="ThumbnailImage" nillable="true" type="tns:ImageAsset" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

The [VideoAsset](videoasset.md) object has the following elements: [SubType](#subtype), [ThumbnailImage](#thumbnailimage).

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="subtype"></a>SubType|Reserved.|**string**|
|<a name="thumbnailimage"></a>ThumbnailImage|Reserved.|[ImageAsset](imageasset.md)|

The [VideoAsset](videoasset.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementsasset"></a>Inherited Elements from Asset
The [VideoAsset](videoasset.md) object derives from the [Asset](asset.md) object, and inherits the following elements: [Id](#id), [Name](#name), [Type](#type). The descriptions below are specific to [VideoAsset](videoasset.md), and might not apply to other objects that inherit the same elements from the [Asset](asset.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="id"></a>Id|The unique Microsoft Advertising identifier for the asset in a Microsoft Advertising account.<br/><br/>The same image asset identifier can be used multiple times in the same ad for different aspect ratios, and can also be used by multiple ads in the same Microsoft Advertising account.<br/><br/>**Add:** Read-only. Even if the asset already exists and you specify an invalid identifier, this value will be ignored.<br/>**Update:** Read-only. Even if the asset already exists and you specify an invalid identifier, this value will be ignored.|**long**|
|<a name="name"></a>Name|Reserved for future use.|**string**|
|<a name="type"></a>Type|The type of the asset. This value is *VideoAsset* when you retrieve a video asset. For more information about asset types, see the [Asset Data Object Remarks](asset.md#remarks).<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**string**|

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

