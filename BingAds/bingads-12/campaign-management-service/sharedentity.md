---
title: SharedEntity Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the base class of a shared entity.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# SharedEntity Data Object - Campaign Management
Defines the base class of a shared entity.

Do not try to instantiate a *SharedEntity*. You can create the following object that derives from it.
-   [NegativeKeywordList](negativekeywordlist.md)  

A [NegativeKeywordList](negativekeywordlist.md) is derived from the [SharedList](sharedlist.md), which derives from the [SharedEntity](sharedentity.md) object.

## Syntax
```xml
<xs:complexType name="SharedEntity" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element name="AssociationCount" nillable="true" type="xs:int" />
    <xs:element minOccurs="0" name="ForwardCompatibilityMap" nillable="true" type="q85:ArrayOfKeyValuePairOfstringstring" xmlns:q85="http://schemas.datacontract.org/2004/07/System.Collections.Generic" />
    <xs:element minOccurs="0" name="Id" nillable="true" type="xs:long" />
    <xs:element name="Name" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="Type" nillable="true" type="xs:string" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="associationcount"></a>AssociationCount|The number of active associations between this object and an entity such as a campaign.|**int**|
|<a name="forwardcompatibilitymap"></a>ForwardCompatibilityMap|The list of key and value strings for forward compatibility to avoid otherwise breaking changes when new elements are added in the current API version.<br /><br />Forward compatibility changes will be noted here in future releases. There are currently no forward compatibility changes for this object.|[KeyValuePairOfstringstring](keyvaluepairofstringstring.md) array|
|<a name="id"></a>Id|The unique Bing Ads identifier of the shared entity.|**long**|
|<a name="name"></a>Name|The name of the shared entity.|**string**|
|<a name="type"></a>Type|The type of the shared entity. For more information about shared entity types, see [SharedEntity Data Object Remarks](sharedentity.md#remarks).|**string**|

## <a name="remarks"></a>Remarks
For Java and the .NET languages, do not set the *Type* element because the value is determined by the object instance.

If you generate the SOAP manually, use the *type* attribute of the `<SharedEntity>` node as shown in the following example, to specify whether the shared entity is a negative keyword list.

```xml
<SharedEntity i:type="NegativeKeywordList" xmlns:i="http://www.w3.org/2001/XMLSchema-instance">
  <AssociationCount i:nil="true" />
  <ForwardCompatibilityMap i:nil="true" xmlns:a="http://schemas.datacontract.org/2004/07/System.Collections.Generic" />
  <Id i:nil="true" />
  <Name>My Negative Keyword List</Name>
  <ItemCount i:nil="true" />
</SharedEntity>
```

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

## Used By
[AddSharedEntity](addsharedentity.md)  
[DeleteSharedEntities](deletesharedentities.md)  
[GetSharedEntitiesByAccountId](getsharedentitiesbyaccountid.md)  
[UpdateSharedEntities](updatesharedentities.md)  
