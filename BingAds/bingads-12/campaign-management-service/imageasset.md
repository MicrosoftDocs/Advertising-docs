---
title: ImageAsset Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Reserved.
---
# ImageAsset Data Object - Campaign Management
Reserved.

## Syntax
```xml
<xs:complexType name="ImageAsset" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:Asset">
      <xs:sequence>
        <xs:element minOccurs="0" name="CropHeight" nillable="true" type="xs:int" />
        <xs:element minOccurs="0" name="CropWidth" nillable="true" type="xs:int" />
        <xs:element minOccurs="0" name="CropX" nillable="true" type="xs:int" />
        <xs:element minOccurs="0" name="CropY" nillable="true" type="xs:int" />
        <xs:element minOccurs="0" name="SubType" nillable="true" type="xs:string" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="cropheight"></a>CropHeight|Reserved.|**int**|
|<a name="cropwidth"></a>CropWidth|Reserved.|**int**|
|<a name="cropx"></a>CropX|Reserved.|**int**|
|<a name="cropy"></a>CropY|Reserved.|**int**|
|<a name="subtype"></a>SubType|Reserved.|**string**|

The [ImageAsset](imageasset.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementsasset"></a>Inherited Elements from Asset
The [ImageAsset](imageasset.md) object derives from the [Asset](asset.md) object, and inherits the following elements. The descriptions below are specific to [ImageAsset](imageasset.md), and might not apply to other objects that inherit the same elements from the [Asset](asset.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="id"></a>Id|Reserved.|**long**|
|<a name="name"></a>Name|Reserved.|**string**|
|<a name="type"></a>Type|Reserved.|**string**|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

