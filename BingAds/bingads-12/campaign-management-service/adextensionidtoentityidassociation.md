---
title: AdExtensionIdToEntityIdAssociation Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an object that associates an ad extension to a supported entity, for example ad group or campaign.
---
# AdExtensionIdToEntityIdAssociation Data Object - Campaign Management
Defines an object that associates an ad extension to a supported entity, for example ad group or campaign.

## Syntax
```xml
<xs:complexType name="AdExtensionIdToEntityIdAssociation" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element name="AdExtensionId" type="xs:long" />
    <xs:element name="EntityId" type="xs:long" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adextensionid"></a>AdExtensionId|The system-generated identifier of the ad extension.|**long**|
|<a name="entityid"></a>EntityId|The identifier of an entity associated with the ad extension.|**long**|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

## Used By
[DeleteAdExtensionsAssociations](deleteadextensionsassociations.md)  
[GetAdExtensionsEditorialReasons](getadextensionseditorialreasons.md)  
[SetAdExtensionsAssociations](setadextensionsassociations.md)  
