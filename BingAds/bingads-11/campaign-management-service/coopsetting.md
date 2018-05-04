---
title: CoOpSetting Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Reserved.
---
# CoOpSetting Data Object - Campaign Management
Reserved.

## Syntax
```xml
<xs:complexType name="CoOpSetting" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:Setting">
      <xs:sequence>
        <xs:element minOccurs="0" name="BidBoostValue" nillable="true" type="xs:double" />
        <xs:element minOccurs="0" name="BidMaxValue" nillable="true" type="xs:double" />
        <xs:element minOccurs="0" name="BidOption" nillable="true" type="tns:BidOption" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="bidboostvalue"></a>BidBoostValue|Reserved.|**double**|
|<a name="bidmaxvalue"></a>BidMaxValue|Reserved.|**double**|
|<a name="bidoption"></a>BidOption|Reserved.|[BidOption](bidoption.md)|

The [CoOpSetting](coopsetting.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementssetting"></a>Inherited Elements from Setting
The [CoOpSetting](coopsetting.md) object derives from the [Setting](setting.md) object, and inherits the following elements. The descriptions below are specific to [CoOpSetting](coopsetting.md), and might not apply to other objects that inherit the same elements from the [Setting](setting.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="type"></a>Type|Reserved.|**string**|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

