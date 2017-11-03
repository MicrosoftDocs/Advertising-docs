---
title: SharedList Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the base class of a shared list.
---
# SharedList Data Object - Campaign Management
Defines the base class of a shared list.

Do not try to instantiate a *SharedList*. You can create the following object that derives from it.
-   [NegativeKeywordList](../campaign-management-service/negativekeywordlist.md)

## Syntax
```xml
<xs:complexType name="SharedList" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:SharedEntity">
      <xs:sequence>
        <xs:element minOccurs="0" name="ItemCount" nillable="true" type="xs:int" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="itemcount"></a>ItemCount|The number of [SharedListItem](../campaign-management-service/sharedlistitem.md) objects that are added to this shared list.<br /><br />**Add:** Read-only<br />**Update:** Read-only|**int**|

The [SharedList](sharedlist.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementssharedentity"></a>Inherited Elements from SharedEntity
The [SharedList](sharedlist.md) object derives from the [SharedEntity](sharedentity.md) object, and inherits the following elements. The descriptions below are specific to [SharedList](sharedlist.md), and might not apply to other objects that inherit the same elements from the [SharedEntity](sharedentity.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="associationcount"></a>AssociationCount|The number of active associations between this object and an entity such as a campaign.<br /><br />For a [NegativeKeywordList](../campaign-management-service/negativekeywordlist.md), the maximum association count is 20.<br /><br />**Add:** Read-only<br />**Update:** Read-only|**int**|
|<a name="forwardcompatibilitymap"></a>ForwardCompatibilityMap|The list of key and value strings for forward compatibility to avoid otherwise breaking changes when new elements are added in the current API version.<br /><br /> Forward compatibility changes will be noted here in future releases. There are currently no forward compatibility changes for the *SharedEntity* object.|[KeyValuePairOfstringstring](keyvaluepairofstringstring.md) array|
|<a name="id"></a>Id|The unique Bing Ads identifier of the shared entity.<br /><br />**Add:** Read-only<br />**Update:** Required|**long**|
|<a name="name"></a>Name|The name of the shared entity.<br /><br />For a [NegativeKeywordList](../campaign-management-service/negativekeywordlist.md), the maximum length is 255.<br /><br />**Add:** Optional<br />**Update:** Optional|**string**|
|<a name="type"></a>Type|The type of the shared entity. For more information about shared entity types, see [SharedEntity Data Object Remarks](../campaign-management-service/sharedentity.md#remarks).<br /><br />**Add:** Read-only<br />**Update:** Read-only|**string**|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[AddListItemsToSharedList](addlistitemstosharedlist.md)  
[DeleteListItemsFromSharedList](deletelistitemsfromsharedlist.md)  
[GetListItemsBySharedList](getlistitemsbysharedlist.md)  
