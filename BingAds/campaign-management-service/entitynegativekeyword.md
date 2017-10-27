---
title: EntityNegativeKeyword Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: "article"
ms.date: 11/01/2017
author: eric-urban
ms.author: eur
description: Defines an object that contains a set of negative keywords that are only associated with the corresponding entity such as a campaign or ad group.
---
# EntityNegativeKeyword Data Object - Campaign Management
Defines an object that contains a set of negative keywords that are only associated with the corresponding entity such as a campaign or ad group.

## Syntax
```xml
<xs:complexType name="EntityNegativeKeyword" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element name="EntityId" type="xs:long" />
    <xs:element name="EntityType" nillable="true" type="xs:string" />
    <xs:element name="NegativeKeywords" nillable="true" type="tns:ArrayOfNegativeKeyword" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="entityid"></a>EntityId|The system-generated identifier of a campaign or ad group that is associated with the negative keywords.|**long**|
|<a name="entitytype"></a>EntityType|The type of entity such as a campaign that is associated with the negative keywords.<br /><br />The possible values are *AdGroup* and *Campaign*.|**string**|
|<a name="negativekeywords"></a>NegativeKeywords|An array of negative keywords that are associated with the corresponding campaign or ad group.|[NegativeKeyword](negativekeyword.md) array|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[AddNegativeKeywordsToEntities](addnegativekeywordstoentities.md)  
[DeleteNegativeKeywordsFromEntities](deletenegativekeywordsfromentities.md)  
[GetNegativeKeywordsByEntityIds](getnegativekeywordsbyentityids.md)  
