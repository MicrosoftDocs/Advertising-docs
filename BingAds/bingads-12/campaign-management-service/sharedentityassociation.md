---
title: SharedEntityAssociation Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an object that contains association information for a campaign and shared entity such as a negative keyword list.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change.

# SharedEntityAssociation Data Object - Campaign Management
Defines an object that contains association information for a campaign and shared entity such as a negative keyword list.

## Syntax
```xml
<xs:complexType name="SharedEntityAssociation" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element name="EntityId" type="xs:long" />
    <xs:element name="EntityType" nillable="true" type="xs:string" />
    <xs:element name="SharedEntityId" type="xs:long" />
    <xs:element name="SharedEntityType" nillable="true" type="xs:string" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="entityid"></a>EntityId|The system-generated identifier of the campaign that is associated with the shared entity.|**long**|
|<a name="entitytype"></a>EntityType|The type of entity.<br /><br />Currently the only supported value is Campaign.|**string**|
|<a name="sharedentityid"></a>SharedEntityId|The system-generated identifier of the shared entity.|**long**|
|<a name="sharedentitytype"></a>SharedEntityType|The type of the shared entity.<br /><br />Currently the only supported value is NegativeKeywordList.|**string**|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[DeleteSharedEntityAssociations](deletesharedentityassociations.md)  
[GetSharedEntityAssociationsByEntityIds](getsharedentityassociationsbyentityids.md)  
[GetSharedEntityAssociationsBySharedEntityIds](getsharedentityassociationsbysharedentityids.md)  
[SetSharedEntityAssociations](setsharedentityassociations.md)  
