---
title: LabelAssociation Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the relationship between a label and campaign, ad group, ad, or keyword entity.
---
# LabelAssociation Data Object - Campaign Management
Defines the relationship between a label and campaign, ad group, ad, or keyword entity.

## Syntax
```xml
<xs:complexType name="LabelAssociation" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element name="EntityId" type="xs:long" />
    <xs:element name="LabelId" type="xs:long" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="entityid"></a>EntityId|The identifier of an entity associated with the label.<br/><br/>Supported entity types for labels are campaign, ad group, ad, and keyword. The entity type is specified in the request message of each [DeleteLabelAssociations](../campaign-management-service/deletelabelassociations.md), [GetLabelAssociationsByEntityIds](../campaign-management-service/getlabelassociationsbyentityids.md), [GetLabelAssociationsByLabelIds](../campaign-management-service/getlabelassociationsbylabelids.md), and [SetLabelAssociations](../campaign-management-service/setlabelassociations.md) operation.<br/><br/>Each entity can be associated with a maximum of 50 labels. For example *Campaign A* can be associated with up to 50 labels.<br/><br/>**Set:** Required<br/>**Delete:** Required|**long**|
|<a name="labelid"></a>LabelId|The identifier of the label.<br/><br/>**Set:** Required<br/>**Delete:** Required|**long**|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[DeleteLabelAssociations](deletelabelassociations.md)  
[GetLabelAssociationsByEntityIds](getlabelassociationsbyentityids.md)  
[GetLabelAssociationsByLabelIds](getlabelassociationsbylabelids.md)  
[SetLabelAssociations](setlabelassociations.md)  
