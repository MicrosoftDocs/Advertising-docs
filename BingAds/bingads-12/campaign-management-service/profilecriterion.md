---
title: ProfileCriterion Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Reserved.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change.

# ProfileCriterion Data Object - Campaign Management
Reserved.

## Syntax
```xml
<xs:complexType name="ProfileCriterion" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:Criterion">
      <xs:sequence>
        <xs:element minOccurs="0" name="ProfileId" type="xs:long" />
        <xs:element minOccurs="0" name="ProfileType" type="tns:ProfileType" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="profileid"></a>ProfileId|Reserved.|**long**|
|<a name="profiletype"></a>ProfileType|Reserved.|[ProfileType](profiletype.md)|

The [ProfileCriterion](profilecriterion.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementscriterion"></a>Inherited Elements from Criterion
The [ProfileCriterion](profilecriterion.md) object derives from the [Criterion](criterion.md) object, and inherits the following elements. The descriptions below are specific to [ProfileCriterion](profilecriterion.md), and might not apply to other objects that inherit the same elements from the [Criterion](criterion.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="type"></a>Type|Reserved.|**string**|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

