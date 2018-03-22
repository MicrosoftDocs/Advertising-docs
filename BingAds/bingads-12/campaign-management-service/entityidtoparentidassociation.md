---
title: EntityIdToParentIdAssociation Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an object that contains the unique system identifier of an entity such as ad or keyword, and the identifier of its parent.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# EntityIdToParentIdAssociation Data Object - Campaign Management
Defines an object that contains the unique system identifier of an entity such as ad or keyword, and the identifier of its parent. An ad group is the parent of an ad or keyword.

## Syntax
```xml
<xs:complexType name="EntityIdToParentIdAssociation" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="EntityId" type="xs:long" />
    <xs:element minOccurs="0" name="ParentId" type="xs:long" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="entityid"></a>EntityId|The system-generated unique identifier of an entity such as ad or keyword.|**long**|
|<a name="parentid"></a>ParentId|The identifier of the entity's parent. An ad group is the parent of an ad or keyword.|**long**|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

## Used By
[AppealEditorialRejections](appealeditorialrejections.md)  
[GetEditorialReasonsByIds](geteditorialreasonsbyids.md)  
